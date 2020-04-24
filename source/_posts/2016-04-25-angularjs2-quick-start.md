---
title: Angular2：5分钟快速入门 (for javascript)
date: 2016-04-25T18:05:14+00:00
author: crazy4x
categories:
  - Angular
tags:
  - Angular2
---

让我们从零开始使用 JavaScript 建立一个超简单的 Angular2 应用，还可以使用 TypeScript 和 Dart

## 看看运行效果

运行[在线示例](https://angular.io/resources/live-examples/quickstart/js/plnkr.html/)能快速看到看到 Angular 2 应用的实例，运行结果如下图：

<!--more-->

文件目录结构如下

![](http://www.ziwuo.com/wp-content/uploads/2016/04/QQ截图20160505105117.jpg)

从功能上看只有一个 index.html 和两个 app 文件夹中的 JavaScript 文件。

当然，我们不会只在 plunker 上建立应用，接下来展示一个实际操作流程

- 建立我们的开发环境
- 为我们的应用编写 Angular 根组件
- 引到它控制主页面
- 编写主页面

> 我们真的可以在五分钟内建立快速入门，如果我们按照指示并且忽略评论。

> 我们大多数人会感兴趣的“为什么”以及“如何”，这将需要更长的时间。

## 开发环境

我们需要一个应用程序项目文件夹，一些库和编辑器。

### 创建一个新项目文件夹

### 加入我们需要的库文件

我们建议使用 npm 包管理器来采集和管理我们的开发库。

> 在这个文档中会大量繁复使用 npm 包管理器。

添加一个 package.json 文件到项目文件夹，复制粘贴以下内容：

> package.json 的设置细节在下面的附录中会有解释

打开一个 terminal 窗口（Windows 系统在 cmd 中打开）运行下面的 npm 命令</em>

> [AngularJS,自定义 filter 实现文字和拼音的双过滤](http://www.ziwuo.com/archives/24.html) 在安装过程中可能会出现红色错误消息。 别理他们。安装会成功。请参阅下面的附录以获取更多信息。

## 我们的第一个 Angular 组件

组件是最基本的 Angular 概念。组件管理着视图。

从技术上讲，一个组件是控制视图模板的类。在因为 Angular 应用中我们会建立很多组件。这是我们的第一次尝试，所以我们做一个简单的。

### 创建一个应用程序源的子文件夹

规范上把应用代码都放在 app 的子文件夹里面

### 添加组件文件

添加一个 app.component.js 文件复制粘贴以下代码

我们通过 Component 和 Class 的方法创建一个名为 AppComponent 的可视化组件 ，属于全局 Angular 的核心命名方法，ng.core。

Component 方法具有两个属性。Class 方法是我们运行组件的地方，用属性和方法来绑定视图和 UI 的行为。

回顾以下详细代码

### Modules 模块

Angular 应用程序是模块化的。它们包括许多文件每个文件都有它专门的用处。

ES5 JavaScript 本身没有本地模块系统。我们可以使用一些流行的第三方模块系统。作为代替，为了简便起见和避免优先级问题，我们会为应用程序创建一个单一的全局命名空间。

我们称呼它为 app ，我们将所有的代码构件到这一个全局对象。

不要去污染全局命名空间。所以每个文件的代码围绕 IIFE（“立即执行函数表达式”）。

我们绕过全局应用命名空间对象到 IIFE，用一个空对象初始化。

大多数应用程序文件通过添加东西到命名空间输出这个东西。例如我们的 app.component.js 文件输出 AppComponent。

更复杂的应用会有 AppComponent 的子组件。一个更复杂的应用程序将有更多的文件和模块。

这个快速入门应用是很简单的;只有一个我们需要的组件。但是模块依然在这样一个小小的应用程序发挥了一个基本的组织作用。

模块依赖于其他模块。在 JavaScript [11.](http://loyal-friend.de/2015/05/11-september-2008/) Angular 应用中，当我们需要另一个模块提供的东西，我们从 app 对象获取它。当另一个模块涉及到 AppComponent，它从 app.AppComponent 中获取它。

Angular 本身也是模块化的。它是一个库模块的集合。每个库本身由一些相关的功能模块组成。

当我们需要 Angular 的某些东西，我们用 ng 对象来获取。

### The Class definition object?类定义对象

在文件的底部是一个空的、不做任何事情的类定义对象。当我们准备好建立一个独立应用，我们以用属性和应用逻辑来扩展此对象。在快速入门中我们 AppComponent 类只有一个空的构造，是因为我们不需要它在这个快速入门中做任何事情。

### The Component definition object?组件定义对象

ng.core.Component()告诉 Angular 这个类定义对象是一个 Angular 组件。配置对象传递给 ng.core.Component()方法两个字段，一个 selector 和一个 template。

selector 为名为 my-app 的 HTML 元素指定一个简单的 CSS 选择器。Angular 无论在 HTML 中哪里遇到 my-app 元素就会创建和显示 AppComponent 实例 。

> [Een](http://www.managing-it.nl/management-artikelen/teamwork/een-tevreden-team-is-een-sterk-team/) 记住 my-app 选择器，我们会在编写 index.html 中用到

> [cheap nba jerseys](http://www.cheapelitejerseys.us.com) 模板属性保存组件的同步模板。模板是 HTML 的一种形式，它告诉 Angular 如何呈现一个视图。我们的模板是一个单行的 HTML 显示“My First Angular App”。

> 现在我们需要一些东西来告诉 Angular 来加载这个组件。

### Bootstrap it! 引导

添加一个新文件 main.js 到 app 文件夹

我们需要两样东西来启动应用程序：

- Angular 的浏览器引导功能
- 我们刚写的应用根组件

两个东西都在我们的“命名空间”里。引导它，传递到根组件类型，AppComponent。

> 了解为什么引到和 main.js 的详情点击[链接](https://angular.io/docs/js/latest/quickstart.html#main)

我们要求 Angular 在浏览器启动应用程序与我们的根组件。Angular 会放在哪里呢？

## 添加 index.html 文件

Angular 会在 index.html 的特定位置的显示我们的应用程序。现在是时候创建这个文件。

我们不会把 index.html 放在 app 文件夹。我们把它放在上一级项目的根文件夹。

现在创建 index.html

在 HTML 中有三个值得关注的部分：

- 加载需要的 JavaScript 库
- 加载我们的 JavaScript 文件，注意它们的顺序（app.component.js 放在 main.js 前面）。
- 我们在<body>中加入<my-app>标签。这是我们的应用程序运行的地方。

当 Angular 调用 main.js 引导功能，它会读取 AppComponent 元数据，发现 my-app 选择器，找到名为 my-app 的元素，并在这个标签内加载我们的应用程序。

## Run! 运行

打开 terminal 窗口输入以下命令：

该命令会在浏览器中运行一个名叫 lite-server 的静态服务器加载 index.html，并在应用文件改变时刷新浏览器。

片刻后，一个浏览器标签页会打开并显示

恭喜！我们做好了

> 如果你一直看到 loading&#8230;界面，查看 ES2015 的浏览器支持

### 做一些改动

尝试更改消息为“My SECOND [前端编码规范](http://www.ziwuo.com/archives/6.html) Angular 2 app”

lite-server 会一直监听，当检测到变化，会刷新浏览器，并显示修改后的消息。

这是开发一个应用程序的一个很巧妙的方法！

关闭终端窗口，当我们完成终止服务器。

##最终的文件结构</em></h2>

我们最终的项目文件夹结构看起来是这样的：

![](http://www.ziwuo.com/wp-content/uploads/2016/04/QQ截图20160504153700.jpg)

所有的文件：

## Wrap Up ?打包

我们的第一个应用程序不会去做太多。它基本上是 Angular2 版本的“Hello, World”?。

我们保持了它的简洁：编写一个小 Angular 组件，给 index.html 增加了一些 JavaScript 库，用一个静态文件服务器启动。这就是预期的“Hello, [Online](http://philadelphiaeaglesjerseyspop.forumcity.com/viewtopic.php?p=20#20) World”应用程序需要做的。

但是我们需要 Angular2 做的更多。

好消息是，大部分设置我们可以丢到脑后。我们可能只会触及 package.json 的更新。除了为我们的应用“模块”增加脚本文件，我们很可能只有当我们需要添加一个库或 CSS 样式表才会打开 index.html。

下一步，构建一个小的应用程序演示，用 Angular2 建立更好的东西。

[加入我们的英雄教程之旅！](https://angular.io/docs/js/latest/tutorial)

## 附录

这章由几部分快速阐述几个重要点

这里没有详细的资料，如果你好奇可以继续查阅。

<div class="l-main-section">
</div>

### 附录：库

我们载入下面的脚本文件

我们开始于一个 Internet Explorer 填充工具。 IE 需要填充工具来运行依赖于 ES2015 promises 和动态加载模块的应用程序。大多数应用程序需要这些功能并且能在 Internet Explorer 中运行。

接下来是 Angular2 的 polyfills，zone.js 和 Reflect.js，跟随 the Reactive Extensions RxJS 库.

> 我们的快速入门没有使用 RxJS 库,但是任何实质的应用都想要 RxJS 库，我们在快速入门项目中加入库，以后以后忘记。

最后，我们载入了 Angular2 本身的 web 开发版本

以后为了提升产品质量（载入时间，内存占用）我们会做出不同的选择

### 附录： package.json

npm 是一个流行的包管理器，Angular 应用开发者依靠它获得和管理应用依赖的库。

我们在 npm 中指定我们需要的库文件 package.json.

The Angular team suggests the packages listed [wholesale nfl jerseys](http://www.newenglandpatriotsjerseyspop.com) in the `dependencies` and `devDependencies` sections listed [wholesale mlb jerseys](http://www.dallascowboysjerseyspop.com) in this file:

Angular 官方建议把包的清单列入文件的 dependencies 和 devDependencies 部分：

> 还有一些其他的包可供选择。我们推荐这个很好使用的专门设置。现在和我们一起使用吧。以后可以随意替换来适应你的习惯和经验。

> 一个 package.json 文件有一个可供选择的 script 部分，方便我们定义有用的命令来进行开发和建设任务。我们已经包含了一些这样的脚本在我们的 package.json：

我们可以看到如何在服务器上运行这些命令

我们使用专用的 npm start 命令，但是它所做的只是运行`npm run lite`。

我们用这样的方式执行 npm 脚本：`npm run` + 脚本名。下面是这些脚本所做的：

- npm run lite &#8211; 运行 lite-server,一个轻量的静态文件服务器，由 John Papa 编写和维护，对 Angular 应用使用路由有很好的支持。

### 附录: Npm 的错误和警告

如果没有以`npm <a href="http://www.ziwuo.com/archives/36.html">AngularJS，实现contenteditable的双向绑定</a> ERR!`开头的消息出现在 npm 安装的尾部表示一切都没问题。也许会有一些`npm WARN`的消息，这是完全没问题的。

我们有时候会看到`npm WARN`的消息在一系列的`gyp ERR!`的消息后面。忽略它。一个包可能会使用`node-gyp`重新编译它自己。如果重新编译失败，包就会还原（通常是预发布版本）一切都能正常使用。

只要确定没有`npm ERR!`消息在`npm install`的最后面。

### 附录: main.js

#### 引导特定的平台

我们从`ng.platformBrowserDynamic`中使用`bootstrap`功能，而不是`ng.core`，这里有一个非常好的理由。

只有在所有平台的目标功能我们才称之为&#8221;core&#8221;。大部分 Angular 应用只运行在浏览器上，我们大部分时间只从这个库调用引到函数。如果我们总是为浏览器来编写这就是一个标准的&#8221;core&#8221;

但是它有可能在不同环境载入一个组件。我们可能在一个移动设备的`Apache Cordova`或者`NativeScript`上载入它。我们也许希望渲染应用的第一页来提高启动性能或便于搜索引擎优化。

这些目标需要我们从不同的库中引入不同的引导函数

#### 为什么要建立一个单独的 main.js 文件？

main.js 文件很小。这只是个快速入门项目。你可以把它合并到`app.component.js`文件来避免复杂度。

我们不这么做的原因是：

1. 正确的做法很容易

2. 便于测试

3. 便于重复使用

4. 关系的分离

5. [Федоровна](http://profservis59.ru/717-2/) 我们学习到导入和导出

#### 这很简单

虽然这是额外的步骤和文件，但是能有多难呢？

我们可以看到一个单独的`main.js`文件有益于大部分应用，良好的开发习惯能降低成本。

####便于测试

及时一开始就知道不会去测试，我们也应该从开始就要考虑便于测试。

当组件内同时有调用`bootstrap`是很难去单元测试这个组件的。当我们尽快载入组件文件来测试组件的时候，`bootstrap`函数会尝试去载入浏览器的应用。它会抛出一个错误因为我们没有准备去运行整个应用而只运行组件。

重定位`bootstrap`函数到`main.js`来消除这个伪错误，留给我们干净的组件模块文件。

#### 重复使用性

随着应用的发展我们重构、重命名、重定位文件。当文件调用`bootStrap`我们不能做任何事情，我们不能移动它，不能再另一个应用中重复使用，不能为了性能在服务器上预渲染组件

#### 关系的分离

组件的职责是呈现和管理视图。

应用启动和视图管理没有任何关系。这是关系的分离。我们在测试和重用中遇到的摩擦源于这种不必要的职责混合。

#### 导入和导出

当编写一个单独的 main.js 文件我们学习到了一个必要的 Angular 技巧：如何从一个模块中导出和导入到另一个途径的命名空间的概念。在以后的 Angular 学习中我们会做很多这样的事。
