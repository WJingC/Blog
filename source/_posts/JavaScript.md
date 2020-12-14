---
title: 前端基础知识——JavaScript
date: 2019-03-28 10:18:43
categories: 前端知识 
tags: Front
copyright: true
---

### **JavaScript篇：**

##### 1.javascript的typeof返回哪些数据类型?

​	string、number、boolean、Ｏbject、underfind、function ;

##### 2.js的数据类型都有哪些？

 	字符串、数字、布尔、数组、对象、Null、Undefined、Symbol\

<!-- more -->

##### 3.例举3种强制类型转换和2种隐式类型转换?

​	强制类型转换：parseInt,parseFloat,number

​	隐世类型转换：==和===

##### 4.数组方法pop() push() unshift() shift()

​	Push()尾部添加            pop()尾部删除

​	Unshift()头部添加        shift()头部删除

##### 5.谈谈This对象的理解。

​	this是js的一个关键字，随着函数使用场合不同，this的值会发生变化。

​	但是有一个总原则，那就是this指的是调用函数的那个对象。

​	this一般情况下：是全局对象Global。 作为方法调用，那么this就是指这个对象