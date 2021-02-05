---
title: instanceof 的用法
date: 2021-02-05 15:58:10
tags: 技术
---
# instanceof运算符

左边是一个对象，右边是表示对象的类

```js
var d = new Date()
console.log(d instanceof Date);//true,d是由Date()创建的
console.log(d instanceof Object);//true,所以的对象都是Object的实例
console.log(d instanceof Array);//false，不是一个数组
```

可以用`instanceof`来判断是不是Array，而`typeof` 不能

```js
var a = new Array()
//var a = [1,2,3]
console.log(typeof a);//object
console.log(a instanceof Array);//Array
```

