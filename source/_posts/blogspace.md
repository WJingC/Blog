---
title: Github Pages + Hexo搭建个人技术博客
copyright: true
date: 2019-04-01 22:08:46
categories: 博客搭建
reprintPolicy: cc_by_nc_nd
tags:
- Blog
- Hexo
- Github
- NexT
top: 150
---

## **用Github Pages + Hexo搭建个人技术博客**



### 序

Hexo安装过后，默认的主题是[landscape](https://github.com/hexojs/hexo-theme-landscape)，如果不喜欢，我们也可以进行更换。本文主要讲解NexT主题的使用。先看下我博客网站的效果吧：[wjingc.github.io](https://wjingc.github.io),我使用的主题是 Mist.

### 主要网站

- [Github](https://github.com)
- [Hexo](https://hexo.io/zh-cn/)
- [Next](http://theme-next.iissnan.com/getting-started.html)

<!--more-->

### 目录

####   Github配置

##### 	注册Github账号

打开<https://github.com/>站点，注册一个账号

##### 	创建Github仓库

接下来到这个页面去创建一个新仓库
<https://github.com/new>

这个新仓库就将是存放你即将拥有的博客的地方

注意，你的仓库名不能随便取，这样会导致github混乱，取名的格式应该为“**用户名.github.io**”

后面的操作照配图做就可以了

##### 	生成Github Pages

建完仓库后，在当前页面右边选择Settings，进入设置页面，在这里生成你的github pages



####   系统环境配置

##### 	安装Node.js

参考地址：[Node.js安装配置](http://www.runoob.com/nodejs/nodejs-install-setup.html)

##### 	安装Git

```bash
apt-get install git
```

##### 	安装Hexo

```bash
cd d:/hexo
npm install hexo-cli -g
hexo init blog
cd blog
npm install
hexo g # 或者hexo generate
hexo s # 或者hexo server，可以在http://localhost:4000/ 查看
```

这里有必要提下Hexo常用的几个命令：

1. hexo generate (hexo g) 生成静态文件，会在当前目录下生成一个新的叫做public的文件夹
2. hexo server (hexo s) 启动本地web服务，用于博客的预览
3. hexo deploy (hexo d) 部署播客到远端（比如github, heroku等平台）

另外还有其他几个常用命令：

另外还有其他几个常用命令：

```bash
hexo new "postName" #新建文章
hexo new page "pageName" #新建页面
```

常用简写

```powershell
hexo n == hexo new
hexo g == hexo generate
hexo s == hexo server
hexo d == hexo deploy
```

常用组合

```shell
hexo d -g #生成部署
hexo s -g #生成预览
```

现在我们打开<http://localhost:4000/> 已经可以看到一篇内置的blog了。



####   Hexo主题设置

我选的是**NexT**主题，主题喜好根据自己选择。

Hexo 安装主题的方式非常简单，只需要将主题文件拷贝至站点目录的 `themes` 目录下， 然后修改下配置文件即可。具体到 NexT 来说，安装步骤如下。

##### 下载主题

如果你熟悉 [Git](http://git-scm.com/)，建议你使用克隆最新版本的方式，之后的更新可以通过 `git pull` 来快速更新， 而不用再次下载压缩包替换。

在终端窗口下，定位到 Hexo 站点目录下。使用 `Git` checkout 代码：

```bash
cd blog
git clone https://github.com/iissnan/hexo-theme-next themes/next
```

##### 启用主题

与所有 Hexo 主题启用的模式一样。当克隆/下载完成后，打开 **站点配置文件**， 找到 `theme` 字段，并将其值更改为 `next`。

启用 NexT 主题

```yml
theme: next
```

到此，NexT 主题安装完成。下一步我们将验证主题是否正确启用。在切换主题之后、验证之前， 我们最好使用 `hexo clean` 来清除 Hexo 的缓存。

##### 验证主题

首先启动 Hexo 本地站点，并开启调试模式（即加上 `--debug`），整个命令是 `hexo s --debug`。 在服务启动的过程，注意观察命令行输出是否有任何异常信息，如果你碰到问题，这些信息将帮助他人更好的定位错误。 当命令行输出中提示出：

```bash
INFO  Hexo is running at http://0.0.0.0:4000/. Press Ctrl+C to stop.
```

此时即可使用浏览器访问 `http://localhost:4000`，检查站点是否正确运行。

当你看到站点的外观与下图所示类似时即说明你已成功安装 NexT 主题。这是 NexT 默认的 Scheme —— Muse



#### NexT主题配置美化



##### 选择 Scheme

Scheme 是 NexT 提供的一种特性，借助于 Scheme，NexT 为你提供多种不同的外观。同时，几乎所有的配置都可以 在 Scheme 之间共用。目前 NexT 支持三种 Scheme，他们是：

- Muse - 默认 Scheme，这是 NexT 最初的版本，黑白主调，大量留白
- Mist - Muse 的紧凑版本，整洁有序的单栏外观
- Pisces - 双栏 Scheme，小家碧玉似的清新

Scheme 的切换通过更改 主题配置文件，搜索 scheme 关键字。 你会看到有三行 scheme 的配置，将你需用启用的 scheme 前面注释 `#` 去除即可。

选择 Mist Scheme

```yml
#scheme: Muse
scheme: Mist
#scheme: Pisces
```



##### 设置语言

编辑 **站点配置文件**， 将 `language` 设置成你所需要的语言。建议明确设置你所需要的语言，例如选用简体中文，配置如下：

```yml
language: zh-Hans
```

目前 NexT 支持的语言如以下表格所示：

| 语言         | 代码                 | 设定示例                            |
| ------------ | -------------------- | ----------------------------------- |
| English      | `en`                 | `language: en`                      |
| 简体中文     | `zh-Hans`            | `language: zh-Hans`                 |
| Français     | `fr-FR`              | `language: fr-FR`                   |
| Português    | `pt`                 | `language: pt` or `language: pt-BR` |
| 繁體中文     | `zh-hk` 或者 `zh-tw` | `language: zh-hk`                   |
| Русский язык | `ru`                 | `language: ru`                      |
| Deutsch      | `de`                 | `language: de`                      |
| 日本語       | `ja`                 | `language: ja`                      |
| Indonesian   | `id`                 | `language: id`                      |
| Korean       | `ko`                 | `language: ko`                      |



##### 设置菜单

菜单配置包括三个部分，第一是菜单项（名称和链接），第二是菜单项的显示文本，第三是菜单项对应的图标。 NexT 使用的是 [Font Awesome](http://fontawesome.io/) 提供的图标， Font Awesome 提供了 600+ 的图标，可以满足绝大的多数的场景，同时无须担心在 Retina 屏幕下 图标模糊的问题。

编辑 **`主题配置文件`**，修改以下内容：

1. 设定菜单内容，对应的字段是 `menu`。 菜单内容的设置格式是：`item name: link`。其中 `item name `是一个名称，这个名称并不直接显示在页面上，她将用于匹配图标以及翻译。

   菜单示例配置

   ```yml
   menu:
     home: /
     archives: /archives
     #about: /about
     #categories: /categories
     tags: /tags
     #commonweal: /404.html
   ```

   若你的站点运行在子目录中，请将链接前缀的 `/` 去掉

   NexT 默认的菜单项有（标注  的项表示需要手动创建这个页面）：

   | 键值       | 设定值                    | 显示文本（简体中文） |
   | ---------- | ------------------------- | -------------------- |
   | home       | `home: /`                 | 主页                 |
   | archives   | `archives: /archives`     | 归档页               |
   | categories | `categories: /categories` | 分类页               |
   | tags       | `tags: /tags`             | 标签页               |
   | about      | `about: /about`           | 关于页面             |
   | commonweal | `commonweal: /404.html`   | 公益 404             |

2. 设置菜单项的显示文本。在第一步中设置的菜单的名称并不直接用于界面上的展示。Hexo 在生成的时候将使用 这个名称查找对应的语言翻译，并提取显示文本。这些翻译文本放置在 NexT 主题目录下的 `languages/{language}.yml`（`{language}` 为你所使用的语言）。

   以简体中文为例，若你需要添加一个菜单项，比如 `something`。那么就需要修改简体中文对应的翻译文件`languages/zh-Hans.yml`，在 `menu` 字段下添加一项：

   ```yml
   menu:
     home: 首页
     archives: 归档
     categories: 分类
     tags: 标签
     about: 关于
     search: 搜索
     commonweal: 公益404
     something: 有料
   ```

3. 设定菜单项的图标，对应的字段是 `menu_icons`。 此设定格式是 `item name: icon name`，其中 `item name` 与上一步所配置的菜单名字对应，`icon name` 是 Font Awesome 图标的 名字。而 `enable` 可用于控制是否显示图标，你可以设置成 `false` 来去掉图标。

   菜单图标配置示例

   ```yml
   menu_icons:
     enable: true
     # Icon Mapping.
     home: home
     about: user
     categories: th
     tags: tags
     archives: archive
     commonweal: heartbeat
   ```

   在菜单图标开启的情况下，如果菜单项与菜单未匹配（没有设置或者无效的 Font Awesome 图标名字） 的情况下，NexT 将会使用  作为图标。

   请注意键值（如 `home`）的大小写要严格匹配



##### **设置侧栏**

默认情况下，侧栏仅在文章页面（拥有目录列表）时才显示，并放置于右侧位置。 可以通过修改 主题配置文件 中的 `sidebar` 字段来控制侧栏的行为。侧栏的设置包括两个部分，其一是侧栏的位置， 其二是侧栏显示的时机。

1. 设置侧栏的位置，修改 `sidebar.position` 的值，支持的选项有：

   - left - 靠左放置
   - right - 靠右放置

   目前仅 Pisces Scheme 支持 `position` 配置。影响版本5.0.0及更低版本。

   ```yml
   sidebar:
     position: left
   ```

2. 设置侧栏显示的时机，修改 `sidebar.display` 的值，支持的选项有：

   - `post` - 默认行为，在文章页面（拥有目录列表）时显示
   - `always` - 在所有页面中都显示
   - `hide` - 在所有页面中都隐藏（可以手动展开）
   - `remove` - 完全移除

   ```yml
   sidebar:
     display: post
   ```

   已知侧栏在 `use motion: false` 的情况下不会展示。 影响版本5.0.0及更低版本。

##### 设置头像

编辑 主题配置文件， 修改字段 `avatar`， 值设置成头像的链接地址。其中，头像的链接地址可以是：

| 地址             | 值                                                           |
| ---------------- | ------------------------------------------------------------ |
| 完整的互联网 URI | `http://example.com/avatar.png`                              |
| 站点内的地址     | 将头像放置主题目录下的 `source/uploads/` （新建 uploads 目录若不存在）  配置为：`avatar: /uploads/avatar.png`或者 放置在 `source/images/` 目录下  配置为：`avatar: /images/avatar.png` |

头像设置示例

```js
avatar: http://example.com/avatar.png
```



##### 设置作者昵称

编辑 站点配置文件， 设置 `author` 为你的昵称。



##### 站点描述

编辑 站点配置文件， 设置 `description` 字段为你的站点描述。站点描述可以是你喜欢的一句签名:) 





下一步：[**配置Hexo-NexT，使你的博客酷炫**](<https://wjingc.github.io/2019/03/29/NexT/>)



##### **参考链接**



- [手把手教你使用Hexo + Github Pages搭建个人独立博客](<https://segmentfault.com/a/1190000004947261>)
- [开始使用NexT](http://theme-next.iissnan.com/getting-started.html)
- [Hexo-NexT配置超炫网页效果](https://www.jianshu.com/p/9f0e90cc32c2)

