title: shop-management-eslint
speaker: 丁丁
url: https://github.com/coolguy001tv/nodePPT/share/shop-management-eslint
transition: zoomin
files: /css/common.css
theme: dark
date: 2016/12/22

[slide data-transitioin="move"]
# shop-management-eslint
[note]
ESLint is an open source project originally created by Nicholas C. Zakas in June 2013.  
Its goal is to provide a pluggable linting utility for JavaScript. 
[/note]

[slide]
# 检查范围
-------
* shop-management项目src/js所有jsx(忽略文件参考.eslintignore) {:&.rollIn}
* .eslintignore内容
```
/src/js/**/*.js
# 所有名称为test.jsx的也不检查
/src/js/**/test.jsx
# 特殊文件
/src/js/weChat/comm/face.jsx
/src/js/weChat/comm/textToFace.jsx
```
[slide]
# .eslintrc.js内容(局部)
```
"globals": {
    "$": true,
    "jQuery":true,
    "React": true,
    "ReactDOM": true,
    "RUI": true
},
"extends": "eslint:recommended",
"rules": {
        "no-console": "off",
        "indent": [
            "error",
            4
        ],
        "linebreak-style": [
            "error",
            "windows"
        ],
        "quotes": [
            "error",
            "double"
        ],
        "semi": [
            "error",
            "always"
        ],
        "indent":["error", 4, { "SwitchCase": 1 }],
    }
```

[note]
    编译失败，后文有跳过方法 
    其他全局变量的问题，后面再讲
[/note]

[slide]
#  eslint errors
-------
* 缺少分号 {:&.fadeIn}
* 单引号和双引号
* 去掉debugger
* 缩进不对（tab请用4个空格代替）

[note]
以下内容整体上都是报error级别的错误（目前显示有点问题）
[/note]

[slide]
* switch的格式 {:&.bounceIn}
```
switch (i){
    case 1 : indexCN="一";break;
    case 2 : indexCN="二";break;
    case 3 : indexCN="三";break;
}
```
* 不必要的break:
```
case 0 : return "全部";break;
```
* case中的大括号:
```
case 1: {a=1;b=2;c=3;}break;
```

[note]
switch专题
[/note]

[slide]
* if-else-var 的else分支不应该继续出现var {:&.bounceIn}
```
if(...){
    var a = 1;
}else{
    var a = 2;
}
```
[note]
类似的有多个for循环中同样的变量
[/note]

[slide]
* 代码被多次复制 {:&.moveIn}
* 单双引号问题
```
tip.addClass("success").html('<i class="ok"></i>')
```
* no-unused-vars
* function的参数如果临时需要保留，请注释掉，否则会被报错(no-unused-vars)，比如
```
function(i/*,reserve*/){}
```
常见的情况是
```
map((v,i)=>{console.log(v)})
```

[slide]
* 不需要的else请不要保留(no-empty),如果因为某些原因需要保留，请写明注释，比如：
```
if(...){
    t = 1;
}else{
    //这里表示XXXXX
}
```

[slide]
* 不要保留不必要的分号(no-extra-semi)，eg: {:&.moveIn}
```
let a = 5;;
function b(){};
if(){};
```
* if语句中不要使用赋值表达式
```
if(a=1){}
```
* 不要在if语句中使用!!(no-extra-boolean-cast)



[slide]
* no-dupe-keys
```
let t = {berbonAcc:"",upperShopId:"",skuCode:"",productName:"",skuCode:""}
```

[slide]
* ajax error的处理问题

```
$.ajax({
            url:url,
            dataType:"json",
            type:"post",
            data:{d:JSON.stringify(requestData)},
            success:function(data){
                //balabala
            },
            error:function(){
                _this.refs.loading.close();
                Pubsub.publish("showMsg",["wrong", data.description]);
            }
        });
```




[slide]
* WS注释的使用：ctrl+/ & ctrl+shift+/ 

```
function(upload,name){

}
```



[slide]
# eslint中检测的异常情况
* no-unused-vars
```
setKey:function(key){
    var menus=this.props.menus.concat([]);
    var currentMenu=this.props.currentMenu,
        currentSubMenu=this.props.currentSubMenu;
    var theMenu=menus[currentMenu]; /*eslint no-unused-vars:0*/
    theMenu=$.extend(theMenu,{
        key:key,
        type:"click",
        url:""
    });
    return menus;
}
```


[slide]
# 使用eslint语法标明不需要处理的情况
---- 
* /\*eslint no-extra-boolean-cast:0\*/ {:&.zoomIn}
* /\*eslint-disable\*/
* /\*global BMap\*/

[note]
禁止使用eslint-disable！！！！
[/note]

[slide]
# 其他问题
-----

* $.extend的使用问题
```
jQuery.extend([deep], target, object1, [objectN])
$.extend(item, append, true);
```


[slide]
* 多余的逗号是允许的 {:&.zoomIn}
```
var a = {a:1,b:2,};
```
* 理论上尽量一行不要超过80字
* Variable initializer is redundant
```
var totalPrice = 0;
//balabala
totalPrice=Number(_this.getInputTotalValue())-Number(_this.state.favValue)+Number(_this.state.freightValue);
```

[note]
理论上尽量一行不要超过80字（目前看到过500+列的）
[/note]



[slide]
# 代码头部标明作者(和文件创建时间)
```
//good example
/**
 * Created with JetBrains WebStorm.
 * User: lixue
 * Date: 2016/1/8
 */
//bad example
/**
 * Created by adminstrator on 2016/1/24.
 */
```

[note]
UserName随意，能标识就可以，英文拼音均可 
WS上新建时可以直接建立模板 
关于模板的东西涵哥要讲 
[/note]


[slide]
# EditorConfig

[note]
感谢 凡哥 小慧
[/note]

[slide]

```
root = true
[*]
charset = utf-8
indent_style = space
indent_size = 4
max_line_length = 80
insert_final_newline = true
end_of_line = crlf
```

[note]
   ws默认支持，其他IDE可能需要插件
   //->https->http
[/note]



