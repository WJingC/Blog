---
title: 从Linux Deepin 系统迁移Blog到 MacOS Mojave
copyright: true
date: 2019-04-13 21:11:48
categories: 博客搭建
tags:
 - MacOS Mojave 10.14.4
 - MacOS
 - Hexo
 - Github
 - Deepin
 - Linux
top: 80
---



## Hexo Blog + Github Pages 从 Deepin 15.9.3 迁移至 MacOS Mojave 10.14.4





### 安装git和node.js

- 首先在自己电脑上转好node和git

  > `brew install git`
  >
  > `brew install node`



### 安装hexo

- 用node.js来安装

  > `npm install hexo g`

<!--more-->



### 初始化hexo

- 新建一个hexo目录，然后在 `hexo init`
-  在用`hexo s`测试是否成功，打开`localhost:4000`查看本地



### 生成SSH key

- 先查看本地的SSH key: `cd ~/.ssh`
-  然后生成一个SSH key `ssh-keygen -t rsa -C "xxxxxx@xxx.com"`,后面那个是注册邮箱



### 添加SSH key到自己github

- 进入.ssh文件夹： `cd ~/.ssh`，然后打开里面的 id_rsa.pub文件，里面的内容就是 SSH key，复制全部内容；
- 网页打开 github 的设置：Settings -> SSH and GPG keys，点击绿色的按钮 New SSH key，然后在输入框中输入刚才复制的内容；
- 保存后，github 会向你的邮箱发送一个验证链接（记得要去登录邮箱验证，不然之后的 hexo d 部署会一直不成功的！）；
- 测试一下是否成功：ssh [git@github.com](mailto:git@github.com)，
   看到以下即成功：

```
PTY allocation request failed on channel 0
Hi gjincai! You've successfully authenticated, but GitHub does not provide shell access.
Connection to github.com closed.
```



### 文件配置转移

-  windows 下的博客根目录 hexo，复制该目录下的：`_config.yml`, `scaffolds`, `source`, `themes`；
-  mac 下的博客根目录 hexo，把刚才复制的内容，直接覆盖替换相同的文件文件夹。





 

 

 

 

 