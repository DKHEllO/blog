---
layout: post
title: Ubuntu下搭建jekyll
---

## jekyll
### jekyll是什么
[jekyll中文文档](http://jekyll.com.cn)这样描述:
> Jekyll 是一个简单的博客形态的静态站点生产机器。它有一个模版目录，其中包含原始文本格式的文档，通过Markdown(或者Textile)以及Liquid转化成一个完整的可发布的静态网站，你可以发布在任何你喜爱的服务器上。Jekyll也可以运行在GitHub Page上，也就是说，你可以使用GitHub的服务来搭建你的项目页面、博客或者网站，而且是完全免费的。

### jekyll的几个优点
- 简单
  无需数据库、评论功能，不需要不断的更新版本，只用关心你的博客内容。
- 静态
  只用 Markdown(或Textile)、Liquid、HTML&CSS就可以构建可部署的静态网站。
- 博客形态
  自定义地址、分类、页面、博客内容 以及 自定义的布局设计 都是系统中的一等公民。

### jekyll的安装
jekyll安装需要以下环境
- Ruby
- RubGems
- Linux,Unix or MacOS X

[Ruby](https://www.ruby-lang.org/en/documentation/installation/)的安装，这里以Debian,Ubuntu为例:

`$ sudo apt-get install ruby-full`

然后安装jekyll

`$ gem install jekyll`

这样jeykll的安装就已经完成了
