title: JS TIPS
speaker: 丁丁
url: https://github.com/coolguy001tv/nodePPT/share/js-tips
transition: zoomin
files: /css/common.css
theme: dark
date: 2016/11/06

[slide]
# Js Tips

[note]
* js tips(原生 js的相关，rn同学也可以收获一些玩意)
[/note]

[slide data-transition="vertical3d"]
# Inserting an item into an existing array

[slide data-transitioin="move"]
## Adding an element at the end  
----
* arr[arr.length] = 6 {:&.zoomIn}
* arr.push(6) 
* arr=arr.concat([6])

[note]
* push 会操作原始数组，而concat不会
* push的返回值是数组长度
[/note]


[slide]
# Performace on mobile/desktop
----
 mobile/desktop |arr[arr.length]| push | concat
-------|------|-------|--------
Android (v4.2.2) |3 319 694 ops/sec | 3 319 694 ops/sec |50.61 % slower 
Chrome Mobile (v33.0.0)|6 125 975 ops/sec|66.74 % slower|87.63 % slower
Safari Mobile (v9)|7 452 898 ops/sec|40.19 % slower|49.78 % slower
Chrome (v48.0.2564)|21 602 722 ops/sec|61.94 % slower|87.45 % slower
Firefox (v44)|0.52 % slower|56 032 805 ops/sec|87.36 % slower
IE (v11)|67 197 046 ops/sec|39.61 % slower|93.41 % slower
Safari (v9.0.3)|0.80 % slower|42 670 978 ops/sec|76.07 % slower

https://jsperf.com/push-item-inside-an-array 
[note]
我的win10+chrome54.0 测试结果：
* arr\[arr.length\] 48,151,153 
* arr.push 43,570,453 6% slower
* arr.concat 6,270,323 86% slower
[/note]

[slide data-transitioin="move"]
## Add an element at the beginning
---
* arr.unshift(0)  {:&.bounceIn}
* [0].concat(arr)


[note]
MOBILE: 
```javascript
Final victor

1. [0].concat(arr); // with an average of 4 972 622 ops/sec
2. arr.unshift(0); // 64.70 % slower
```
DESKTOP: 
```javascript
Final victor

1. [0].concat(arr); // with an average of 6 032 573 ops/sec
2. arr.unshift(0); // 78.65 % slower
```

[/note]


[slide data-transitioin="move"]
## Add an element in the middle
---- 
{:&.bounceIn}
```javascript
var items = ['one', 'two', 'three', 'four'];
items.splice(items.length / 2, 0, 'hello');
```
[note]
`array.splice(start, deleteCount[, item1[, item2[, ...]]])` 
与slice不同，他直接修改数组本身
[/note]
[slide]
# Sorting String Array with accented characters
## ```arr.sort([compareFunction])```
----
{:&.bounceIn}
```javascript
[1, 10, 2, 21].sort();
['中国','啊'].sort();
```



[note]
compareFunction 
可选。用来指定按某种顺序进行排列的函数。如果省略，元素按照转换为的字符串的诸个字符的Unicode位点进行排序
上面两个例子输出结果都是本身 
sort对原始数组进行操作 
如果指明了 compareFunction ，那么数组会按照调用该函数的返回值排序。记 a 和 b 是两个将要被比较的元素： 
* 如果 compareFunction(a, b) 小于 0 ，那么 a 会被排列到 b 之前； 
* 如果 compareFunction(a, b) 等于 0 ， a 和 b 的相对位置不变。备注： ECMAScript 标准并不保证这一行为，而且也不是所有浏览器都会遵守（例如 Mozilla 在 2003 年之前的版本）；
* 如果 compareFunction(a, b) 大于 0 ， b 会被排列到 a 之前。
* compareFunction(a, b) 必须总是对相同的输入返回相同的比较结果，否则排序的结果将是不确定的。
[/note]

[slide]
# localeCompare
----
{:&.fadeIn}
```javascript
referenceStr.localeCompare(compareString[, locales[, options]])

"中国".localeCompare("啊");//1
['中国','啊'].sort(function(a,b){return a.localeCompare(b)});//['啊','中国']
```
[note]
locale 不是 local  
localeCompare() 方法返回一个数字来表明调用该函数的字符串（reference string）的排列顺序是否在某个给定的字符串的前面或者后面，或者是一样的（编码中的位置）。  
当 referenceStr 在 compareStr 前面时返回负数 (简单理解就是大于)  
浏览器支持性： 根据MDN，所有浏览器都基础支持， locales and options 大部分不支持 
[/note]

[slide data-transitioin="move"]
# Intl.Collator
----
{:&.fadeIn}
```javascript
['中国','啊','谈','覃','啥','提','批'].sort(Intl.Collator().compare)
```

```javascript
["啊", "批", "啥", "谈", "覃", "提", "中国"]
```

[note] 
注意，像“覃”这种多音字的处理并不太让人满意（（qín)，（xún)，（tán)） 
Intl.Collator的支持性不如localeCompare（特别是移动端，几乎都不支持）
与localeCompare的数据结果一致
[/note]


[slide]
# Differences between undefined and null
----
- `undefined` means a variable has not been declared, or has been declared but has not yet been assigned a value  {:&.moveIn}
- `null` is an assignment value that means "no value"
- Javascript sets unassigned variables with a default value of `undefined`
- Javascript never sets a value to `null`. It is used by programmers to indicate that a `var` has no value.
- `undefined` is not valid in JSON while `null` is
- Both are primitives
- `undefined` typeof is `undefined`
- `null` typeof is an `object`. 

[note]
检测他们的方法：
typeof variable === "undefined" 
variable === null 
1. Data types & primitives
2. typeof
3. why type of null is object
[/note]

[slide data-transitioin="move"]
# Data types
----
* 6 data types that are primitives:  {:&.fadeIn}
    - Boolean  {:&.fadeIn}
    - Null
    - Undefined
    - Number
    - String
    - Symbol  (new in ECMAScript 6)
* Object

[slide]
# typeof
----
* returns a string indicating the type of the unevaluated operand {:&.zoomIn}
* operand is an expression representing the object or primitive whose type is to be returned.

[slide]
Type	|Result
-------|------|
Undefined	|"undefined"
Null	|"object" 
Boolean	|"boolean"
Number	|"number"
String	|"string"
Symbol (new in ECMAScript 2015)	|"symbol"
Host object (provided by the JS environment)	|Implementation-dependent
Function object (implements [[Call]] in ECMA-262 terms)	|"function"
Any other object	|"object"

[note]
operand: 操作数   
typeof Infinity ,NaN === 'number'  
typeof new Array,[] === 'object'  
typeof Object,Array === 'function'   
object supplied by the host environment to complete the execution environment of ECMAScript.   
NOTE Any object that is not native is a host object.  
[/note]

[slide data-transitioin="move"]
# Why typeof null === 'object'
----
*  first version of JavaScript
    * 000: object. The data is a reference to an object.
    * 1: int. The data is a 31 bit signed integer.
    * 010: double. The data is a reference to a double floating point number.
    * 100: string. The data is a reference to a string.
    * 110: boolean. The data is a boolean.
[note]
In this version, values were stored in 32 bit units, which consisted of a small type tag (1–3 bits) and the actual data of the value. The type tags were stored in the lower bits of the units. There were five of them
That is, the lowest bit was either one, then the type tag was only one bit long. Or it was zero, then the type tag was three bits in length, providing two additional bits, for four types
Two values were special:

undefined (JSVAL_VOID) was the integer −2^30 (a number outside the integer range).
null (JSVAL_NULL) was the machine code NULL pointer. Or: an object type tag plus a reference that is zero.

[/note]

[slide]
```c
    #define JSVAL_IS_VOID(v)  ((v) == JSVAL_VOID)
    JS_PUBLIC_API(JSType)
    JS_TypeOfValue(JSContext *cx, jsval v)
    {
        //...

        CHECK_REQUEST(cx);
        if (JSVAL_IS_VOID(v)) {  // (1)
            type = JSTYPE_VOID;
        } else if (JSVAL_IS_OBJECT(v)) {  // (2)
            obj = JSVAL_TO_OBJECT(v);
            if (obj &&
                (ops = obj->map->ops,
                 ops == &js_ObjectOps
                 ? (clasp = OBJ_GET_CLASS(cx, obj),
                    clasp->call || clasp == &js_FunctionClass) // (3,4)
                 : ops->call != 0)) {  // (3)
                type = JSTYPE_FUNCTION;
            } else {
                type = JSTYPE_OBJECT;
            }
        } else if (JSVAL_IS_NUMBER(v)) {
            type = JSTYPE_NUMBER;
        } else if (JSVAL_IS_STRING(v)) {
            type = JSTYPE_STRING;
        } else if (JSVAL_IS_BOOLEAN(v)) {
            type = JSTYPE_BOOLEAN;
        }
        return type;
    }
```

http://www.2ality.com/2013/10/typeof-null.html
[note]
* At (1), the engine first checks whether the value v is undefined (VOID). This check is performed by comparing the value via equals:
    \#define JSVAL_IS_VOID(v)  ((v) == JSVAL_VOID)
* The next check (2) is whether the value has an object tag. If it additionally is either callable (3) or its internal property [[Class]] marks it as a function (4) then v is a function. Otherwise, it is an object. This is the result that is produced by typeof null.
* The subsequent checks are for number, string and boolean. There is not even an explicit check for null, which could be performed by the following C macro.
    \#define JSVAL_IS_NULL(v)  ((v) == JSVAL_NULL)
This may seem like a very obvious bug, but don’t forget that there was very little time to finish the first version of JavaScript.
[/note]


[slide data-transitioin="move"]
# Solutions
----
* It was implemented in V8 but it turned out that it broke a lot of existing sites. *In the spirit of One JavaScript* this is not feasible.
* Douglas Crockford: 
```javascript
Object.isObject = function isObject(value) {
      return typeof value === 'object' && value !== null;
  }
```
http://wiki.ecmascript.org/doku.php?id=harmony%3atypeof_null

[slide]
# put constant left
----
* a == 1 {:&.rollIn}
* a = 1
* 1 == a 

[note]
C编程规范上移植过来  
jslint  
[/note]
[slide]
# Template Strings \` (ES6)
----
{:&.rollIn}
```javascript
var firstName = 'Jake';
var lastName = 'Rawr';
console.log(`My name is ${firstName} ${lastName}`);
// My name is Jake Rawr
```
You can do multi-line strings without \n, perform simple logic (ie 2+3) or even use the ternary operator inside ${} in template strings
```javascript
  var val1 = 1, val2 = 2;
  console.log(`${val1} is ${val1 < val2 ? 'less than': 'greater than'} ${val2}`)
  // 1 is less than 2
```

[slide data-transitioin="move"]
# Tip to measure performance of a javascript block
----
* console.time(label) and console.timeEnd(label) 
```javascript
console.time("Array initialize");
var arr = new Array(100),
    len = arr.length,
    i;
for (i = 0; i < len; i++) {
    arr[i] = new Object();
};
console.timeEnd("Array initialize"); // Outputs: Array initialize: 0.711ms
```
[note]
不要用在正式代码中 console.log()->ie>=8
Console.group() Console.profile() Console.table()
[/note]

[slide]
Fat Arrow Functions
----
* param => expression {:&.fadeIn}
* eg: 
```javascript
var arrFunc = [5,3,2,9,1].map((x) => x*x);
```
*  capturing the keyword this from the surrounding context
*  the parentheses will be needed for multiple input parameters

* Why doesn't ES6 have thin-arrow functions
    * http://softwareengineering.stackexchange.com/questions/306082/why-doesnt-es6-have-thin-arrow-functions
    * http://wiki.ecmascript.org/doku.php?id=harmony:arrow_function_syntax

[note]
one reason: differ from coffee script
[/note]

[slide]
# Even simpler way of using indexOf as a contains clause
----
 {:&.fadeIn}
```javascript
var someText = 'javascript rules';
if (someText.indexOf('javascript') !== -1) {
}

// or
if (someText.indexOf('javascript') >= 0) {
}
```
->
```javascript
if (~someText.indexOf('javascript')) {
}
```
String.prototype.includes() (ES6)  

Array.prototype.includes() (ES7/2016)
[note]
~someText.indexOf('javascript') 实际上返回的结果是-1，但是-1是true
[/note]


[slide data-transitioin="move"]
# Safe string concatenation
----
```javascript
var one = 1;
var two = 2;
var three = '3';

var result = one + two + three; //"33" instead of "123"
```
* result = ''.concat(one, two, three); //"123"  {:&.fadeIn}
* result = [one, two, three].join(""); //"123"
* result = '' + one + two + three; //"123" instead of "123"


[note]
join效率没有concat高
concat效率没有+高
[/note]


[slide]
# Using JSON.stringify
----
```javascript
var obj = {
    'prop1': 'value1',
    'prop2': 'value2',
    'prop3': 'value3'
};
var selectedProperties = ['prop1', 'prop2'];
var str = JSON.stringify(obj, selectedProperties);
// str
// {"prop1":"value1","prop2":"value2"}
```

```javascript
str = JSON.stringify(obj, selectedProperties, '\t\t');
/* str output with double tabs in every line.
{
        "prop1": "value1",
        "prop2": "value2"
}
*/
```



[slide]
# Others
---
* Map: Key the orders  {:&.fadeIn}
* Set: store unique values of any type. 
    * set->array:
        *  \[...set\]
        * Array.from(new Set(...))

[note]
通过Object加入的key的排序是不确定的，但是Map是按照key的加入顺序来的
[/note]

[slide data-transitioin="move"]
# Website
---
* https://github.com/loverajoel/jstips
* https://github.com/explore

