# CSS入门学习笔记+案例

## CSS入门学习

### 一、CSS简介

#### 1、什么是CSS

CSS：Cascading Style Sheet 层叠样式表

是一组[样式设置](https://so.csdn.net/so/search?q=%E6%A0%B7%E5%BC%8F%E8%AE%BE%E7%BD%AE&spm=1001.2101.3001.7020)的规则，用于控制页面的外观样式

#### 2、为什么使用CSS

实现内容与样式的分离，便于团队开发

样式复用，便于网站的后期维护

页面的精确控制，让页面更精美

#### 3、CSS作用

页面外观美化

布局和定位

### 二、基本用法

#### 1、CSS语法

```html
<head>
	<style>
		选择器{
			属性名：属性值;
			属性名：属性值;
		}
	</style>
</head>
```

-   选择器：要修饰的对象（东西）
-   属性名：修饰对象的哪一个属性（样式）
-   属性值：样式的取值

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style>
		p{
			color:red;
			background: #cccccc;
		}
		h2{
			color:blue;
		}
	</style>
</head>
<body>
	<p>CSS从入门到精通</p>
	<h2>主讲：hector</h2>
</body>
</html>
```

示例：

![css语法.png](https://i-blog.csdnimg.cn/blog_migrate/450e338b40a361f604fa13637cae122c.png)

#### 2、CSS应用方式

也称为CSS引用方式，有三种方式：内部样式、行内样式、外部样式

##### 2.1 内部样式

也称为内嵌样式，在页面头部通过[style标签](https://so.csdn.net/so/search?q=style%E6%A0%87%E7%AD%BE&spm=1001.2101.3001.7020)定义

对当前页面中所有符合样式选择器的标签都起作用

##### 2.2 行内样式

也称为嵌入样式，使用HTML标签的style属性定义

只对设置style属性的标签起作用

##### 2.3 外部样式

使用单独的 `.CSS` 文件定义，然后在页面中使用 `link标签` 或 `@import指令` 引入

-   使用 `link标签` 链接外部样式文件
    
    ```html
    <link rel="stylesheet" type="text/css" href="CSS样式文件的路径">
    ```
    
    提示：type属性可以省略
    
-   `@import` 指令 导入外部样式文件
    
    ```html
    <style>
    	@import "CSS样式文件路径";
    	@import url(CSS样式文件路径);
    </style>
    ```
    

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style>
		/* 1.内部样式 */
		p{
			color:blue;
		}
	</style>
	<!-- link链接外部样式文件 -->
	<!-- <link rel="stylesheet" type="text/css" href="style/hello.css"> -->
	<!-- 3.import导入外部样式文件 -->
	<style>
		/* @import "style/hello.css" */
		@import url(style/hello.css);
	</style>
</head>
<body>
	<p>welcome to CSS!</p>
	<p>欢迎来到CSS课堂!</p>
	<hr>
	<h2 style="color:red;">WEB前段工程师</h2>
	<h2>JAVA开发工程师</h2>
	<hr>
	<div>嘿嘿</div>
	<div>哈哈</div>
</body>
</html>
```

示例：

![css应用样式.png](https://i-blog.csdnimg.cn/blog_migrate/237b605b2e6a24ba084a7489e65ecd8e.png)

### 三、选择器

#### 1、基础选择器

##### 1.1 标签选择器

也称为元素选择器，使用HTML标签作为选择器的名称

以标签名作为样式应用的依据

##### 1.2 类选择器

使用自定义的名称，以 `.` 号作为前缀，然后再通过HTML标签的class属性调用类选择器

以标签的class属性作为样式应用的依据

注意事项：

-   调用时不能添加 `.` 号
-   同时调用多个类选择器时，以 `空格` 分隔
-   类选择器名称不能以 `数字` 开头

##### 1.3 ID选择器

使用自定义名称，以 `#` 作为前缀，然后通过HTML标签的id属性进行名称匹配

以标签的id属性作为样式应用的依据，一对一的关系

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style>
		p{
			color:red;
			font-size:20px;
		}
		h2{
			color:yellow;
		}
		.hello{
			background: #cccccc;
		}
		.world{
			font-weight:bold;
		}
		#haha{
			color:blue;
		}
	</style>
</head>
<body>
	<p>welcome to css!</p>
	<p>hello world!</p>
	<h2>WEB前端开发</h2>
	<h3>Java开发</h3>
	<hr>
	<p class="hello">welcome to css!</p>
	<p>hello world!</p>
	<h2>WEB前端开发</h2>
	<h3>Java开发</h3>
	<div class="hello">主讲：Hector</div>
	<div class="world">主讲：Hector</div>
	<hr>
	<h1 id="haha">哈哈</h1>
</body>
</html>
```

示例：

![css选择器.png](https://i-blog.csdnimg.cn/blog_migrate/65e6dfa7e6a1f5f715cdad13aea4086a.png)

#### 2、复杂选择器

##### 2.1 复合选择器

标签选择器和类选择器、标签选择器和ID选择器，一起使用

必须同时满足两个条件才能应用样式

##### 2.2组合选择器

也称为集体声明

将多个具有相同样式的选择器放在一起声明，使用逗号隔开

##### 2.3 嵌套选择器

在某个选择器内部再设置选择器，通过空格隔开

只有满足层次关系最里层的选择器所对应的标签才会应用样式

注意：使用 `空格` 时不区分父子还是后代，使用CSS3中新增的 `>` 时必须是父子关系才行

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style>
		/* 1.标签选择器和类选择器合起来使用----复合选择器 */
		h1.aaa{
			color:red;
		}
		/* 1.标签选择器和ID选择器合起来使用----复合选择器 */
		p#bbb{
			color:blue;
		}
		/* 2.组合选择器 */
		h1,p,div,span,.ccc{
			font-size:30px;
		}
		div{
			background:violet;
		}
		.ccc{
			font-weight:bold;
		}
		/* 3.嵌套选择器 */
		/* div p{
			color:green;
			text-decoration:underline;
		} */
		div>p{
			color:green;
			text-decoration:underline;
		}
		div h3.ddd{
			color:red;
		}
	</style>
</head>
<body>
	<!-- 需求：只想修饰class属性为aaa的h1标签 -->
	<h1 class="aaa">welcome</h1>
	<h4 class="aaa">css</h4>
	<h1>hello</h1>
	<hr>
	<!-- 我要修饰ID属性为bbb的p标签 -->
	<p id="bbb">world</p >
	<p>html</p>
	<h1 id="bbb">主讲：叽叽</h1>
	<hr>
	<!-- 给h1、p、div、span标签中的内容设置字号为30px -->
	<h1>hello</h1>
	<p>CSS</p>
	<div>WEB开发</div>
	<span class="ccc">JAVA开发</span>
	<hr>
	<!-- 需求：修饰div内部的p标签 -->
	<div>
		<p>div内部的p标签</p>
		<h3>div内部的h3标签</h3>
	</div>
	<hr>
	<div>
		<h3>
			<p>div内部的h3内部的p标签</p>
		</h3>
	</div>
	<hr>
	<!-- 需求：修饰div内部的class为ddd的标签 -->
	<div>
		<p>div内部的p</p>
		<h3 class="ddd">div内部的h3</h3>
		<p class="ddd">PPPP</p>
	</div>
	<h3 class="ddd">h3h3h3</h3>
</body>
</html>
```

示例：

![复杂选择器.png](https://i-blog.csdnimg.cn/blog_migrate/ed550799698d084c3e7cefb00d1591b7.png)

##### 2.4 伪类选择器

根据不同的状态显示不同的样式，一般多用于 标签

四种状态：

-   :link 未访问的链接
-   :visited 已访问的链接
-   :hover 鼠标悬浮到连接上，即移动在连接上
-   :active 选定的链接，被激活

注：默认超链接为：蓝色、下划线

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>伪类选择器</title>
	<style>
		/*a:link{
			font-size: 12px;
			color:black;
			text-decoration: none;
		}
		a:visited{
			font-size: 15px;
			color:;
		}
		a:hover{
			font-size: 20px;
			color:blue;
		}
		a:active{
			font-size: 40px;
			color:green;
		}*/
		a:link,a:visited{
			color:#666666;
			font-size: 13px;
			text-decoration: none;
		}
		a:hover,a:active{
			color:#ff7300;
			text-decoration: underline;
		}
		/*普通的标签也可以使用伪类选择器*/
		p:hover{
			color:red;
		}
		p:active{
			color:blue;
		}
	</style>
</head>
<body>
	<a href="复杂选择器.html">复杂选择器.html</a>
	<p>CSS从入门到精通！</p>
</body>
</html>
```

示例：

![伪类选择器.gif](https://i-blog.csdnimg.cn/blog_migrate/48fd4cae61ec039b16c0e30bfe476fb6.gif)

##### 2.5 伪元素选择器

-   :first-letter 为第一个字符的样式
-   :first-line 为第一行添加样式
-   :before 在元素内容的最前面添加的内容，需要配合content属性使用
-   :after 在元素内容的最后面添加的内容，需要配合content属性使用

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style>
		p:first-letter{
			color:red;
			font-size:30px;
		}
		p:first-line{
			background:pink;
		}
		p:before{
			content:"嘿嘿";
		}
		p:after{
			content:"哈哈";
		}
	</style>
</head>
<body>
	<p>hello world!</p>
	<hr>
	<p>
		hello world! <br>
		welcome to css!
	</p>
</body>
</html>
```

示例：

![伪元素选择器.png](https://i-blog.csdnimg.cn/blog_migrate/0d7af6d3f43796f72c6813c40028e1e6.png)

#### 3、选择器优先级

##### 3.1 优先级

行内样式>ID选择器>类选择器>标签选择器

原因：首先加载标签选择器,再加载类选择器，然后加载ID选择器，最后加载行内样式

后加载会覆盖先加载的同名样式

##### 3.2 内外部样式加载顺

就近原则

原因：按照书写顺序依次加载，在同优先级的前提下，后加载的会覆盖先加载的同名样式，所以离的越近

越优先

##### 3.3 !important

可以使用!important使某个样式有最高的优先级

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<link rel="stylesheet" type="text/css" href="style/world.css">

	<style>
		div{
			font-size:20px;
		}
		.hello{
			font-weight:bold;
			color:blue;
		}
		#world{
			text-decoration: underline;
			color:green;
		}
		p{
			color:red;
		}
	</style>
</head>
<body>
	<div class="hello" id="world" style="color:#ff7300">CSS从入门到精通</div>
<p>主讲：叽叽</p>
</body>
</html>
```

示例：

![选择器优先级.png](https://i-blog.csdnimg.cn/blog_migrate/a6d89042ab80ad1cc7fdc7c3949bfd85.png)

### 四、常用CSS属性

#### 1.字体属性

设置字体相关的样式

| 属性 | 含义 | 说明 |
| --- | --- | --- |
| font-size | 大小、尺寸 | 可以使用多种单位 |
| font-weight | 粗细 |   |
| font-family | 字体 |   |
| font-style | 样式 |   |
| font | 简写 |   |

##### 1.1 font-size

取值：

-   inherited继承，默认从父标签继承字体大小（默认值），所有CSS属性的默认值都是inherited
-   px像素 pixel
-   %百分比，相对父标签字体大小的百分比
-   em倍数，相对于父标签字体大小的倍数

HTML根元素默认字体的大小为16px,也称为基础字体大小

##### 1.2 font-weight

取值：

-   normal普通（默认）
-   bold粗体
-   自定义400 normal 700 bold

##### 1.3 font-family

要求系统中要安装指定的字体

一般建议写3种字体：首选、其次、备用。以逗号隔开

##### 1.4 font-style

取值：

-   normal普通
-   italic斜体

##### 1.5 font

简写属性：font:font-style|font-weight|font-size|font-family

必须按此顺序书写

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style>
		div{
			font-size: 30px;
		}
		p{
			/*font-size: 20px;*/
			font-size: 80%;
		}
		.hello{
			font-size: 2em;
		}
		body{
			font-size: 62.5%;
		}
		ul li{
			/*font-size: 30px;
			font-weight: bold;
			font-family: 华文行楷,宋体,黑体;
			font-style: italic;*/
			font: italic bold 30px 微软雅黑;
		}
	</style>
</head>
<body>
	<p>
		CSS从入门到精通！
		<span>主讲：叽叽</span>
	</p>
	<span>主讲：叽叽</span>
	<hr>

	<div>
		我的DIV
		<p>
			CSS从入门到精通
			<span>主讲：叽叽</span>
		</p>
	</div>
	<hr>

	<span class="hello">主讲：叽叽</span>
	<hr>

	<ul>
		<li>
			嘿嘿
		</li>
	</ul>
</body>
</html>
```

示例：

![字体属性.jpg](https://i-blog.csdnimg.cn/blog_migrate/9b01aeccbb136b5f396c018c8381093c.png)

#### 2.文本属性

| 属性 | 含义 | 说明 |
| --- | --- | --- |
| color | 颜色 |   |
| line-height | 行高 | 行之间的高度 |
| text-align | 水平对齐方式 | 取值：left、center、right |
| vertical-align | 垂直对齐方式 | 取值：top、middle、bottom可以用于图片和文字的对齐方式 |
| text-indent | 首行缩进 |   |
| text-decoration | 文本修饰 | 取值：underline、overline、line-through |
| text-transform | 字母大小写转换 | 取值：lowercase、uppercase、capitalize首字母大写 |
| letter-spacing | 字符间距 |   |
| word-spacing | 单词间距 | 只对英文有效 |
| white-space | 空白的处理方式 | 文本超出后是否换行，取值：nowrap |

##### 2.1 color

取值，四种写法：

-   颜色名称：使用英文单词
    
-   16进制的RGB值：#RRGGBB
    
-   特定情况下可以缩写
    
    ```html
    #FFFFFF--->#FFF 白色 
    #000000--->#000 黑色 
    #FF0000--->#F00 红色 
    #00FF00--->#0F0 绿色 
    #0000FF--->#00F 蓝色 
    #CCCCCC--->#CCC 灰色 
    #FF7300--->无法简写
    ```
    
    注意:不区分大小写
    
-   rgb函数：rgb(red,green,blue)
    
    每种颜色的取值范围，\[0,255\]
    
    ```html
    rgb(255,0,0)----->红 
    rgb(0,255,0)----->绿 
    rgb(0,0,255)----->蓝
    ```
    
-   rgba函数：rbga(red,green,blue,alpha)
    
    可以设置透明度，alpha取值范围：\[0,1\] 0表示完全透明 1表示完全不透明
    
    ```html
    rgba(255,0,0,1)----->纯红 
    rgba(255,0,0,0.5)---->红色半透明
    ```
    

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style>
		p{
			color: red;
			/*background-color: #ccc;*/
			/*background-color: rgba(0,255,0,0.5);*/
			background-color: rgba(0, 237, 255, 0.5);
			line-height: 50px;
			text-align: center;
		}
		img{
			vertical-align: middle;
		}
		div{
			text-indent: 30px;
		}
		span{
			font-size: 30px;
			text-decoration: underline;
			text-transform: capitalize;
			letter-spacing: 10px;
			world-spacing:;
		}
		h3{
			width: 300px;
			height: 200px;
			background-color:#ccc;
			white-space: nowrap;
			overflow:hidden;
		}
	</style>
</head>
<body>
	<p>welcome to css!</p>
	<p>welcome to css!</p>
	<p>welcome to css!</p>
	<hr>

	<img src="../qq.png" alt="" width="15%">
	HTML和CSS很简单吗？
	<hr>


	<div>&nbsp;&nbsp;welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS</div>
	<hr>
	<div>welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS</div>
	<hr>

	<span>hello world</span>
	<hr>

	<h3>welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS welcome to CSS</h3>
	<hr>
</body>
</html>
```

示例：

![文本属性.jpg](https://i-blog.csdnimg.cn/blog_migrate/f782a19f8f18374a8d69d1bc5f416311.png)

#### 3.背景属性

| 属性 | 含义 | 说明 |
| --- | --- | --- |
| background-color | 背景颜色 |   |
| background-image | 背景图片 |   |
| background-repeat | 背景图片的重复方式 |   |
| background-position | 背景图片的显示位置 |   |
| background-attachment | 背景图片是否跟随滚动 |   |
| background | 简写 |   |

##### 3.1 background-color

取值：transparent 透明

##### 3.2 background-image

-   必须使用url()方式指定图片的路径
-   如果是在css样式文件中使用相对路径，此时是相对于css文件，不是相对html文件

##### 3.3 background-repeat

取值：repeat(默认)，repeat-x，repeat-y,no-repeat

##### 3.4 background-position

默认背景图显示在左上角

取值：

-   关键字：top、bottom、left、right、center
-   坐标：左上角为(0,0)坐标，向右为x正方向,向下为y正方向

CSS雪碧图，即CSS Sprites,也称为CSS精灵,一种CSS图像合并技术

含 义：将网页中许多非常小的图标/图片整合到一张大图中，当访问面面时只需要下载一次，可以减少访问

服务器的次数，提高性能

原理：使用background-position进行背景定位，使用坐标精确地定位出背景图片的位置

##### 3.5 background-attachment

取值：scroll(默认)、fixed固定不动

##### 3.6 background

简写属性：background:background-color|background-image|background-repeat|background-position

以空格隔开，书写顺序没有要求

#### 4.列表属性

| 属性 | 含义 | 说明 |
| --- | --- | --- |
| list-style-type | 设置列表前的标记 |   |
| list-style-image | 将图像作为列表前的标记 |   |
| list-style-position | 设置标记的位置 | 取值：outside(默认)、inside |
| list-style | 简写 |   |

##### 4.1 list-style-type

取值：none、disc、circle、square、decimal

此时不再区分有序列表还是无序列表，只要设置列表前的标记就可以了

##### 4.2 list-style

简写属性：list-style:list-style-type|list-style-image|list-style-position

书写顺序没有要求

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style>
/* 		li{
			list-style-type:decimal;
		} */	
		.first{
			list-style-type:circle;
		}
		.second{
			list-style-image:url(../images/male.gif);
		}
		.third{
			list-style-type:circle;
			list-style-position:inside;
		}
		.fourth{
			list-style:circle url(../images/female.gif)inside;
			/* list-style:none; */
		}
		.nav{
			/* list-style:none;
			float:left; */
		}
		.nav li{
			list-style:none;
			float:left;
			width:70px;
		}
	</style>
</head>
<body>
	<ul>
		<li class="first">hello</li>
		<li class="second">hello</li>
		<li class="third">hello</li>
		<li class="fourth">hello</li>
	</ul>
	<hr>
	<nav>
		<ul class="nav">
			<li>新闻</li>
			<li>小说</li>
			<li>艾瑞蒂</li>
			<li>政治</li>
			<li>学习</li>
		</ul>
	</nav>
</body>
</html>
```

示例：

![列表属性.jpg](https://i-blog.csdnimg.cn/blog_migrate/9963c2b1e0b727450e5921ea9bd72680.png)

#### 5.表格属性

border-collapse:表格中相邻的边框是否合并（折叠）为单一边框

取值：separated（默认） collapse

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style>
		table{
			width:500px;
			border:1px solid blue;
			border-collapse:collapse;
		}
		td{
			border:1px solid blue;
		}
	</style>
</head>
<body>
	<!-- table>(tr>td{td$}*5)*4 -->
	<table cellspacing="0px"cellpadding="0px">
		<tr>
			<td>bbb</td>
			<td>aaa</td>
			<td>aaa</td>
			<td>td4</td>
			<td>td5</td>
		</tr>
		<tr>
			<td>aaa</td>
			<td>aaa</td>
			<td>bbb</td>
			<td>td4</td>
			<td>td5</td>
		</tr>
		<tr>
			<td>td1</td>
			<td>td2</td>
			<td>td3</td>
			<td>td4</td>
			<td>td5</td>
		</tr>
		<tr>
			<td>td1</td>
			<td>td2</td>
			<td>td3</td>
			<td>td4</td>
			<td>td5</td>
		</tr>
	</table>
</body>
</html>
```

示例：

![表格属性.jpg](https://i-blog.csdnimg.cn/blog_migrate/09004ff61c045a71e6b99333df7f0307.png)

#### 6.使用LiveReload

可以实现当保存页面文件时实时刷新浏览器

步骤：

1.  在Chrome中安装LiveReload扩展程序
    
    将 `livereload` 解压–>chrome浏览器选择"…"–>更多工具–>扩展程序–>开启“开发者模式”–>加载已解压的扩展程序–>选择文件夹名 `livereload`
    
    提示：“允许”在所有网站上读取和更改留存信息
    
2.  在sublime中安装livereload插件
    
    将"livereload.rar-----sublime中使用"解压到sublime中的插件目录packages/中
    
3.  配置Sublime中的LiveReload插件
    
    preference–>packages settings–>livereload–>settings-default
    
    ```
    { 
    	"enabled_plugins": [ 
    	"SimpleReloadPlugin" 
    	"SimpleRefresh"
    	] 
    }
    ```
    
4.  在浏览器中启用LiveReload
    
    先打开浏览器要访问的页面，然后点击浏览器地址栏右侧的黑色圆圈，当中心的小圆圈变为实心圆时表示已启用
    
5.  在sublime中启用liveReload
    
    按ctrl+shift+P–>搜索livereload,选择enable–>搜索simple reload:选择enable
    

### 五、盒子模型

#### 1.简介

盒子模型是网页布局的基础，将页面中所有元素都看作是一个盒子，盒子都包含以下几个属性：

-   width 宽度
-   height 高度
-   border 边框
-   padding 内边距
-   margin 外边距

#### 2.盒子模型

##### 2.1 border

表示盒子的边框

分为四个方向：

-   上top、右right、下bottom、左left
-   border-top、border-right、border-bottom、border-left

每个边框包含三种样式：

-   border-top-color、border-top-width、border-top-style
-   border-right-color、border-right-width、border-right-style
-   border-bottom-color、border-bottom-width、border-bottom-style
-   border-left-color、border-left-width、border-left-style

样式style的取值：

solid实线、dashed虚线、dotted点线、double双线、inset内嵌的3D线、outset外嵌的3D线

简写，三种方式：

-   按方向简写：
    
    border-top、border-right、border-bottom、border-left
    
    书写顺序：
    
    border-顺序：width style color
    
-   按样式简写：
    
    border-color、border-width、border-style
    
    书写顺序：
    
    border-样式：top right bottom left
    
    必须按顺时针方向书写，同时可以缩写：
    
    -   border-width:2px;--------->四个边框的宽度均为2px
    -   border-width:1px 2px;
    -   border-width:1px 2px 4px;
    
    规则：如果省略，则认为上下一样，左右一样
    
-   终级简写：
    
    如果四个边框样式完全相同，border:width style color;
    

##### 2.2 padding

表示盒子的内边距，即内容与边框之间的距离

同样也分为四个方向，也可以简写（按顺时针方向，默认上下一样，左右一样）

注意：如果上下冲突，则以上为准，如果左右冲突，则以左为准

##### 2.3 margin

表示盒子的外边距，即盒子与盒子之间的距离

同样也分为四个方向，也可以简写（按顺时针方向，默认上下一样，左右一样）

居中对齐：

```html
/* 元素的水平居中 */ 
/* 1.块级元素的水平居中 */ 
    margin:0 auto; 
    /* 提示：块级元素必须指定宽度 */
    /* 2.文本的水平居中 */ 
    text-align:center; 
    /* 3.垂直居中，将height和line-height设置为相同 */ 
    height:100px; 
    line-height:100px;
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style>
		p{
			width:250px;
			background:#ccc;
		}
		.first{
			/* border-top-color:red;
			border-top-width:1px;
			border-top-style:solid;
			border-right-color:blue;
			border-right-width:2px;
			border-right-style:dotted;
			border-bottom-color:green;
			border-bottom-width:4px;
			border-bottom-style:dashed;
			border-left-color:gray;
			border-left-width:6px;
			border-left-style:double; */

			/* border-top:1px solid red;
			border-bottom:2px dashed blue; */
			
			/* border-color:red yellow green;
			border-width:1px 2px 4px 6px;
			border-style:solid dashed dotted solid; */

			border:1px solid red;
			padding:20px;
			margin:10px;
		}
		.second{
			/* padding-top:5px;
			padding-left:3px;
			padding-bottom:10px;
			padding-right:8px; */

			/* padding:1px 2px 4px 6px; */

			padding:5px;
		}
		.third{
			/* margin-top:50px;
			margin-left:30px; */

			/* margin:10px 20px; */

			/* 元素的居中 */
			/* 1.块级元素水平居中 */
			margin:auto;
			/* 2.文本水平居中 */
			text-align:center;
			/* 3.文本垂直居中 将height与line-height设置为相同 */
			height:100px;
			line-height:100px;
		}
	</style>
</head>
<body>
	<p class="first">nihao</p>
	<p class="second">hello</p>
	<p class="third">welcome</p>
</body>
</html>
```

示例：

![盒子模型.png](https://i-blog.csdnimg.cn/blog_migrate/f8867e8627b39a5ade39d7270aba7719.png)

#### 3.其他

##### 3.1 元素所占空间

页面中的元素实际所占的空间

-   宽度=width+左右padding+左右border+左右margin
-   高度=height+上下padding+上下border+上下margin

##### 3.2 盒子属性默认值

不同标签的盒子属性默认值可能不同，需要自己设置

```html
body,ul,ol,dl,li,p,h1,h2,h3,h4,h5,h6,form{
	margin:0; 
	padding:0; 
}
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style>
	/* body默认margin不为0 */
		body{
			margin:0;
			padding:0;
		}
	/* p默认margin不为0 */
		p{
			margin:0;
		}
		ul{
			list-style:none;
			margin:0;
			padding:0;
		}
		body,ul,ol,dl,li,p,h1,h2,h3,h4,h5,h6,form{
			margin:0;
			padding:0;
		}
	</style>
</head>
<body>
	welcome to css!
	<p>hello world</p>
	<!-- ul>li{hello$}*3 -->
	<ul>
		<li>hello1</li>
		<li>hello2</li>
		<li>hello3</li>
	</ul>
</body>
</html>
```

示例：

![盒子模型的默认值.png](https://i-blog.csdnimg.cn/blog_migrate/fdcc16569cb2facf8f41a59c28a755f0.png)

##### 3.3 外边距的合并

也称为外边距的折叠，指的是两个块级元素垂直外边距相遇时，它们将合并为一个外边距，合并后的外边

距值为其中较大的那个外边距值

两种情况：

-   当一个元素出现在另一个元素上面时，第一个元素的下边距与第二元素的上边距会发生合并
-   当一个元素包含在另一个元素中时，并且没有内边距或边框把外边距分隔开时，两个元素的上外边距会发生合并

外边距的合并的好处，让排版在视觉上显得更美观

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style>
		div{
			width:50px;
			height:50px;
			background:#cccccc;
		}
		.div1{
			margin-bottom:20px;
		}
		.div2{
			margin-top:30px;
		}
		.div3{
			width:100px;
			height:100px;
			background:blue;
			margin-top:20px;
			/* padding:2px;
 */			/* border:1px solid red; */
		}
		.div4{
			margin-top:30px;
		}
		p{
			margin:20px 0;
		}
	</style>
</head>
<body>
	<div class="div1">div1</div>
	<div class="div2">div2</div>
	<hr>

	<div class="div3">
		<div class="div4"></div>
	</div>
	<hr>
	<p>p1</p>
	<p>p2</p>
	<p>p3</p>
	<p>p4</p>
	<p>p5</p>
	<p>p6</p>
	<p>p7</p>
</body>
</html>
```

示例：

![外边距的合并.png](https://i-blog.csdnimg.cn/blog_migrate/5609ccdffbcb7d8da1f94d0b7c6fc86f.png)

### 六、定位方式

#### 1.简介

通过position属性实现对元素的定位，有四种定位方式

常用取值：

| 取值 | 含义 | 说明 |
| --- | --- | --- |
| static | 默认值 | 按照常规文档流进行显示 |
| relative | 相对定位 | 相对于标签原来的位置进行的定位 |
| absolute | 绝对定位 | 相对于第一个非static定位的父标签的定位 |
| fixed | 固定定位 | 相对于浏览器窗品进行定位 |

设置定位方式后，还要设置定位属性（偏移量）：top、bottom、left、right

#### 2.相对定位

先设置元素的position属性为relative,然后再设置偏移量

#### 3.绝对定位

先设置父标签为非static定位，然后设置元素的position属性为absolute，最后再设置偏移量

注意：

-   一般来说都会将父标签设置为非static定位
-   如果父标签不是非static定位，则会相对于浏览器窗口进行定位
-   设置元素为绝对定位后，元素会浮到页面上方

#### 4.固定定位

先设置元素的position属性为fixed，然后再设置偏移量

设置元素为固定定位后，元素会浮动在面面上方

#### 5.z-index

设置元素定位方式后，元素会浮在页面上方，此时可以通过z-index属性设置优先级，控制元素的堆叠顺序

取值为数字，值越大优先级越高，默认为auto(大多数浏览器默认为0)

注意：只能给非static定位的元素设置z-index属性

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style>
		#container{
			width:800px;
			border:1px solid #000000;
			position:relative;
		}
		.div1,.div2,.div3,.div4{
			width:100px;
			height:50px;
		}
		.div1{
			background:red;
			position:relative;/* 相对定位 */
			top:20px;
			left:50px;
			z-index:-5;
		}
		.div2{
			background:blue;
			position:absolute;
			left:100px;
			bottom:50px;
			z-index:-8;
		}
		.div3{
			background:green;
			position:fixed;
			bottom:50px;
			left:100px;
		}
		.div4{
			background:cyan;
		}
	</style>
</head>
<body>
	<div id="container">
		<div class="div1">div1</div>
		<div class="div2">div2</div>
		<div class="div3">div3</div>
		<div class="div4">div4</div>
	</div>
</body>
</html>
```

示例：

![定位方式.png](https://i-blog.csdnimg.cn/blog_migrate/1bb0caef75fd49db21e77e1f850879ff.png)

### 七、其他CSS属性

#### 1.浮动和清除

##### 1.1 浮动属性

通过float属性来实现元素的浮动，可以让块级元素脱离常规的文档流，向左或向右移动，在同一行显示，

如果一行显示不下，则会换行显示

常用取值：

-   left左浮动
-   right右浮动
-   none不浮动，默认值

设置float属性后，元素会浮在页面上层，此时父容器无法计算自己尺寸，如果我们还想显示父容器通常会在末尾添加一个清除了float属性的空的div来解决

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style>
		#container{
			/* width:800px; */
			border:1px solid #000000;
		}
		.div1,.div2,.div3,.div4{
			width:100px;
			height:50px;
		}
		.div1{
			background:red;
			float:left;
		}
		.div2{
			background:blue;
			float:left;
		}
		.div3{
			background:green;
			float:left;
		}
		.div4{
			background:cyan;
			float:left;
		}
		.clr{
			clear:left;
		}
	</style>
</head>
<body>
	<div id="container">
		<div class="div1">div1</div>
		<div class="div2">div2</div>
		<div class="div3">div3</div>
		<div class="div4">div4</div>
		<div class="clr"></div>
	</div>
	aaa
</body>
</html>
```

示例：

![其他css属性.png](https://i-blog.csdnimg.cn/blog_migrate/39e3dd2d1f9a4428d637a3b42d0aad56.png)

##### 1.2 清除属性

通过clear属性来实现清除，设置元素的哪一侧不允许有浮动元素

常用取值：

-   left左侧不允许出现浮动元素
-   right右侧不允许出现浮动元素
-   both两侧不允许出现浮动元素
-   none允许两侧出现浮动元素，默值

结论：

-   对于非浮动元素，两边都可以设置清除（常用）
-   对于浮动元素，向哪边浮动，就只能设置哪边的清除

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style>
		body{
			margin:0;
			padding:0;
		}
		#container{
			width:660px;
			margin:0 auto;
			border:2px solid #0f0;
		}
		.div1,.div2,.div3,.div4{
			width:200px;
			height:180px;
			float:left;
			margin:5px;
			border:5px outset #ff7300;
			padding:10px;
		}
		#container img{
			width:100%;
			height:100%;
		}
		.clr{
			clear:left;
		}
	</style>
</head>
<body>
	<div id="container">
	<div class="div1"><img src="../images/adv1.jpg" alt=""></div>
	<div class="div2"><img src="../images/adv2.jpg" alt=""></div>
	<div class="div3"><img src="../images/adv3.jpg" alt=""></div>
	<div class="div4"><img src="../images/adv4.jpg" alt=""></div>
	<div class="clr"></div>
	</div>
	<p>welcome to css</p>
</body>
</html>
```

示例：

![练习.png](https://i-blog.csdnimg.cn/blog_migrate/823a86b1e2b760d584843df96bea9f11.png)

#### 2.元素的显示和隐藏

##### 2.1 display

通过display属性设置元素是否显示，以及是否独占一行

常用取值：

| 取值 | 含义 | 说明 |
| --- | --- | --- |
| none | 不显示 |   |
| inline | 显示为内联元素，行级元素的默认值 | 将块级元素变为行级元素，不再独占一行 |
| block | 显示为块级元素，块级元素的默认值 | 将行级元素变为块级元素，独占一行 |
| inline-block | 显示为内联元素，但是可以设置宽和高 | 在inline基础上允许设置宽度和高度 |

注意：

行级元素是无法设置宽度和高度的，可以为行级元素设置 `display:inline-block` ,然后就可以设置宽和高了

##### 2.2 visibility

也可以通过visibility属性设置元素的显示和隐藏

常用属性：

| 取值 | 含义 | 说明 |
| --- | --- | --- |
| visible | 显示 |   |
| hidden | 隐藏 |   |

##### 2.3 区别

-   display隐藏时不再占据页面中的空间，后面的元素会占用其位置
    
-   visibility隐藏时会占据页面中的空间，位置还保留在页面中，只是不显示
    

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style>
		.div1{
			width: 100px;
			height: 100px;
			background:blue;
			display:inline;
		}
		span{
			width: 100px;
			height: 50px;
			background:yellow;
			display:inline-block;
		}
		i{
			display:block;
			width: 100px;
			height: 50px;
			background:red;
		}
		p{
			width: 50px;
			height: 50px;
			background:red;
		}
		.p1{
			visibility:hidden;
		}
		.login{
			display:inline-block;
			width: 100px;
			text-decoration:none;
			background:rgba(255, 0, 0, 0.7);
			color:#fff;
			padding:10px;
			text-align:center;
			border-radius:10px;
		}
		.login:hover{
			background:rgba(255, 0, 0, 0.5);
		}
	</style>
</head>
<body>
	<div class="div1">div1</div>
	<span>span1</span>
	<i>呵呵</i>
	<hr>
	<p class="p1">hello</p>
	<p class="p2">world</p>
	<hr>
	<a href="javascript:alert('欢迎光临')" class="login">登&nbsp;&nbsp;&nbsp;&nbsp;录</a>
</body>
</html>
```

示例：

![元素的显示和隐藏.png](https://i-blog.csdnimg.cn/blog_migrate/73f02358c84d10e53b393a4f6870130e.png)

#### 3.轮廓属性

##### 3.1 简介

轮廓outline,用于在元素周围绘制一个轮廓，位于border外围，可以突出显示元素

##### 3.2 基本用法

常用属性:

-   outline-width:轮廓宽度
-   outline-color:轮廓颜色
-   outline-style:轮廓样式
-   outline简写

在浏览器中，当鼠标单击或使用TAB键让一个表单或链接获得焦点时，该元素会有一个轮廓outline

优点：可以提高使用表单的用户体验

缺点：有时会影响美观

##### 3.3 outline和border的区别

-   border可以应用于所有html元素，而outline主要用于表单元素、超链接元素
-   当元素获得焦点时会自动出现outline轮廓效果，当失去焦点时会自动消失，这是浏览器默认行为
-   outline不影响元素的尺寸和位置，而border会影响

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style>
		span{
			border:2px solid red;
			outline:4px dashed green;
		}
		.username{
			border:1px solid red;
			outline:none;
			padding-left:3px;
			width:80px;
		}
		.email{
			border:0;
			outline:0;
			border-bottom:1px solid #000;
		}
		.btnsubmit{
			border:0;
			padding:5px;
			width:100px;
		}
		.mydiv{
			width:100px;
			background:#ccc;
			border:2px solid red;
		}
	</style>
</head>
<body>
	<span>welcome to CSS</span>
	<hr>
	用户名：<input type="text" class="username">
	<a href="#">CSS</a>
	<hr>
	邮箱：<input type="text" class="email">
	<input type="submit" value="提交" class="btnsubmit">
	<hr>
	<div class="mydiv">div</div>
</body>
</html>
```

示例：

![轮廓属性.png](https://i-blog.csdnimg.cn/blog_migrate/578d2269bc6319455243f879dc738056.png)

#### 4.其他属性

##### 4.1 宽高相关

-   max-width:设置元素的最大宽度
-   max-height:设置元素的最大高度
-   min-width设置元素的最小宽度
-   min-height设置元素的最小高度

##### 4.2 overflow属性

当元素内容溢出时该如何处理

常用取值：

-   visible溢出时可见，显示在元素外，默认值
-   hidden溢出的部分不可见（常用）
-   scroll无论是否出现溢出始终出现滚动条
-   auto溢出时自动出现滚动条

##### 4.3 cursor属性

用于设置光标的形状

常用属性：

-   default默认光标，一般为箭头
-   pointer手形，光标移动超链接上时一般显示为手形
-   move表示可移动
-   text表示文 本
-   wait表示程序正忙，需要等待
-   hep表示帮助

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style>
		p{
			border:1px solid red;
			min-width:500px;
		}
		div{
			border:1px solid blue;
			width: 300px;
			height: 100px;
			overflow:auto;
		}
		span{
			cursor:help;
		}
	</style>
</head>
<body>
	<p>
		welcome to css welcome to css welcome to css welcome to css
		welcome to css welcome to css welcome to css welcome to css
		welcome to css welcome to css welcome to css welcome to css
		welcome to css welcome to css welcome to css welcome to css
	</p>
	<hr>
	<div>
		welcome to css welcome to css welcome to css welcome to css
		welcome to css welcome to css welcome to css welcome to css
		welcome to css welcome to css welcome to css welcome to css
		welcome to css welcome to css welcome to css welcome to css
	</div>
	<hr>
	<span>光标形状</span>
</body>
</html>
```

示例：

![其他属性.png](https://i-blog.csdnimg.cn/blog_migrate/acfe03b996a4111ef884a34abb834604.png)

### 八、页面布局

#### 1.简介

常见页面布局：

-   表格布局
-   div布局

#### 2.表格布局

##### 2.1 简介

不适用于复杂布局，仅用于简单 、有规则的结构

定位相对准确，与浏览器基本无关，适用于简单分隔

##### 2.2 用法

table常用样式的属性

-   border在表格外围设置边框
-   border-spacing设置单元格之间的距离（相当于table标签中的cellspacing属性，即间距）
-   border-collapse表格中相邻边框是否合并，取值：seprate、collapse

th/td常用样式属性：

-   border为单元格设置边框
-   padding设置单元格的内边距（相当于table标签中的cellpadding属性，边距）

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style>
		.hello{
			width: 80%;
			border:1px solid #ccc;
			border-spacing:0;
			border-collapse:collapse;
		}
		.hello th,.hello td{
			border:1px solid #ccc;
			padding:5px;
		}
	</style>
</head>
<body>
	 <!-- table>(thead>tr>th{th$}*4)+tbody>(tr>td{td$}*4)*6 -->
	 <table>
	 	<thead>
	 		<tr>
	 			<th>th1</th>
	 			<th>th2</th>
	 			<th>th3</th>
	 			<th>th4</th>
	 		</tr>
	 	</thead>
	 	<tbody>
	 		<tr>
	 			<td>td1</td>
	 			<td>td2</td>
	 			<td>td3</td>
	 			<td>td4</td>
	 		</tr>
	 		<tr>
	 			<td>td1</td>
	 			<td>td2</td>
	 			<td>td3</td>
	 			<td>td4</td>
	 		</tr>
	 		<tr>
	 			<td>td1</td>
	 			<td>td2</td>
	 			<td>td3</td>
	 			<td>td4</td>
	 		</tr>
	 		<tr>
	 			<td>td1</td>
	 			<td>td2</td>
	 			<td>td3</td>
	 			<td>td4</td>
	 		</tr>
	 		<tr>
	 			<td>td1</td>
	 			<td>td2</td>
	 			<td>td3</td>
	 			<td>td4</td>
	 		</tr>
	 		<tr>
	 			<td>td1</td>
	 			<td>td2</td>
	 			<td>td3</td>
	 			<td>td4</td>
	 		</tr>
	 	</tbody>
	 </table>
</body>
</html>
```

示例：

![表格布局.png](https://i-blog.csdnimg.cn/blog_migrate/893b3687251f5989f570881eefda202f.png)

#### 3.div布局

定位绝对精确，使用灵活，适合于复杂的布局方式

##### 3.1 简单布局

两种形式：

-   1-1-1布局
    
    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
    	<meta charset="UTF-8">
    	<title>Document</title>
    	<link rel="stylesheet" href="css/style1.css">
    </head>
    <body>
    	<div id="container">
    		<header class="header">
    			header
    		</header>
    		<article class="main">
    			main
    		</article>
    		<footer class="footer">
    			footer
    		</footer>
    	</div>
    </body>
    </html>
    ```
    
    示例：
    
    ![简单布局1.png](https://i-blog.csdnimg.cn/blog_migrate/2082fddddb2437c972098600f74c2b10.png)
    
-   1-2/ 3-1布局
    
    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
    	<meta charset="UTF-8">
    	<title>Document</title>
    	 <link rel="stylesheet" href="css/style2.css"> 
    </head>
    <body>
    	<div id="container">
    		<header class="header">
    			herder
    		</header>
    		<article class="wrapper">
    			<section>
    				main
    			</section>
    			<aside>
    				right aside
    			</aside>
    		</article>
    		<footer class="footer">
    			footer
    		</footer>
    	</div>
    </body>
    </html>
    ```
    
    示例：
    
    ![简单布局2.png](https://i-blog.csdnimg.cn/blog_migrate/cf6592a309701f4a19247b6e5cd5e1a6.png)
    

##### 3.2 圣杯布局

页面结构，两边的边栏宽度固定，中间主体在一定范围内可自适应，并且主体优先被加载

一般防止页面缩放影响浏览，都会为页面设置一个最小宽度

```html
<!DOCTYPE html>
<html lang="en"> 
<head>
	<meta charset="UTF-8"> 
	<title>Document</title> 
	<link rel="stylesheet" href="css/style4.css"> 
</head> 
<body>
	<div id="container">
		<header class="header"> 
            header 
        </header> 
		<article class="wrapper"> 
			<section class="main">
				main
			</section>
			<aside class="left"> 
				left
			</aside>  
			<aside class="right"> 
				right
			</aside> 
		</article>
		<footer class="footer"> 
            footer 
        </footer>  
    </div>
</body> 
</html>
```

示例：

![双飞翼布局.png](https://i-blog.csdnimg.cn/blog_migrate/20c06a3e8d4bbe8a783745704fb72893.png)

##### 3.3 双飞翼布局

源自淘宝的UED(用户体验设计)团队

双飞翼布局和圣杯布局要实现的效果是相同的，只是思路不同

圣杯布局和双飞翼布局的区别

双飞翼布局比圣杯布局多创建一个div

双飞翼布局不用设置内边距和相对定位，也不用设置偏移量

双飞翼布局使用的margin,圣杯布局使用的是padding

实际开发中建议使用CSS3中新增的flex弹性盒子布局，更简间

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
    <title>Document</title> 
    <link rel="stylesheet" href="css/style5.css">
</head>
<body>
    <div id="container">
        <header class="header">
            header 
        </header> 
        <article class="wrapper">
            <section class="main">
                <div class="main-wrapper">
                    main 
                </div> 
            </section>
            <aside class="left">
                left aside
            </aside>
            <aside class="right">
                right aside 
            </aside>
        </article>
        <footer class="footer">
            footer 
        </footer> 
    </div>
    </body>
</html>
```

示例：

![双飞翼布局.png](https://i-blog.csdnimg.cn/blog_migrate/78afcafd7a53643661e2d31ef3cb2f86.png)  
附件：[https://share.weiyun.com/t8QMk1kx](https://share.weiyun.com/t8QMk1kx)