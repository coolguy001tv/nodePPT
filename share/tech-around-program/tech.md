title: 开发周边的技术
speaker: 丁丁
url: https://github.com/coolguy001tv/nodePPT/share/tech-around-program
transition: zoomin
files: /css/common.css
theme: dark
date: 2016/03/16
[slide]
# 开发周边的技术
----

* MarkDown {:&.rollIn}
* 正则实例
* 最常用的几个win批处理命令

[note]
* MarkDown 
* 正则实例
* 最常用的几个win批处理命令
[/note]

[slide data-transition="vertical3d"]
# MarkDown

[slide data-transition="glue"]
# MarkDown
## 目标： ** 易读易写 **
-----
Markdown 是一种轻量级标记语言，创始人为约翰·格鲁伯（John Gruber）。它允许人们“使用易读易写的纯文本格式编写文档，然后转换成有效的XHTML(或者HTML)文档”。这种语言吸收了很多在电子邮件中已有的纯文本标记的特性。

<small style="font-size:small">摘自 https://zh.wikipedia.org/wiki/Markdown</small>
[note]
一份使用 Markdown 格式撰写的文件应该可以直接以纯文本发布 并且 兼容 HTML

Markdown 语法受到一些既有 text-to-HTML 格式的影响，

包括 Setext、atx、Textile、reStructuredText、Grutatext 和 EtText，

而最大灵感来源其实是纯文本电子邮件的格式。

\*.md文件

[/note]

[slide data-transitioin="move"]
# 基本语法
----

* 段落、标题 
    * Setext: 底线的形式利用=（1阶）和 -（2阶） {:&.zoomIn}
    * Atx: 行首插入 1 到 6 个 \# ，对应到标题 1 到 6 阶
    * eg: 

    * <pre class="pre">
        A First Level Header
        ====================
        A Second Level Header
        ---------------------
        # A 1st Level Header
        ## A 2nd Level Header
     </pre>
[slide]  
# **段落、标题**展示效果
----

A First Level Header
====================
A Second Level Header
---------------------
# A 1st Level Header
## A 2nd Level Header

[slide]
# 基本语法(续)
----
* 强调
    * 星号（1个或者2个） {:&.moveIn}
    * 底线（1个或者2个）
    * <pre class="pre">
        Some of these words _are emphasized_
        Use two asterisks for __strong emphasis__
      </pre>
    * Some of these words _are emphasized_ 
    * Use two asterisks for __strong emphasis__

[slide]
# 基本语法(续)
----
* 列表
    * 星号 {:&.moveIn}
    * 加号
    * 减号
    * 数字接着一个英文句点
    * <pre class="pre">
        + Candy
        + Gum
        + Booze
      </pre>
[note]
请不要混合使用符号，以免出现不一样的解析结果

数字接着一个英文句点 方式其实并不关心数字的顺序

[/note]

[slide]
# 基本语法(续)
----
* 链接 {:&.moveIn}
    * 行内链接 {:&.moveIn}
        * 接在后面用括号直接接上链接
    * 参考链接
        * 链接定一个名称，之后你可以在文件的其他地方定义该链接的内容  

[slide]
# **链接**实例
----
<pre class="pre">
    This is an [example link](http://example.com/ "With a Title"). 
    I get 10 times more traffic from [Google][1] than from
    [Yahoo][2] or [MSN][3].
    [1]: http://google.com/ "Google"
    [2]: http://search.yahoo.com/ "Yahoo Search"
    [3]: http://search.msn.com/ "MSN Search"
</pre>
[slide]
# **链接**展示效果
----
This is an [example link](http://example.com/ "With a Title").
    
I get 10 times more traffic from [Google][1] than from
[Yahoo][2] or [MSN][3].

[1]: http://google.com/ "Google"
[2]: http://search.yahoo.com/ "Yahoo Search"
[3]: http://search.msn.com/ "MSN Search"

[note]
下一页先讲换行
[/note]

[slide]
#  基本语法(续)
----
* 换行 {:&.moveIn}
    * 行尾插入至少两个空格，或直接一行空行
* 图片
    * 行内形式 {:&.moveIn}
<pre class="pre">![alt text](/path/to/img.jpg "Title")</pre>
    * 参考形式

    
[slide]
#  基本语法(续)
----
* 代码 {:&.moveIn}
    * 反引号(`) {:&.moveIn}
    * 制表符或至少四个空格缩进的行
* 引用
    * 段落开头加上右尖括号('>')
        * 一个引用里插入一个引用，可以用两个('>')开头
    
[note]
`区段内的 &、< 和 > 都会被自动的转换成 HTML 实体，这项特性让你可以很容易的在代码区段内插入 HTML 码`
[/note]
[slide]
# 总结
---
类型 | 表述方式 | HTML
:---|:---|:---
段落、标题|Setext/Atx|`<h1>~<h6>`
强调|\*/\_|`<em>/<strong>`
列表|\*/\+/\-/数字与句点|`<ul(ol)>/<li>`
链接|\[\]\(\)|`<a>`
换行|2个空格或者一个空行|`<br>`
图片|\!\[\]\(\)|`<img>`
代码|\`/制表符|`<code>`
引用|\>|`<blockquote><p>`

[slide]
一个典型例子
-------
```
# React Native 
[![Build Status](https://travis-ci.org/facebook/react-native.svg?branch=master)](https://travis-ci.org/facebook/react-native) [![Circle CI](https://circleci.com/gh/facebook/react-native.svg?style=svg)](https://circleci.com/gh/facebook/react-native) [![npm version](https://badge.fury.io/js/react-native.svg)](http://badge.fury.io/js/react-native)

React Native enables you to build world-class ...

- [Getting Started](#getting-started)
- [Getting Help](#getting-help)

## Documentation
- There are **Guides** that discuss topics like [debugging](https://facebook.github.io/react-native/docs/debugging.html), [integrating with existing apps](https://facebook.github.io/react-native/docs/embedded-app-ios.html), and [the gesture responder system](https://facebook.github.io/react-native/docs/gesture-responder-system.html).
- Finally, React Native provides a small number of **Polyfills** that offer web-like APIs.
```

[note]
* \`\`\`的使用
* 表格的使用
[/note]

[slide]
实际效果
----
# React Native 
[![Build Status](https://travis-ci.org/facebook/react-native.svg?branch=master)](https://travis-ci.org/facebook/react-native) [![Circle CI](https://circleci.com/gh/facebook/react-native.svg?style=svg)](https://circleci.com/gh/facebook/react-native) [![npm version](https://badge.fury.io/js/react-native.svg)](http://badge.fury.io/js/react-native)

React Native enables you to build world-class ...

- [Getting Started](#getting-started)
- [Getting Help](#getting-help)

## Documentation
- There are **Guides** that discuss topics like [debugging](https://facebook.github.io/react-native/docs/debugging.html), [integrating with existing apps](https://facebook.github.io/react-native/docs/embedded-app-ios.html), and [the gesture responder system](https://facebook.github.io/react-native/docs/gesture-responder-system.html).
- Finally, React Native provides a small number of **Polyfills** that offer web-like APIs.

[slide]
# 参考链接
----

[Markdown快速入门](http://wowubuntu.com/markdown/basic.html)

[Markdown维基百科](https://zh.wikipedia.org/wiki/Markdown)

[GitHub官方帮助文档](https://help.github.com/articles/basic-writing-and-formatting-syntax/)

[GitHub上README写法暨markdown语法解读](http://www.tuicool.com/articles/zIJrEjn)

[麻花在线markdown编辑器](http://mahua.jser.me/)


[slide]
# 正则实例
----

* 版本号替换 {:&.moveIn}
* 文本替换
* 字符串拼接
* 其他
[note]
测试均在web-storm上进行
[/note]
[slide]
# 版本号替换(1)
## 将所有引入css的地方加入一个版本号：?v=2
----
```
<link rel="stylesheet" href="demo/css/demo.css">
<link rel="stylesheet" href="demo/css/demo.css?v=1">
<link rel="stylesheet" href="demo/css/demo.css?w=1">
<link rel="stylesheet" href="demo/css/demo.css?x=1" >
<link rel="stylesheet" href="demo/css/demo.css?yx=10" />
```
[note]
不考虑`<link rel="stylesheet" href='demo/css/demo.css'>`

两个正则表达式的区别？
[/note]
[slide]
#解决思路
----
* 其中的一个思路：
    * `\.css[^"]*"  -> .css?v=2"`
    * `\.css.*"`

等等 {:&.fadeIn}

出问题了 {:&.fadeIn}

[slide]
# 问题
----

```
<script>
    var height = $(window).css("height");
    $(window).css("height","320px");
</script>
```
变成了
```
<script>
    var height = $(window).css?v=2");
    $(window).css?v=2"height","320px");
</script>
```
[slide]
#解决思路（续）
----
* `\.css(\?\w+=\d+)?"  -> .css?v=2"`

[note]
方案不是完美的，需要自行考虑:如果是
* a.css?=1
* a.css?1
* a.css?v=1 (后面跟空格)
[/note]

[slide]
# 版本号替换(2)
## 加入所有引入的js文件的版本号
-----
```
<script src="demo/js/demo.js"></script>
<script src="demo/js/demo.js?v=1"></script>
<script src='demo/js/demo.js'></script>
```
[slide]
#解决思路
----
* 其中的一个思路：
    * `\.js[^"]*"  -> .js?v=2"`

等等 {:&.fadeIn}

出问题了 {:&.fadeIn}

[note]
我们仍然不考虑单引号的问题
[/note]

[slide]
# 问题
----
```
<script>
    $(".js_confirm").click();
</script>
```
变成了
```
<script>
    $(".js?v=2").click();
</script>
```

[slide]
# 文本替换
----
将代码
```
<li id="menu-distribution-order"><a class="menu-link" href="//xxxx"><span
        class=" menu-item clearfix"><i class="left icon-menu-right"></i><span
        class="left">分销订单</span></span></a></li>
```

转化成

```
<a id="menu-distribution-order" href="//xxxx">分销订单</a>
```

[slide]
# 解决思路
----
* `<li id="(.*)"` ....

等等 {:&.fadeIn}

出问题了 {:&.fadeIn}

[slide]
# ** 贪婪模式 ** 和 ** 非贪婪模式 **
-----

*   贪婪模式： 尽可能多 {:&.moveIn}
* 非贪婪模式：尽可能少
    * 问号(?)符紧跟在任何一个其他限制符（*,+,?，{n}，{n,}，{n,m}）后面时，匹配模式是非贪婪的 {:&.moveIn}
    * 例如，对于字符串“oooo”，“o+?”将匹配单个“o”，而“o+”将匹配所有“o”

思考一下 {:&.fadeIn}
+ `\.css[^"]*"` 与 `\.css.*"`在匹配下面两个表达式的不同  {:&.moveIn}
+ `<link rel="stylesheet" href="demo/css/demo.css" >`
+ `<link rel="stylesheet" href="demo/css/demo.css" type="text/css">`
[note]
思考一下我们一开始的正则表达式  
* `\.css[^"]*"`
* `\.css.*"`
[/note]
[slide]
# $n与括号
## 第n个匹配项
----

* $n表示第n个括号匹配的项 {:&.moveIn}
* 实际测试中$0是表示整个字符串
* (?:pattern)是一个非获取匹配
    * 对于字符串`<li id="menu-distribution-order">`   {:&.moveIn}
    * 正则表达式`<li id="(.*?)"`中$1是`menu-distribution-order`
    * 正则表达式`<li id="(?:.*?)"`中$1是空串

然后继续我们的思路 {:&.fadeIn}

[slide]
# 解决思路（续）
----
```
<li id="menu-distribution-order"><a class="menu-link" href="//xxxx"><span
        class=" menu-item clearfix"><i class="left icon-menu-right"></i><span
        class="left">分销订单</span></span></a></li>
```

* `<li id="(.*?)".*?href="(.*?)".*\n.*\n.*?>(.*?)</.*` ->  {:&.fadeIn}
* `<a id="$1" href="$2">$3</a>`


等等 {:&.fadeIn}

出问题了 {:&.fadeIn}

[note]
思考一下如果用的是`<li id="(.*)"`会出现什么？
[/note]
[slide]
# 问题
----
```
<!--<li id="menu-distribution-order"><a class="menu-link" href="//xxxx"><span
        class=" menu-item clearfix"><i class="left icon-menu-right"></i><span
        class="left">分销订单</span></span></a></li>-->
```
会被替换成：
```
<!--<a id="menu-distribution-order" href="//xxxx">分销订单</a>
```
导致不应该被注释掉的代码被注释掉（没有结束注释符号）  
解决方案请自行考虑


[slide]
# 字符串拼接
## html转化成JS中拼接的字符串
----
```
<form id="home-search-form" action="/zh-CN/search" method="get">
    <div class="home-search-form search-form">
        <input class="search-input" type="search" id="home-q">
        <button type="submit" class="offscreen">搜索</button>
    </div>
</form>
```

转化成JS中的字符串拼接，类似于
```
'<form id="home-search-form" action="/zh-CN/search" method="get">' + 
'<div class="home-search-form search-form">' +
....
```


[slide]
# 解决思路
## 头部替换为\'，尾部替换为\'\+
----
* 方案一 {:&.fadeIn}
    1. `^ -> '` 
    2. `$ -> '+`
    3. 删除最后一个加号
    
* 方案二：
    1. `^(.*)$ -> '$1'+ `
    2. 删除最后一个加号
    
思考：反过来怎么写?   {:&.fadeIn}

`'(.*)'+` -> `$1` {:&.fadeIn}

等等 {:&.fadeIn}

出问题了 {:&.fadeIn}

[note]注意加号前面有\\，即`'(.*)'\+`[/note]
[slide]
# 正则-其他
## 简单聊聊身份证的验证
----
* 15位身份证的年用2位，没有校验位 {:&.moveIn}
* 18位身份证最后一位是校验位 
    * 1-2 省级行政区代码 {:&.moveIn}
    * 3-4 地级行政区划分代码
    * 5-6 县区行政区分代码
    * 7-10 11-12 13-14 出生年、月、日
    * 15-17 顺序码，同一地区同年、同月、同日出生人的编号，奇数是男性，偶数是女性
    * 18 校验码，如果是0-9则用0-9表示，如果是10则用X（罗马数字10）表示
        * [ISO 7064:1983,MOD 11-2校验码系统](https://zh.wikipedia.org/wiki/%E4%B8%AD%E5%8D%8E%E4%BA%BA%E6%B0%91%E5%85%B1%E5%92%8C%E5%9B%BD%E5%85%AC%E6%B0%91%E8%BA%AB%E4%BB%BD%E5%8F%B7%E7%A0%81)
    
[slide]
# 18位身份证的正则
-----

*  `\d{17}[\dxX]`  {:&.moveIn}
* `\d{6}\d{4}[01]\d[0123]\d\d{3}[\dxX]`
* `\d{6}(18|19|20)\d{2}(0\d|1[012])([012]\d|3[01])\d{3}[\dxX]`
* `\d{6}(?:18|19|20)\d{2}(?:0\d|1[012])(?:[012]\d|3[01])\d{3}[\dxX]`
* ....
[note]
*  `\d{17}[\dxX]`
* `\d{6}\d{4}[01]\d[0123]\d\d{3}[\dxX]`
* `\d{6}(18|19|20)\d{2}(0\d|1[012])([012]\d|3[01])\d{3}[\dxX]`
* `\d{6}(?:18|19|20)\d{2}(?:0\d|1[012])(?:[012]\d|3[01])\d{3}[\dxX]`
* ....
[/note]
[slide]
# 正则-非技术总结
----
* 胆大心细 {:&.moveIn}
* 多和同事交流
* 正则不是万能的
* ....

[slide]
# 最常用的几个win批处理命令
## 目标：可以正常读脚本文件
----
* %var_name%
* echo
    * echo %path%
* set
* rem
* @
* call
* :label与goto
* pause
* %errorlevel%
    
[note]
windows不区分大小写  
* @与echo off功能相似，但它是加在其他命令行的最前面，表示运行时不显示命令行本身。
* errorlevel == 0 表示成功

[/note]

[slide]
#一个批处理实例
----
```
set DIRNAME=%~dp0
if "%DIRNAME%" == "" set DIRNAME=.
set APP_HOME=%DIRNAME%

@rem Find java.exe
if defined JAVA_HOME goto findJavaFromJavaHome

set JAVA_EXE=java.exe
%JAVA_EXE% -version >NUL 2>&1
if "%ERRORLEVEL%" == "0" goto init

echo.
echo ERROR: JAVA_HOME is not set and no 'java' command could be found in your PATH.
goto fail

:findJavaFromJavaHome
set JAVA_HOME=%JAVA_HOME:"=%
set JAVA_EXE=%JAVA_HOME%/bin/java.exe
if exist "%JAVA_EXE%" goto init
echo ERROR: JAVA_HOME is set to an invalid directory: %JAVA_HOME%
goto fail

:init
rem 执行一堆东西，如果出错goto fail

:fail
rem Set variable GRADLE_EXIT_CONSOLE if you need the _script_ return code instead of
rem the _cmd.exe /c_ return code!
if  not "" == "%GRADLE_EXIT_CONSOLE%" exit 1
exit /b 1

:omega
```
[note]注意：这个例子本身是不完整的[/note]

[slide]
# End









