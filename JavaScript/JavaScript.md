---
title: JavaScript基础
date: 2021-01-28 11:23:46
tags: 技术
---
## JavaScript用法

* HTML中的脚本必须位于<script></script>标签之间
* 脚本可被放置在HTML页面的<body>和<head>中

## JavaScript标签

* 在HTMl中插入JavaScript，使用<script>标签
* 在<script></script>之间书写代码

## JavaScript使用限制

* 在HTML中，不限制脚本数量
* 通常会把脚本放置于<head>标签中，以不干扰页面内容

## JS的语法和注释

* 语句之间的间隔是分号
* JS的执行顺序是按编写顺序执行
* JS的关键字不能使用
* JS大小写敏感
* 注释和C语言一样

## JS的变量

```
var x=10；
var string="hello";
var arr=[1,2,3,4];
var arr=new Array("hello","jike","daojiahao");
var arr=new Array();
arr[0]=10;
```

* 任何类型和字符串相加都会变成字符串

```
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>文档标题</title>
</head>
<body>
	<p>i=10 j=10</p>
	<p id="sumid"></p>
	<botton onclick="mysum()">结果</botton>
</body>
</html>
```

```
function mysum(){
	var i = 10;
	var j = 10;
	var m=j+i;	document.getElementById("sumid").innerHTML=m;
}
```

## 运算符

```
两个==
字符串"10"可以和数字10相等

三个===
字符串"10"可以和数字10相等

```

## 三则运算

```
var i=11;
document.write(i>10?"i大于10":"i小于10")；
```

## if

```
if(i>=10){
	document.write("hello");
}
else{
	....
}
```

## switch

和C++一样

## for

和C++一样

```
var i=[1,2,3,4];
var j;
for(j in i){
	document.write(i[j]);
}
```

## while

和C++一样

## alert

```
alert(i);
```

弹出对话框,显示内容

## function

```
function demo(a,b){     //不需要写类型
	var sum=a+b;
	alert(sum);
	}
	demo(10,20);
function demo1(name,age){
	alert("Hello:"+name",我的今年"+age+"岁")；
}
```

## 局部变量和全局变量

全局变量不需要 var

## 异常

```
try{
	alert(str);
}catch(err){
	alert(err);
}
```

```
<body>
	<form>
		<input id="txt" type="text">
		<input id="btn" type="button" onclick="demo()" value="按钮">
	</form>
	<script>
		function demo(){
			try{
				var e=document.getElementById("txt").value;
				if(e==""){
					throw"用户输入异常"；
				}
			}catch(err){
				alert(err);
			}
		}
	</script>
</body>
```

## 事件

```
onClick            单击事件
onMouseOver        鼠标经过事件
onMouseOut         鼠标移出事件
onChange           文本内容改变事件
onSelect           文本框选中事件
onFocus            光标聚集事件
onBlur             移开光标事件
onLoad             网页加载事件
onUnload           关闭网页事件
```

## JS的DOM对象(Document Object Model)

## DOM操作HTML

1. 使用document.write("")来改变HTML

==不要在文档加载完成之后使用document.write()，这会覆盖该文档==

2. 寻找元素

* 通过id找到HTML元素
* 通过标签名找到HTML元素、

3. 改变HTML内容

使用属性：innerHTML


```
function demo(){
	var nv=document.getElementById("pid").innerHTML="hello";
	
}
```

4. 改变HTML属性

使用属性：attribute,例如href，src

## DOM操作CSS

语法：document.getElementByid(id).style.background-color:...;

## DOM EvenListener

```
document.getElementById("btn").addEventListener("click",function(){
alert("hello")});
```

```
var x=document.getElementById("btn");
x.addEventListener("click",hello);
x.addEventListener("click",world);
x.removeEventListener("click",hello);
function hello(){
	alert("Hello");
}
function world(){
	alert("world");
}
```

## JS事件流

* 事件冒泡：最具体的元素接受，到最不具体的
* 事件捕获：最不具体的接受，到最具体的

## JS事件的处理

### HTML事件的处理

```
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>文档标题</title>
</head>
<body>
  <div id="div">
    <button id="btn" onclick="demo()">按钮</button>
  </div>
  <script>
    function demo(){
	alert("Hello html事件处理");
}
  </script>
</body>
</html>
```

### DOM0级处理

把一个函数赋值给一个事件处理程序属性

```
var btn=document.getElementById("btn");
btn.onclick= function(){alert("hello1")};   //会被覆盖
btn.onclick= function(){alert("hello2")};
```

### DOM2级事件处理

```
var btn1=document.getElementById("btn");
btn1.addEventListener("click",demo1);
btn1.addEventListener("click",demo2);
btn1.removeEventListener("click",demo3);
function demo2(){
  alert("hello world");
}
function demo1(){
  alert("hello");
}
```


### IE事件处理程序

* attachEvent类似addEventListener
* detachEvent类似removeEventListenr

## 事件对象

在触发DOM事件的时候会产生一个对象

### 事件对象event

#### type：获取事件类型

```
document.getElementById("btn").addEventListener("click",showtype);
function showtype(event){
	alert(event.type);
}

输出：click
```

#### target：获取事件目标

```
document.getElementById("btn").addEventListener("click",showtype);
function showtype(event){
	alert(event.target);
}
输出：[object HTMLButtonElement]
```

#### stopPropagation：阻止事件冒泡

```
document.getElementById("btn").addEventListener("click",showtype);
document.getElementById("div").addEventListener("click",showdiv);
function showtype(event){
	alert(event.target);
	event.stopPropagation();
}
function showdiv(){
	alert("div");
}
```

#### preventDefault：阻止事件默认行为

`event.preventDefault();`

## 对象

定义并创建对象实例

```
people = new Object();
people.name = "Lawted";
people.age = "18";
document.write("name: "+people.name+",age:"+people.age);

people={name:"Lawted",age:"30"}
```

使用函数来定义对象，然后创建新的对象实例

```
function people(name,age){
	this._name=name;
	this._age=age;
}
son = new people("Lawted",30);
document.write("name:"+son._name+"<br/>"+ "age:"+son._age);
```


## string字符串对象

string对象：
字符串可以使用单引号和双引号

### 在字符串中查找字符串：.indexOf()

```
var str= "Hello world";
document.write(str.indexOf("world"));
```


### 字符串长度.length
```
var str= "Hello world";
document.write("字符串长度："+str.length);
```

返回位置，从0开始，如果没有则返回-1

### 内容匹配.match()

```
var str= "Hello world";
document.write(str.match("world")); 
```

如果有则返回内容，没有则返回null

### 替换内容.replace()

```
var str= "Hello world";
document.write(str.replace("world","nihao"));
```

两个参数，将内容替换

### 字符串大小写转换toUpperCase()/toLowerCase()

```
var str= "Hello world";
document.write(str.toUpperCase());
```

### 字符串转为数组strong>split()

```
var str= "hello,jike,xueyuan";
var s= str.split(",");
document.write(s[1]);
```

## Date日期对象

```
var date = new Date();
document.write(date);
```

### 获取年份getFullyear

```
var date = new Date();
document.write(date.getFullYear());
```

### 设置时间

```
var date = new Date();
date.setFullYear(2011,0,1);       //年份，月份，日期  月份从0开始
document.write(date)
```

## 数组

使用单独的变量名来存储一系列的值

### 数组的创建

`var myArray=["Hello","iwen","ime"];`

### 合并数组concat()

```
var a=["hello","world"];
var b=["Lawted","123"];
var c=a.concat(b);
document.write(c);
```

### 排序sort()
	
```
var a=["1","2","67","4","-10"];
document.write(a.sort());
```

降序排序

```
var a = ["1", "2", "67", "4", "-10"];
document.write(
	a.sort(function (a, b) {
		return b - a;
	})
);
```

### 在末尾追加push()

```
var a=["a","b"];
a.push("c");
document.write(a);
```


### 翻转reverse()

```
var a=["c","b","a"];
document.write(a.reverse());
```

## Math对象

执行常见的算数任务

### 四舍五入round()

`document.write(Math.round(4.7));`

### 随机数random()

`document.write(Math.random());`

取0-10的随机整数

`document.write(parseInt(Math.random()*10))`

### 最大数max()/最小数min()/绝对值abs()

`document.write(Math.max(1,23,424,55));`

## JSDOM对象控制HTML

```
getElementsByName()       获取name
getElementsByTagName()    获取元素
getAttribute()            获取元素属性
setAttribute()            设置元素属性
childNodes()              访问子结点
parentNode()              访问父结点
createElement()           创建元素结点
createTextNode            创建文本结点
insertBefore()            插入结点
removeChild()             删除结点
offsetHeight              网页尺寸，不包含滚动条
scrollHeight              网页尺寸，包含滚动条
```

### 获取元素 getElementsByTagName()

```
function getName(){
	var count=document.getElementsByTagName("p")
	var p = count[3];
	p.innerHTML="World";
}
getName();
```

### 获取属性 getAttribute()

```
HTML
<a id="aid" title="标签">world</a>

JS
function getAttr(){
	var anode=document.getElementById("aid");
	var attr=anode.getAttribute("title");
	alert(attr);
}
getAttr();
```

### 设置新属性 setAttribute()

```
function getAttr(){
	var anode=document.getElementById("aid");
	anode.setAttribute("title","新的属性");
	alert(anode.getAttribute("title"));
}
getAttr();
```

### 访问子结点 chidNodes

```
function getchildnode() {
	var childnode = document.getElementsByTagName("ul")[0].childNodes;
	alert(childnode.length);
}
getchildnode();
```

### 添加一个节点 createElement()

```
function createNode(){
  var body=document.body;
  var input=document.createElement("input");
  input.type="button";
  input.value="按钮";
  body.appendChild(input);
}

createNode();
```

### 插入一个节点 .insertBefore()

```

  <div id="div">
    <p id="pid">这是一个坐标</p>
  </div>

function addNode(){
	var div=document.getElementById("div");
  	var node=document.getElementById("pid");
  	var newnode=document.createElement("p");
  	newnode.innerHTML="动态添加一个"
  	div.insertBefore(newnode,node);
}
addNode();
```

### 删除结点 .removeChild()

```
function removeNode(){
	var div=document.getElementById("div");
	var p=div.removeChild(div.childNodes[1]);
}
removeNode();
```

### 网页尺寸

```
function getSize(){
	var width=document.documentElement.offsetWidth;
  	alert(width);
  	var height=document.documentElement.offsetHeight;
  	alert(height);
}
getSize();
```


## window对象

* window对象是BOM的核心、window对象指当前的浏览器窗口
* 所有JS全局对象、函数以及变量均自动成为window对象的成员

### window尺寸

```
document.write("宽度："+window.innerWidth+"高度："+window.innerHeight)
```

* window.innerWidth  浏览器窗口的内部宽度
* window.innerHeight  浏览器窗口的内部高度
* window.open         打开页面
* window.close        关闭页面

## 计时器

通过JS，在设定的时间间隔之后来执行，而不是在函数被调用后立即执行

### 计时方法

```
setinterval()    间隔指定的毫秒数不停的执行指定代码
clearinterval()  用来停止setinterval()方法执行的函数代码
setTimeout()     暂停指定的毫秒数之后执行指定的代码
clearTimeout()   用来停止setTimeout()方法执行的函数代码
```

```

  <p id="ptime"></p>
  <button onclick="stoptime()">按钮</button>

var mytime=setInterval(function(){getTime()});
function getTime(){
  var d= new Date();
  var t= d.toLocaleTimeString();
  document.getElementById("ptime").innerHTML=t;
}
function stoptime(){
	clearInterval(mytime);
}
```

## History 对象

window.history 对象包含浏览器的历史（url）的集合

### History 方法

```
history.back()      浏览器后退按钮
history.forward()   浏览器前进按钮
history.go()        进入历史中的某个界面
```

## Location 对象

window.location对象用于获得当前页面的地址，并把浏览器重定向到新的页面

### Location对象的属性

```
location.hostname    返回web主机的域名
location.pathname    返回当前页面的路径和文件名
location.port        返回web主机的端口
location.protocol    返回所使用的web协议
location.href        返回当前页面的url
location.assign()    加载新文档
```

```
function get(){
document.getElementById("ptime").innerHTML=window.location.href
}
```

## screen 对象

```
screen.availWidth     可用屏幕宽度
screen.availHeight    可用屏幕高度
screen.height         屏幕高度
screen.width          屏幕宽度
```

## 面向对象

```
(function(){function People(){

}
People.prototype.say=function(){
	alert("hello");
}}());                             //封装

function Student(){

}
Student.prototype = new People();
var s=new Student();
s.say();
```



 