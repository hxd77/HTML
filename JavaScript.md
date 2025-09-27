# JavaScript一篇文章就够了

**Author:** Lion_H

**Date:** 2021-07-29

**Link:** https://blog.csdn.net/qq_38869493/article/details/119221427?spm=1001.2101.3001.6650.15&utm_medium=distribute.pc_relevant.none-task-blog-2%7Edefault%7EBlogCommendFromBaidu%7ERate-15-119221427-blog-109257751.235%5Ev43%5Epc_blog_bottom_relevance_base9&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2%7Edefault%7EBlogCommendFromBaidu%7ERate-15-119221427-blog-109257751.235%5Ev43%5Epc_blog_bottom_relevance_base9

#### 文章目录

-   -   -   [一：第一个JS代码](#JS_1)
        -   -   [1.为什么是JavaScript](#1JavaScript_2)
            -   [2\. 第一个JavaScript程序](#2_JavaScript_7)
        -   [二：JS基本语法](#JS_22)
        -   -   [1\. 使用var定义变量，条件控制，多行注释，控制台输出](#1_var_23)
            -   [2\. 数据类型介绍，对象的定义](#2__49)
            -   [3\. use strict严格检查模式](#3_use_strict_101)
            -   [4\. 字符串数据类型和方法详解](#4__118)
            -   [5\. 数组类型和方法详解](#5__146)
            -   [6\. 对象类型及相关操作](#6__178)
            -   [7\. 流程控制](#7__201)
            -   [8\. Map和Set集合](#8_MapSet_231)
            -   [9\. 函数的定义和使用](#9__264)
            -   [10\. 对象的作用域](#10__306)
            -   [11\. 对象的行为](#11__341)
            -   [12\. 常用对象（Data等）](#12_Data_357)
            -   [13\. ES6后的面向对象编程](#13_ES6_376)
        -   [三：操作BOM和DOM](#BOMDOM_416)
        -   -   [1\. 操作Bom对象 （Browser Object Model）](#1_Bom_Browser_Object_Model_417)
            -   [2\. 操作Dom对象 （Document Object Model）](#2_Dom_Document_Object_Model_454)
            -   [3\. 获取表单值](#3__490)
        -   [四：Jquery](#Jquery_499)

#### 一：第一个JS代码

##### 1.为什么是JavaScript

-   JavaScript和Java毫无关系，初始为了蹭热度命名为JavaScript
-   JavaScript运行在网页的客户端，能被用来设计和编程网页在事件发生时的行为。（一句话：可实现纯前端的动态交互）
-   即面向过程，又面向对象
-   用的人多，易于学习

##### 2\. 第一个JavaScript程序

既可以直接在html使用script标签写，也可以单独写一个js文件，在需要使用的前端页面中引入即可

```javascript
<!--外部引入,注意别自闭和引入-->
<script src="js/qj.js"></script>

<!--script标签中，写js代码-->
<script>
    alert("hello world");
</script>

<!--不用显式写js，也会默认js-->
<script type="text/javascript">
</script>
```

#### 二：JS基本语法

##### 1\. 使用var定义变量，条件控制，多行注释，控制台输出

```javascript
<script>
    //1 : 定义变量 变量类型 变量名 = 变量值；
    var num = 1;
    alert(num)
    //2 : 条件控制
    if (2>1){
        // 其中也可以嵌套控制和else
        alert("true");
    }
    var score = 1;
    if (score>60&&score<70){
        alert("60-70");
    }else if(score>70&&score<80){
        alert("70-80")
    }else {
        alert("80+");
    }
    // 3 : 多行注释
    /**
     * sd
     */
    //4 : console.log(score) 在浏览器控制台打印变量
</script>
```

##### 2\. 数据类型介绍，对象的定义

```javascript
 <script>
    /*js不区分整数和小数，都为Number类型*/
    123 //整数123
    123.1 //浮点数123.1
    1.123e3 //科学计数法
    -99 // 负数
    NaN //Not a Number
    Infinity //无穷数（无限大，一般不能遇到）

    /*字符串*/
    "abc" / 'abc'

    /*布尔值*/
    true / false

    /*逻辑运算符*/
    // && || ! //与或非

    /*比较运算符，坚持不使用==*/
    /**
     * = 赋值运算
     * == 等于 类型不一样，值一样，会判断为true
     * === 绝对等于 类型一样，值一样，判断为true
     */

    // 注 NaN === NaN NaN与所有东西比较，都返回false，如果需要判断是否是NaN，使用isNaN
    isNaN(NaN) //返回true

    // 浮点数问题
    console.log((1/3)===(1-2/3)) //返回为false，因为会有浮点数精度问题，可以使用这样比较完成功能
    Math.abs(1/3-(1-2/3))<0.000000000001

    // null 和 undefined

    // 数组：可以放入不同类型，java中必须是相同类型对象
    var arr = [1,2,3,4,"add",null]
    // 定义数组
    new Array(1,2,3,4,5)

    // 数组下标越界 会undefined

    // 对象,数组是中括号，对象是大括号
    var person = {
        name:"chelsea",
        age:3,
        tags:[1,2,3,"java"]
    }
    person.age //打印对象属性值
</script>
```

##### 3\. use strict严格检查模式

```javascript
<!--
    'use strict' 必须写在第一行
    局部变量建议let定义（必须支持ES6）
-->
<script>
    /*加上这句话，配置严格检查模式，建议每次js代码都加这句话,这样的话下面i = 1会报错*/
    'use strict';

    // 默认是全局变量，直接在控制台可以打印，这在业务中来说是不应该被允许的
    var i = 1;
    // 局部变量建议使用let 关键字
    let j = 1;
</script>
```

##### 4\. 字符串数据类型和方法详解

```javascript
<!--字符串数据类型讲解-->
<script>
    'use strict';
    //正常字符串使用单引号或双引号包裹
    //可以使用转义字符打印单引号或双引号\' \"
    //多行字符串编写(tab键上面的斜引号包裹 可以包裹多行字符串)
    var msg = `
    chelsea
    chelsea
    `;
    // 模板字符串，类似于el表达式,必须使用``来包裹。
    let name = "chelsea";
    let age = 3;
    let msg = `你好呀，${name}`;

    // 字符串长度等方法，注意js中字符串也是不可变类型
    var student = "student";
    student.length;
    student[1];
    student.toUpperCase();
    student.toLowerCase();
    student.indexOf("t");
    student.substring(1,3); //tu 包前不包后
    student.substring(1); // 从第一个截取到最后
</script>
```

##### 5\. 数组类型和方法详解

```javascript
<!--数组类型详解-->
<script>
    'use strict';
    var arr = [1,2,3,4,5,6];
    arr.length;//长度可变，内容也可变
    // 数组大小发生变化，但后面的值都为undefined
    arr.length = 10;
    // 数组长度变小 数据会丢失
    arr.indexOf(2); // 通过元素获取下标索引，和字符串方法一样
    // 数组版的substring() 数组切片
    arr.slice(1,5);
    // push给数组中添加元素，压入尾部
    arr.push("aaa","bbb");
    // pop 数组中弹出元素,弹出最后一个，弹出后数组中没这个元素
    arr.pop();
    // 头部添加弹出元素
    arr.unshift("aaaa","asdasd");
    arr.shift();
    // 数组排序
    arr.sort();
    //元素反转
    arr.reverse();
    // 数组拼接到后面，返回一个新的数组，原数组内容不变
    arr.concat([1,2,3,4,5]);
    // 连接符。打印拼接数组，使用特定的字符串连接。
    arr.join("-");
    // 多维数组,和java取值一样
    arr = [[1,2,3,4],[3,4,5]];
</script>
```

##### 6\. 对象类型及相关操作

```javascript
<!--对象类型，若干个键值对形式-->
<script>
    /*定义一个person对象,用大括号包起来,属性用逗号隔开，有三个属性*/
    var person = {
        name:"chelsea",
        age:3,
        prop:"yaoshi"
    };
    // 使用一个不存在的对象属性，不会报错，为undefined
    // 动态删减属性
    delete person.name;
    // 动态添加属性,直接给新属性赋值即可
    person.email = "chelsea@foxmail.com";
    // 判断属性值是否在这个对象中 使用in关键字
    "age" in person; // 会返回true
    "tostring" in person; //也会返回true，继承上层对象
    // 判断一个属性是否是这个对象自身拥有的，使用hasOwnProperty方法
    person.hasOwnProperty("toString");//返回false
    person.hasOwnProperty("age");//返回true
</script>
```

##### 7\. 流程控制

```javascript
<!--流程控制-->
<script>
    let age = 3;
    if (age>3){
        alert("haha");
    }else {
        alert("kua~");
    }

    while (age<100){
        age += 1;
    }

    for (let i = 0; i < 10; i++) {
        age += 1;
    }

    /*数组forEach循环*/
    var age = [1,2,3,4,4,5,6];
    age.forEach(function (value) {
        console.log(value);
    });
    /*返回的是一个索引 通过索引获取数据*/
    for (var num in age){
        console.log(age[num]);
    }
</script>
```

##### 8\. Map和Set集合

```javascript
<!--Map和Set-->
<script>
    var map = new Map([["tom",80],["chelsea",100]]);
    /*通过key获得value*/
    console.log(map.get("chelsea"));
    /*给map中添加键值对*/
    map.set("admin",99);
    map.delete("tom");

    /*set：无序不重复集合*/
    var set = new Set([3,1,1,1,1]);//结果只有3，1
    /*添加数值*/
    set.add(2);
    set.delete(1);
    set.has(3); //返回true

    /*使用iterator遍历set和map*/
    var arr = [1,2,3];
    /*上述for in获取到的是下标，这次for of 获取到的是值*/
    for (var value of arr){
        console.log(value);
    }

    for (var x of map){
        console.log(x);//打印出每一对键值对
    }
    for (var x of set){
        console.log(x);//打印set内容
    }
</script>
```

##### 9\. 函数的定义和使用

```javascript
<!--函数-->
<script>
    /*定义方式一：定义一个绝对值函数*/
    function abs(x) {
        /*此判断防止传错参或者不传参*/
        if(typeof x!=="number"){
            throw "Not a Number!";
        }
        if(x>=0){
            return x;
        }else {
            return -x;
        }
    }
    /*如果没有执行return 函数执行也会返回结果 就是undefined*/
    /*定义方式二：匿名函数*/
    var abs = function (x) {
        if(x>=0){
            return x;
        }else {
            return -x;
        }
    }
    /*函数调用，直接调用即可*/
    /*js可以传任意个参数，也可以不传参，不会报错，返回结果不理想而已*/


    /*arguments包含所有的参数，有时候想使用对于的参数来进行附加操作，使用此关键字来接收传入的所有参数*/
    function aaa(a,b,...rest) {
        console.log("a"+a);
        console.log("b"+b);
        // if(arguments.length>2){
        //     console.log(arguments[2]);
        // }
        // 默认rest为多余的参数，如果只传入需要的个数，则rest为空
        // rest参数只能写在最后面，必须要用...标识
        console.log(rest);
    }
</script>
```

##### 10\. 对象的作用域

```javascript
<!--变量的作用域-->
<script>
    function qj() {
        var x = 1;
        x = x+1;
    }
    x = x+2; //会报错：x is not defined;
    function f() {
        // 此处和上面函数中的x不冲突；
        var x = 1;
        x = x+2;
    }
    //js的执行引擎，自动提升了变量声明，但不会提升变量y的赋值，如下
    function f1() {
        // 此处不会报错，但y的值第一时间没有赋进去
        var x = "x"+y;
        console.log(x);
        y = "y";
    }
    //由上述得：所有的变量定义都放在方法头部

    /*全局变量window*/
    var z = "xxx";
    alert(z);
    alert(window.z);//此处两种方式等价，由此可见alert这个函数也是一个全局变量，可直接调用

    // for循环建议使用let来创建变量，如果是var，则for循环外也可使用

    // 常量
    // ES6之前：按照规定，变量名全为大写的默认为常量，但本质还是可以改变的
    // ES6:引入了const关键字，const PI = '3.14' 只读变量，不可更改
</script>
```

##### 11\. 对象的行为

```javascript
<!--对象行为-->
<script>
    var person = {
        name:"chelsea",
        birth:"2020",
        age:function () {
            var now = new Data().getFullYear();
            return now-this.birth;
        }
    };
    // 调用方法时需要加括号
    person.age();
</script>
```

##### 12\. 常用对象（Data等）

```javascript
<!--特殊对象-->
<script>
    /*Data对象*/
    var now = new Data(); //标准时区时间
    now.getFullYear(); //年
    now.getMonth(); //月0-11
    now.getDate();  //日
    now.getDay();   //星期几
    now.getHours();
    now.getMinutes();
    now.getSeconds();
    now.getTime();  //时间戳
    now.toLocaleString();//2021/7/21 下午10：49：35
    /*时间戳转为时间*/
    console.log(new Data(12352342432))
</script>
```

##### 13\. ES6后的面向对象编程

```javascript
<!--面向对象-->
<script>
    var user = {
        name:"chelsea",
        age:10,
        run:function () {
            console.log(this.name+"run!");
        }
    };
    var xiaomign = {
        name:"xiaoming"
    };
    /*本来小明没有run，这样类似于继承，小明也有了run行为，ES6之前就这样*/
    xiaomign.__proto__ = user;


    /*ES6之后有了明确的类class*/
    class Student{
        constructor(name) {
            this.name = name;
        }
        hello(){
            alert("hello");
        }
    }
    var xiaoming = new Student("xiaoming");
    /*继承,和ES6之前的原型模式一样*/
    class xiaoStudent extends Student{
        constructor(name,grade) {
            super(name);
            this.grade = grade;
        }
        mygrade(){
            alert("i am xiao student");
        }
    }
</script>
```

#### 三：操作BOM和DOM

##### 1\. 操作Bom对象 （Browser Object Model）

```javascript
<!--操作Bom对象 Browser Object Model-->
<script>
     /*window对象：代表浏览器窗口*/
     window.alert(111);
     /*获取浏览器内外高宽*/
     window.innerHeight;
     window.innerWidth;
     window.outerWidth;
     window.outerHeight;

     /*Navigator封装了浏览器的信息*/
     Navigator.appName;//浏览器名称
     Navigator.userAgent;

     /*代表全屏幕属性，宽高等*/
     screen.width;
     screen.height;

     /*location代表当前页面的url信息*/
     location.host;//主机
     location.href;//指向的页面
     location.protocol;//协议
     location.reload();//重新加载网页
     location.assign("codelearing.life");//设置网页跳转

     /*document代表当前页面*/
     document.title;//标题
     document.getElementById("app");//获取网页所有节点
     document.cookie;//获取网页的cookie

     /*history对象*/
     history.back();//
     history.forward();//前进后退
 </script>
```

##### 2\. 操作Dom对象 （Document Object Model）

```javascript
<!--操作Dom对象 Document Object Model-->
<script>
    /*得到Dom后进行增删改查*/
    var father1 = document.getElementsByTagName("h1");
    var father2 = document.getElementById("p1");
    var father3 = document.getElementsByClassName("myClass");
    var childrens = father2.children;//获取父节点下的所有子节点
    /*只要能定位到一个节点，就可以获取到其他所有节点*/

    /*更新节点*/
    var id1 = document.getElementById("id1");
    id1.innerText = "123";//修改文本值
    id1.innerHTML = "<a href='ww.baidu.com'>";//向节点内部插入超文本
    id1.style.color = "red";//设置标签的style
    id1.style.margin = "200px";

    /*删除节点：先获取父节点，在父节点中删除子节点*/
    var father = document.getElementById("father");
    father.removeChild(p1);//获取后进行删除
    var father1 = document.getElementById("children").parentElement;

    /*注：删除节点的时候，节点是在动态持续变化的*/

    /*插入、追加节点*/
    var js = document.getElementById("js");
    var list = document.getElementById("list");
    var newP = document.createElement("p");
    newP.id = "newP";
    newP.innerText = "newP";
    newP.setAttribute("href","www.baidu.com");
    list.appendChild(js);
    list.appendChild(newP);
</script>
```

##### 3\. 获取表单值

```javascript
<!--操作表单-->
<script>
    /*文本框 下拉框 单选框 多选框 隐藏于 密码框 text select radio checkbox hidden password*/
    /*得到输入框的值*/
    var username = document.getElementById("username").value;//也可以赋值.value = 123312
</script>
```

#### 四：Jquery

Jquery本质上就是一个封装好的JS类库，可以直接调用人家写好的方法，因为直接使用JS开发部分代码冗余，操作不方便，就产生了Jquery。  
Jquery官网下载地址：[https://jquery.com/](https://jquery.com/)  
JqueryApi介绍文档：[http://jquery.cuishifeng.cn](http://jquery.cuishifeng.cn)

```javascript
<!--Jquery-->
<script>
    /*封装了大量js代码的库*/
    /*选择器*/
    $("#submit").click(function () {
        alert("123");
    })

    /*标签选择器*/$("span");
    /*类选择器*/$(".myclass");
    /*id选择器*/$("#myId");
    /*Jquery文档：http://jquery.cuishifeng.cn*/

    /*鼠标事件 键盘事件*/
    $("#submit").mousedown(function () {
        alert("点击了")
    });
    /*网页加载完毕后响应时间*/
    $(function () {
        alert("网页加载完毕")
    });
</script>

<!--操作Dom-->
<script>
    $("#test-ul li[name=python]").text();//获得值
    $("#test-ul li[name=python]").text("addtest");
    $("#test-ul li[name=python]").html("addtest");

    $("#test-ul li[name=python]").show();//显示
    $("#test-ul li[name=python]").hidden;//隐藏
</script>
```