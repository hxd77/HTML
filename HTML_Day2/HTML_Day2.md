
# HTML标签（下）

## 1. 表格
表格是实际开发中非常常用的标签:  
1. 表格的主要作用 
2. 表格的基本语法 

### 1.1 表格的主要作用

表格主要用于显示、展示数据，因为它可以让数据显示的非常的规整，可读性非常好。特别是后台展示数据 的时候，能够熟练运用表格就显得很重要。一个清爽简约的表格能够把繁杂的数据表现得很有条理。 

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <table>
        <tr> <td>支出项目</td> <td>单价（元）</td> <td>数目</td> <td>金额（元）</td></tr>
        <tr> <td>垃圾箱</td> <td>30</td> <td>12</td> <td>360</td></tr>
        <tr> <td>垃圾牌</td> <td>100</td> <td>12</td> <td>1200</td></tr>
        <tr> <td>宣传单</td> <td>0.08（元）</td> <td>400</td> <td>32</td></tr>
        <tr> <td>宣传小册子</td> <td>3</td> <td>250</td> <td>750</td></tr>
        <tr> <td>合计</td> <td>--</td> <td>--</td> <td>2342</td></tr>
    </table>
</body>
</html>



   ### 1.2 表格的基本用法


```html
<table> 
	<tr> 
		<td>单元格内的文字</td> 
		... 
	</tr> 
	... 
</table>
```

1. `<table> </table> `是用于定义表格的标签。 
2. `<tr> </tr>` 标签用于定义表格中的行，必须嵌套在 `<table> </table>`标签中。 
3. `<td> </td>` 用于定义表格中的单元格，必须嵌套在`<tr></tr>`标签中。 
4. 字母 td 指表格数据（table data），即数据单元格的内容。



### 1.3 表头单元格标签

一般表头单元格位于表格的第一行或第一列，表头单元格里面的文本内容加粗居中显示.  

`<th>`标签表示 HTML 表格的表头部分(table head 的缩写)

```html
<table> 
	<tr> 
		<th>姓名</th> 
		... 
	</tr> 
	... 
</table> 
```

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <table>
        <tr><th>姓名</th><th>性别</th><th>电话</th></tr>
        <tr><td>小王</td><td>女</td><td>110</td></tr>
        <tr><td>姓名</td><td>男</td><td>120</td></tr>
    </table>
</body>
</html>



### 1.4 表格属性

表格标签这部分属性我们实际开发我们不常用，后面通过 CSS 来设置.  

目的有2个:    

1. 记住这些英语单词,后面 CSS 会使用.  
2. 直观感受表格的外观形态.

![表格属性](https://cdn.jsdelivr.net/gh/hxd77/BlogImage/Blog/%E8%A1%A8%E6%A0%BC%E5%B1%9E%E6%80%A7.png)

**案例1：小说排行榜**

![image-20250729190109792](https://cdn.jsdelivr.net/gh/hxd77/BlogImage/Blog/image-20250729190109792.png)

先制作表格的结构.    

1. 第一行里面是 th 表头单元格  

2. 第二行开始里面是 td 普通单元格 

3. 单元格里面可以放任何元素,文字链接图片等都可以  

后书写表格属性.  

1. 用到宽度高度边框cellpadding 和 cellspacing  
2.  表格浏览器中对齐 align    

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <table align="center" width="500" height="249" border="1" cellspacing="0">
        <tr>
            <th>排名</th>
            <th>关键词</th>
            <th>趋势</th>
            <th>今日搜索</th>
            <th>最近七日</th>
            <th>相关链接</th>
        </tr>
        <tr>
            <td>1</td>
            <td>鬼吹灯</td>
            <td><img src="https://cdn.jsdelivr.net/gh/hxd77/BlogImage/Blog/down.jpg"></td>
            <td>345</td>
            <td>123</td>
            <td><a href="#">贴吧</a> <a href="#">图片</a> <a href="#">百科</a></td>
        </tr>
        <tr>
            <td>2</td>
            <td>盗墓笔记</td>
            <td><img src="https://cdn.jsdelivr.net/gh/hxd77/BlogImage/Blog/down.jpg"></td>
            <td>124</td>
            <td>675432</td>
            <td><a href="#">贴吧 </a> <a href="#">图片</a> <a href="#">百科</a></td>
        </tr>
        <tr>
            <td>3</td>
            <td>西游记</td>
            <td><img src="https://cdn.jsdelivr.net/gh/hxd77/BlogImage/Blog/up.jpg"></td>
            <td>212</td>
            <td>7654</td>
            <td><a href="#">贴吧</a> <a href="#">图片</a> <a href="#">百科</a></td>
        </tr>
        <tr>
            <td>4</td>
            <td>东游记</td>
            <td><img src="https://cdn.jsdelivr.net/gh/hxd77/BlogImage/Blog/up.jpg"></td>
            <td>23</td>
            <td>75645</td>
            <td><a href="#">贴吧</a> <a href="#">图片</a> <a href="#">百科</a></td>
        </tr> 
        <tr>
            <td>5</td>
            <td>甄嬛传</td>
            <td><img src="https://cdn.jsdelivr.net/gh/hxd77/BlogImage/Blog/down.jpg"></td>
            <td>121</td>
            <td>7676</td>
            <td><a href="#">贴吧</a> <a href="#">图片</a> <a href="#">百科</a></td>
        </tr> 
        <tr>
            <td>6</td>
            <td>水浒传</td>
            <td><img src="https://cdn.jsdelivr.net/gh/hxd77/BlogImage/Blog/up.jpg"></td>
            <td>576576</td>
            <td>1231421</td>
            <td><a href="#">贴吧</a> <a href="#">图片</a> <a href="#">百科</a></td>
        </tr> 
        <tr>
            <td>7</td>
            <td>三国演义</td>
            <td><img src="https://cdn.jsdelivr.net/gh/hxd77/BlogImage/Blog/up.jpg"></td>
            <td>234</td>
            <td>7686</td>
            <td><a href="#">贴吧</a> <a href="#">图片</a> <a href="#">百科</a></td>
        </tr>     
    </table>
</body>
</html>



### 1.5 表格结构标签

使用场景:因为表格可能很长,为了更好的表示表格的语义，可以将表格分割成 表格头部和表格主体两大部分. 
在表格标签中，分别用：`<thead>`标签 表格的头部区域、`<tbody>`标签 表格的主体区域. 这样可以更好的分清表格结构。

![表格结构标签](https://cdn.jsdelivr.net/gh/hxd77/BlogImage/Blog/%E8%A1%A8%E6%A0%BC%E7%BB%93%E6%9E%84%E6%A0%87%E7%AD%BE.png)

1. `<thead></thead>`：用于定义表格的头部。`<thead>` 内部必须拥有 `<tr>` 标签。 一般是位于第一行。 
2. `<tbody></tbody>`：用于定义表格的主体，主要用于放数据本体 。 
3.  以上标签都是放在 `<table></table>` 标签中。

### 1.6 合并单元格

特殊情况下,可以把多个单元格合并为一个单元格,  这里同学们会最简单的合并单元格即可.  

1. 合并单元格方式 
2. 目标单元格 
3. 合并单元格的步骤

![合并单元格](https://cdn.jsdelivr.net/gh/hxd77/BlogImage/Blog/%E5%90%88%E5%B9%B6%E5%8D%95%E5%85%83%E6%A0%BC.png)

**合并单元格方式：**

+ 跨行合并：rowspan="合并单元格的个数"        
+ 跨列合并：colspan="合并单元格的个数"

![image-20250729201451078](https://cdn.jsdelivr.net/gh/hxd77/BlogImage/Blog/image-20250729201451078.png)

**目标单元格：(写合并代码)**  

+ 跨行：最上侧单元格为目标单元格, 写合并代码
+ 跨列：最左侧单元格为目标单元格, 写合并代码

![image-20250729201654331](https://cdn.jsdelivr.net/gh/hxd77/BlogImage/Blog/image-20250729201654331.png)

**合并单元格三步曲：** 

1. 先确定是跨行还是跨列合并。 
2. 找到目标单元格. 写上合并方式 = 合并的单元格数量。比如：`<td colspan="2"></td>`。 
3. 删除多余的单元格。



<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>合并单元格</title>
</head>
<body>
    <table width="500" height="249" border="1" cellspacing="0">
        <tr>
            <td ></td>
            <td colspan="2"></td> 
            <!-- 合并列 -->
             </tr>
    <tr>
        <td rowspan="2""></td>
        <!-- 合并行 -->
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td "></td>
        <td></td>
    </tr>
</table>
 </body>
</html>



### 1.7 表格总结

1. 表格的相关标签

​	我们学习了table 标签  tr 行 标签  td 单元格 标签    th 表头单元格 标签   thead 表格头部区域标签 

![image-20250729203055182](https://cdn.jsdelivr.net/gh/hxd77/BlogImage/Blog/image-20250729203055182.png)

2. 表格的相关属性

![](https://cdn.jsdelivr.net/gh/hxd77/BlogImage/Blog/%E8%A1%A8%E6%A0%BC%E5%B1%9E%E6%80%A7.png)

3. 合并单元格

![image-20250729203340412](https://cdn.jsdelivr.net/gh/hxd77/BlogImage/Blog/image-20250729203340412.png)

## 2. 列表标签

表格是用来显示数据的，那么列表就是用来布局的。   

列表最大的特点就是整齐、整洁、有序，它作为布局会更加自由和方便。  

根据使用情景不同，列表可以分为三大类：无序列表、有序列表和自定义列表。

![image-20250729203431491](https://cdn.jsdelivr.net/gh/hxd77/BlogImage/Blog/image-20250729203431491.png)

### 2.1 无序列表（重点）

`<ul>` 标签表示 HTML 页面中项目的无序列表，一般会以项目符号呈现列表项，而列表项使用 `<li>` 标签定义。 
无序列表的基本语法格式如下： 

```html
<ul> 
	<li>列表项1</li> 
	<li>列表项2</li> 
	<li>列表项3</li> 
	... 
</ul>
```

1. 无序列表的各个列表项之间没有顺序级别之分，是并列的。 
2. `<ul></ul>` 中只能嵌套 `<li></li>`，直接在` <ul></ul>` 标签中输入其他标签或者文字的做法是不被允许的。 
3. `<li>` 与 `</li>` 之间相当于一个容器，可以容纳所有元素。 
4. 无序列表会带有自己的样式属性，但在实际使用时，我们会使用 CSS 来设置。

例子如下：

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>无序列表</title>
</head>
<body>
    <h4>您喜欢的食物?</h4>
    <ul>
        <li>榴莲</li>
        <li>臭豆腐</li>
        <li>鲱鱼罐头</li>
        <li>
            <p>123</p>
        </li>
    </ul>
</body>
</html>



### 2.3 有序列表（理解）

有序列表即为有排列顺序的列表，其各个列表项会按照一定的顺序排列定义。 
在 HTML 标签中，`<ol>` 标签用于定义有序列表，列表排序以数字来显示，并且使用 `<li>` 标签来定义列表项。 
有序列表的基本语法格式如下：

```html
<ol> 
	<li>列表项1</li> 
	<li>列表项2</li> 
	<li>列表项3</li> 
	... 
</ol>
```
1. `<ol></ol>`中只能嵌套`<li></li>`，直接在`<ol></ol>`标签中输入其他标签或者文字的做法是不被允许的。 
2. `<li> 与 </li>`之间相当于一个容器，可以容纳所有元素。 
3. 有序列表会带有自己样式属性，但在实际使用时，我们会使用 CSS 来设置。

例子如下：

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>有序列表(理解)</title>
</head>
<body>
    <h4>粉丝排行榜</h4>
    <ol>
        <li>刘德华 10000</li>
        <li>刘若英 1000</li>
        <li>pink老师 1</li>
    </ol>
</body>
</html>



### 2.3 自定义列表（重点）

自定义列表的使用场景:  

自定义列表常用于对术语或名词进行解释和描述，定义列表的列表项前没有任何项目符号。

![image-20250729204519861](https://cdn.jsdelivr.net/gh/hxd77/BlogImage/Blog/image-20250729204519861.png)

在 HTML 标签中，`<dl>` 标签用于定义描述列表（或定义列表），该标签会与 `<dt>`（定义项目/名字）和 `<dd>`（描述每一个项目/名字）一起使用。 
其基本语法如下：

```html
<dl> 
	<dt>名词1</dt> 
	<dd>名词1解释1</dd> 
	<dd>名词1解释2</dd> 
</dl>
```
1. `<dl></dl>` 里面只能包含 `<dt>` 和 `<dd>`。 
2. `<dt>` 和 `<dd>`个数没有限制，经常是一个`<dt>` 对应多个`<dd>`。
3. `<dt>`和`<dd>`是并列关系

例子如下：

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>自定义列表(重点)</title>
</head>
<body>
    <dl>
        <dt>关注我们</dt>
        <dd>新浪微博</dd>
        <dd>官方微信</dd>
        <dd>联系我们</dd>
        <dt>关注我们</dt>
        <dd>新浪微博</dd>
        <dd>官方微信</dd>
        <dd>联系我们</dd>
    </dl>
</body>
</html>

![皇上](https://cdn.jsdelivr.net/gh/hxd77/BlogImage/Blog/%E7%9A%87%E4%B8%8A.png)



### 2.4 列表总结

![列表总结](https://cdn.jsdelivr.net/gh/hxd77/BlogImage/Blog/%E5%88%97%E8%A1%A8%E6%80%BB%E7%BB%93.png)
**注意：** 

1. 学会什么时候用无序列表， 什么时候用自定义列表。 
2. 无序列表和自定义列表代码怎么写？ 
3. 列表布局在学习完 CSS 后再来完成。



## 3. 表单标签

现实中的表单，我们去银行办理信用卡填写的单子。 

![image-20250729205318269](https://cdn.jsdelivr.net/gh/hxd77/BlogImage/Blog/image-20250729205318269.png)

网页中的表单展示

![表单](https://cdn.jsdelivr.net/gh/hxd77/BlogImage/Blog/%E8%A1%A8%E5%8D%95.png)

网页中的表单展示  

1. 为什么需要表单  
2. 表单的组成



### 3.1 为什么需要表单

使用表单目的是为了收集用户信息。  

在我们网页中， 我们也需要跟用户进行交互，收集用户资料，此时就需要表单。



### 3.2 表单的组成

在 HTML 中，一个完整的表单通常由表单域、表单控件（也称为表单元素）和 提示信息3个部分构成。

![image-20250729205518407](https://cdn.jsdelivr.net/gh/hxd77/BlogImage/Blog/image-20250729205518407.png)

### 3.3 表单域

表单域是一个包含表单元素的区域。 
在 HTML 标签中， `<form>` 标签用于定义表单域，以实现用户信息的收集和传递。 
`<form>` 会把它范围内的表单元素信息提交给服务器.

```html
<form action=“url地址” method=“提交方式” name=“表单域名称"> 
	各种表单元素控件 
</form>
```

![表单常用属性](https://cdn.jsdelivr.net/gh/hxd77/BlogImage/Blog/%E8%A1%A8%E5%8D%95%E5%B8%B8%E7%94%A8%E5%B1%9E%E6%80%A7.png)

这里只需要记住两点:  

1. 在我们写表单元素之前,应该有个表单域把他们进行包含. 
2. 表单域是 form标签.

### 3.4 表单控件（表单元素）

在表单域中可以定义各种表单元素，这些表单元素就是允许用户在表单中输入或者选择的内容控件。  接下来我们学习:  

1. input输入表单元素 
1. select下拉表单元素 
1. textarea 文本域元素



#### 3.4.1 `<input>`表单元素
在英文单词中，input 是输入的意思，而在表单元素中 `<input>` 标签用于收集用户信息。 
在 `<input>` 标签中，包含一个 type 属性，根据不同的 type 属性值，输入字段拥有很多种形式（可以是文本字段、复选框、掩码后的文本控件、单选按钮、按钮等）。 

```html
<input type="属性值"  />
```

+ `<input>` 标签为单标签 
+ type 属性设置不同的属性值用来指定不同的控件类型

type 属性的属性值及其描述如下：

![表单标签](https://cdn.jsdelivr.net/gh/hxd77/BlogImage/Blog/%E8%A1%A8%E5%8D%95%E6%A0%87%E7%AD%BE.png)

除 type 属性外，`<input>`标签还有其他很多属性，其常用属性如下：

![表单其他属性](https://cdn.jsdelivr.net/gh/hxd77/BlogImage/Blog/%E8%A1%A8%E5%8D%95%E5%85%B6%E4%BB%96%E5%B1%9E%E6%80%A7.png)
1. name 和value 是每个表单元素都有的属性值,主要给后台人员使用. 
2. name 表单元素的名字, 要求 单选按钮和复选框要有相同的name值. 
3. checked属性主要针对于单选按钮和复选框, 主要作用一打开页面,就要可以默认选中某个表单元素. 
4. maxlength 是用户可以在表单元素输入的最大字符数, 一般较少使用.

**使用场景：**

1. 有些表单元素想刚打开页面就默认显示几个文字怎么做?  

​	答: 可以给这些表单元素设置 value 属性=“值” 

```html
用户名: <input type="text"  value="请输入用户名" /> 
```

2. 页面中的表单元素很多，如何区别不同的表单元素? 

   答：name 属性：当前 input 表单的名字，后台可以通过这个 name 属性找到这个表单。页面中的表单很多， name 的主要作用就是用于区别不同的表单。 

```html
用户名: <input type="text"  value="请输入用户名" name="username" /> 
```

+ name 属性后面的值，是自定义的
+ radio (或者checkbox）如果是一组，我们必须给他们命名相同的名字  

```html
<input type="radio" name="sex"  />男 
<input type="radio" name="sex" />女
```

3. 如果页面一打开就让某个单选按钮或者复选框是选中状态?

   答: checked 属性：表示默认选中状态。用于单选按钮和复选按钮。

```html
性    别: 
<input type="radio" name="sex" value="男" checked="checked" />男 
<input type="radio" name="sex" value="女" />女 
```

4. 如何让input表单元素展示不同的形态? 比如单选按钮或者文本框

​	答: type属性：type属性可以让input表单元素设置不同的形态.

```html
<input type="radio" name="sex" value="男" checked="checked" />男 
<input type="text" value=“请输入用户名”> 
```

**例子如下：**

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>input 表单元素</title>
</head>
<body>
    <form action="xxx.php" method="get">
         <!-- text 文本框 用户可以里面输入任何文字 username是自己选择的名字-->
        用户名: <input type="text" name="username" value="请输入用户名" maxlength="6">   <br> 
        <!-- max是能输入的最多字符 -->
        <!-- password 密码框 用户看不见输入的密码 -->
        密码: <input type="password" name="pwd" >  <br> 
        <!-- radio 单选按钮  可以实现多选一 -->
        <!-- name 是表单元素名字 这里性别单选按钮必须有相同的名字name 才可以实现多选1 -->
        <!-- 单选按钮和复选框可以设置checked 属性, 当页面打开的时候就可以默认选中这个按钮 -->
        性别: 男 <input type="radio" name="sex" value="男"> 女  <input type="radio" name="sex" value="女" checked="checked"> 人妖   <input type="radio" name="sex" value="人妖">   <br> 
        <!-- checkbox 复选框  可以实现多选 -->
        爱好: 吃饭 <input type="checkbox" name="hobby" value="吃饭"> 睡觉 <input type="checkbox" name="hobby">  打豆豆 <input type="checkbox" name="hobby" checked="checked"> 
        <br> 
        <!-- 点击了提交按钮,可以把 表单域 form 里面的表单元素 里面的值 提交给后台服务器 -->
        <input type="submit" value="免费注册">
        <!-- 重置按钮可以还原表单元素初始的默认状态 -->
        <input type="reset" value="重新填写">
        <!-- 普通按钮 button  后期结合js 搭配使用-->
        <input type="button" value="获取短信验证码"> <br>
        <!-- 文件域 使用场景 上传文件使用的 -->
        上传头像:  <input type="file" >
    </form>
</body>
</html>



#### 3.4.2 `<label>`标签
`<label>` 标签为 input 元素定义标注（标签）。 
`<label>` 标签用于绑定一个表单元素, 当点击`<label>` 标签内的文本时，浏览器就会自动将焦点(光标)转到或者
选择对应的表单元素上,用来增加用户体验.

**语法：**   

```html
<label for="sex">男</label> 
<input type="radio" name="sex"  id="sex" />
```

核心：` <label>` 标签的 for 属性应当与相关元素的 id 属性相同。

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>label标签</title>
</head>
<body>
   <label for="text"> 用户名:</label> <input type="text" id="text" >
   <input type="radio" id="nan" name="sex"> <label for="nan">男</label>
   <input type="radio" id="nv"  name="sex"> <label for="nv">女</label>
</body>
</html>


#### 3.4.3 `<select>`表单元素
使用场景: 在页面中，如果有多个选项让用户选择，并且想要节约页面空间时，我们可以使用`<select>`标签控件定义下
拉列表。

![下拉列表](https://cdn.jsdelivr.net/gh/hxd77/BlogImage/Blog/%E4%B8%8B%E6%8B%89%E5%88%97%E8%A1%A8.png)

**语法：**

```html
<select> 
	<option>选项1</option> 
	<option>选项2</option> 
	<option>选项3</option> 
	... 
</select>
```
1. `<select>` 中至少包含一对`<option>` 。 
2. 在`<option>` 中定义 selected =“ selected " 时，当前项即为默认选中项。 

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>select下拉表单</title>
</head>
<body>
    <form>
    籍贯: 
    <select>
        <option>山东</option>
        <option>北京</option>
        <option>天津</option>
        <option selected="selected">火星</option>
    </select>
</form>
</body>
</html>



#### 3.4.4 `<textarea>`表单元素

**语法：**

```html
<textarea rows="3" cols="20"> 
	文本内容 
</textarea>
```
1. 通过 `<textarea>` 标签可以轻松地创建多行文本输入框。 
2. cols=“每行中的字符数” ，rows=“显示的行数”，我们在实际开发中不会使用，都是用 CSS 来改变大小。 

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>textarea 文本域</title>
</head>
<body>
    <form>
        今日反馈:
        <textarea cols="50" rows="5">我真帅</textarea>
    </form>
</body>
</html>



**案例2-注册页面：**

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>案例2-注册页面</title>
</head>
<body>
    <h3> 青春不常在，抓紧谈恋爱</h3>
    <table width="600">
        <!-- 第一行 -->
        <tr>
            <td>性别</td>
            <td>
                <input type="radio" name="sex" id="nan"><label  for="nan"><img src="images/man.jpg" ></label> 男  
                <input type="radio" name ="sex" id="nv"><label for="nv"><img src="images/women.jpg" ></label > 女 
            </td>
        </tr>
        <!-- 第二行 -->
        <tr>
            <td>生日</td>
            <td>
                <select>
                    <option>---请选择年份---</option>
                    <option>2001</option>          
                    <option>2002</option>          
                    <option>2003</option>          
                </select>
                <select>
                    <option>---请选择月份---</option>
                    <option>1</option>          
                    <option>2</option>          
                    <option>3</option>          
                </select>
                <select>
                    <option>---请选择日---</option>
                    <option>1</option>          
                    <option>2</option>          
                    <option>3</option>          
                </select>
            </td>
        </tr>
        <!-- 第三行 -->
        <tr>
            <td>所在地区</td>
            <td><input type=text value="北京思密达"></td>
        </tr>
        <!-- 第四行 -->
        <tr>
            <td>婚宴状况:</td>
            <td><input type="radio" checked=checked name=marry>未婚 <input type="radio" name=marry>已婚 <input type="radio" name=marry>离婚</td>
        </tr>
        <!-- 第五行 -->
        <tr>
            <td>学历:</td>
            <td><input type=text value=博士后></td>
        </tr>
        <!-- 第六行 -->
        <tr>
            <td>喜欢的类型:</td>
            <td>
                <input type="checkbox" name=love>妩媚的
                <input type="checkbox" name=love>可爱的
                <input type="checkbox" name=love>小鲜肉
                <input type="checkbox" name=love>老腊肉
                <input type="checkbox" name=love checked="checked">都喜欢
            </td>
        </tr>
        <!-- 第七行 -->
         <td>个人介绍</td>
         <td>
            <textarea>个人简介</textarea>
         </td>
         <!-- 第八行 -->
          <tr>
            <td></td>
            <td><input type="submit" value="免费注册"></td>
          </tr>
          <tr>
            <td></td>
            <td><input type="checkbox" checked=checked>我同意注册条款和会员加入标准</td>
          </tr>
          <tr>
            <td></td>
            <td><a href=# >我是会员，立即登录</a></td>
          </tr>
          <tr>
            <td></td>
            <td>
                <h5>我承诺</h5>
                <ul>
                    <li>年满18岁、单身</li>
                    <li>抱着严肃的态度</li>
                    <li>真诚寻找另一半</li>
                </ul>
            </td>
          </tr>
    </table>
</body>
</html>

