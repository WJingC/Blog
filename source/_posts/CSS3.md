---
title: 前端基础知识——CSS3
date: 2019-03-28 10:21:44
categories: 前端知识
tags: Front
copyright : true
---

### **CSS3篇：**

##### 1.CSS清除浮动的几种方法（至少两种）

   	使用带clear属性的空元素;        使用CSS的overflow属性；

   	使用CSS的:after伪元素；         使用邻接元素处理；

<!-- more -->

##### 2.页面导入样式时，使用link和@import有什么区别？

​	link属于HTML标签，除了加载CSS外，还能用于定义RSS, 定义rel连接属性等作用；而	　@import是CSS提供的，只能用于加载CSS;

​	页面被加载的时，link会同时被加载，而@import引用的CSS会等到页面被加载完再加载;

​	import是CSS2.1 提出的，只在IE5以上才能被识别，而link是XHTML标签，无兼容问题;



