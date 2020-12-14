---
title: 前端基础知识——Webpack
date: 2019-03-28 10:18:57
categories: 前端知识
tags: Front
copyright: true
---

### **Webpack篇：**

##### 1.Webpack是什么？

​	Webpack 是一个前端资源加载/打包工具。它将根据模块的依赖关系进行静态分析，然后将这些模块按照指定的规则生成对应的静态资源

<!-- more -->

##### 2.loader的作用：

​	实现对不同格式的文件的处理，比如说将scss转换为css，或者typescript转化为js 

转换这些文件，从而使其能够被添加到依赖图中

##### 3.优化插件：

​	OccurenceOrderPlugin: 为组件分配ID,通过这个插件webpack可以分析和优先考虑使用最多 的模块，然后为他们分配最小的ID

​	UglifyJsPlugin: 压缩代码