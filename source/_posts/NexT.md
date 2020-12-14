---
title: 配置Hexo-NexT，使你的博客酷炫
copyright: true
date: 2019-03-29 18:03:00
categories: 博客搭建
tags:
- Hexo
- Github
- NexT
top: 100
---

### 目录



#### NexT安装

- 切换到**Blog**文件夹下（就是`hexo init`的文件夹），查看文件

```bash
cd [Blog]
ls
_config.yml node_modules    scaffolds   themes
db.json     package.json    source
```

- 通过git安装，前提是你的电脑安装了git.

```bash
git clone https://github.com/iissnan/hexo-theme-next themes/next
```

<!--more-->

- 查看标签列表

```bash
git tag -l
输出：
...
v5.1.3
v5.1.4
```

- 切换到**v5.1.4** 

```bash
git checkout tags/v5.1.4
输出：
HEAD is now at 4f75fe5... 2018 NY update.
```

- 通过**curl**安装NexT

```bash
mkdir themes/next
curl -s https://api.github.com/repos/iissnan/hexo-theme-next/releases/latest | grep tarball_url | cut -d '"' -f 4 | wget -i - -O- | tar -zx -C themes/next --strip-components=1
```

- 更新主题NexT

```bash
cd themes/next
git pull
```

- 切换成NexT主题，在hexo根文件夹下，编辑**_config.yml**文件

```yml
theme: next

//切换后，用命令清除下缓存
hexo clean

//执行hexo s本地产看NexT主题效果
hexo s
```



#### 切换主题

- 在列表中选择一款自己喜欢的主题风格。

```yml
# Schemes
#scheme: Muse  //默认主题
scheme: Mist
#scheme: Pisces
#scheme: Gemini
```

#### 设置Menu

- 默认只有两个首页和归档，如下图所示：  

  ![img](https://upload-images.jianshu.io/upload_images/3072214-cbbe8efe8b4b7bbc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/438/format/webp)

- 如果还要添加，编辑`themes/next/_config.yml`：

```yml
menu:
  home: / || home  //首页
  about: /about/ || user  //关于
  tags: /tags/ || tags  //标签
  categories: /categories/ || th   //分类
  archives: /archives/ || archive //归档
  schedule: /schedule/ || calendar   //日程表
  sitemap: /sitemap.xml || sitemap   //站点地图
```

- 将需要的Menu前面`#`号去掉。如下图所示: 

  ![img](https://upload-images.jianshu.io/upload_images/3072214-47bacb2e4f2852f4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1000/format/webp)

 

#### 初始化对应的Menu文件夹

没有创建Menu对应的文件夹，`Blog/source`文件目录如下：

![img](https://upload-images.jianshu.io/upload_images/3072214-a71568665089efaf.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1000/format/webp)

- 在博客网站点击标签菜单可能会提示：

  ![img](https://upload-images.jianshu.io/upload_images/3072214-a1cce579d49cb369.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/484/format/webp)

- 比如要创建标签文件夹，终端中输入（前提在**Hexo**文件路径下）：

```bash
hexo new page "tags"
输出：
INFO  Created: ~/Desktop/MyBlog/Blog/source/tags/index.md
```

- 成功过后目录如下：

- 编辑`Blog/source/tags`中**index.md**文件，添加`type: "tags"`，其他Menu也同理创建。

```yml
title: tags
date: 2018-01-20 18:57:48
type: "tags"
```



#### 设置动态背景

- **主题配置文件**内置4种特效，选择你喜欢的，设置成**ture**就OK啦。

  ```yml
  # Canvas-nest
  canvas_nest: false
  
  # three_waves
  three_waves: true
  
  # canvas_lines
  canvas_lines: false
  
  # canvas_sphere
  canvas_sphere: false
  ```

  

#### 在右上角或者左上角实现fork me on github

- 效果图如下所示：


![img](https://upload-images.jianshu.io/upload_images/3072214-7a59adb6558e5756.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1000/format/webp)

- 在[GitHub Ribbons](https://github.com/blog/273-github-ribbons)或[GitHub Corners](http://tholman.com/github-corners/)选择一款你喜欢的挂饰，拷贝方框内的代码：

![img](https://upload-images.jianshu.io/upload_images/3072214-8b79d3a1ec518d12.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1000/format/webp)

- 将刚刚复制的挂饰代码，添加到`Blog/themes/next/layout/_layout.swig`文件中，添加位置如下图所示(放在`<div class="headband"></div>`下方)：

![img](https://upload-images.jianshu.io/upload_images/3072214-15e34a9841adc5b4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1000/format/webp)



#### 添加添加RSS

- 切换到**Blog**文件夹（hexo init的文件夹）下

```bash
cd [Blog]
```

- 安装Hexo插件

```bash
npm install --save hexo-generator-feed
```

- 安装成功之后，编辑`Blog/_config.yml`文件，在文件末尾添加

```yml
# Extensions
## Plugins: http://hexo.io/plugins/
plugins: hexo-generate-feed
```

- 配置主题`_config.yml`文件，`command+f`搜索`rss`，在后面加上`/atom.xml` 

```yml
# Set rss to false to disable feed link.
# Leave rss as empty to use site's feed link.
# Set rss to specific value if you have burned your feed already.
rss: /atom.xml //注意：有一个空格
```

- 之后，终端输入`hexo s`查看效果

```zsh
hexo s
```

  ![img](https://upload-images.jianshu.io/upload_images/3072214-313c1804b92eb9a0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/344/format/webp)

 

#### 修改文章内链接文本样式

- 修改`Blog/themes/next/source/css/_common/components/post/post.styl`，在末尾添加CSS样式：

```javascript
// 文章内链接文本样式
.post-body p a{
  color: #0593d3; //原始链接颜色
  border-bottom: none;
  border-bottom: 1px solid #0593d3; //底部分割线颜色
  &:hover {
    color: #fc6423; //鼠标经过颜色
    border-bottom: none;
    border-bottom: 1px solid #fc6423; //底部分割线颜色
  }
}
```

- 设置后，效果如下

![img](https://upload-images.jianshu.io/upload_images/3072214-36e89e89696a255a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1000/format/webp) 



#### 修改底部标签样式

- 修改`Blog\themes\next\layout\_macro\post.swig`中文件，`command+f`搜索`rel="tag">#`，将`#`替换成`<i class="fa fa-tag"></i>`。输入以下命令，查看效果：

```bash
hexo clean
hexo s
```

![img](https://upload-images.jianshu.io/upload_images/3072214-36dcbfd6cd83d271.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/386/format/webp)

#### 在文章末尾添加“文章结束”标记

- 在路径`Blog\themes\next\layout\_macro`文件夹中新建`passage-end-tag.swig`文件。

```bash
//切换到路径_macro
cd [_macro路径]

//创建passage-end-tag.swig文件
touch passage-end-tag.swig
```

- 在passage-end-tag.swig添加以下内容，直接用文本编辑器打开，粘贴以下内容后保存

```html
<div>
    {% if not is_index %}
        <div style="text-align:center;color: #ccc;font-size:14px;">-------------本文结束<i class="fa fa-paw"></i>感谢您的阅读-------------</div>
    {% endif %}
</div>
```

- 打开`Blog\themes\next\layout\_macro\post.swig`，在`post-body`之后，`post-footer`之前（**post-footer之前两个DIV**），添加以下代码：

```html
<div>
  {% if not is_index %}
    {% include 'passage-end-tag.swig' %}
  {% endif %}
</div>
```

- 添加位置，如下图所示：  

![img](https://upload-images.jianshu.io/upload_images/3072214-976a8cf36c994dc7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1000/format/webp)

-  修改主题配置文件**_config.yml**，在末尾添加：

```yml
# 文章末尾添加“本文结束”标记
passage_end_tag:
  enabled: true
```

- 配置完成之后，效果如下： 

![img](https://upload-images.jianshu.io/upload_images/3072214-b1b5a73b99793610.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/788/format/webp)

 

#### 设置头像并设置动画效果

- 在`Blog/_config.yml`中添加头像链接地址：

```yml
//添加头像地址
avatar: [ http://....]
```

- 设置头像圆角并旋转，打开`Blog/themes/next/source/css/_common/components/sidebar/sidebar-author.styl`，添加以下代码：

```javascript
.site-author-image {
  display: block;
  margin: 0 auto;
  padding: $site-author-image-padding;
  max-width: $site-author-image-width;
  height: $site-author-image-height;
  border: $site-author-image-border-width solid $site-author-image-border-color;
  /* 头像圆形 */
  border-radius: 80px;
  -webkit-border-radius: 80px;
  -moz-border-radius: 80px;
  box-shadow: inset 0 -1px 0 #333sf;
  /* 设置循环动画 [animation: (play)动画名称 (2s)动画播放时长单位秒或微秒 (ase-out)动画播放的速度曲线为以低速结束 
    (1s)等待1秒然后开始动画 (1)动画播放次数(infinite为循环播放) ]*/
 
  /* 鼠标经过头像旋转360度 */
  -webkit-transition: -webkit-transform 1.0s ease-out;
  -moz-transition: -moz-transform 1.0s ease-out;
  transition: transform 1.0s ease-out;
}
img:hover {
  /* 鼠标经过停止头像旋转 
  -webkit-animation-play-state:paused;
  animation-play-state:paused;*/
  /* 鼠标经过头像旋转360度 */
  -webkit-transform: rotateZ(360deg);
  -moz-transform: rotateZ(360deg);
  transform: rotateZ(360deg);
}
/* Z 轴旋转动画 */
@-webkit-keyframes play {
  0% {
    -webkit-transform: rotateZ(0deg);
  }
  100% {
    -webkit-transform: rotateZ(-360deg);
  }
}
@-moz-keyframes play {
  0% {
    -moz-transform: rotateZ(0deg);
  }
  100% {
    -moz-transform: rotateZ(-360deg);
  }
}
@keyframes play {
  0% {
    transform: rotateZ(0deg);
  }
  100% {
    transform: rotateZ(-360deg);
  }
}
```

- 效果如下：

 



#### 修改代码块``自定义样式

- 打开`Blog\themes\next\source\css\_custom\custom.styl`，添加以下代码：

```javascript
// Custom styles.
code {
    color: #ff7600;
    background: #fbf7f8;
    margin: 2px;
}
// 大代码块的自定义样式
.highlight, pre {
    margin: 5px 0;
    padding: 5px;
    border-radius: 3px;
}
.highlight, code, pre {
    border: 1px solid #d6d6d6;
}
```



#### 侧边栏社交小图标设置

- 打开主题配置文件`_config.yml`，`command+f`搜索`Social`，将你有的社交账号前面的`#`号去掉。格式为：

```yml
[社交平台名]: [社交地址] || [图标名称]
```

```yml
#social:
  GitHub: https://github.com/yourname || github
  简书: https://www.jianshu.com/u/63445e24e8bf || heartbeat
  掘金: https://juejin.im/user/5a371ae551882512d0607108 || spinner
  #E-Mail: mailto:yourname@gmail.com || envelope
  #Google: https://plus.google.com/yourname || google
  #Twitter: https://twitter.com/yourname || twitter
  #FB Page: https://www.facebook.com/yourname || facebook
  #VK Group: https://vk.com/yourname || vk
  #StackOverflow: https://stackoverflow.com/yourname || stack-overflow
  #YouTube: https://youtube.com/yourname || youtube
  #Instagram: https://instagram.com/yourname || instagram
  #Skype: skype:yourname?call|chat || skype
```

- 效果图如下：

![img](https://upload-images.jianshu.io/upload_images/3072214-8291624f1f133bb4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/624/format/webp)

-  图标可以去[Font Awesome Icon](http://fontawesome.io/icons/)网站去找，找到后复制名字到相应的位置即可。



#### 主页文章添加阴影效果

- 打开`Blog\themes\next\source\css\_custom\custom.styl`，添加以下代码：

```javascript
// 主页文章添加阴影效果
 .post {
   margin-top: 60px;
   margin-bottom: 60px;
   padding: 25px;
   -webkit-box-shadow: 0 0 5px rgba(202, 203, 203, .5);
   -moz-box-shadow: 0 0 5px rgba(202, 203, 204, .5);
  }
```

- 效果如下：

![img](https://upload-images.jianshu.io/upload_images/3072214-8d203b9886de2f5f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1000/format/webp)

 

#### 网站底部加上访问量

- 打开`Blog/themes/next/layout/_partials/footer.swig`文件，在`copyright`加上如下代码：

```javascript
<script async src="https://dn-lbstatics.qbox.me/busuanzi/2.3/busuanzi.pure.mini.js"></script>
```

![img](https://upload-images.jianshu.io/upload_images/3072214-edfa365aee1b5839.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1000/format/webp)

- 在适当的位置添加显示统计代码

```html
<div class="powered-by">
<i class="fa fa-user-md"></i><span id="busuanzi_container_site_uv">
  本站访客数:<span id="busuanzi_value_site_uv"></span>
</span>
</div>
```

![img](https://upload-images.jianshu.io/upload_images/3072214-63afac6bc7922943.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1000/format/webp) 

- 设置统计方式

```html
//pv的方式，单个用户连续点击n篇文章，记录n次访问量
<span id="busuanzi_container_site_pv">
    本站总访问量<span id="busuanzi_value_site_pv"></span>次
</span>

//uv的方式，单个用户连续点击n篇文章，只记录1次访客数
<span id="busuanzi_container_site_uv">
  本站总访问量<span id="busuanzi_value_site_uv"></span>次
</span>
```

- 效果图如下： 

  ![img](https://upload-images.jianshu.io/upload_images/3072214-5372d142a230191c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1000/format/webp)



#### 网站底部字数统计

- 安装hexo插件，切换到根目录：

```bash
npm install hexo-wordcount --save
```

- 在`Blog/themes/next/layout/_partials/footer.swig`末尾添加代码：

```html
<div class="theme-info">
  <div class="powered-by"></div>
  <span class="post-count">博客全站共{{ totalcount(site) }}字</span>
</div>
```

- 效果图如下图所示： 

  ![img](https://upload-images.jianshu.io/upload_images/3072214-6c9e57b47b80946a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1000/format/webp)

  

#### 设置网站的图标Favicon

- 在图标网站找一张你喜欢的图标（大：32x32 小：16x16），图标网站：[easyicon](http://www.easyicon.net/)或者[阿里巴巴矢量图标库](http://www.iconfont.cn/)。将下载下来的小图和中图放在`Blog/themes/next/source/images`，将默认的两张图片替换掉。命名和默认的一样也可以自己定义： 

![img](https://upload-images.jianshu.io/upload_images/3072214-cf67d50c1502275d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/786/format/webp)

- 修改主题配置文件，如果你自定义了图片名字，需要做修改：

```yml
# For example, you put your favicons into `hexo-site/source/images` directory.
# Then need to rename & redefine they on any other names, otherwise icons from Next will rewrite your custom icons in Hexo.
favicon:
  small: /images/favicon-16x16-next.png  //16X16小图
  medium: /images/favicon-32x32-next.png  //32X32大图
  apple_touch_icon: /images/apple-touch-icon-next.png  //apple-touch-icon 
  safari_pinned_tab: /images/logo.svg 
  #android_manifest: /images/manifest.json
  #ms_browserconfig: /images/browserconfig.xml
```



#### 实现文章统计功能

- 安装Hexo插件，参考**网站底部字数统计**。
- 编辑主题配置文件，配置如下：

```yml
# Post wordcount display settings
# Dependencies: https://github.com/willin/hexo-wordcount
post_wordcount:
  item_text: true
  wordcount: true
  min2read: true
  totalcount: true
  separated_meta: true
```

- 效果图： 

![img](https://upload-images.jianshu.io/upload_images/3072214-6e0b5bbaf686557c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/454/format/webp)



#### 添加网页顶部进度加载条

- 编辑主题配置文件，`command+F`搜索`pace`，将其值改为`ture`就可以了，选择一款你喜欢的样式。

```yml
# Progress bar in the top during page loading.
pace: ture
# Themes list:
#pace-theme-big-counter
#pace-theme-bounce
#pace-theme-barber-shop
#pace-theme-center-atom
#pace-theme-center-circle
#pace-theme-center-radar
#pace-theme-center-simple
#pace-theme-corner-indicator
#pace-theme-fill-left
#pace-theme-flash
#pace-theme-loading-bar
#pace-theme-mac-osx
#pace-theme-minimal
# For example
# pace_theme: pace-theme-center-simple
pace_theme: pace-theme-minimal
```



#### 底部隐藏由Hexo强力驱动、主题--NexT.Mist

- 打开`Blog/themes/next/layout/_partials/footer.swig`，注释掉相应代码。

```javascript
//用下面的符号注释，注释代码用下面括号括起来
<!-- -->

<!--
<span class="post-meta-divider">|</span>

{% if theme.footer.powered %}
  <div class="powered-by">{#
  #}{{ __('footer.powered', '<a class="theme-link" target="_blank" href="https://hexo.io">Hexo</a>') }}{#
#}</div>
{% endif %}

{% if theme.footer.powered and theme.footer.theme.enable %}
  <span class="post-meta-divider">|</span>
{% endif %}

{% if theme.footer.theme.enable %}
  <div class="theme-info">{#
  #}{{ __('footer.theme') }} &mdash; {#
  #}<a class="theme-link" target="_blank" href="https://github.com/iissnan/hexo-theme-next">{#
    #}NexT.{{ theme.scheme }}{#
  #}</a>{% if theme.footer.theme.version %} v{{ theme.version }}{% endif %}{#
#}</div>
{% endif %}

{% if theme.footer.custom_text %}
  <div class="footer-custom">{#
  #}{{ theme.footer.custom_text }}{#
#}</div>
{% endif %}
-->
```

 

#### 去掉底部重复字数统计

- 注释掉如下代码：

```javascript
<!--
  {% if theme.post_wordcount.totalcount %}
    <span class="post-meta-divider">|</span>
    <span class="post-meta-item-icon">
      <i class="fa fa-area-chart"></i>
    </span>
    {% if theme.post_wordcount.item_text %}
      <span class="post-meta-item-text">{{ __('post.totalcount') }}&#58;</span>
    {% endif %}
    <span title="{{ __('post.totalcount') }}">{#
    #}{{ totalcount(site, '0,0.0a') }}{#
  #}</span>
  {% endif %}
-->
```



#### 博文置顶

- 修改**hexo-generator-index**插件，把`node_modules/hexo-generator-index/lib/generator.js`中代码替换为：

```javascript
'use strict';
var pagination = require('hexo-pagination');
module.exports = function(locals){
  var config = this.config;
  var posts = locals.posts;
    posts.data = posts.data.sort(function(a, b) {
        if(a.top && b.top) { // 两篇文章top都有定义
            if(a.top == b.top) return b.date - a.date; // 若top值一样则按照文章日期降序排
            else return b.top - a.top; // 否则按照top值降序排
        }
        else if(a.top && !b.top) { // 以下是只有一篇文章top有定义，那么将有top的排在前面（这里用异或操作居然不行233）
            return -1;
        }
        else if(!a.top && b.top) {
            return 1;
        }
        else return b.date - a.date; // 都没定义按照文章日期降序排
    });
  var paginationDir = config.pagination_dir || 'page';
  return pagination('', posts, {
    perPage: config.index_generator.per_page,
    layout: ['index', 'archive'],
    format: paginationDir + '/%d/',
    data: {
      __index: true
    }
  });
};
```

- 文章添加Top值，值越大，越靠前：

```yml
---
title: Hexo-NexT主题配置
date: 2018-01-20 20:41:08
categories: Hexo
tags:
- Hexo
- NexT
top: 100
---
```

 

#### 修改字体大小

- 编辑`Blog/themes/next/source/css/_variables/base.styl`，`command+F`搜索`$font-size-base`，修改为你想要的大小：

```javascript
// Font size
$font-size-base           = 16px
```



#### 添加DaoVoice在线联系

- 首先到[DaoVoice](https://www.daocloud.io/)注册账号，登录成过后，进入到后台管理，点击**应用设置——>安装到网站**查看安装代码和AppID。
- 将安装代码添加到`Blog/themes/next/layout/_partials/head.swig`中：

```javascript
{% if theme.daovoice %}
  <script>
  (function(i,s,o,g,r,a,m){i["DaoVoiceObject"]=r;i[r]=i[r]||function(){(i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;a.charset="utf-8";m.parentNode.insertBefore(a,m)})(window,document,"script",('https:' == document.location.protocol ? 'https:' : 'http:') + "//widget.daovoice.io/widget/0f81ff2f.js","daovoice")
  daovoice('init', {
      app_id: "{{theme.daovoice_app_id}}"
    });
  daovoice('update');
  </script>
{% endif %}
```

  ![img](https://upload-images.jianshu.io/upload_images/3072214-4d76c0b99050cc8f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1000/format/webp)

- 编辑主题配置文件，添加如下代码：

```yml
# Online contact 
daovoice: true
daovoice_app_id: daovoice_app_id
```

- 效果图如下所示： 

  ![img](https://upload-images.jianshu.io/upload_images/3072214-47892289003cae0e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/226/format/webp)

  

#### 添加底部桃心

- 打开`Blog/themes/next/layout/_partials/footer.swig`搜索`with-love`，在[fontawesom](http://fontawesome.io/icons/)找到你喜欢的图标，在如下位置替换即可：



#### 添加侧栏推荐阅读

- 编辑主题配置文件，如下配置即可：

```yml
# Blog rolls
links_icon: link
links_title: 推荐阅读
#links_layout: block
links_layout: inline
links:
  Swift 4: https://developer.apple.com/swift/
  Objective-C: https://developer.apple.com/documentation/objectivec
```



#### 在文章底部增加版权信息

- 在目录`Blog/themes/next/layout/_macro/`，添加文件 `my-copyright.swig`，内容如下：

```javascript
{% if page.copyright %}
<div class="my_post_copyright">
  <script src="//cdn.bootcss.com/clipboard.js/1.5.10/clipboard.min.js"></script>
  
  <!-- JS库 sweetalert 可修改路径 -->
  <script src="https://cdn.bootcss.com/jquery/2.0.0/jquery.min.js"></script>
  <script src="https://unpkg.com/sweetalert/dist/sweetalert.min.js"></script>
  <p><span>本文标题:</span><a href="{{ url_for(page.path) }}">{{ page.title }}</a></p>
  <p><span>文章作者:</span><a href="/" title="访问 {{ theme.author }} 的个人博客">{{ theme.author }}</a></p>
  <p><span>发布时间:</span>{{ page.date.format("YYYY年MM月DD日 - HH:MM") }}</p>
  <p><span>最后更新:</span>{{ page.updated.format("YYYY年MM月DD日 - HH:MM") }}</p>
  <p><span>原始链接:</span><a href="{{ url_for(page.path) }}" title="{{ page.title }}">{{ page.permalink }}</a>
    <span class="copy-path"  title="点击复制文章链接"><i class="fa fa-clipboard" data-clipboard-text="{{ page.permalink }}"  aria-label="复制成功！"></i></span>
  </p>
  <p><span>许可协议:</span><i class="fa fa-creative-commons"></i> <a rel="license" href="https://creativecommons.org/licenses/by-nc-nd/4.0/" target="_blank" title="Attribution-NonCommercial-NoDerivatives 4.0 International (CC BY-NC-ND 4.0)">署名-非商业性使用-禁止演绎 4.0 国际</a> 转载请保留原文链接及作者。</p>  
</div>
<script> 
    var clipboard = new Clipboard('.fa-clipboard');
    $(".fa-clipboard").click(function(){
      clipboard.on('success', function(){
        swal({   
          title: "",   
          text: '复制成功',
          icon: "success", 
          showConfirmButton: true
          });
    });
    });  
</script>
{% endif %}
```

- 在目录`Blog/themes/next/source/css/_common/components/post/`下添加文件`my-post-copyright.styl`，添加以下代码：

```javascript
.my_post_copyright {
  width: 85%;
  max-width: 45em;
  margin: 2.8em auto 0;
  padding: 0.5em 1.0em;
  border: 1px solid #d3d3d3;
  font-size: 0.93rem;
  line-height: 1.6em;
  word-break: break-all;
  background: rgba(255,255,255,0.4);
}
.my_post_copyright p{margin:0;}
.my_post_copyright span {
  display: inline-block;
  width: 5.2em;
  color: #b5b5b5;
  font-weight: bold;
}
.my_post_copyright .raw {
  margin-left: 1em;
  width: 5em;
}
.my_post_copyright a {
  color: #808080;
  border-bottom:0;
}
.my_post_copyright a:hover {
  color: #a3d2a3;
  text-decoration: underline;
}
.my_post_copyright:hover .fa-clipboard {
  color: #000;
}
.my_post_copyright .post-url:hover {
  font-weight: normal;
}
.my_post_copyright .copy-path {
  margin-left: 1em;
  width: 1em;
  +mobile(){display:none;}
}
.my_post_copyright .copy-path:hover {
  color: #808080;
  cursor: pointer;
}
```

- 在`Blog/themes/next/source/css/_common/components/post/`添加文件`my-post-copyright.styl`，文件内容如下：

```javascript
.my_post_copyright {
  width: 85%;
  max-width: 45em;
  margin: 2.8em auto 0;
  padding: 0.5em 1.0em;
  border: 1px solid #d3d3d3;
  font-size: 0.93rem;
  line-height: 1.6em;
  word-break: break-all;
  background: rgba(255,255,255,0.4);
}
.my_post_copyright p{margin:0;}
.my_post_copyright span {
  display: inline-block;
  width: 5.2em;
  color: #b5b5b5;
  font-weight: bold;
}
.my_post_copyright .raw {
  margin-left: 1em;
  width: 5em;
}
.my_post_copyright a {
  color: #808080;
  border-bottom:0;
}
.my_post_copyright a:hover {
  color: #a3d2a3;
  text-decoration: underline;
}
.my_post_copyright:hover .fa-clipboard {
  color: #000;
}
.my_post_copyright .post-url:hover {
  font-weight: normal;
}
.my_post_copyright .copy-path {
  margin-left: 1em;
  width: 1em;
  +mobile(){display:none;}
}
.my_post_copyright .copy-path:hover {
  color: #808080;
  cursor: pointer;
}
```

- 修改`Blog/themes/next/layout/_macro/post.swig`，在如图位置添加以下代码：

```javascript
<div>
      {% if not is_index %}
        {% include 'my-copyright.swig' %}
      {% endif %}
</div>
```

![img](https://upload-images.jianshu.io/upload_images/3072214-52a341c7f39b9ba6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1000/format/webp)

- 在`Blog/themes/next/source/css/_common/components/post/post.styl`文件最后加入下面的代码：

```javascript
@import "my-post-copyright"
```

- 在Markdown文章中加入`copyright : ture`：

```yml
---
title: Hexo-NexT主题配置
date: 2018-01-20 20:41:08
categories: Hexo
tags:
- Hexo
- NexT
top: 100
copyright: ture
---
```

- 配置根目录下的`_config.yml`文件，配置为：

```yml
# URL
## If your site is put in a subdirectory, set url as 'http://yoursite.com/child' and root as '/child/'
url: https://wenmobo.github.io/  //你的网站地址
root: /
permalink: :year/:month/:day/:title/
permalink_defaults:
```

- 效果图如下所示：

![img](https://upload-images.jianshu.io/upload_images/3072214-f14827039037cb3d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1000/format/webp)



#### Hexo博客添加站内搜索

- NexT主题支持集成 Swiftype、 微搜索、Local Search 和 Algolia。下面介绍Local Search的安装吧。
- 安装 hexo-generator-search

```bash
npm install hexo-generator-search --save
```

- 安装 hexo-generator-searchdb

```bash
 npm install hexo-generator-searchdb --save 
```

-  编辑站点配置文件，添加以下内容 

![img](https://upload-images.jianshu.io/upload_images/3072214-aff43f0e07e85647.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/972/format/webp)



```yml
search:
  path: search.xml
  field: post
  format: html
  limit: 10000
```

- 编辑主题配置文件，设置`Local search`enable为`ture` 

```yml
# Local search
# Dependencies: https://github.com/flashlab/hexo-generator-search
local_search:
  enable: ture
  # if auto, trigger search by changing input
  # if manual, trigger search by pressing enter key or search button
  trigger: auto
  # show top n results per article, show all results by setting to -1
  top_n_per_article: 1
```

- 效果如下图所示：

![img](https://upload-images.jianshu.io/upload_images/3072214-7d4440ed648d76c7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/972/format/webp) 

 



 

 

 