---
layout: post
title: 个人博客搭建之Hexo和Jekyll - 搭建篇
date: 2017-12-03 15:32:24.000000000 +09:00
---

###### 本文介绍两种博客的搭建：Github Pages +Hexo，Github Pages +Jekyll

##### 简介：

[极客学院翻译—GitHub Pages](http://wiki.jikexueyuan.com/project/github-pages-basics/) 可以为你或者你的项目提供介绍网页，它是由 GitHub 官方托管和发布的。你可以使用 GitHub 
提供的页面自动生成器。也可以做个人博客，是个轻量级的博客系统，没有麻烦的配置。使用标记语言如Markdown，不需自己搭建服务器，还可以绑定自己的域名。

[Hexo](https://hexo.io/)是一个npm包，在node环境上运行，他的功能就是将你的文章（.md文件）生成为静态html文件。虽然他在生成静态文件时需要你的本地机器安装node环境，但部署你的站点时则不需要后台环境，这一点不同于php驱动的wp，typecho和node驱动的ghost，你只需要一个托管静态资源的云平台即可。

[Jekyll](http://jekyllcn.com/) l是一种简单的、适用于博客的、静态网站生成引擎。它使用一个模板目录作为网站布局的基础框架，支持Markdown、Textile等标记语言的解析，提供了模板、变量、插件等功能，最终生成一个完整的静态Web站点。说白了就是，只要安装Jekyll的规范和结构，不用写html，就可以生成网站。

## 一 、GiHub Pages

你需要拥有一个GitHub账号，注册或者登录 [GitHub](https://github.com)
创建仓库并填写好对应名称：

#### <img src="https://ljykangaroo.github.io/public/image/1.png" height="568" hspace="20">

<img src="https://ljykangaroo.github.io/public/image/2.png" height="568" hspace="20">

**Tips**： Respository name 中一定要输入：`你的用户名.github.io`，然后直接点 `Create repository“`按钮完成创建。

**区别：**jekyll的现在可把仓库cloning下来，看初步效果。hexo的往下。

## 二、Hexo

首先搭配好环境：由于Hexo是在node环境运行。所以我们先安装node环境

Nodejs安装：[官网](https://nodejs.org/en/download/) and 终端运行:

```shell
 brew install node
```

使用以下命令验证是否安装成功

```shell
node -v
npm -v
```

Hexo安装：[官网](https://hexo.io/) and 终端运行：

```shell
npm install -g hexo
```

这里可能会出现安装失败的错误,

```
ERROR debug.log等错误
```

这种时候终端运行继续完成安装：

```shell
sudo npm install --unsafe-perm --verbose -g hexo
```

**Tips：**其他错误可以百度hexo安装与配置解决。

##### Hexo使用命令

```shell
hexo s --debug  # 启动服务预览
```
在浏览器上输入网址：[http://localhost:4000/](http://localhost:4000/)就可以预览博客效果了。（相对于Jekyll的一键提交式的来说复杂）

## 三、Jekyll

首先将主题下载到本地[Vno-Jekyll](https://github.com/onevcat/vno-jekyll)，

相对于Hexo。jekyll不用搭建什么环境，因为mac已经自带了ruby了。

直接打开终端执行	

```shell
sudo gem install jekyll
```

淘宝镜像可能会找不到Jekyll。

更换镜像：

`gem source -r https://ruby.taobao.org/`  (移除淘宝镜像)

`gem source -a https://rubygems.org/`  (添加新镜像)

再次执行`sudo gem install jekyll`等待。

把创建好的github.io clone到你的电脑下，选择你自己想要的目录。把下载好的主题解压到代码仓库下。

进入主题文件目录`cd /Users/Jekyll/用户名.github.io`

执行
```shell
bundle install
```

没有bundle就先执行`sudo gem install bundle`再install

然后就可以开启Jekyll的调试了。`bundle exec jekyll serve`

看见  Server address: http://127.0.0.1:4000/就可以打开成效了。

最后可以git提交代码。浏览器输入`(用户名).github.io` 。

**Tips：**[Hexo主题](https://hexo.io/themes/)   and   [Jekyll主题](http://jekyllthemes.org/)