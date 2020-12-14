---
title: 前端基础知识——Web
date: 2019-03-27 21:15:49
categories: 前端知识
tags: Front
copyright: true
---

### **Web篇**：

##### 1.常见的浏览器内核有哪些？

```
	IE：Trident内核             FireFox：gecko内核                

	Opera ：原是用Presto，现改用Blink

	Safari ：webkit内核       Chrome：Blink（WebKit的分支）	

```

<!-- more -->

##### 2.前端页面有哪三层构成，分别是什么?作用是什么?

​	结构层 Html    ， 表示层 CSS  ，   行为层 js　

##### 3.请描述一下 cookies，sessionStorage 和 localStorage 的区别？

```
	sessionStorage 和 localStorage 是HTML5 Web Storage API 提供的，可以方便的在web请求之间保存数据。有了本地数据，就可以避免数据在浏览器和服务器间不必要地来回传递。

	sessionStorage、localStorage、cookie都是在浏览器端存储的数据，其中sessionStorage的概念很特别，引入了一个”浏览器窗口”的概念。sessionStorage是在同源的同窗口（或tab）中，始终存在的数据。也就是说只要这个浏览器窗口没有关闭，即使刷新页面或进入同源另一页面，数据仍然存在。关闭窗口后，sessionStorage即被销毁。同时”独立”打开的不同窗口，即使是同一页面，sessionStorage对象也是不同的

 	cookies会发送到服务器端。其余两个不会。
```



##### 4.ajax的缺点

- ajax不支持浏览器back按钮。

- 安全问题 AJAX暴露了与服务器交互的细节。

- 对搜索引擎的支持比较弱。

- 破坏了程序的异常机制。不容易调试。

  

##### 5.怎样添加、移除、移动、复制、创建和查找节点。

1）创建新节点

```
  createDocumentFragment()    //创建一个DOM片段
 
  createElement()   //创建一个具体的元素
 
  createTextNode()   //创建一个文本节点
```

2）添加、移除、替换、插入

```
  appendChild()
 
  removeChild()
 
  replaceChild()
 
  insertBefore() //并没有insertAfter()
```

3）查找

```
  getElementsByTagName()    //通过标签名称
  getElementsByName()    //通过元素的Name属性的值(IE容错能力较强，会得到一个数组，其中包括id等于name值的)
  getElementById()    //通过元素Id，唯一性
```

