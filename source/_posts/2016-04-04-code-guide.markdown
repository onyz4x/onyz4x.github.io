---
layout: post
title:  "前端编码规范"
date:   2018-09-10 11:26:03 +0800
categories: jekyll update
toc: true
---

## 前言
首先，写这篇代码规范是为了我自己在以后的项目中方便引用，让前端人员统一标准，方便在开发中保持代码的一致性，HTML和CSS的规范参照 [bootstrap编码规范](https://codeguide.bootcss.com/) ，以下多为JS规则

eslint 统一代码规范，通常推荐项目框架默认的eslint设置

## 黄金定律
永远遵循同一套编码规范 -- 可以是这里列出的，也可以是你自己总结的。如果你发现本规范中有任何错误，敬请指正。通过 open an issue on GitHub 为本规范添加内容或贡献力量。

```
不管有多少人共同参与同一项目，一定要确保每一行代码都像是同一个人编写的。
```

## 语法
HTML,CSS和Javascript都用两个空格来代替制表符（tab）；
webstorm设置HTML和CSS格式化的方法：File-Settings,Editor-CodeStyle-HTML(或者CSS),在Tabs and Indents选项卡下把TabSize和Indent的值均改为2；
webstorm格式化快捷键Ctrl+Alt+L;
命名规则
文件命名规则：小写单英文单词，多单词使用“-”连接:
```text
index.html
task-bg.jpg
title-bg.png
project-task.css
project-ctrl.js
projectCtrl.js
```
Css类名命名规则：英文单词，多单词使用“-”连接
```html
<div class="task-list-title">
   <h3 class="task-list-title-h3">
       这里是标题
   </h3>
</div>

<style>
   .task-list-title{
       float:left;
   }
</style>
```
Javasctipt命名规则：英文单词，多单词使用小驼峰
```javascript
$scope.taskOpen = function () {
    $scope.taskOpenState = true;
};
```
代码格式化
把webstorm的格式化换行去掉，设置方法：找到File-Settings,Editor-General-Appearance，去掉Show right margin(configured in Code Style options)的勾选

其他书写规范
当<a>标签中href属性不使用时，不用#作为填充，使用空白来填充,例如：
```html
<a href="javascript:" ng-click="openPopbox()"></a>
```

注释
首先代码注释永远不嫌多，不管是不是给别人看或者协同开发，注释必须尽可能的详尽，就算是你自己写的代码也可能时间太久或者逻辑太复杂而忘记具体功能，所以一定要写注释；
其次注释能帮助你快速理解代码所做的事情，看一段有注释的代码和一段没有注释的代码是两个概念，前者可以让你很快的理解代码的用途和方法，后者需要自己慢慢分析，而时间就是开发成本；
再次注释能帮你更好的整理你的逻辑，在写注释的时候，往往能发现一些自己忽略掉的一些东西，减少挖坑的次数；

```css
/*
 * Component section heading
 */

.element { ... }


/*
 * Component section heading
 *
 * Sometimes you need to include optional context for the entire component. Do that up here if it's important enough.
 */

.element { ... }

/* Contextual sub-component or modifer */
.element-heading { ... }
```

