---
title: Mac 打造前端开发环境
Copyright: true
date: 2019-05-08 17:05:48
categories: 开发环境
tags:
 - macOS
 - Front
 - Software
 - Developer Tools
top: 101
---

## **macOS Mojave 打造高效率前端开发环境**

### 

### **安装Homebrew**

​	包管理工具。类似于node下的npm。可以用来安装管理大部分的无界面的工具，如node，git，Python等。 
​	摘自官网的安装命令：

```bash
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

<!--more-->

### 安装Git

```bash
brew install git
```

### 安装npm

```bash
npm install npm -g
```

### 安装webpack

```bash
npm install webpack -g
```



### **用 iTerm2 代替Mac Terminal **

​	Mac原生terminal 也很强大也可以设置很美观，但是iTerm2 明显更优秀。

#### 安装

​	首先我们下载的 iTem2 这个软件，比Mac自带的终端更加强大。直接官网 <http://iterm2.com/> 下载并安装即可。

#### 配置

​	将iTem2设置为默认终端：（菜单栏）iTerm2 -> Make iTerm2 Default Term

​						![屏幕快照 2019-05-09 下午4.16.20](/Users/evildevil/Pictures/Screen Shot/屏幕快照 2019-05-09 下午4.16.20.png)

​	然后打开偏好设置preference，选中Keys，勾选Hotkey下的Show/hide iTerm2 with a system-wide hotkey，我将热键设置为 Option + Space，这样你就可以通过Option + Space . 全局热键来打开或关闭iTerm2窗口，非常方便。

#### 主题配色

​	首先我来介绍一下如何下载并应用我们看好的主题配置文件。

​	我们可以点击 [这个链接](https://github.com/mbadolato/iTerm2-Color-Schemes/archive/master.zip) 直接下载主题项目的所有文件，得到压缩包，解压即可。使用 `git` 版本控制系统的同学也可以通过下面这个命令将 GitHub 仓库整个克隆至本地：

```bash
git clone https://github.com/mbadolato/iTerm2-Color-Schemes.git
```

​	我个人推荐One Dark 主题。One 系列主题同样也有一暗一亮两个配色方案。**其中的 One Dark 是 Atom 编辑器的默认主题配色**，简洁、养眼。不得不承认这一主题确实很符合我的胃口，我现在所有可以配色的地方（比如各种终端和 VS Code 等编辑器）几乎就直接使用 One Dark 配色。

![img](https://cdn.sspai.com/2019/02/22/7cadc29a9e9ef2df38cff8d74c8b2f2e.png?imageView2/2/w/1120/q/90/interlace/1/ignore-error/1)

​	这是我的iTerm2界面，自认为很简洁美观。

![屏幕快照 2019-05-09 下午4.23.47](/Users/evildevil/Pictures/Screen Shot/屏幕快照 2019-05-09 下午4.23.47.png)

推荐链接：[10 个 Terminal 主题，让你的 macOS 终端更好看](https://sspai.com/post/53008)

#### 安装oh-my-zsh

​	github连接：<https://github.com/robbyrussell/oh-my-zsh>

​	使用 crul 安装：

```bash
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

​	或使用wget：

```bash
`sh -c ``"$(wget https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"`
```





### **编辑器**

#### Vusual Studio Code

​	**Visual Studio Code** is a **lightweight but powerful source code editor** which runs on your desktop and is available for Windows, macOS and Linux. It comes with built-in support for `JavaScript, TypeScript and Node.js` and has `a rich ecosystem of extensions for other languages (such as C++, C#, Java, Python, PHP, Go) and runtimes (such as .NET and Unity)`.
 支持的拓展常见的包含如下：

![img](https://upload-images.jianshu.io/upload_images/3980862-5825acffe2b3a3f4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/793/format/webp)

##### 优点：

​	重新定义了 Code 编辑。

​	在任何操作系统上编辑和调试应用程序 

​	内置 Git 支持 ，1000 种以上的扩展

​	免费和开源

##### 官网：[Vusual Studio Code](https://code.visualstudio.com/) 

##### 下载安装；[Downloads](https://code.visualstudio.com/Download)

##### 官方文档：[VS Code Docs](https://code.visualstudio.com/docs)

##### 扩展官网：[Extensions Marketplace](https://marketplace.visualstudio.com/VSCode)

##### 推荐扩展

​	我将单独写一篇博文具体介绍一些实用的开发插件。

#### WebStorm

​	WebStorm 是[jetbrains](https://baike.baidu.com/item/jetbrains)公司旗下一款JavaScript 开发工具。目前已经被广大中国JS开发者誉为“Web前端开发神器”、“最强大的HTML5编辑器”、“最智能的JavaScript IDE”等。与[IntelliJ IDEA](https://baike.baidu.com/item/IntelliJ IDEA)同源，继承了IntelliJ IDEA强大的JS部分的功能。



#### Submlie Text3

##### 下载安装：[官网](http://www.sublimetext.com/3)

##### 插件推荐：





