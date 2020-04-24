---
id: 203
title: angular2 官方教程中 关于templateUrl和styleUrls 引用文件路径的问题
date: 2017-04-14T09:56:26+00:00
author: crazy4x
layout: post
categories:
  - Angular
---

在跟随 angular 官方教程练习的过程中发现一个问题，关于`@Component`[装饰器](https://www.angular.cn/docs/ts/latest/glossary.html#decorator ""decorator" explained")<span class="ng-scope">函数中 templateUrl 和 styleUrls 路径的问题，具体表现为</span>

<!--more-->

&nbsp;

在教程中 templateUrl 和 styleUrls 中引用的模板路径都是类似

<pre class="hljs http"><code>    &lt;span class="hljs-attribute">templateUrl&lt;/span>: &lt;span class="hljs-string">'./heroes.component.html',&lt;/span>
    &lt;span class="hljs-attribute">styleUrls&lt;/span>: &lt;span class="hljs-string">['./heroes.component.css']&lt;/span></code></pre>

但是实际上如果定义了 moduleId，就会出现 404 的问题，找不到文件

<pre class="hljs ruby"><code>&lt;span class="hljs-variable">@component&lt;/span>({
    &lt;span class="hljs-symbol">moduleId:&lt;/span> &lt;span class="hljs-class">&lt;span class="hljs-keyword">module&lt;/span>.&lt;span class="hljs-title">id&lt;/span>&lt;/span>
    ...
    ...
})</code></pre>

![](https://sfault-image.b0.upaiyun.com/705/487/705487986-58eddef99c310_articlex)

这时候只能把文件路径改成如下，才能正确加载

<pre class="hljs http"><code>    &lt;span class="hljs-attribute">templateUrl&lt;/span>: &lt;span class="hljs-string">'heroes.component.html',&lt;/span>
    &lt;span class="hljs-attribute">styleUrls&lt;/span>: &lt;span class="hljs-string">['heroes.component.css']&lt;/span></code></pre>

疑问

<pre class="hljs"><code>1.这里moduleId作用是什么
2.为什么会影响到模板和样式文件的路径获取
3.正确的写法是什么</code></pre>

&nbsp;

---

&nbsp;

&nbsp;

&nbsp;

从官方教程的代码中可以看到模块加载器是 systemjs

首先参考官方的文档

-组件样式：<https://angular.cn/docs/ts/latest/cookbook/component-relative-paths.html>

-相对于组件的路径：<https://angular.cn/docs/ts/latest/cookbook/component-relative-paths.html>

&nbsp;

从上面两个文档中，我们知道的是 Angular 不可能知道在运行期这些文件的正确位置，Angular 能够确定的唯一的位置是首页`index.html`的 URL，也就是应用的根目录。 所以，默认情况下，它只能计算相对于`index.html`的模板和样式表路径。 这就是为什么我们以前用`app/`基准路径的前缀来写文件的 URL。Angular 应用可能被用多种方式加载：独立文件、SystemJS 包、CommonJS 包等等。 用来生成模块的格式可以是任何格式。 甚至可能完全没有写成模块化代码。

&nbsp;

但是这里并没有详细解释为什么 systemjs 打包运行的情况下用 moduleId 出现的问题

而后另外一篇文章才有详细说明

<https://blog.thoughtram.io/angular/2016/06/08/component-relative-paths-in-angular-2.html>

里面介绍了几种不同的打包模块下的写法

&nbsp;

&nbsp;
