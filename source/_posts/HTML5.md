---
title: 前端基础知识——HTML5
date: 2019-03-28 10:14:45
categories: 前端知识
tags: Front
copyright: true
---

### **HTML5篇：**

##### 1.html5有哪些新特性、移除了那些元素？

​	新增的元素有绘画 canvas ，用于媒介回放的 video 和 audio 元素，本地离线存储     	localStorage 长期存储数据，浏览器关闭后数据不丢失，而sessionStorage的数据在浏览器关闭后自动删除，此外，还新增了以下的几大类元素。

    内容元素:

```
article、footer、header、nav、section
```

    表单控件:

```
calendar、date、time、email、url、search
```

<!-- more -->

    控件元素:

```
webworker, websockt, Geolocation
```

    移出的元素有下列这些：

    显现层元素：

```
basefont，big，center，font, s，strike，tt，u
```

    性能较差元素：

```
frame，frameset，noframes
```

##### 2.如何处理HTML5新标签的浏览器兼容问题？

 处理兼容问题有两种方式：

    	(1)    IE8/IE7/IE6支持通过document.createElement方法产生的标签，利用这一特性让这些浏览器支持HTML5新标签。

    	(2)    最好的方式是直接使用成熟的框架、使用最多的是html5shim框架

##### 3.如何区分 HTML 和HTML5？

​	DOCTYPE声明的方式是区分HTML和HTML5标志的一个重要因素，此外，还可以根据新增的结构、功能元素来加以区分。

##### 4.行内元素有哪些？块级元素有哪些？空（void）元素有哪些？

    行内元素有：

```
a b span img input select strong
```

    块级元素有：

```
div ul ol li dl dt dd h1 h2 h3 h4…p
```

    知名的空元素： 

```
<br><hr> <img> <input> <link> <meta>
```

    鲜为人知的是：

```
 <area> <base> <col> <command> <embed> <keygen> <param> <source> <track> <wbr>
```

##### 5.什么是 FOUC（无样式内容闪烁）？你如何来避免 FOUC？

```
<style type="text/css" media="all">@import "../fouc.css";</style>
```

​	而引用CSS文件的@import就是造成这个问题的罪魁祸首。

​	IE会先加载整个HTML文档的DOM，然后再去导入外部的CSS文件，

​	因此，在页面DOM加载完成到CSS导入完成中间会有一段时间页面上的内容是没有样式的，这段时间的长短跟网速，电脑速度都有关系。

​	解决方法简单的出奇，只要在<head>之间加入一个<link>或者<script>元素就可以了。

 



