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

```
$ sudo apt-get install ruby-full
```

然后安装jekyll

```
$ gem install jekyll
```

这样jeykll的安装就已经完成了

### jekyll的运行
安装了Jekyll的Gem包之后，就可以在命令行中使用Jekyll命令了。有以下这些用法：
```
$ jekyll build
# => 当前文件夹中的内容将会生成到 ./site 文件夹中。

$ jekyll build --destination <destination>
# => 当前文件夹中的内容将会生成到目标文件夹<destination>中。

$ jekyll build --source <source> --destination <destination>
# => 指定源文件夹<source>中的内容将会生成到目标文件夹<destination>中。

$ jekyll build --watch
# => 当前文件夹中的内容将会生成到 ./site 文件夹中，
#    查看改变，并且自动再生成
```

Jekyll 同时也集成了一个开发用的服务器，可以让你使用浏览器在本地进行预览。

```
jekyll serve
# => 一个开发服务器将会运行在 http://localhost:4000/

$ jekyll serve --detach
# => 功能和`jekyll serve`命令相同，但是会脱离终端在后台运行。
#    如果你想关闭服务器，可以使用`kill -9 1234`命令，"1234" 是进程号（PID）。
#    如果你找不到进程号，那么就用`ps aux | grep jekyll`命令来查看，然后关闭服务器。[更多](http://unixhelp.ed.ac.uk/shell/jobz5.html).

$ jekyll serve --watch
# => 和`jekyll serve`相同，但是会查看变更并且自动再生成。
```

还有一些可以配置的配置选项. 很多配置选项既可以在命令行中作为标识(flags)设定，也可以在源文件根目录中的 _config.yml 文件中进行设定。Jekyll 会自动加载这些配置。比如你在你的 _config.yml 文件中添加了下面几行：

```
source:      _source
destination: _deploy
```

那么就等价于执行了以下两条命令：

```
$ jekyll build
$ jekyll build --source _source --destination _deploy
```

## 部署方法

### GitHub Pages

Github Pages 是面向用户、组织和项目开放的公共静态页面搭建托管服 务，站点可以被免费托管在 Github 上，你可以选择使用 Github Pages 默 认提供的域名 github.io 或者自定义域名来发布站点。Github Pages 支持 自动利用 Jekyll 生成站点，也同样支持纯 HTML 文档，将你的 Jekyll 站 点托管在 Github Pages 上是一个不错的选择。

Github Pages 依靠 Github 上项目的某些特定分支来工作。Github Pages 分为两种基本类型：用户/组织的站点和项目的站点。搭建这两种类型站 点的方法除了一小些细节之外基本一致。

用户和组织的站点被放置在一个特殊的专用仓库中，在该仓库中只存在 Github Pages 的相关文件。这个仓库应该根据用户/组织的名称来命名， 例如： @mojombo 的用户站点仓库 应该被命名为 mojombo.github.io 。

仓库中master分支里的文件将会被用来生成 Github Pages 站点，所以请 确保你的文件储存在该分支上。

详细见[官方文档](http://jekyll.com.cn/docs/github-pages/)

### 服务器部署

部署在自己的服务器上，首先需要安装上面jekyll运运行的环境，然后将`_site`文件夹`scp`到服务器上，运行`jekyll serve &`命令即可

## 遇到的坑

出现下面报错需要在`_config.yml`添加一行`plugins: [jekyll-paginate]`

```
Deprecation: You appear to have pagination turned on, but you haven't included the `jekyll-paginate` gem. Ensure you have `plugins: [jekyll-paginate]` in your configuration file.
```

出现下面的报错需要在`_config.yml`中将`relative_permalinks: true`这一行注释掉

```
Since v3.0, permalinks for pages in subfolders must be relative to the site source directory, not the parent directory. Check https://jekyllrb.com/docs/upgrading/ for more info.
```



