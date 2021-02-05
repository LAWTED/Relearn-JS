---
title: JavaScript 语句小结
date: 2021-02-05 14:41:06
tags: 技术
---
# JavaScript 语句小结

## 类似C++的

###  break

### case

### continue

### default

### do/while

### while

### for

### if/else

### return

### switch

## JavaScript中的

### debugger

断点调试器

### empty

```
;
```

什么都不做

### for/in

```js
for(let i in list){
    console.log(list[i])
}
```

### function

声明一个函数

```js
var a = function (){

}

function a(){
    
}
```

### label

给statement指定一个名字，然后就可以在别的地方通过标签名字来引用这段代码

```js
domost :
for(var i = 0;i<10;i++){
  console.log(i);
  if(i === 5)
    break domost;
}
```

### throw

抛出异常

```js
function f(x){
  if(x<0)
  throw new Error("wrong");
}
```

### try,catch,finally

### use srict

对脚本和函数应用严格模式
