---
title: jquery 自动生成目录插件 autoMenu
description: jquery 自动生成目录插件 autoMenu，支持两级目录，可自定义 h1、h2、h3、h4、h5、h6。
categories: jquery
tags: jquery autoMenu
---

* content
{:toc}

## 需求
最近在写网站的教程，有些教程很长，阅读过程中，想回头找找之前的内容，发现很麻烦，于是想到能不能给文章生成一个目录，就像我的博客这样。
分析了文章和博客源码后，发现是可行的，给文章重要的部分加上标题，用 h2、h3 标签区分目录的级别。
我的博客提交后，github 会自动生成目录，没有现成的代码。

## 实现
自己写的思路是，jquery 遍历所有 h2 和 h3 标签，给这些标签加上 id 属性，再循环生成一个目录，用锚点和相应的 id 关联起来。
看了网上不少文章，基本也是这个思路，偶然发现一个 jquery 插件，很符合要求，就直接拿来用了。
这个插件叫 autoMenu，首先引入样式和 js 文件：

``` html
<link rel="stylesheet" href="css/jquery.autoMenu.css">
<script src="https://cdn.bootcss.com/jquery/1.10.2/jquery.min.js"></script>
```

再加上如下标签就可以了：

``` html
<div class="autoMenu" id="autoMenu" data-autoMenu></div>
```

这个插件只能支持两级目录，默认给 h3 和 h4 标签生成目录，如果想要灵活配置，可以用如下代码：

``` js
$(function(){
  $("#autoMenu").autoMenu({
    levelOne : 'h2', //一级标题
    levelTwo : 'h3',  //二级标题（暂不支持更多级）
    width : 200, //容器宽度
    height : 400, //容器高度
    padding: 20, //内部间距
    offTop : 100 //滚动切换导航时离顶部的距离
  });
})
```

## 演示&源码
演示：[jquery 自动生成目录插件 autoMenu](https://zhaoxinglong.com/demo/js/autoMenu/)
源码：[jquery 自动生成目录插件 autoMenu](http://code.52zxw.net/detail/id/1508)
