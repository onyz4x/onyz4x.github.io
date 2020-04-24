---
id: 172
title: yeoman，generator-angular
date: 2016-07-15T11:29:06+00:00
author: crazy4x
layout: post
categories:
  - AngularJS
  - yeoman
---

## 前言

最近一个月新项目启动，为了更快速的搭建架构使用了 yeoman(1.8.3)和 generator-angular。

yeoman 是一个脚手架工具，而 generator-angular 就是 Yeoman generator for AngularJS，专门为 Angular 创建的一个脚手架工具。旨在提供快速搭建前端架构，提供开发环境，代码合并压缩混淆，一系列的自动化操作。

&nbsp;

### 安装

首先 yeoman 是 nodejs 下的工具，所以肯定要有 nodejs 和 npm

用 npm 全局安装`yo`, `grunt-cli`, `bower`, `generator-angular` and `generator-karma`

如果你要使用 sass，还需要安装 Ruby 和 Compass

接下来创建一个项目的文件夹，在文件夹下运行

    yo angular [app-name]

安装的每一步选择在这里我不具体列举出来

值得注意的是，安装过程 gulp 和 grunt 的选择，在 generator-angular 中 gulp 还是实验性质的，所以更推荐 grunt，

安装完成后你会发现项目文件夹下多了一大堆的文件

在项目文件夹根目录下运行 grunt serve 页面会自动打开，你编辑代码页面也会自动刷新

grunt build 命令是用于创建发布版本，文件的工程文件夹在 app 内，而 dist 就是 build 后生成出来的

&nbsp;

### 用法

- [angular:controller](https://github.com/yeoman/generator-angular#controller)
- [angular:directive](https://github.com/yeoman/generator-angular#directive)
- [angular:filter](https://github.com/yeoman/generator-angular#filter)
- [angular:route](https://github.com/yeoman/generator-angular#route)
- [angular:service](https://github.com/yeoman/generator-angular#service)
- [angular:provider](https://github.com/yeoman/generator-angular#service)
- [angular:factory](https://github.com/yeoman/generator-angular#service)
- [angular:value](https://github.com/yeoman/generator-angular#service)
- [angular:constant](https://github.com/yeoman/generator-angular#service)
- [angular:decorator](https://github.com/yeoman/generator-angular#decorator)
- [angular:view](https://github.com/yeoman/generator-angular#view)

yeoman 的主要用法如上：

举例，创建一个 controller 只需要运行命令

<pre class="lang:default decode:true ">yo angular:controller home</pre>

yeoman 会自动生成一个 home.js 并引入到 index.html 文件，并且 home.js 里已经写好了一个叫做 HomeCtrl 的 controller，甚至已经在 test 文件夹内生成了一个用作单元测试的 js 文件，

这样把很多的人工操作自动化后会省去很多麻烦，而且能更好的规避错误。

&nbsp;

angular:route 的方法在建立路由的同时同时建立了 controller 和 view，是不是感觉非常方便，

但是由于 angular-route 的局限性，我还是使用了 ui-router，这样一来 angular:route 的方法我就没有使用了

但是总体上还是非常方便的

更多细节，可以参考<a href="https://github.com/yeoman/generator-angular" target="_blank">https://github.com/yeoman/generator-angular</a>
