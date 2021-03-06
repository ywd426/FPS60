# HTML #
## 属性顺序 ##
属性应该按照特定的顺序出现以保证易读性；


- class
- id
- name
- data-*
- src, for, type, href, value , max-length, max, min, pattern
- placeholder, title, alt
- aria-*, role
- required, readonly, disabled

class是为高可复用组件设计的，所以应处在第一位；

id更加具体且应该尽量少使用，所以将它放在第二位。

    <a class="..." id="..." data-modal="toggle" href="#">Example link</a>
    <input class="form-control" type="text">
    <img src="..." alt="...">

# CSS, SCSS #
## 缩进 ##

使用soft tab（4个空格）。

    .element {
    	position: absolute;
    	top: 10px;
    	left: 10px;
    
    	border-radius: 10px;
    	width: 50px;
    	height: 50px;
    }

## 分号 ##

每个属性声明末尾都要加分号。

    .element {
    	width: 20px;
    	height: 20px;
    
    	background-color: red;
    }

## 空格 ##

以下几种情况不需要空格：

- 属性名后
- 多个规则的分隔符','前
- !important '!'后
- 属性值中'('后和')'前
- 行末不要有多余的空格

以下几种情况需要空格：

- 属性值前
- 选择器'>', '+', '~'前后
- '{'前
- !important '!'前
- @else 前后
- 属性值中的','后
- 注释'/*'后和'*/'前
    
> 

    /* not good */
    
    .element {
    	color :red! important;
    	background-color: rgba(0,0,0,.5);
    }
    
    /* good */
    
    .element {
    	color: red !important;
    	background-color: rgba(0, 0, 0, .5);
    }
    
    /* not good */
    
    .element ,
    .dialog{
    	...
    }
    
    /* good */
    
    .element,
    .dialog {
    
    }
    
    /* not good */
    
    .element>.dialog{
    	...
    }
    
    /* good */
    
    .element > .dialog{
    	...
    }
    
    /* not good */
    
    .element{
    	...
    }
    
    /* good */
    
    .element {
    	...
    }
    
    /* not good */
    
    @if{
    	...
    }@else{
    	...
    }
    
    /* good */
    
    @if {
    	...
    } @else {
    	...
    }
    

## 空行 ##

以下几种情况需要空行：

- 文件最后保留一个空行
- '}'后最好跟一个空行，包括scss中嵌套的规则
- 属性之间需要适当的空行
> 


    /* not good */
    .element {
    	...
    }
    .dialog {
    	color: red;
    	&:after {
    		...
    	}
    }
    
    /* good */
    .element {
    	...
    }
    
    .dialog {
    	color: red;
    
    	&:after {
    		...
    	}
    }

## 换行 ##

以下几种情况不需要换行：

- '{'前

以下几种情况需要换行：

- '{'后和'}'前
- 每个属性独占一行
- 多个规则的分隔符','后
> 


     /* not good */

    .element
    {color: red; background-color: black;}
    
    /* good */
    .element {
    	color: red;
    	background-color: black;
    }
    
    /* not good */
    .element, .dialog {
    	...
    }
    
    /* good */
    .element,
    .dialog {
    	...
    }

## 注释 ##

注释统一用'/* */'（scss中也不要用'//'），具体参照右边的写法；

缩进与下一行代码保持一致；

可位于一个代码行的末尾，与代码间隔一个空格。

    /* Modal header */
    
    .modal-header {
    	...
    }
    
    /*
     * Modal header
     */
    
    .modal-header {
    	...
    }
    
    .modal-header {
    /* 50px */
    width: 50px;
    
    	color: red; /* color red */
    }


## 引号 ##

最外层统一使用双引号；

url的内容要用引号；

属性选择器中的属性值需要引号。

    .element:after {
    	content: "";
    	background-image: url("logo.png");
    }
    
    li[data-type="single"] {
    	...
    }

## 命名 ##

- 类名使用小写字母，以中划线分隔
- scss中的变量、函数、混合、placeholder采用驼峰式命名
> 

 
    /* class */
    .element-content {
    	...
    }    
    
    
    /* 变量 */
    $colorBlack: #000;
    
    /* 函数 */
    @function pxToRem($px) {
    	...
    }
    
    /* 混合 */
    @mixin centerBlock {
    	...
    }
    
    /* placeholder */
    %myDialog {
    	...
    }

## 属性声明顺序 ##

相关的属性声明按下边的顺序做分组处理，组之间需要有一个空行。

    .declaration-order {
    	display: block;
    	float: right;
    
    	position: absolute;
    	top: 0;
    	right: 0;
    	bottom: 0;
    	left: 0;
    	z-index: 100;
    
    	border: 1px solid #e5e5e5;
    	border-radius: 3px;
    	width: 100px;
    	height: 100px;
    
    	font: normal 13px "Helvetica Neue", sans-serif;
    	line-height: 1.5;
    	text-align: center;
    
    	color: #333;
    	background-color: #f5f5f5;
    
    	opacity: 1;
    }
    // 下面是推荐的属性的顺序
    [
    	[
    		"display",
    		"visibility",
    		"float",
    		"clear",
    		"overflow",
    		"overflow-x",
    		"overflow-y",
    		"clip",
    		"zoom"
    	],
    	[
    		"table-layout",
    		"empty-cells",
    		"caption-side",
    		"border-spacing",
    		"border-collapse",
    		"list-style",
    		"list-style-position",
    		"list-style-type",
    		"list-style-image"
    	],
    	[
    		"-webkit-box-orient",
    		"-webkit-box-direction",
    		"-webkit-box-decoration-break",
    		"-webkit-box-pack",
    		"-webkit-box-align",
    		"-webkit-box-flex"
    	],
    	[
    		"position",
    		"top",
    		"right",
    		"bottom",
    		"left",
    		"z-index"
    	],
    	[
    		"margin",
    		"margin-top",
    		"margin-right",
    		"margin-bottom",
    		"margin-left",
    		"-webkit-box-sizing",
    		"-moz-box-sizing",
    		"box-sizing",
    		"border",
    		"border-width",
    		"border-style",
    		"border-color",
    		"border-top",
    		"border-top-width",
    		"border-top-style",
    		"border-top-color",
    		"border-right",
    		"border-right-width",
    		"border-right-style",
    		"border-right-color",
    		"border-bottom",
    		"border-bottom-width",
    		"border-bottom-style",
    		"border-bottom-color",
    		"border-left",
    		"border-left-width",
    		"border-left-style",
    		"border-left-color",
    		"-webkit-border-radius",
    		"-moz-border-radius",
    		"border-radius",
    		"-webkit-border-top-left-radius",
    		"-moz-border-radius-topleft",
    		"border-top-left-radius",
    		"-webkit-border-top-right-radius",
    		"-moz-border-radius-topright",
    		"border-top-right-radius",
    		"-webkit-border-bottom-right-radius",
    		"-moz-border-radius-bottomright",
    		"border-bottom-right-radius",
    		"-webkit-border-bottom-left-radius",
    		"-moz-border-radius-bottomleft",
    		"border-bottom-left-radius",
    		"-webkit-border-image",
    		"-moz-border-image",
    		"-o-border-image",
    		"border-image",
    		"-webkit-border-image-source",
    		"-moz-border-image-source",
    		"-o-border-image-source",
    		"border-image-source",
    		"-webkit-border-image-slice",
    		"-moz-border-image-slice",
    		"-o-border-image-slice",
    		"border-image-slice",
    		"-webkit-border-image-width",
    		"-moz-border-image-width",
    		"-o-border-image-width",
    		"border-image-width",
    		"-webkit-border-image-outset",
    		"-moz-border-image-outset",
    		"-o-border-image-outset",
    		"border-image-outset",
    		"-webkit-border-image-repeat",
    		"-moz-border-image-repeat",
    		"-o-border-image-repeat",
    		"border-image-repeat",
    		"padding",
    		"padding-top",
    		"padding-right",
    		"padding-bottom",
    		"padding-left",
    		"width",
    		"min-width",
    		"max-width",
    		"height",
    		"min-height",
    		"max-height"
    	],
    	[
    		"font",
    		"font-family",
    		"font-size",
    		"font-weight",
    		"font-style",
    		"font-variant",
    		"font-size-adjust",
    		"font-stretch",
    		"font-effect",
    		"font-emphasize",
    		"font-emphasize-position",
    		"font-emphasize-style",
    		"font-smooth",
    		"line-height",
    		"text-align",
    		"-webkit-text-align-last",
    		"-moz-text-align-last",
    		"-ms-text-align-last",
    		"text-align-last",
    		"vertical-align",
    		"white-space",
    		"text-decoration",
    		"text-emphasis",
    		"text-emphasis-color",
		    "text-emphasis-style",
		    "text-emphasis-position",
		    "text-indent",
		    "-ms-text-justify",
		    "text-justify",
		    "letter-spacing",
		    "word-spacing",
		    "-ms-writing-mode",
		    "text-outline",
		    "text-transform",
		    "text-wrap",
		    "-ms-text-overflow",
		    "text-overflow",
		    "text-overflow-ellipsis",
		    "text-overflow-mode",
		    "-ms-word-wrap",
		    "word-wrap",
		    "-ms-word-break",
		    "word-break"
	    ],
	    [
		    "color",
		    "background",
		    "filter:progid:DXImageTransform.Microsoft.AlphaImageLoader",
		    "background-color",
		    "background-image",
		    "background-repeat",
		    "background-attachment",
		    "background-position",
		    "-ms-background-position-x",
		    "background-position-x",
		    "-ms-background-position-y",
		    "background-position-y",
		    "-webkit-background-clip",
		    "-moz-background-clip",
		    "background-clip",
		    "background-origin",
		    "-webkit-background-size",
		    "-moz-background-size",
		    "-o-background-size",
		    "background-size"
	    ],
	    [
		    "outline",
		    "outline-width",
		    "outline-style",
		    "outline-color",
		    "outline-offset",
		    "opacity",
		    "filter:progid:DXImageTransform.Microsoft.Alpha(Opacity",
		    "-ms-filter:\\'progid:DXImageTransform.Microsoft.Alpha",
		    "-ms-interpolation-mode",
		    "-webkit-box-shadow",
		    "-moz-box-shadow",
		    "box-shadow",
		    "filter:progid:DXImageTransform.Microsoft.gradient",
		    "-ms-filter:\\'progid:DXImageTransform.Microsoft.gradient",
		    "text-shadow"
	    ],
	    [
		    "-webkit-transition",
		    "-moz-transition",
		    "-ms-transition",
		    "-o-transition",
		    "transition",
		    "-webkit-transition-delay",
		    "-moz-transition-delay",
		    "-ms-transition-delay",
		    "-o-transition-delay",
		    "transition-delay",
		    "-webkit-transition-timing-function",
		    "-moz-transition-timing-function",
		    "-ms-transition-timing-function",
		    "-o-transition-timing-function",
		    "transition-timing-function",
		    "-webkit-transition-duration",
		    "-moz-transition-duration",
		    "-ms-transition-duration",
		    "-o-transition-duration",
		    "transition-duration",
		    "-webkit-transition-property",
		    "-moz-transition-property",
		    "-ms-transition-property",
		    "-o-transition-property",
		    "transition-property",
		    "-webkit-transform",
		    "-moz-transform",
		    "-ms-transform",
		    "-o-transform",
		    "transform",
		    "-webkit-transform-origin",
		    "-moz-transform-origin",
		    "-ms-transform-origin",
		    "-o-transform-origin",
		    "transform-origin",
		    "-webkit-animation",
		    "-moz-animation",
		    "-ms-animation",
		    "-o-animation",
		    "animation",
		    "-webkit-animation-name",
		    "-moz-animation-name",
		    "-ms-animation-name",
		    "-o-animation-name",
		    "animation-name",
		    "-webkit-animation-duration",
		    "-moz-animation-duration",
		    "-ms-animation-duration",
		    "-o-animation-duration",
		    "animation-duration",
		    "-webkit-animation-play-state",
		    "-moz-animation-play-state",
		    "-ms-animation-play-state",
		    "-o-animation-play-state",
		    "animation-play-state",
		    "-webkit-animation-timing-function",
		    "-moz-animation-timing-function",
		    "-ms-animation-timing-function",
		    "-o-animation-timing-function",
		    "animation-timing-function",
		    "-webkit-animation-delay",
		    "-moz-animation-delay",
		    "-ms-animation-delay",
		    "-o-animation-delay",
		    "animation-delay",
		    "-webkit-animation-iteration-count",
		    "-moz-animation-iteration-count",
		    "-ms-animation-iteration-count",
		    "-o-animation-iteration-count",
		    "animation-iteration-count",
		    "-webkit-animation-direction",
		    "-moz-animation-direction",
		    "-ms-animation-direction",
		    "-o-animation-direction",
		    "animation-direction"
	    ],
	    [
		    "content",
		    "quotes",
		    "counter-reset",
		    "counter-increment",
		    "resize",
		    "cursor",
		    "-webkit-user-select",
		    "-moz-user-select",
		    "-ms-user-select",
		    "user-select",
		    "nav-index",
		    "nav-up",
		    "nav-right",
		    "nav-down",
		    "nav-left",
		    "-moz-tab-size",
		    "-o-tab-size",
		    "tab-size",
		    "-webkit-hyphens",
		    "-moz-hyphens",
		    "hyphens",
		    "pointer-events"
    	]
    ]
    
## 颜色 ##

颜色16进制用小写字母；

**PC端**颜色16进制尽量用简写。

    /* not good */
    .element {
	    color: #ABCDEF;
	    background-color: #001122;
    }
    
    /* good */
    .element {
	    color: #abcdef;
	    background-color: #012;
    }
    
## 属性简写 ##

**margin** 和 **padding** 需要使用简写；

    .element {
    	margin: 10px 0 0；
    }
    .element {
    	padding: 10px 10px；
    }

## 媒体查询 ##

尽量将媒体查询的规则靠近与他们相关的规则，不要将他们一起放到一个独立的样式文件中，或者丢在文档的最底部，这样做只会让大家以后更容易忘记他们。

    .element {
    	...
    }
    
    .element-avatar{
    	...
    }
    
    @media (min-width: 480px) {
    	.element {
    		...
    	}
    
    	.element-avatar {
    		...
    	}
    }

## SCSS相关 ##

提交的代码中不要有 **@debug**；

声明顺序：

- **@extend**
- 不包含 **@content** 的 **@include**
- 包含 **@content** 的 **@include**
- 自身属性
- 嵌套规则

**@import** 引入的文件不需要开头的'_'和结尾的'.scss'；

嵌套最多不能超过5层；

**@extend** 中使用placeholder选择器；

去掉不必要的父级引用符号'&'。

    /* not good */
    @import "_dialog.scss";
    
    /* good */
    @import "dialog";
    
    /* not good */
    .fatal {
    	@extend .error;
    }
    
    /* good */
    .fatal {
    	@extend %error;
    }
    
    /* not good */
    .element {
    	& > .dialog {
    		...
    	}
    }
    
    /* good */
    .element {
    	> .dialog {
    		...
    	}
    }


## 杂项 ##

不允许有空的规则；

元素选择器用小写字母；

去掉小数点前面的0；

去掉数字中不必要的小数点和末尾的0；

属性值'0'后面不要加单位；

同个属性不同前缀的写法需要在垂直方向保持对齐，具体参照右边的写法；

无前缀的标准属性应该写在有前缀的属性后面；

不要在同个规则里出现重复的属性，如果重复的属性是连续的则没关系；

不要在一个文件里出现两个相同的规则；

用 **border: 0**; 代替 **border: none**；

选择器不要超过5层（在scss中如果超过5层应该考虑用嵌套的方式来写）；

发布的代码中不要有 **@import**；

尽量少用'*'选择器。

    /* not good */
    .element {
    }
    
    /* not good */
    LI {
    	...
    }
    
    /* good */
    li {
    	...
    }
    
    /* not good */
    .element {
    	color: rgba(0, 0, 0, 0.5);
    }
    
    /* good */
    .element {
    	color: rgba(0, 0, 0, .5);
    }
    
    /* not good */
    .element {
    	width: 50.0px;
    }
    
    /* good */
    .element {
    	width: 50px;
    }
    
    /* not good */
    .element {
    	width: 0px;
    }
    
    /* good */
    .element {
    	width: 0;
    }
    
    /* not good */
    .element {
	    border-radius: 3px;
	    -webkit-border-radius: 3px;
	    -moz-border-radius: 3px;
	    
	    background: linear-gradient(to bottom, #fff 0, #eee 100%);
	    background: -webkit-linear-gradient(top, #fff 0, #eee 100%);
	    background: -moz-linear-gradient(top, #fff 0, #eee 100%);
    }
    
    /* good */
    .element {
	    -webkit-border-radius: 3px;
	       -moz-border-radius: 3px;
	    		border-radius: 3px;
	    
	    background: -webkit-linear-gradient(top, #fff 0, #eee 100%);
	    background:	   -moz-linear-gradient(top, #fff 0, #eee 100%);
	    background: linear-gradient(to bottom, #fff 0, #eee 100%);
    }
    
    /* not good */
    .element {
	    color: rgb(0, 0, 0);
	    width: 50px;
	    color: rgba(0, 0, 0, .5);
    }
    
    /* good */
    .element {
	    color: rgb(0, 0, 0);
	    color: rgba(0, 0, 0, .5);
    }

# JavaScript #

## 缩进 ##

使用soft tab（4个空格）。

## 分号 ##

以下几种情况后需加分号：

- 变量声明
- 表达式
- return
- throw
- break
- continue
- do-while
> 


    /* 变量声明 */
    var x = 1;
    
    /* 表达式 */
    x++;
    
    /* do-while */
    do {
    	x++;
    } while (x < 10);

## 空格 ##

以下几种情况不需要空格：

- 对象的属性名后
- 前缀一元运算符后
- 后缀一元运算符前
- 函数调用括号前
- 无论是函数声明还是函数表达式，'('前不要空格
- 数组的'['后和']'前
- 对象的'{'后和'}'前
- 运算符'('后和')'前

以下几种情况需要空格：

- 二元运算符前后
- 三元运算符'?:'前后
- 代码块'{'前
- 下列关键字前：**else, while, catch, finally**
- 下列关键字后：**if, else, for, while, do, switch, case, try, catch, finally, with, return, typeof**
- 单行注释'//'后（若单行注释和代码同行，则'//'前也需要），多行注释'*'后
- 对象的属性值前
- for循环，分号后留有一个空格，前置条件如果有多个，逗号后留一个空格
- 无论是函数声明还是函数表达式，'{'前一定要有空格
- 函数的参数之间
> 


    // not good
    var a = {
    	b :1
    };
    
    // good
    var a = {
    	b: 1
    };
    
    // not good
    ++ x;
    y ++;
    z = x?1:2;
    
    // good
    ++x;
    y++;
    z = x ? 1 : 2;
    
    // not good
    var a = [ 1, 2 ];
    
    // good
    var a = [1, 2];
    
    // not good
    var a = ( 1+2 )*3;
    
    // good
    var a = (1 + 2) * 3;
    
    //  '('前不要空格, '{'前1个空格,  function 参数间有1个空格
    var doSomething = function(a, b, c) {
    // do something
    };
    
    // no space before '('
    doSomething(item);
    
    // not good
    for(i=0;i<6;i++){
    	x++;
    }
    
    // good
    for (i = 0; i < 6; i++) {
    	x++;
    }

## 空行 ##

以下几种情况需要空行：

- 变量声明后（当变量声明在代码块的最后一行时，则无需空行）
- 注释前（当注释在代码块的第一行时，则无需空行）
- 代码块后（在函数调用、数组、对象中则无需空行）
- 文件最后保留一个空行
> 
   
    // 变量声明后，需要空行
    var x = 1;
    
    // 当变量声明在代码块的最后一行时，则无需空行
    if (x >= 1) {
    	var y = x + 1;
    }
    
    var a = 2;
    
    // 注释前，需要空行
    a++;
    
    function b() {
    	// 当注释在代码块的第一行时，则无需空行
    	return a;
    }
    
    // 每个代码块后要有空行
    for (var i = 0; i < 2; i++) {
    	if (true) {
    		return false;
    	}
    
    	continue;
    }
    
    var obj = {
    	foo: function() {
    		return 1;
    	},
    
    	bar: function() {
    		return 2;
    	}
    };
    
    // 参数队列，数组，对象不要有空行
    func(
    	2,
    	function() {
    		a++;
    	},
    	3
    );
    
    var foo = [
    	2,
    	function() {
    	a++;
    	},
    	3
    ];
    
    
    var foo = {
    	a: 2,
    	b: function() {
    	a++;
    	},
    	c: 3
    };

## 换行 ##

换行的地方，行末必须有','或者运算符；

以下几种情况不需要换行：

- 下列关键字后：**else, catch, finally**
- 代码块'{'前

以下几种情况需要换行：

- 代码块'{'后和'}'前
- 变量赋值后
> 


    // not good
    var a = {
    	b: 1
    	, c: 2
    };
    
    x = y
    ? 1 : 2;
    
    // good
    var a = {
    	b: 1,
    	c: 2
    };
    
    x = y ? 1 : 2;
    x = y ?
    1 : 2;
    
    // 'else', 'catch', 'finally'不需要换行
    if (condition) {
    	...
    } else {
    	...
    }
    
    try {
    	...
    } catch (e) {
    	...
    } finally {
    	...
    }
    
    // not good
    function test()
    {
    	...
    }
    
    // good
    function test() {
    	...
    }
    
    // not good
    var a, foo = 7, b,
    c, bar = 8;
    
    // good
    var a,
    foo = 7,
    b, c, bar = 8;

## 单行注释 ##

双斜线后，必须跟一个空格；

缩进与下一行代码保持一致；

可位于一个代码行的末尾，与代码间隔一个空格。

    if (condition) {
    	// if you made it here, then all security checks passed
    	allowed();
    }
    
    var zhangsan = 'zhangsan'; // one space after code


## 多行注释 ##

最少三行, '*'后跟一个空格，具体参照右边的写法；

建议在以下情况下使用：

- 难于理解的代码段
- 可能存在错误的代码段
- 浏览器特殊的HACK代码
- 业务逻辑强相关的代码
> 


    /*
     * one space after '*'
     */
    var x = 1;

## 文档注释 ##

各类标签@param, @method等；

建议在以下情况下使用：

- 所有常量
- 所有函数
- 所有类
> 

   
    /**
     * @func
     * @desc 一个带参数的函数
     * @param {string} a - 参数a
     * @param {number} b=1 - 参数b默认值为1
     * @param {string} c=1 - 参数c有两种支持的取值</br>1—表示x</br>2—表示xx
     * @param {object} d - 参数d为一个对象
     * @param {string} d.e - 参数d的e属性
     * @param {string} d.f - 参数d的f属性
     * @param {object[]} g - 参数g为一个对象数组
     * @param {string} g.h - 参数g数组中一项的h属性
     * @param {string} g.i - 参数g数组中一项的i属性
     * @param {string} [j] - 参数j是一个可选参数
     */
    function foo(a, b, c, d, g, j) {
    	...
    }

## 引号 ##

最外层统一使用单引号。
    
    // not good
    var x = "test";
    
    // good
    var y = 'foo',
    z = '<div id="test"></div>';

## 变量命名 ##

- 标准变量采用驼峰式命名（除了对象的属性外，主要是考虑到cgi返回的数据）
- 'ID'在变量名中全大写
- 'URL'在变量名中全大写
- 'Android'在变量名中大写第一个字母
- 'iOS'在变量名中小写第一个，大写后两个字母
- 常量全大写，用下划线连接
- 构造函数，大写第一个字母
> 

    var thisIsMyName;
    
    var goodID;
    
    var reportURL;
    
    var AndroidVersion;
    
    var iOSVersion;
    
    var MAX_COUNT = 10;
    
    function Person(name) {
    	this.name = name;
    }

## 变量声明 ##

一个函数作用域中所有的变量声明尽量提到函数首部，用一个var声明，不允许出现两个连续的var声明。  

    function doSomethingWithItems(items) {
    	// 使用1个var
    	var value = 10,
    	result = value + 10,
    	i,
    	len;
    
    	for (i = 0, len = items.length; i < len; i++) {
    		result += 10;
    	}
    }  

## 函数 ##

无论是函数声明还是函数表达式，'('前不要空格，但'{'前一定要有空格；

函数调用括号前不需要空格；

立即执行函数外必须包一层括号；

不要给inline function命名；

参数之间用', '分隔，注意逗号后有一个空格。

    // '('前不要空格, '{'前有个空格
    var doSomething = function(item) {
    	// do something
    };
    
    function doSomething(item) {
    	// do something
    }
    
    // not good
    doSomething (item);
    
    // good
    doSomething(item);
    
    // 立即执行函数外必须包一层括号；
    (function() {
    	return 1;
    })();
    
    // not good
    [1, 2].forEach(function x() {
    	...
    });
    
    // good
    [1, 2].forEach(function() {
    	...
    });
    
    // not good
    var a = [1, 2, function a() {
    	...
    }];
    
    // good
    var a = [1, 2, function() {
    ...
    }];
    
    // 参数之间用', '分隔，注意逗号后有一个空格。
    var doSomething = function(a, b, c) {
    	// do something
    };
    
## 数组、对象 ##

对象属性名不需要加引号；

对象以缩进的形式书写，不要写在一行；

数组、对象最后不要有逗号。

    // not good
    var a = {
    	'b': 1
    };
    
    var a = {b: 1};
    
    var a = {
    	b: 1,
    	c: 2,
    };
    
    // good
    var a = {
    	b: 1,
    	c: 2
    };

## 括号 ##

下列关键字后必须有大括号（即使代码块的内容只有一行）：**if, else, for, while, do, switch, try, catch, finally, with。**

    // not good
    if (condition)
    	doSomething();
    
    // good
    if (condition) {
    	doSomething();
    }

## null ##

适用场景：

- 初始化一个将来可能被赋值为对象的变量
- 与已经初始化的变量做比较
- 作为一个参数为对象的函数的调用传参
- 作为一个返回对象的函数的返回值

不适用场景：

- 不要用null来判断函数调用时有无传参
- 不要与未初始化的变量做比较
> 

    // not good
    function test(a, b) {
    	if (b === null) {
    		// 要用null来判断函数调用时有无传参
    		...
    	}
    }
    
    var a;
    
    if (a === null) {
    	...
    }
    
    // good
    var a = null;
    
    if (a === null) {
    	...
    }

## undefined ##

永远不要直接使用undefined进行变量判断；

使用typeof和字符串'undefined'对变量进行判断。

    // not good
    if (person === undefined) {
    	...
    }
    
    // good
    if (typeof person === 'undefined') {
    	...
    }

## jshint ##

用'===', '!=='代替'==', '!='；

for-in里一定要有hasOwnProperty的判断；

不要在内置对象的原型上添加方法，如Array, Date；

不要在内层作用域的代码里声明了变量，之后却访问到了外层作用域的同名变量；

变量不要先使用后声明；

不要在一句代码中单单使用构造函数，记得将其赋值给某个变量；

不要在同个作用域下声明同名变量；

不要在一些不需要的地方加括号，例：delete(a.b)；

不要使用未声明的变量（全局变量需要加到.jshintrc文件的globals属性里面）；

不要声明了变量却不使用；

不要在应该做比较的地方做赋值；

debugger不要出现在提交的代码里；

数组中不要存在空元素；

不要在循环内部声明函数；

不要像这样使用构造函数，例：new function () { ... }, new Object；

    // not good
    if (a == 1) {
    	a++;
    }
    
    // good
    if (a === 1) {
    	a++;
    }
    
    // good
    for (key in obj) {
	    if (obj.hasOwnProperty(key)) {
		    // for-in里一定要有hasOwnProperty的判断
		    console.log(obj[key]);
	    }
    }
    
    // not good
    Array.prototype.count = function(value) {
    	return 4;
    };
    
    // not good
    var x = 1;
    
    function test() {
    if (true) {
    var x = 0;
    }
    
    x += 1;
    }
    
    // not good
    function test() {
	    console.log(x);
	    
	    var x = 1;
    }
    
    // not good
    new Person();
    
    // good
    var person = new Person();
    
    // not good
    delete(obj.attr);
    
    // good
    delete obj.attr;
    
    // not good
    if (a = 10) {
    	a++;
    }
    
    // not good
    var a = [1, , , 2, 3];
    
    // not good
    var nums = [];
    
    for (var i = 0; i < 10; i++) {
    	(function(i) {
    		nums[i] = function(j) {
    			return i + j;
    		};
    	}(i));
    }
    
    // not good
    var singleton = new function() {
    	var privateVar;
    
    	this.publicMethod = function() {
    		privateVar = 1;
    	};
    
    	this.publicMethod2 = function() {
    		privateVar = 2;
    	};
    };

## 杂项 ##

不要混用tab和space；

不要在一处使用多个tab或space；

对上下文this的引用只能使用'_this', 'that', 'self'其中一个来命名；

行尾不要有空白字符；

switch的falling through和no default的情况一定要有注释特别说明；

不允许有空的代码块。

    // not good
    var a   = 1;
    
    function Person() {
	    // not good
	    var me = this;
	    
	    // good
	    var _this = this;
	    
	    // good
	    var that = this;
	    
	    // good
	    var self = this;
    }
    
    // good
    switch (condition) {
    	case 1:
    	case 2:
	    	...
	    break;
	    case 3:
	    	...
	    // why fall through
	    case 4
	    	...
	    break;
	    // why no default
    }
    
    // not good with empty block
    if (condition) {
    
    }

# 编辑器配置和构建检查 #

## sublime3插件 ##

1、安装node包

jscs 

npm install jscs -g

jshint 

npm install jshint -g

2、安装gem包

scss-lint 

gem install scss_lint.

> 注意：
> 
- 使用gem update遇到这个问题，原来是ruby没有包含SSL证书，所以Https的链接被服务器拒绝。解决方法很简单，首先在这里下载证书(http://curl.haxx.se/ca/cacert.pem), 然后再环境变量=》系统变量里设置SSL_CERT_FILE这个环境变量，并把value指向这个文件
> 
- gem sources --remove https://rubygems.org/ // 如果有资源链接https://rubygems.org/
> 
- gem sources -l // 此命令列出资源链接
> 
- gem sources -a http://gems.ruby-china.org/ //添加http://gems.ruby-china.org/资源链接


3、安装sublime3 Package Control

4、安装sublime3插件

- 按下 ctrl+shift+p，输入'ip'（Install Package）
- 输入以下插件的名字，按顺序逐个进行安装：

	- EditorConfig
	- Sass
	- SublimeLinter
	- SublimeLinter-jscs
	- SublimeLinter-jshint	
	- JSFormat //ctr+alt+f
	- SublimeLinter-contrib-scss-lint
	
5、插件的配置文件

将以下配置文件分别下载后放入项目根目录下：

- EditorConfig 配置文件
- JSCS 配置文件
- JSHint 配置文件
> 
    配置文件规则
    {
	    "curly": true,//循环或者条件语句必须使用花括号包住
	    "eqeqeq": true,//禁止使用== 和 ！=  强制使用=== 和 ！==
	    "forin": true,/*这个选项要求所有 for in循环过滤对象的item。他在声明中允许for遍历一个对象所有属性的名称包括通过原型链继承来的属性。*/
	    "freeze": true,//这个选项禁止重写原生对象的原型列如 Array, Date等等。
	    "globals": {
	    	"ImageHandle": true
	    },
	    "latedef": true,//禁止定义之前使用变量
	    "maxerr": 200,//设置JSHint最大警告数
	    "nonew": true,//这个选项禁止使用new构造器函数。有些人喜欢调用构造函数，但是不赋值给任何对象
	    "shadow": "inner",//只检查是否在相同的作用域重复定义
	    "singleGroups": true,//禁止使用分组操作符
	    "undef": true,//禁止使用不在全局变量列表中的未定义变量
	    "unused": true,//变量定义未使用    
	    "evil": true,//禁止使用eval （可以去掉）
	    "expr": true,//禁止使用表达式，一般的使用函数调用。
	    "proto": true,//禁止关于__proto__属性的警告
	    "scripturl": true,//禁止使用脚本URL定向，比如javascript:...
	    "sub": true,//检查[]使用，可以使用.代替[] 比如person['name'] vs.person.name.    
	    "browser": true,//暴露浏览器属性的全局变量 如window document
	    "devel": true,//定义用于调试的全局变量：console,alert
	    "jquery": true,//定义全局暴露的jQuery库
	    "nonstandard": true,//这个选项定义非标准但广泛采用全局变量等 escape和 unescape.
	    "typed": true,//这个选项定义全局变量数组类型构造函数。
	    "worker": true/*这个选项定义全局变量可以当你的代码运行在web worker.web worker 是运行在后台的 JavaScript，独立于其他脚本，不会影响页面的性能.所有主流浏览器均支持 web worker，除了 Internet Explorer。*/
    }




	注意：全局变量需要手动加到配置文件的globals属性里，例：
	    
	    {
    		"globals": {
    			"ImageHandle": true
    		}
    	}

- SCSS-Lint 配置文件
> 
    // sass文件目录
    scss_files: "sass/**/*.scss"     
    linters:
      BangFormat:
	    enabled: true
	    space_before_bang: true
	    space_after_bang: false    
      BemDepth:
	    enabled: false
	    max_elements: 1
    //border 0 规则，不能写成null，只能0
      BorderZero:
	    enabled: true
	    convention: zero # or `none`    
      ColorKeyword:
    	enabled: false    
      ColorVariable:
    	enabled: false    
      Comment:
    	enabled: false    
      DebugStatement:
    	enabled: true    
      DeclarationOrder:
    	enabled: true    
      DuplicateProperty:
    	enabled: false    
      ElsePlacement:
	    enabled: true
	    style: same_line # or 'new_line'    
      EmptyLineBetweenBlocks:
	    enabled: false
	    ignore_single_line_blocks: false    
      EmptyRule:
    	enabled: true    
      FinalNewline:
	    enabled: false
	    present: true    
      HexLength:
	    enabled: true
	    style: short # or 'long' PC=>short ,M=>long    
      HexNotation:
	    enabled: true
	    style: lowercase # or 'uppercase'    
      HexValidation:
    	enabled: true    
      IdSelector:
    	enabled: false    
      ImportantRule:
    	enabled: false    
      ImportPath:
	    enabled: true
	    leading_underscore: false
	    filename_extension: false    
      Indentation:
	    enabled: false
	    allow_non_nested_indentation: false
	    character: space # or 'tab'
	    width: 4    
      LeadingZero:
	    enabled: true
	    style: exclude_zero # or 'include_zero'    
      MergeableSelector:
	    enabled: true
	    force_nesting: false    
      NameFormat:
	    enabled: true
	    allow_leading_underscore: false
	    convention: hyphenated_lowercase # or 'camel_case', or 'snake_case', or a regex pattern	    
      NestingDepth:
	    enabled: false
	    max_depth: 5    
      PlaceholderInExtend:
    	enabled: true    
      PropertyCount:
	    enabled: false
	    include_nested: false
	    max_properties: 10    
      PropertyUnits:
	    enabled: true
	    global: [
	      'ch', 'em', 'ex', 'rem', # Font-relative lengths
	      'cm', 'in', 'mm', 'pc', 'pt', 'px', 'q', # Absolute lengths
	      'vh', 'vw', 'vmin', 'vmax',  # Viewport-percentage lengths
	      'deg', 'grad', 'rad', 'turn',# Angle
	      'ms', 's',   # Duration
	      'Hz', 'kHz', # Frequency
	      'dpi', 'dpcm', 'dppx',   # Resolution
	      '%'] # Other
	    properties: {}    
      PropertySortOrder:
	    enabled: false
	    ignore_unspecified: false
	    min_properties: 2
	    separate_groups: true    
      PropertySpelling:
	    enabled: true
	    extra_properties: []    
      QualifyingElement:
	    enabled: false
	    allow_element_with_attribute: false
	    allow_element_with_class: false
	    allow_element_with_id: false    
      SelectorDepth:
	    enabled: false
	    max_depth: 5    
      SelectorFormat:
	    enabled: true
	    convention: hyphenated_lowercase # or 'strict_BEM', or 'hyphenated_BEM', or 'snake_case', or 'camel_case', or a regex pattern
	    ignored_types: ['id']    
      Shorthand:
	    enabled: true
	    allowed_shorthands: [1, 2, 3, 4]    
      SingleLinePerProperty:
	    enabled: true
	    allow_single_line_rule_sets: false    
      SingleLinePerSelector:
    	enabled: true    
      SpaceAfterComma:
    	enabled: true    
      SpaceAfterPropertyColon:
    	enabled: true
    	style: at_least_one_space # 'one_space', or 'no_space', or 'aligned'    
      SpaceAfterPropertyName:
    	enabled: true    
      SpaceBeforeBrace:
	    enabled: true
	    style: space # or 'new_line'
	    allow_single_line_padding: false    
      SpaceBetweenParens:
	    enabled: true
	    spaces: 0    
      StringQuotes:
	    enabled: true
	    style: double_quotes # or single_quotes    
      TrailingSemicolon:
    	enabled: true    
      TrailingZero:
    	enabled: true    
      UnnecessaryMantissa:
    	enabled: true    
      UnnecessaryParentReference:
    	enabled: true    
      UrlFormat:
    	enabled: false    
      UrlQuotes:
    	enabled: true    
      VariableForProperty:
	    enabled: false
	    properties: []    
      VendorPrefix:
	    enabled: false
	    identifier_list: base
	    additional_identifiers: []
	    excluded_identifiers: []    
      ZeroUnit:
    	enabled: true    
      Compass::*:
    	enabled: false
    

6、编辑器及插件设置

- sublime3 自身
	
	
	Preferences->Setting-User，增加下面两个配置：
	
	    {
    	"translate_tabs_to_spaces": true,
    	"word_wrap": true
    	}
	点击右下角的Spaces->Convert Indentation to Spaces可以将文件中的所有tab转换成空格


- SublimeLinter

	    右键->SublimeLinter->Lint Mode，有4种检查模式，建议选择 Load/save
    	
    	右键->SublimeLinter->Mark Style，建议选择 Outline
    	
    	右键->SublimeLinter->Choose Gutter Theme，建议选择 Blueberry-round
    	
    	右键->SublimeLinter->Open User Settings，将linter里面jscs的args改成 ["--verbose"]
    	"jshint": {
    		"@disable": false,
    		"args": [
    		"--config",
    		"E:\\workspace\\b2b-gulp\\.jshintrc"//真实项目windows下jshint文件路径
    		],
    		"excludes": []
    	}
    	
    	当光标处于有错误的代码行时，详细的错误信息会显示在下面的状态栏中
    	
    	右键->SublimeLinter可以看到所有的快捷键，其中 ctrl+k, a 可以列出所有错误
