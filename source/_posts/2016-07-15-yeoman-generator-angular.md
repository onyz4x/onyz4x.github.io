---
id: 172
title: yeoman，generator-angular
date: 2016-07-15T11:29:06+00:00
author: crazy4x
layout: post
categories:
  - AngularJS
---
## 前言

最近一个月新项目启动，为了更快速的搭建架构使用了yeoman(1.8.3)和generator-angular。

yeoman是一个脚手架工具，而generator-angular就是Yeoman generator for AngularJS，专门为Angular创建的一个脚手架工具。旨在提供快速搭建前端架构，提供开发环境，代码合并压缩混淆，一系列的自动化操作。

&nbsp;

### 安装

首先yeoman 是nodejs下的工具，所以肯定要有nodejs和npm

用npm全局安装`yo`, `grunt-cli`, `bower`, `generator-angular` and `generator-karma`

如果你要使用sass，还需要安装Ruby 和 Compass

接下来创建一个项目的文件夹，在文件夹下运行

    yo angular [app-name]

安装的每一步选择在这里我不具体列举出来

值得注意的是，安装过程gulp和grunt的选择，在generator-angular中gulp还是实验性质的，所以更推荐grunt，

安装完成后你会发现项目文件夹下多了一大堆的文件

在项目文件夹根目录下运行grunt serve页面会自动打开，你编辑代码页面也会自动刷新

grunt build命令是用于创建发布版本，文件的工程文件夹在app内，而dist就是build后生成出来的

&nbsp;

### 用法

  * [angular:controller](https://github.com/yeoman/generator-angular#controller)
  * [angular:directive](https://github.com/yeoman/generator-angular#directive)
  * [angular:filter](https://github.com/yeoman/generator-angular#filter)
  * [angular:route](https://github.com/yeoman/generator-angular#route)
  * [angular:service](https://github.com/yeoman/generator-angular#service)
  * [angular:provider](https://github.com/yeoman/generator-angular#service)
  * [angular:factory](https://github.com/yeoman/generator-angular#service)
  * [angular:value](https://github.com/yeoman/generator-angular#service)
  * [angular:constant](https://github.com/yeoman/generator-angular#service)
  * [angular:decorator](https://github.com/yeoman/generator-angular#decorator)
  * [angular:view](https://github.com/yeoman/generator-angular#view)

yeoman的主要用法如上：

举例，创建一个controller只需要运行命令

<pre class="lang:default decode:true ">yo angular:controller home</pre>

yeoman会自动生成一个home.js并引入到index.html文件，并且home.js里已经写好了一个叫做HomeCtrl的controller，甚至已经在test文件夹内生成了一个用作单元测试的js文件，

这样把很多的人工操作自动化后会省去很多麻烦，而且能更好的规避错误。

&nbsp;

angular:route的方法在建立路由的同时同时建立了controller和view，是不是感觉非常方便，

但是由于angular-route的局限性，我还是使用了ui-router，这样一来angular:route的方法我就没有使用了

但是总体上还是非常方便的

更多细节，可以参考<a href="https://github.com/yeoman/generator-angular" target="_blank">https://github.com/yeoman/generator-angular</a>