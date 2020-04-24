---
id: 44
title: Angular2：5分钟快速入门 (for javascript)
date: 2016-04-25T18:05:14+00:00
author: crazy4x
layout: post
categories:
  - Angular
tags:
  - Angular2
  - quickstart
  - 快速开始
---
让我们从零开始使用JavaScript建立一个超简单的Angular2应用，还可以使用TypeScript和Dart

## 看看运行效果

运行[在线示例](https://angular.io/resources/live-examples/quickstart/js/plnkr.html/)能快速看到看到 Angular 2应用的实例，运行结果如下图：
  
<!--more-->

文件目录结构如下
  
![](http://www.ziwuo.com/wp-content/uploads/2016/04/QQ截图20160505105117.jpg)

从功能上看只有一个index.html和两个app文件夹中的JavaScript文件。

当然，我们不会只在plunker上建立应用，接下来展示一个实际操作流程

  * 建立我们的开发环境
  * 为我们的应用编写Angular根组件
  * 引到它控制主页面
  * 编写主页面

> 我们真的可以在五分钟内建立快速入门，如果我们按照指示并且忽略评论。
    
> 我们大多数人会感兴趣的“为什么”以及“如何”，这将需要更长的时间。 

## 开发环境

我们需要一个应用程序项目文件夹，一些库和编辑器。

### 创建一个新项目文件夹

<!-- Crayon Syntax Highlighter v_2.7.2_beta -->

        <div id="crayon-589875b298eb4008357418" class="crayon-syntax crayon-theme-sublime-text crayon-font-sourcecodepro crayon-os-pc print-yes notranslate" style="margin-top: 12px;margin-bottom: 12px;font-size: 14px !important;line-height: 24px !important">
    
            <div class="crayon-plain-wrap"></div>
            <div class="crayon-main">
                <table class="crayon-table">
                    <tr class="crayon-row">
                <td class="crayon-nums ">
                    <div class="crayon-nums-content" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-num">1</div><div class="crayon-num">2</div></div>
                </td>
                        <td class="crayon-code"><div class="crayon-pre" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-line" id="crayon-589875b298eb4008357418-1"><span class="crayon-e">mkdir </span><span class="crayon-v">angular2</span><span class="crayon-o">-</span><span class="crayon-e">quickstart</span></div><div class="crayon-line" id="crayon-589875b298eb4008357418-2"><span class="crayon-e">cd&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-v">angular2</span><span class="crayon-o">-</span><span class="crayon-v">quickstart</span></div></div></td>
                    </tr>
                </table>
            </div>
        </div>
    

<!-- [Format Time: 0.0009 seconds] -->

### 加入我们需要的库文件

我们建议使用npm包管理器来采集和管理我们的开发库。

> 在这个文档中会大量繁复使用npm包管理器。

添加一个package.json文件到项目文件夹，复制粘贴以下内容：

<!-- Crayon Syntax Highlighter v_2.7.2_beta -->

        <div id="crayon-589875b298ed4240652242" class="crayon-syntax crayon-theme-sublime-text crayon-font-sourcecodepro crayon-os-pc print-yes notranslate" style="margin-top: 12px;margin-bottom: 12px;font-size: 14px !important;line-height: 24px !important">
    
            <div class="crayon-plain-wrap"></div>
            <div class="crayon-main">
                <table class="crayon-table">
                    <tr class="crayon-row">
                <td class="crayon-nums ">
                    <div class="crayon-nums-content" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-num">1</div><div class="crayon-num">2</div><div class="crayon-num">3</div><div class="crayon-num">4</div><div class="crayon-num">5</div><div class="crayon-num">6</div><div class="crayon-num">7</div><div class="crayon-num">8</div><div class="crayon-num">9</div><div class="crayon-num">10</div><div class="crayon-num">11</div><div class="crayon-num">12</div><div class="crayon-num">13</div><div class="crayon-num">14</div><div class="crayon-num">15</div><div class="crayon-num">16</div><div class="crayon-num">17</div><div class="crayon-num">18</div><div class="crayon-num">19</div><div class="crayon-num">20</div><div class="crayon-num">21</div><div class="crayon-num">22</div><div class="crayon-num">23</div><div class="crayon-num">24</div><div class="crayon-num">25</div><div class="crayon-num">26</div><div class="crayon-num">27</div><div class="crayon-num">28</div><div class="crayon-num">29</div><div class="crayon-num">30</div><div class="crayon-num">31</div></div>
                </td>
                        <td class="crayon-code"><div class="crayon-pre" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-line" id="crayon-589875b298ed4240652242-1"><span class="crayon-sy">{</span></div><div class="crayon-line" id="crayon-589875b298ed4240652242-2"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-s">"name"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"angular2-quickstart"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298ed4240652242-3"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-s">"version"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"1.0.0"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298ed4240652242-4"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-s">"scripts"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-sy">{</span></div><div class="crayon-line" id="crayon-589875b298ed4240652242-5"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"start"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"npm run lite"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298ed4240652242-6"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"lite"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"lite-server"</span></div><div class="crayon-line" id="crayon-589875b298ed4240652242-7"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-sy">}</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298ed4240652242-8"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-s">"license"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"ISC"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298ed4240652242-9"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-s">"dependencies"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-sy">{</span></div><div class="crayon-line" id="crayon-589875b298ed4240652242-10"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"@angular/common"</span><span class="crayon-o">:</span><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-s">"2.0.0-rc.1"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298ed4240652242-11"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"@angular/compiler"</span><span class="crayon-o">:</span><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-s">"2.0.0-rc.1"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298ed4240652242-12"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"@angular/core"</span><span class="crayon-o">:</span><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-s">"2.0.0-rc.1"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298ed4240652242-13"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"@angular/http"</span><span class="crayon-o">:</span><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-s">"2.0.0-rc.1"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298ed4240652242-14"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"@angular/platform-browser"</span><span class="crayon-o">:</span><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-s">"2.0.0-rc.1"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298ed4240652242-15"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"@angular/platform-browser-dynamic"</span><span class="crayon-o">:</span><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-s">"2.0.0-rc.1"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298ed4240652242-16"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"@angular/router"</span><span class="crayon-o">:</span><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-s">"2.0.0-rc.1"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298ed4240652242-17"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"@angular/router-deprecated"</span><span class="crayon-o">:</span><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-s">"2.0.0-rc.1"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298ed4240652242-18"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"@angular/upgrade"</span><span class="crayon-o">:</span><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-s">"2.0.0-rc.1"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298ed4240652242-19">&nbsp;</div><div class="crayon-line" id="crayon-589875b298ed4240652242-20"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"reflect-metadata"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"0.1.3"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298ed4240652242-21"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"rxjs"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"5.0.0-beta.6"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298ed4240652242-22"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"zone.js"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"0.6.12"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298ed4240652242-23">&nbsp;</div><div class="crayon-line" id="crayon-589875b298ed4240652242-24"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"angular2-in-memory-web-api"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"0.0.7"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298ed4240652242-25"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"bootstrap"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"^3.3.6"</span></div><div class="crayon-line" id="crayon-589875b298ed4240652242-26"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-sy">}</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298ed4240652242-27"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-s">"devDependencies"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-sy">{</span></div><div class="crayon-line" id="crayon-589875b298ed4240652242-28"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"concurrently"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"^2.0.0"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298ed4240652242-29"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"lite-server"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"^2.2.0"</span></div><div class="crayon-line" id="crayon-589875b298ed4240652242-30"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-sy">}</span></div><div class="crayon-line" id="crayon-589875b298ed4240652242-31"><span class="crayon-sy">}</span></div></div></td>
                    </tr>
                </table>
            </div>
        </div>
    

<!-- [Format Time: 0.0057 seconds] -->

> package.json的设置细节在下面的附录中会有解释

打开一个terminal窗口（Windows系统在cmd中打开）运行下面的npm命令</em>

<!-- Crayon Syntax Highlighter v_2.7.2_beta -->

        <div id="crayon-589875b298edc085478325" class="crayon-syntax crayon-theme-sublime-text crayon-font-sourcecodepro crayon-os-pc print-yes notranslate" style="margin-top: 12px;margin-bottom: 12px;font-size: 14px !important;line-height: 24px !important">
    
            <div class="crayon-plain-wrap"></div>
            <div class="crayon-main">
                <table class="crayon-table">
                    <tr class="crayon-row">
                <td class="crayon-nums ">
                    <div class="crayon-nums-content" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-num">1</div></div>
                </td>
                        <td class="crayon-code"><div class="crayon-pre" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-line" id="crayon-589875b298edc085478325-1"><span class="crayon-e">npm </span><span class="crayon-v">install</span></div></div></td>
                    </tr>
                </table>
            </div>
        </div>
    

<!-- [Format Time: 0.0004 seconds] -->

> [AngularJS,自定义filter实现文字和拼音的双过滤](http://www.ziwuo.com/archives/24.html) 在安装过程中可能会出现红色错误消息。 别理他们。安装会成功。请参阅下面的附录以获取更多信息。

## 我们的第一个Angular组件

组件是最基本的Angular概念。组件管理着视图。
  
从技术上讲，一个组件是控制视图模板的类。在因为Angular应用中我们会建立很多组件。这是我们的第一次尝试，所以我们做一个简单的。

### 创建一个应用程序源的子文件夹

规范上把应用代码都放在app的子文件夹里面

<!-- Crayon Syntax Highlighter v_2.7.2_beta -->

        <div id="crayon-589875b298ee3040454562" class="crayon-syntax crayon-theme-sublime-text crayon-font-sourcecodepro crayon-os-pc print-yes notranslate" style="margin-top: 12px;margin-bottom: 12px;font-size: 14px !important;line-height: 24px !important">
    
            <div class="crayon-plain-wrap"></div>
            <div class="crayon-main">
                <table class="crayon-table">
                    <tr class="crayon-row">
                <td class="crayon-nums ">
                    <div class="crayon-nums-content" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-num">1</div><div class="crayon-num">2</div></div>
                </td>
                        <td class="crayon-code"><div class="crayon-pre" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-line" id="crayon-589875b298ee3040454562-1"><span class="crayon-r">mkdir</span><span class="crayon-h"> </span>app</div><div class="crayon-line" id="crayon-589875b298ee3040454562-2"><span class="crayon-r">cd</span><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span>app</div></div></td>
                    </tr>
                </table>
            </div>
        </div>
    

<!-- [Format Time: 0.0007 seconds] -->

### 添加组件文件

添加一个app.component.js文件复制粘贴以下代码

<!-- Crayon Syntax Highlighter v_2.7.2_beta -->

        <div id="crayon-589875b298ee9347246607" class="crayon-syntax crayon-theme-sublime-text crayon-font-sourcecodepro crayon-os-pc print-yes notranslate" style="margin-top: 12px;margin-bottom: 12px;font-size: 14px !important;line-height: 24px !important">
    
            <div class="crayon-plain-wrap"></div>
            <div class="crayon-main">
                <table class="crayon-table">
                    <tr class="crayon-row">
                <td class="crayon-nums ">
                    <div class="crayon-nums-content" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-num">1</div><div class="crayon-num">2</div><div class="crayon-num">3</div><div class="crayon-num">4</div><div class="crayon-num">5</div><div class="crayon-num">6</div><div class="crayon-num">7</div><div class="crayon-num">8</div><div class="crayon-num">9</div><div class="crayon-num">10</div></div>
                </td>
                        <td class="crayon-code"><div class="crayon-pre" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-line" id="crayon-589875b298ee9347246607-1"><span class="crayon-sy">(</span><span class="crayon-t">function</span><span class="crayon-sy">(</span><span class="crayon-v">app</span><span class="crayon-sy">)</span><span class="crayon-h"> </span><span class="crayon-sy">{</span></div><div class="crayon-line" id="crayon-589875b298ee9347246607-2"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-v">app</span><span class="crayon-sy">.</span><span class="crayon-v">AppComponent</span><span class="crayon-h"> </span><span class="crayon-o">=</span></div><div class="crayon-line" id="crayon-589875b298ee9347246607-3"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-v">ng</span><span class="crayon-sy">.</span><span class="crayon-v">core</span><span class="crayon-sy">.</span><span class="crayon-e">Component</span><span class="crayon-sy">(</span><span class="crayon-sy">{</span></div><div class="crayon-line" id="crayon-589875b298ee9347246607-4"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-v">selector</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">'my-app'</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298ee9347246607-5"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-v">template</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">'&lt;h1&gt;My First Angular 2 App&lt;/h1&gt;'</span></div><div class="crayon-line" id="crayon-589875b298ee9347246607-6"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-sy">}</span><span class="crayon-sy">)</span></div><div class="crayon-line" id="crayon-589875b298ee9347246607-7"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-sy">.</span><span class="crayon-t">Class</span><span class="crayon-sy">(</span><span class="crayon-sy">{</span></div><div class="crayon-line" id="crayon-589875b298ee9347246607-8"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-v">constructor</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-t">function</span><span class="crayon-sy">(</span><span class="crayon-sy">)</span><span class="crayon-h"> </span><span class="crayon-sy">{</span><span class="crayon-sy">}</span></div><div class="crayon-line" id="crayon-589875b298ee9347246607-9"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-sy">}</span><span class="crayon-sy">)</span><span class="crayon-sy">;</span></div><div class="crayon-line" id="crayon-589875b298ee9347246607-10"><span class="crayon-sy">}</span><span class="crayon-sy">)</span><span class="crayon-sy">(</span><span class="crayon-v">window</span><span class="crayon-sy">.</span><span class="crayon-v">app</span><span class="crayon-h"> </span><span class="crayon-o">||</span><span class="crayon-h"> </span><span class="crayon-sy">(</span><span class="crayon-v">window</span><span class="crayon-sy">.</span><span class="crayon-v">app</span><span class="crayon-h"> </span><span class="crayon-o">=</span><span class="crayon-h"> </span><span class="crayon-sy">{</span><span class="crayon-sy">}</span><span class="crayon-sy">)</span><span class="crayon-sy">)</span><span class="crayon-sy">;</span></div></div></td>
                    </tr>
                </table>
            </div>
        </div>
    

<!-- [Format Time: 0.0030 seconds] -->

我们通过Component 和Class的方法创建一个名为AppComponent的可视化组件 ，属于全局Angular 的核心命名方法，ng.core。

<!-- Crayon Syntax Highlighter v_2.7.2_beta -->

        <div id="crayon-589875b298eef224119993" class="crayon-syntax crayon-theme-sublime-text crayon-font-sourcecodepro crayon-os-pc print-yes notranslate" style="margin-top: 12px;margin-bottom: 12px;font-size: 14px !important;line-height: 24px !important">
    
            <div class="crayon-plain-wrap"></div>
            <div class="crayon-main">
                <table class="crayon-table">
                    <tr class="crayon-row">
                <td class="crayon-nums ">
                    <div class="crayon-nums-content" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-num">1</div><div class="crayon-num">2</div><div class="crayon-num">3</div><div class="crayon-num">4</div><div class="crayon-num">5</div></div>
                </td>
                        <td class="crayon-code"><div class="crayon-pre" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-line" id="crayon-589875b298eef224119993-1"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-v">app</span><span class="crayon-sy">.</span><span class="crayon-v">AppComponent</span><span class="crayon-h"> </span><span class="crayon-o">=</span></div><div class="crayon-line" id="crayon-589875b298eef224119993-2"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-v">ng</span><span class="crayon-sy">.</span><span class="crayon-v">core</span><span class="crayon-sy">.</span><span class="crayon-e">Component</span><span class="crayon-sy">(</span><span class="crayon-sy">{</span></div><div class="crayon-line" id="crayon-589875b298eef224119993-3"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-sy">}</span><span class="crayon-sy">)</span></div><div class="crayon-line" id="crayon-589875b298eef224119993-4"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-sy">.</span><span class="crayon-t">Class</span><span class="crayon-sy">(</span><span class="crayon-sy">{</span></div><div class="crayon-line" id="crayon-589875b298eef224119993-5"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-sy">}</span><span class="crayon-sy">)</span><span class="crayon-sy">;</span></div></div></td>
                    </tr>
                </table>
            </div>
        </div>
    

<!-- [Format Time: 0.0014 seconds] -->

Component方法具有两个属性。Class方法是我们运行组件的地方，用属性和方法来绑定视图和UI的行为。
  
回顾以下详细代码

### Modules模块

Angular应用程序是模块化的。它们包括许多文件每个文件都有它专门的用处。
  
ES5 JavaScript本身没有本地模块系统。我们可以使用一些流行的第三方模块系统。作为代替，为了简便起见和避免优先级问题，我们会为应用程序创建一个单一的全局命名空间。
  
我们称呼它为app ，我们将所有的代码构件到这一个全局对象。
  
不要去污染全局命名空间。所以每个文件的代码围绕IIFE（“立即执行函数表达式”）。

<!-- Crayon Syntax Highlighter v_2.7.2_beta -->

        <div id="crayon-589875b298ef6074070245" class="crayon-syntax crayon-theme-sublime-text crayon-font-sourcecodepro crayon-os-pc print-yes notranslate" style="margin-top: 12px;margin-bottom: 12px;font-size: 14px !important;line-height: 24px !important">
    
            <div class="crayon-plain-wrap"></div>
            <div class="crayon-main">
                <table class="crayon-table">
                    <tr class="crayon-row">
                <td class="crayon-nums ">
                    <div class="crayon-nums-content" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-num">1</div><div class="crayon-num">2</div></div>
                </td>
                        <td class="crayon-code"><div class="crayon-pre" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-line" id="crayon-589875b298ef6074070245-1"><span class="crayon-sy">(</span><span class="crayon-t">function</span><span class="crayon-sy">(</span><span class="crayon-v">app</span><span class="crayon-sy">)</span><span class="crayon-h"> </span><span class="crayon-sy">{</span></div><div class="crayon-line" id="crayon-589875b298ef6074070245-2"><span class="crayon-sy">}</span><span class="crayon-sy">)</span><span class="crayon-sy">(</span><span class="crayon-v">window</span><span class="crayon-sy">.</span><span class="crayon-v">app</span><span class="crayon-h"> </span><span class="crayon-o">||</span><span class="crayon-h"> </span><span class="crayon-sy">(</span><span class="crayon-v">window</span><span class="crayon-sy">.</span><span class="crayon-v">app</span><span class="crayon-h"> </span><span class="crayon-o">=</span><span class="crayon-h"> </span><span class="crayon-sy">{</span><span class="crayon-sy">}</span><span class="crayon-sy">)</span><span class="crayon-sy">)</span><span class="crayon-sy">;</span></div></div></td>
                    </tr>
                </table>
            </div>
        </div>
    

<!-- [Format Time: 0.0014 seconds] -->

我们绕过全局应用命名空间对象到IIFE，用一个空对象初始化。
  
大多数应用程序文件通过添加东西到命名空间输出这个东西。例如我们的app.component.js文件输出AppComponent。

<!-- Crayon Syntax Highlighter v_2.7.2_beta -->

        <div id="crayon-589875b298efc187818661" class="crayon-syntax crayon-theme-sublime-text crayon-font-sourcecodepro crayon-os-pc print-yes notranslate" style="margin-top: 12px;margin-bottom: 12px;font-size: 14px !important;line-height: 24px !important">
    
            <div class="crayon-plain-wrap"></div>
            <div class="crayon-main">
                <table class="crayon-table">
                    <tr class="crayon-row">
                <td class="crayon-nums ">
                    <div class="crayon-nums-content" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-num">1</div></div>
                </td>
                        <td class="crayon-code"><div class="crayon-pre" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-line" id="crayon-589875b298efc187818661-1"><span class="crayon-v">app</span><span class="crayon-sy">.</span><span class="crayon-v">AppComponent</span><span class="crayon-h"> </span><span class="crayon-o">=</span></div></div></td>
                    </tr>
                </table>
            </div>
        </div>
    

<!-- [Format Time: 0.0006 seconds] -->

更复杂的应用会有AppComponent的子组件。一个更复杂的应用程序将有更多的文件和模块。
  
这个快速入门应用是很简单的;只有一个我们需要的组件。但是模块依然在这样一个小小的应用程序发挥了一个基本的组织作用。
  
模块依赖于其他模块。在JavaScript [11.](http://loyal-friend.de/2015/05/11-september-2008/) Angular应用中，当我们需要另一个模块提供的东西，我们从app对象获取它。当另一个模块涉及到AppComponent，它从app.AppComponent中获取它。

<!-- Crayon Syntax Highlighter v_2.7.2_beta -->

        <div id="crayon-589875b298f02250924520" class="crayon-syntax crayon-theme-sublime-text crayon-font-sourcecodepro crayon-os-pc print-yes notranslate" style="margin-top: 12px;margin-bottom: 12px;font-size: 14px !important;line-height: 24px !important">
    
            <div class="crayon-plain-wrap"></div>
            <div class="crayon-main">
                <table class="crayon-table">
                    <tr class="crayon-row">
                <td class="crayon-nums ">
                    <div class="crayon-nums-content" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-num">1</div></div>
                </td>
                        <td class="crayon-code"><div class="crayon-pre" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-line" id="crayon-589875b298f02250924520-1"><span class="crayon-v">ng</span><span class="crayon-sy">.</span><span class="crayon-v">platformBrowserDynamic</span><span class="crayon-sy">.</span><span class="crayon-e">bootstrap</span><span class="crayon-sy">(</span><span class="crayon-v">app</span><span class="crayon-sy">.</span><span class="crayon-v">AppComponent</span><span class="crayon-sy">)</span><span class="crayon-sy">;</span></div></div></td>
                    </tr>
                </table>
            </div>
        </div>
    

<!-- [Format Time: 0.0011 seconds] -->

Angular本身也是模块化的。它是一个库模块的集合。每个库本身由一些相关的功能模块组成。
  
当我们需要Angular的某些东西，我们用ng对象来获取。

### The Class definition object?类定义对象

在文件的底部是一个空的、不做任何事情的类定义对象。当我们准备好建立一个独立应用，我们以用属性和应用逻辑来扩展此对象。在快速入门中我们AppComponent类只有一个空的构造，是因为我们不需要它在这个快速入门中做任何事情。

<!-- Crayon Syntax Highlighter v_2.7.2_beta -->

        <div id="crayon-589875b298f08262980904" class="crayon-syntax crayon-theme-sublime-text crayon-font-sourcecodepro crayon-os-pc print-yes notranslate" style="margin-top: 12px;margin-bottom: 12px;font-size: 14px !important;line-height: 24px !important">
    
            <div class="crayon-plain-wrap"></div>
            <div class="crayon-main">
                <table class="crayon-table">
                    <tr class="crayon-row">
                <td class="crayon-nums ">
                    <div class="crayon-nums-content" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-num">1</div><div class="crayon-num">2</div><div class="crayon-num">3</div></div>
                </td>
                        <td class="crayon-code"><div class="crayon-pre" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-line" id="crayon-589875b298f08262980904-1"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-sy">.</span><span class="crayon-t">Class</span><span class="crayon-sy">(</span><span class="crayon-sy">{</span></div><div class="crayon-line" id="crayon-589875b298f08262980904-2"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-v">constructor</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-t">function</span><span class="crayon-sy">(</span><span class="crayon-sy">)</span><span class="crayon-h"> </span><span class="crayon-sy">{</span><span class="crayon-sy">}</span></div><div class="crayon-line" id="crayon-589875b298f08262980904-3"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-sy">}</span><span class="crayon-sy">)</span><span class="crayon-sy">;</span></div></div></td>
                    </tr>
                </table>
            </div>
        </div>
    

<!-- [Format Time: 0.0011 seconds] -->

### The Component definition object?组件定义对象

ng.core.Component()告诉Angular这个类定义对象是一个Angular组件。配置对象传递给ng.core.Component()方法两个字段，一个selector 和一个 template。

<!-- Crayon Syntax Highlighter v_2.7.2_beta -->

        <div id="crayon-589875b298f0e293927067" class="crayon-syntax crayon-theme-sublime-text crayon-font-sourcecodepro crayon-os-pc print-yes notranslate" style="margin-top: 12px;margin-bottom: 12px;font-size: 14px !important;line-height: 24px !important">
    
            <div class="crayon-plain-wrap"></div>
            <div class="crayon-main">
                <table class="crayon-table">
                    <tr class="crayon-row">
                <td class="crayon-nums ">
                    <div class="crayon-nums-content" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-num">1</div><div class="crayon-num">2</div><div class="crayon-num">3</div><div class="crayon-num">4</div></div>
                </td>
                        <td class="crayon-code"><div class="crayon-pre" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-line" id="crayon-589875b298f0e293927067-1"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-v">ng</span><span class="crayon-sy">.</span><span class="crayon-v">core</span><span class="crayon-sy">.</span><span class="crayon-e">Component</span><span class="crayon-sy">(</span><span class="crayon-sy">{</span></div><div class="crayon-line" id="crayon-589875b298f0e293927067-2"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-v">selector</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">'my-app'</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f0e293927067-3"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-v">template</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">'&lt;h1&gt;My First Angular 2 App&lt;/h1&gt;'</span></div><div class="crayon-line" id="crayon-589875b298f0e293927067-4"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-sy">}</span><span class="crayon-sy">)</span></div></div></td>
                    </tr>
                </table>
            </div>
        </div>
    

<!-- [Format Time: 0.0013 seconds] -->

selector为名为my-app的HTML元素指定一个简单的CSS选择器。Angular无论在HTML中哪里遇到my-app元素就会创建和显示AppComponent实例 。

> [Een](http://www.managing-it.nl/management-artikelen/teamwork/een-tevreden-team-is-een-sterk-team/) 记住my-app选择器，我们会在编写index.html中用到
     
> [cheap nba jerseys](http://www.cheapelitejerseys.us.com) 模板属性保存组件的同步模板。模板是HTML的一种形式，它告诉Angular 如何呈现一个视图。我们的模板是一个单行的HTML显示“My First Angular App”。
    
> 现在我们需要一些东西来告诉Angular 来加载这个组件。

### Bootstrap it! 引导

添加一个新文件main.js到app文件夹

<!-- Crayon Syntax Highlighter v_2.7.2_beta -->

        <div id="crayon-589875b298f14767278600" class="crayon-syntax crayon-theme-sublime-text crayon-font-sourcecodepro crayon-os-pc print-yes notranslate" style="margin-top: 12px;margin-bottom: 12px;font-size: 14px !important;line-height: 24px !important">
    
            <div class="crayon-plain-wrap"></div>
            <div class="crayon-main">
                <table class="crayon-table">
                    <tr class="crayon-row">
                <td class="crayon-nums ">
                    <div class="crayon-nums-content" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-num">1</div><div class="crayon-num">2</div><div class="crayon-num">3</div><div class="crayon-num">4</div><div class="crayon-num">5</div></div>
                </td>
                        <td class="crayon-code"><div class="crayon-pre" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-line" id="crayon-589875b298f14767278600-1"><span class="crayon-sy">(</span><span class="crayon-t">function</span><span class="crayon-sy">(</span><span class="crayon-v">app</span><span class="crayon-sy">)</span><span class="crayon-h"> </span><span class="crayon-sy">{</span></div><div class="crayon-line" id="crayon-589875b298f14767278600-2"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-v">document</span><span class="crayon-sy">.</span><span class="crayon-e">addEventListener</span><span class="crayon-sy">(</span><span class="crayon-s">'DOMContentLoaded'</span><span class="crayon-sy">,</span><span class="crayon-h"> </span><span class="crayon-t">function</span><span class="crayon-sy">(</span><span class="crayon-sy">)</span><span class="crayon-h"> </span><span class="crayon-sy">{</span></div><div class="crayon-line" id="crayon-589875b298f14767278600-3"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-v">ng</span><span class="crayon-sy">.</span><span class="crayon-v">platformBrowserDynamic</span><span class="crayon-sy">.</span><span class="crayon-e">bootstrap</span><span class="crayon-sy">(</span><span class="crayon-v">app</span><span class="crayon-sy">.</span><span class="crayon-v">AppComponent</span><span class="crayon-sy">)</span><span class="crayon-sy">;</span></div><div class="crayon-line" id="crayon-589875b298f14767278600-4"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-sy">}</span><span class="crayon-sy">)</span><span class="crayon-sy">;</span></div><div class="crayon-line" id="crayon-589875b298f14767278600-5"><span class="crayon-sy">}</span><span class="crayon-sy">)</span><span class="crayon-sy">(</span><span class="crayon-v">window</span><span class="crayon-sy">.</span><span class="crayon-v">app</span><span class="crayon-h"> </span><span class="crayon-o">||</span><span class="crayon-h"> </span><span class="crayon-sy">(</span><span class="crayon-v">window</span><span class="crayon-sy">.</span><span class="crayon-v">app</span><span class="crayon-h"> </span><span class="crayon-o">=</span><span class="crayon-h"> </span><span class="crayon-sy">{</span><span class="crayon-sy">}</span><span class="crayon-sy">)</span><span class="crayon-sy">)</span><span class="crayon-sy">;</span></div></div></td>
                    </tr>
                </table>
            </div>
        </div>
    

<!-- [Format Time: 0.0025 seconds] -->

我们需要两样东西来启动应用程序：

  * Angular的浏览器引导功能
  * 我们刚写的应用根组件

两个东西都在我们的“命名空间”里。引导它，传递到根组件类型，AppComponent。

> 了解为什么引到和main.js的详情点击[链接](https://angular.io/docs/js/latest/quickstart.html#main)

我们要求Angular在浏览器启动应用程序与我们的根组件。Angular会放在哪里呢？

## 添加index.html文件

Angular会在index.html的特定位置的显示我们的应用程序。现在是时候创建这个文件。
  
我们不会把index.html放在app文件夹。我们把它放在上一级项目的根文件夹。

<!-- Crayon Syntax Highlighter v_2.7.2_beta -->

        <div id="crayon-589875b298f1b735905073" class="crayon-syntax crayon-theme-sublime-text crayon-font-sourcecodepro crayon-os-pc print-yes notranslate" style="margin-top: 12px;margin-bottom: 12px;font-size: 14px !important;line-height: 24px !important">
    
            <div class="crayon-plain-wrap"></div>
            <div class="crayon-main">
                <table class="crayon-table">
                    <tr class="crayon-row">
                <td class="crayon-nums ">
                    <div class="crayon-nums-content" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-num">1</div></div>
                </td>
                        <td class="crayon-code"><div class="crayon-pre" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-line" id="crayon-589875b298f1b735905073-1"><span class="crayon-i">cd</span><span class="crayon-h"> </span><span class="crayon-sy">.</span><span class="crayon-sy">.</span></div></div></td>
                    </tr>
                </table>
            </div>
        </div>
    

<!-- [Format Time: 0.0005 seconds] -->

现在创建index.html

<!-- Crayon Syntax Highlighter v_2.7.2_beta -->

        <div id="crayon-589875b298f21015591892" class="crayon-syntax crayon-theme-sublime-text crayon-font-sourcecodepro crayon-os-pc print-yes notranslate" style="margin-top: 12px;margin-bottom: 12px;font-size: 14px !important;line-height: 24px !important">
    
            <div class="crayon-plain-wrap"></div>
            <div class="crayon-main">
                <table class="crayon-table">
                    <tr class="crayon-row">
                <td class="crayon-nums ">
                    <div class="crayon-nums-content" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-num">1</div><div class="crayon-num">2</div><div class="crayon-num">3</div><div class="crayon-num">4</div><div class="crayon-num">5</div><div class="crayon-num">6</div><div class="crayon-num">7</div><div class="crayon-num">8</div><div class="crayon-num">9</div><div class="crayon-num">10</div><div class="crayon-num">11</div><div class="crayon-num">12</div><div class="crayon-num">13</div><div class="crayon-num">14</div><div class="crayon-num">15</div><div class="crayon-num">16</div><div class="crayon-num">17</div><div class="crayon-num">18</div><div class="crayon-num">19</div><div class="crayon-num">20</div><div class="crayon-num">21</div><div class="crayon-num">22</div><div class="crayon-num">23</div><div class="crayon-num">24</div><div class="crayon-num">25</div><div class="crayon-num">26</div><div class="crayon-num">27</div><div class="crayon-num">28</div><div class="crayon-num">29</div><div class="crayon-num">30</div><div class="crayon-num">31</div><div class="crayon-num">32</div></div>
                </td>
                        <td class="crayon-code"><div class="crayon-pre" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-line" id="crayon-589875b298f21015591892-1"><span class="crayon-o">&lt;</span><span class="crayon-v">html</span><span class="crayon-o">&gt;</span></div><div class="crayon-line" id="crayon-589875b298f21015591892-2"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-o">&lt;</span><span class="crayon-v">head</span><span class="crayon-o">&gt;</span></div><div class="crayon-line" id="crayon-589875b298f21015591892-3"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-o">&lt;</span><span class="crayon-v">title</span><span class="crayon-o">&gt;</span><span class="crayon-i">Angular</span><span class="crayon-h"> </span><span class="crayon-cn">2</span><span class="crayon-h"> </span><span class="crayon-e">QuickStart </span><span class="crayon-v">JS</span><span class="crayon-o">&lt;</span><span class="crayon-o">/</span><span class="crayon-v">title</span><span class="crayon-o">&gt;</span></div><div class="crayon-line" id="crayon-589875b298f21015591892-4"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-o">&lt;</span><span class="crayon-e">meta </span><span class="crayon-v">name</span><span class="crayon-o">=</span><span class="crayon-s">"viewport"</span><span class="crayon-h"> </span><span class="crayon-v">content</span><span class="crayon-o">=</span><span class="crayon-s">"width=device-width, initial-scale=1"</span><span class="crayon-o">&gt;</span></div><div class="crayon-line" id="crayon-589875b298f21015591892-5"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-o">&lt;</span><span class="crayon-e">link </span><span class="crayon-v">rel</span><span class="crayon-o">=</span><span class="crayon-s">"stylesheet"</span><span class="crayon-h"> </span><span class="crayon-v">href</span><span class="crayon-o">=</span><span class="crayon-s">"styles.css"</span><span class="crayon-o">&gt;</span></div><div class="crayon-line" id="crayon-589875b298f21015591892-6">&nbsp;</div><div class="crayon-line" id="crayon-589875b298f21015591892-7"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-o">&lt;</span><span class="crayon-o">!</span><span class="crayon-o">--</span><span class="crayon-h"> </span><span class="crayon-cn">1.</span><span class="crayon-h"> </span><span class="crayon-e">Load</span><span class="crayon-h"> </span><span class="crayon-e">libraries</span><span class="crayon-h"> </span><span class="crayon-o">--</span><span class="crayon-o">&gt;</span></div><div class="crayon-line" id="crayon-589875b298f21015591892-8"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-o">&lt;</span><span class="crayon-o">!</span><span class="crayon-o">--</span><span class="crayon-h"> </span><span class="crayon-e">IE</span><span class="crayon-h"> </span><span class="crayon-e">required</span><span class="crayon-h"> </span><span class="crayon-e">polyfill</span><span class="crayon-h"> </span><span class="crayon-o">--</span><span class="crayon-o">&gt;</span></div><div class="crayon-line" id="crayon-589875b298f21015591892-9"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-ta">&lt;script </span><span class="crayon-e ">src</span><span class="crayon-o">=</span><span class="crayon-s">"node_modules/es6-shim/es6-shim.min.js"</span><span class="crayon-o">&gt;</span><span class="crayon-ta">&lt;/script&gt;</span></div><div class="crayon-line" id="crayon-589875b298f21015591892-10">&nbsp;</div><div class="crayon-line" id="crayon-589875b298f21015591892-11"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-ta">&lt;script </span><span class="crayon-e ">src</span><span class="crayon-o">=</span><span class="crayon-s">"node_modules/zone.js/dist/zone.js"</span><span class="crayon-o">&gt;</span><span class="crayon-ta">&lt;/script&gt;</span></div><div class="crayon-line" id="crayon-589875b298f21015591892-12"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-ta">&lt;script </span><span class="crayon-e ">src</span><span class="crayon-o">=</span><span class="crayon-s">"node_modules/reflect-metadata/Reflect.js"</span><span class="crayon-o">&gt;</span><span class="crayon-ta">&lt;/script&gt;</span></div><div class="crayon-line" id="crayon-589875b298f21015591892-13">&nbsp;</div><div class="crayon-line" id="crayon-589875b298f21015591892-14"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-ta">&lt;script </span><span class="crayon-e ">src</span><span class="crayon-o">=</span><span class="crayon-s">"node_modules/rxjs/bundles/Rx.umd.js"</span><span class="crayon-o">&gt;</span><span class="crayon-ta">&lt;/script&gt;</span></div><div class="crayon-line" id="crayon-589875b298f21015591892-15"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-ta">&lt;script </span><span class="crayon-e ">src</span><span class="crayon-o">=</span><span class="crayon-s">"node_modules/@angular/core/core.umd.js"</span><span class="crayon-o">&gt;</span><span class="crayon-ta">&lt;/script&gt;</span></div><div class="crayon-line" id="crayon-589875b298f21015591892-16"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-ta">&lt;script </span><span class="crayon-e ">src</span><span class="crayon-o">=</span><span class="crayon-s">"node_modules/@angular/common/common.umd.js"</span><span class="crayon-o">&gt;</span><span class="crayon-ta">&lt;/script&gt;</span></div><div class="crayon-line" id="crayon-589875b298f21015591892-17"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-ta">&lt;script </span><span class="crayon-e ">src</span><span class="crayon-o">=</span><span class="crayon-s">"node_modules/@angular/compiler/compiler.umd.js"</span><span class="crayon-o">&gt;</span><span class="crayon-ta">&lt;/script&gt;</span></div><div class="crayon-line" id="crayon-589875b298f21015591892-18"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-ta">&lt;script </span><span class="crayon-e ">src</span><span class="crayon-o">=</span><span class="crayon-s">"node_modules/@angular/platform-browser/platform-browser.umd.js"</span><span class="crayon-o">&gt;</span><span class="crayon-ta">&lt;/script&gt;</span></div><div class="crayon-line" id="crayon-589875b298f21015591892-19"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-ta">&lt;script </span><span class="crayon-e ">src</span><span class="crayon-o">=</span><span class="crayon-s">"node_modules/@angular/platform-browser-dynamic/platform-browser-dynamic.umd.js"</span><span class="crayon-o">&gt;</span><span class="crayon-ta">&lt;/script&gt;</span></div><div class="crayon-line" id="crayon-589875b298f21015591892-20">&nbsp;</div><div class="crayon-line" id="crayon-589875b298f21015591892-21"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-o">&lt;</span><span class="crayon-o">!</span><span class="crayon-o">--</span><span class="crayon-h"> </span><span class="crayon-cn">2.</span><span class="crayon-h"> </span><span class="crayon-e">Load </span><span class="crayon-i">our</span><span class="crayon-h"> </span><span class="crayon-s">'modules'</span><span class="crayon-h"> </span><span class="crayon-o">--</span><span class="crayon-o">&gt;</span></div><div class="crayon-line" id="crayon-589875b298f21015591892-22"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-ta">&lt;script </span><span class="crayon-e ">src</span><span class="crayon-o">=</span><span class="crayon-s">'app/app.component.js'</span><span class="crayon-o">&gt;</span><span class="crayon-ta">&lt;/script&gt;</span></div><div class="crayon-line" id="crayon-589875b298f21015591892-23"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-ta">&lt;script </span><span class="crayon-e ">src</span><span class="crayon-o">=</span><span class="crayon-s">'app/main.js'</span><span class="crayon-o">&gt;</span><span class="crayon-ta">&lt;/script&gt;</span></div><div class="crayon-line" id="crayon-589875b298f21015591892-24">&nbsp;</div><div class="crayon-line" id="crayon-589875b298f21015591892-25"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-o">&lt;</span><span class="crayon-o">/</span><span class="crayon-v">head</span><span class="crayon-o">&gt;</span></div><div class="crayon-line" id="crayon-589875b298f21015591892-26">&nbsp;</div><div class="crayon-line" id="crayon-589875b298f21015591892-27"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-o">&lt;</span><span class="crayon-o">!</span><span class="crayon-o">--</span><span class="crayon-h"> </span><span class="crayon-cn">3.</span><span class="crayon-h"> </span><span class="crayon-e">Display </span><span class="crayon-e">the </span><span class="crayon-v">application</span><span class="crayon-h"> </span><span class="crayon-o">--</span><span class="crayon-o">&gt;</span></div><div class="crayon-line" id="crayon-589875b298f21015591892-28"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-o">&lt;</span><span class="crayon-v">body</span><span class="crayon-o">&gt;</span></div><div class="crayon-line" id="crayon-589875b298f21015591892-29"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-o">&lt;</span><span class="crayon-v">my</span><span class="crayon-o">-</span><span class="crayon-v">app</span><span class="crayon-o">&gt;</span><span class="crayon-v">Loading</span><span class="crayon-sy">.</span><span class="crayon-sy">.</span><span class="crayon-sy">.</span><span class="crayon-o">&lt;</span><span class="crayon-o">/</span><span class="crayon-v">my</span><span class="crayon-o">-</span><span class="crayon-v">app</span><span class="crayon-o">&gt;</span></div><div class="crayon-line" id="crayon-589875b298f21015591892-30"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-o">&lt;</span><span class="crayon-o">/</span><span class="crayon-v">body</span><span class="crayon-o">&gt;</span></div><div class="crayon-line" id="crayon-589875b298f21015591892-31">&nbsp;</div><div class="crayon-line" id="crayon-589875b298f21015591892-32"><span class="crayon-o">&lt;</span><span class="crayon-o">/</span><span class="crayon-v">html</span><span class="crayon-o">&gt;</span></div></div></td>
                    </tr>
                </table>
            </div>
        </div>
    

<!-- [Format Time: 0.0139 seconds] -->

在HTML中有三个值得关注的部分：

  * 加载需要的JavaScript库
  * 加载我们的JavaScript文件，注意它们的顺序（app.component.js放在main.js前面）。
  * 我们在<body>中加入<my-app>标签。这是我们的应用程序运行的地方。

当Angular调用main.js引导功能，它会读取AppComponent元数据，发现my-app选择器，找到名为my-app的元素，并在这个标签内加载我们的应用程序。

## Run! 运行

打开terminal窗口输入以下命令：

<!-- Crayon Syntax Highlighter v_2.7.2_beta -->

        <div id="crayon-589875b298f28035914915" class="crayon-syntax crayon-theme-sublime-text crayon-font-sourcecodepro crayon-os-pc print-yes notranslate" style="margin-top: 12px;margin-bottom: 12px;font-size: 14px !important;line-height: 24px !important">
    
            <div class="crayon-plain-wrap"></div>
            <div class="crayon-main">
                <table class="crayon-table">
                    <tr class="crayon-row">
                <td class="crayon-nums ">
                    <div class="crayon-nums-content" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-num">1</div></div>
                </td>
                        <td class="crayon-code"><div class="crayon-pre" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-line" id="crayon-589875b298f28035914915-1"><span class="crayon-e">npm </span><span class="crayon-v">start</span></div></div></td>
                    </tr>
                </table>
            </div>
        </div>
    

<!-- [Format Time: 0.0004 seconds] -->

该命令会在浏览器中运行一个名叫 lite-server的静态服务器加载index.html，并在应用文件改变时刷新浏览器。
  
片刻后，一个浏览器标签页会打开并显示

恭喜！我们做好了

> 如果你一直看到loading&#8230;界面，查看ES2015的浏览器支持

### 做一些改动

尝试更改消息为“My SECOND [前端编码规范](http://www.ziwuo.com/archives/6.html) Angular 2 app”
  
lite-server会一直监听，当检测到变化，会刷新浏览器，并显示修改后的消息。
  
这是开发一个应用程序的一个很巧妙的方法！
  
关闭终端窗口，当我们完成终止服务器。

##最终的文件结构</em></h2> 

我们最终的项目文件夹结构看起来是这样的：
  
![](http://www.ziwuo.com/wp-content/uploads/2016/04/QQ截图20160504153700.jpg)

所有的文件：

<!-- Crayon Syntax Highlighter v_2.7.2_beta -->

        <div id="crayon-589875b298f2f387272452" class="crayon-syntax crayon-theme-sublime-text crayon-font-sourcecodepro crayon-os-pc print-yes notranslate" style="margin-top: 12px;margin-bottom: 12px;font-size: 14px !important;line-height: 24px !important">
    
            <div class="crayon-plain-wrap"></div>
            <div class="crayon-main">
                <table class="crayon-table">
                    <tr class="crayon-row">
                <td class="crayon-nums ">
                    <div class="crayon-nums-content" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-num">1</div><div class="crayon-num">2</div><div class="crayon-num">3</div><div class="crayon-num">4</div><div class="crayon-num">5</div><div class="crayon-num">6</div><div class="crayon-num">7</div><div class="crayon-num">8</div><div class="crayon-num">9</div><div class="crayon-num">10</div></div>
                </td>
                        <td class="crayon-code"><div class="crayon-pre" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-line" id="crayon-589875b298f2f387272452-1"><span class="crayon-sy">(</span><span class="crayon-t">function</span><span class="crayon-sy">(</span><span class="crayon-v">app</span><span class="crayon-sy">)</span><span class="crayon-h"> </span><span class="crayon-sy">{</span></div><div class="crayon-line" id="crayon-589875b298f2f387272452-2"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-v">app</span><span class="crayon-sy">.</span><span class="crayon-v">AppComponent</span><span class="crayon-h"> </span><span class="crayon-o">=</span></div><div class="crayon-line" id="crayon-589875b298f2f387272452-3"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-v">ng</span><span class="crayon-sy">.</span><span class="crayon-v">core</span><span class="crayon-sy">.</span><span class="crayon-e">Component</span><span class="crayon-sy">(</span><span class="crayon-sy">{</span></div><div class="crayon-line" id="crayon-589875b298f2f387272452-4"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-v">selector</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">'my-app'</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f2f387272452-5"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-v">template</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">'&lt;h1&gt;My First Angular 2 App&lt;/h1&gt;'</span></div><div class="crayon-line" id="crayon-589875b298f2f387272452-6"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-sy">}</span><span class="crayon-sy">)</span></div><div class="crayon-line" id="crayon-589875b298f2f387272452-7"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-sy">.</span><span class="crayon-t">Class</span><span class="crayon-sy">(</span><span class="crayon-sy">{</span></div><div class="crayon-line" id="crayon-589875b298f2f387272452-8"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-v">constructor</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-t">function</span><span class="crayon-sy">(</span><span class="crayon-sy">)</span><span class="crayon-h"> </span><span class="crayon-sy">{</span><span class="crayon-sy">}</span></div><div class="crayon-line" id="crayon-589875b298f2f387272452-9"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-sy">}</span><span class="crayon-sy">)</span><span class="crayon-sy">;</span></div><div class="crayon-line" id="crayon-589875b298f2f387272452-10"><span class="crayon-sy">}</span><span class="crayon-sy">)</span><span class="crayon-sy">(</span><span class="crayon-v">window</span><span class="crayon-sy">.</span><span class="crayon-v">app</span><span class="crayon-h"> </span><span class="crayon-o">||</span><span class="crayon-h"> </span><span class="crayon-sy">(</span><span class="crayon-v">window</span><span class="crayon-sy">.</span><span class="crayon-v">app</span><span class="crayon-h"> </span><span class="crayon-o">=</span><span class="crayon-h"> </span><span class="crayon-sy">{</span><span class="crayon-sy">}</span><span class="crayon-sy">)</span><span class="crayon-sy">)</span><span class="crayon-sy">;</span></div></div></td>
                    </tr>
                </table>
            </div>
        </div>
    

<!-- [Format Time: 0.0034 seconds] -->

<!-- Crayon Syntax Highlighter v_2.7.2_beta -->

        <div id="crayon-589875b298f35469192486" class="crayon-syntax crayon-theme-sublime-text crayon-font-sourcecodepro crayon-os-pc print-yes notranslate" style="margin-top: 12px;margin-bottom: 12px;font-size: 14px !important;line-height: 24px !important">
    
            <div class="crayon-plain-wrap"></div>
            <div class="crayon-main">
                <table class="crayon-table">
                    <tr class="crayon-row">
                <td class="crayon-nums ">
                    <div class="crayon-nums-content" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-num">1</div><div class="crayon-num">2</div><div class="crayon-num">3</div><div class="crayon-num">4</div><div class="crayon-num">5</div></div>
                </td>
                        <td class="crayon-code"><div class="crayon-pre" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-line" id="crayon-589875b298f35469192486-1"><span class="crayon-sy">(</span><span class="crayon-t">function</span><span class="crayon-sy">(</span><span class="crayon-v">app</span><span class="crayon-sy">)</span><span class="crayon-h"> </span><span class="crayon-sy">{</span></div><div class="crayon-line" id="crayon-589875b298f35469192486-2"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-v">document</span><span class="crayon-sy">.</span><span class="crayon-e">addEventListener</span><span class="crayon-sy">(</span><span class="crayon-s">'DOMContentLoaded'</span><span class="crayon-sy">,</span><span class="crayon-h"> </span><span class="crayon-t">function</span><span class="crayon-sy">(</span><span class="crayon-sy">)</span><span class="crayon-h"> </span><span class="crayon-sy">{</span></div><div class="crayon-line" id="crayon-589875b298f35469192486-3"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-v">ng</span><span class="crayon-sy">.</span><span class="crayon-v">platformBrowserDynamic</span><span class="crayon-sy">.</span><span class="crayon-e">bootstrap</span><span class="crayon-sy">(</span><span class="crayon-v">app</span><span class="crayon-sy">.</span><span class="crayon-v">AppComponent</span><span class="crayon-sy">)</span><span class="crayon-sy">;</span></div><div class="crayon-line" id="crayon-589875b298f35469192486-4"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-sy">}</span><span class="crayon-sy">)</span><span class="crayon-sy">;</span></div><div class="crayon-line" id="crayon-589875b298f35469192486-5"><span class="crayon-sy">}</span><span class="crayon-sy">)</span><span class="crayon-sy">(</span><span class="crayon-v">window</span><span class="crayon-sy">.</span><span class="crayon-v">app</span><span class="crayon-h"> </span><span class="crayon-o">||</span><span class="crayon-h"> </span><span class="crayon-sy">(</span><span class="crayon-v">window</span><span class="crayon-sy">.</span><span class="crayon-v">app</span><span class="crayon-h"> </span><span class="crayon-o">=</span><span class="crayon-h"> </span><span class="crayon-sy">{</span><span class="crayon-sy">}</span><span class="crayon-sy">)</span><span class="crayon-sy">)</span><span class="crayon-sy">;</span></div></div></td>
                    </tr>
                </table>
            </div>
        </div>
    

<!-- [Format Time: 0.0024 seconds] -->

<!-- Crayon Syntax Highlighter v_2.7.2_beta -->

        <div id="crayon-589875b298f3a020753226" class="crayon-syntax crayon-theme-sublime-text crayon-font-sourcecodepro crayon-os-pc print-yes notranslate" style="margin-top: 12px;margin-bottom: 12px;font-size: 14px !important;line-height: 24px !important">
    
            <div class="crayon-plain-wrap"></div>
            <div class="crayon-main">
                <table class="crayon-table">
                    <tr class="crayon-row">
                <td class="crayon-nums ">
                    <div class="crayon-nums-content" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-num">1</div><div class="crayon-num">2</div><div class="crayon-num">3</div><div class="crayon-num">4</div><div class="crayon-num">5</div><div class="crayon-num">6</div><div class="crayon-num">7</div><div class="crayon-num">8</div><div class="crayon-num">9</div><div class="crayon-num">10</div><div class="crayon-num">11</div><div class="crayon-num">12</div><div class="crayon-num">13</div><div class="crayon-num">14</div><div class="crayon-num">15</div><div class="crayon-num">16</div><div class="crayon-num">17</div><div class="crayon-num">18</div><div class="crayon-num">19</div><div class="crayon-num">20</div><div class="crayon-num">21</div><div class="crayon-num">22</div><div class="crayon-num">23</div><div class="crayon-num">24</div><div class="crayon-num">25</div></div>
                </td>
                        <td class="crayon-code"><div class="crayon-pre" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-line" id="crayon-589875b298f3a020753226-1"><span class="crayon-o">&lt;</span><span class="crayon-v">html</span><span class="crayon-o">&gt;</span></div><div class="crayon-line" id="crayon-589875b298f3a020753226-2"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-o">&lt;</span><span class="crayon-v">head</span><span class="crayon-o">&gt;</span></div><div class="crayon-line" id="crayon-589875b298f3a020753226-3"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-o">&lt;</span><span class="crayon-v">title</span><span class="crayon-o">&gt;</span><span class="crayon-i">Angular</span><span class="crayon-h"> </span><span class="crayon-cn">2</span><span class="crayon-h"> </span><span class="crayon-e">QuickStart </span><span class="crayon-v">JS</span><span class="crayon-o">&lt;</span><span class="crayon-o">/</span><span class="crayon-v">title</span><span class="crayon-o">&gt;</span></div><div class="crayon-line" id="crayon-589875b298f3a020753226-4"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-o">&lt;</span><span class="crayon-e">meta </span><span class="crayon-v">name</span><span class="crayon-o">=</span><span class="crayon-s">"viewport"</span><span class="crayon-h"> </span><span class="crayon-v">content</span><span class="crayon-o">=</span><span class="crayon-s">"width=device-width, initial-scale=1"</span><span class="crayon-o">&gt;</span></div><div class="crayon-line" id="crayon-589875b298f3a020753226-5"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-o">&lt;</span><span class="crayon-e">link </span><span class="crayon-v">rel</span><span class="crayon-o">=</span><span class="crayon-s">"stylesheet"</span><span class="crayon-h"> </span><span class="crayon-v">href</span><span class="crayon-o">=</span><span class="crayon-s">"styles.css"</span><span class="crayon-o">&gt;</span></div><div class="crayon-line" id="crayon-589875b298f3a020753226-6"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-o">&lt;</span><span class="crayon-o">!</span><span class="crayon-o">--</span><span class="crayon-h"> </span><span class="crayon-cn">1.</span><span class="crayon-h"> </span><span class="crayon-e">Load</span><span class="crayon-h"> </span><span class="crayon-e">libraries</span><span class="crayon-h"> </span><span class="crayon-o">--</span><span class="crayon-o">&gt;</span></div><div class="crayon-line" id="crayon-589875b298f3a020753226-7"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-o">&lt;</span><span class="crayon-o">!</span><span class="crayon-o">--</span><span class="crayon-h"> </span><span class="crayon-e">IE</span><span class="crayon-h"> </span><span class="crayon-e">required</span><span class="crayon-h"> </span><span class="crayon-e">polyfill</span><span class="crayon-h"> </span><span class="crayon-o">--</span><span class="crayon-o">&gt;</span></div><div class="crayon-line" id="crayon-589875b298f3a020753226-8"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-ta">&lt;script </span><span class="crayon-e ">src</span><span class="crayon-o">=</span><span class="crayon-s">"node_modules/es6-shim/es6-shim.min.js"</span><span class="crayon-o">&gt;</span><span class="crayon-ta">&lt;/script&gt;</span></div><div class="crayon-line" id="crayon-589875b298f3a020753226-9"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-ta">&lt;script </span><span class="crayon-e ">src</span><span class="crayon-o">=</span><span class="crayon-s">"node_modules/zone.js/dist/zone.js"</span><span class="crayon-o">&gt;</span><span class="crayon-ta">&lt;/script&gt;</span></div><div class="crayon-line" id="crayon-589875b298f3a020753226-10"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-ta">&lt;script </span><span class="crayon-e ">src</span><span class="crayon-o">=</span><span class="crayon-s">"node_modules/reflect-metadata/Reflect.js"</span><span class="crayon-o">&gt;</span><span class="crayon-ta">&lt;/script&gt;</span></div><div class="crayon-line" id="crayon-589875b298f3a020753226-11"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-ta">&lt;script </span><span class="crayon-e ">src</span><span class="crayon-o">=</span><span class="crayon-s">"node_modules/rxjs/bundles/Rx.umd.js"</span><span class="crayon-o">&gt;</span><span class="crayon-ta">&lt;/script&gt;</span></div><div class="crayon-line" id="crayon-589875b298f3a020753226-12"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-ta">&lt;script </span><span class="crayon-e ">src</span><span class="crayon-o">=</span><span class="crayon-s">"node_modules/@angular/core/core.umd.js"</span><span class="crayon-o">&gt;</span><span class="crayon-ta">&lt;/script&gt;</span></div><div class="crayon-line" id="crayon-589875b298f3a020753226-13"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-ta">&lt;script </span><span class="crayon-e ">src</span><span class="crayon-o">=</span><span class="crayon-s">"node_modules/@angular/common/common.umd.js"</span><span class="crayon-o">&gt;</span><span class="crayon-ta">&lt;/script&gt;</span></div><div class="crayon-line" id="crayon-589875b298f3a020753226-14"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-ta">&lt;script </span><span class="crayon-e ">src</span><span class="crayon-o">=</span><span class="crayon-s">"node_modules/@angular/compiler/compiler.umd.js"</span><span class="crayon-o">&gt;</span><span class="crayon-ta">&lt;/script&gt;</span></div><div class="crayon-line" id="crayon-589875b298f3a020753226-15"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-ta">&lt;script </span><span class="crayon-e ">src</span><span class="crayon-o">=</span><span class="crayon-s">"node_modules/@angular/platform-browser/platform-browser.umd.js"</span><span class="crayon-o">&gt;</span><span class="crayon-ta">&lt;/script&gt;</span></div><div class="crayon-line" id="crayon-589875b298f3a020753226-16"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-ta">&lt;script </span><span class="crayon-e ">src</span><span class="crayon-o">=</span><span class="crayon-s">"node_modules/@angular/platform-browser-dynamic/platform-browser-dynamic.umd.js"</span><span class="crayon-o">&gt;</span><span class="crayon-ta">&lt;/script&gt;</span></div><div class="crayon-line" id="crayon-589875b298f3a020753226-17"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-o">&lt;</span><span class="crayon-o">!</span><span class="crayon-o">--</span><span class="crayon-h"> </span><span class="crayon-cn">2.</span><span class="crayon-h"> </span><span class="crayon-e">Load </span><span class="crayon-i">our</span><span class="crayon-h"> </span><span class="crayon-s">'modules'</span><span class="crayon-h"> </span><span class="crayon-o">--</span><span class="crayon-o">&gt;</span></div><div class="crayon-line" id="crayon-589875b298f3a020753226-18"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-ta">&lt;script </span><span class="crayon-e ">src</span><span class="crayon-o">=</span><span class="crayon-s">'app/app.component.js'</span><span class="crayon-o">&gt;</span><span class="crayon-ta">&lt;/script&gt;</span></div><div class="crayon-line" id="crayon-589875b298f3a020753226-19"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-ta">&lt;script </span><span class="crayon-e ">src</span><span class="crayon-o">=</span><span class="crayon-s">'app/main.js'</span><span class="crayon-o">&gt;</span><span class="crayon-ta">&lt;/script&gt;</span></div><div class="crayon-line" id="crayon-589875b298f3a020753226-20"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-o">&lt;</span><span class="crayon-o">/</span><span class="crayon-v">head</span><span class="crayon-o">&gt;</span></div><div class="crayon-line" id="crayon-589875b298f3a020753226-21"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-o">&lt;</span><span class="crayon-o">!</span><span class="crayon-o">--</span><span class="crayon-h"> </span><span class="crayon-cn">3.</span><span class="crayon-h"> </span><span class="crayon-e">Display </span><span class="crayon-e">the </span><span class="crayon-v">application</span><span class="crayon-h"> </span><span class="crayon-o">--</span><span class="crayon-o">&gt;</span></div><div class="crayon-line" id="crayon-589875b298f3a020753226-22"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-o">&lt;</span><span class="crayon-v">body</span><span class="crayon-o">&gt;</span></div><div class="crayon-line" id="crayon-589875b298f3a020753226-23"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-o">&lt;</span><span class="crayon-v">my</span><span class="crayon-o">-</span><span class="crayon-v">app</span><span class="crayon-o">&gt;</span><span class="crayon-v">Loading</span><span class="crayon-sy">.</span><span class="crayon-sy">.</span><span class="crayon-sy">.</span><span class="crayon-o">&lt;</span><span class="crayon-o">/</span><span class="crayon-v">my</span><span class="crayon-o">-</span><span class="crayon-v">app</span><span class="crayon-o">&gt;</span></div><div class="crayon-line" id="crayon-589875b298f3a020753226-24"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-o">&lt;</span><span class="crayon-o">/</span><span class="crayon-v">body</span><span class="crayon-o">&gt;</span></div><div class="crayon-line" id="crayon-589875b298f3a020753226-25"><span class="crayon-o">&lt;</span><span class="crayon-o">/</span><span class="crayon-v">html</span><span class="crayon-o">&gt;</span></div></div></td>
                    </tr>
                </table>
            </div>
        </div>
    

<!-- [Format Time: 0.0094 seconds] -->

<!-- Crayon Syntax Highlighter v_2.7.2_beta -->

        <div id="crayon-589875b298f41416670087" class="crayon-syntax crayon-theme-sublime-text crayon-font-sourcecodepro crayon-os-pc print-yes notranslate" style="margin-top: 12px;margin-bottom: 12px;font-size: 14px !important;line-height: 24px !important">
    
            <div class="crayon-plain-wrap"></div>
            <div class="crayon-main">
                <table class="crayon-table">
                    <tr class="crayon-row">
                <td class="crayon-nums ">
                    <div class="crayon-nums-content" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-num">1</div><div class="crayon-num">2</div><div class="crayon-num">3</div><div class="crayon-num">4</div><div class="crayon-num">5</div><div class="crayon-num">6</div><div class="crayon-num">7</div><div class="crayon-num">8</div><div class="crayon-num">9</div><div class="crayon-num">10</div><div class="crayon-num">11</div><div class="crayon-num">12</div><div class="crayon-num">13</div><div class="crayon-num">14</div><div class="crayon-num">15</div><div class="crayon-num">16</div><div class="crayon-num">17</div><div class="crayon-num">18</div><div class="crayon-num">19</div><div class="crayon-num">20</div><div class="crayon-num">21</div><div class="crayon-num">22</div><div class="crayon-num">23</div><div class="crayon-num">24</div><div class="crayon-num">25</div><div class="crayon-num">26</div><div class="crayon-num">27</div><div class="crayon-num">28</div><div class="crayon-num">29</div></div>
                </td>
                        <td class="crayon-code"><div class="crayon-pre" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-line" id="crayon-589875b298f41416670087-1"><span class="crayon-sy">{</span></div><div class="crayon-line" id="crayon-589875b298f41416670087-2"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-s">"name"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"angular2-quickstart"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f41416670087-3"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-s">"version"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"1.0.0"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f41416670087-4"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-s">"scripts"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-sy">{</span></div><div class="crayon-line" id="crayon-589875b298f41416670087-5"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"start"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"npm run lite"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f41416670087-6"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"lite"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"lite-server"</span></div><div class="crayon-line" id="crayon-589875b298f41416670087-7"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-sy">}</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f41416670087-8"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-s">"license"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"ISC"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f41416670087-9"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-s">"dependencies"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-sy">{</span></div><div class="crayon-line" id="crayon-589875b298f41416670087-10"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"@angular/common"</span><span class="crayon-o">:</span><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-s">"2.0.0-rc.1"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f41416670087-11"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"@angular/compiler"</span><span class="crayon-o">:</span><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-s">"2.0.0-rc.1"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f41416670087-12"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"@angular/core"</span><span class="crayon-o">:</span><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-s">"2.0.0-rc.1"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f41416670087-13"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"@angular/http"</span><span class="crayon-o">:</span><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-s">"2.0.0-rc.1"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f41416670087-14"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"@angular/platform-browser"</span><span class="crayon-o">:</span><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-s">"2.0.0-rc.1"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f41416670087-15"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"@angular/platform-browser-dynamic"</span><span class="crayon-o">:</span><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-s">"2.0.0-rc.1"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f41416670087-16"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"@angular/router"</span><span class="crayon-o">:</span><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-s">"2.0.0-rc.1"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f41416670087-17"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"@angular/router-deprecated"</span><span class="crayon-o">:</span><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-s">"2.0.0-rc.1"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f41416670087-18"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"@angular/upgrade"</span><span class="crayon-o">:</span><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-s">"2.0.0-rc.1"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f41416670087-19"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"reflect-metadata"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"0.1.3"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f41416670087-20"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"rxjs"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"5.0.0-beta.6"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f41416670087-21"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"zone.js"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"0.6.12"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f41416670087-22"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"angular2-in-memory-web-api"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"0.0.7"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f41416670087-23"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"bootstrap"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"^3.3.6"</span></div><div class="crayon-line" id="crayon-589875b298f41416670087-24"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-sy">}</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f41416670087-25"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-s">"devDependencies"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-sy">{</span></div><div class="crayon-line" id="crayon-589875b298f41416670087-26"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"concurrently"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"^2.0.0"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f41416670087-27"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"lite-server"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"^2.2.0"</span></div><div class="crayon-line" id="crayon-589875b298f41416670087-28"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-sy">}</span></div><div class="crayon-line" id="crayon-589875b298f41416670087-29"><span class="crayon-sy">}</span></div></div></td>
                    </tr>
                </table>
            </div>
        </div>
    

<!-- [Format Time: 0.0056 seconds] -->

## Wrap Up ?打包

我们的第一个应用程序不会去做太多。它基本上是Angular2版本的“Hello, World”?。
  
我们保持了它的简洁：编写一个小Angular组件，给index.html增加了一些JavaScript库，用一个静态文件服务器启动。这就是预期的“Hello, [Online](http://philadelphiaeaglesjerseyspop.forumcity.com/viewtopic.php?p=20#20) World”应用程序需要做的。
  
但是我们需要Angular2做的更多。
  
好消息是，大部分设置我们可以丢到脑后。我们可能只会触及package.json的更新。除了为我们的应用“模块”增加脚本文件，我们很可能只有当我们需要添加一个库或CSS样式表才会打开index.html。
  
下一步，构建一个小的应用程序演示，用Angular2建立更好的东西。

[加入我们的英雄教程之旅！](https://angular.io/docs/js/latest/tutorial)

## 附录

这章由几部分快速阐述几个重要点
  
这里没有详细的资料，如果你好奇可以继续查阅。

<div class="l-main-section">
</div>

### 附录：库

我们载入下面的脚本文件

<!-- Crayon Syntax Highlighter v_2.7.2_beta -->

        <div id="crayon-589875b298f48773778536" class="crayon-syntax crayon-theme-sublime-text crayon-font-sourcecodepro crayon-os-pc print-yes notranslate" style="margin-top: 12px;margin-bottom: 12px;font-size: 14px !important;line-height: 24px !important">
    
            <div class="crayon-plain-wrap"></div>
            <div class="crayon-main">
                <table class="crayon-table">
                    <tr class="crayon-row">
                <td class="crayon-nums ">
                    <div class="crayon-nums-content" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-num">1</div><div class="crayon-num">2</div><div class="crayon-num">3</div><div class="crayon-num">4</div><div class="crayon-num">5</div><div class="crayon-num">6</div><div class="crayon-num">7</div><div class="crayon-num">8</div><div class="crayon-num">9</div><div class="crayon-num">10</div><div class="crayon-num">11</div><div class="crayon-num">12</div></div>
                </td>
                        <td class="crayon-code"><div class="crayon-pre" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-line" id="crayon-589875b298f48773778536-1"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-o">&lt;</span><span class="crayon-o">!</span><span class="crayon-o">--</span><span class="crayon-h"> </span><span class="crayon-e">IE</span><span class="crayon-h"> </span><span class="crayon-e">required</span><span class="crayon-h"> </span><span class="crayon-e">polyfill</span><span class="crayon-h"> </span><span class="crayon-o">--</span><span class="crayon-o">&gt;</span></div><div class="crayon-line" id="crayon-589875b298f48773778536-2"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-ta">&lt;script </span><span class="crayon-e ">src</span><span class="crayon-o">=</span><span class="crayon-s">"node_modules/es6-shim/es6-shim.min.js"</span><span class="crayon-o">&gt;</span><span class="crayon-ta">&lt;/script&gt;</span></div><div class="crayon-line" id="crayon-589875b298f48773778536-3">&nbsp;</div><div class="crayon-line" id="crayon-589875b298f48773778536-4"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-ta">&lt;script </span><span class="crayon-e ">src</span><span class="crayon-o">=</span><span class="crayon-s">"node_modules/zone.js/dist/zone.js"</span><span class="crayon-o">&gt;</span><span class="crayon-ta">&lt;/script&gt;</span></div><div class="crayon-line" id="crayon-589875b298f48773778536-5"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-ta">&lt;script </span><span class="crayon-e ">src</span><span class="crayon-o">=</span><span class="crayon-s">"node_modules/reflect-metadata/Reflect.js"</span><span class="crayon-o">&gt;</span><span class="crayon-ta">&lt;/script&gt;</span></div><div class="crayon-line" id="crayon-589875b298f48773778536-6">&nbsp;</div><div class="crayon-line" id="crayon-589875b298f48773778536-7"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-ta">&lt;script </span><span class="crayon-e ">src</span><span class="crayon-o">=</span><span class="crayon-s">"node_modules/rxjs/bundles/Rx.umd.js"</span><span class="crayon-o">&gt;</span><span class="crayon-ta">&lt;/script&gt;</span></div><div class="crayon-line" id="crayon-589875b298f48773778536-8"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-ta">&lt;script </span><span class="crayon-e ">src</span><span class="crayon-o">=</span><span class="crayon-s">"node_modules/@angular/core/core.umd.js"</span><span class="crayon-o">&gt;</span><span class="crayon-ta">&lt;/script&gt;</span></div><div class="crayon-line" id="crayon-589875b298f48773778536-9"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-ta">&lt;script </span><span class="crayon-e ">src</span><span class="crayon-o">=</span><span class="crayon-s">"node_modules/@angular/common/common.umd.js"</span><span class="crayon-o">&gt;</span><span class="crayon-ta">&lt;/script&gt;</span></div><div class="crayon-line" id="crayon-589875b298f48773778536-10"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-ta">&lt;script </span><span class="crayon-e ">src</span><span class="crayon-o">=</span><span class="crayon-s">"node_modules/@angular/compiler/compiler.umd.js"</span><span class="crayon-o">&gt;</span><span class="crayon-ta">&lt;/script&gt;</span></div><div class="crayon-line" id="crayon-589875b298f48773778536-11"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-ta">&lt;script </span><span class="crayon-e ">src</span><span class="crayon-o">=</span><span class="crayon-s">"node_modules/@angular/platform-browser/platform-browser.umd.js"</span><span class="crayon-o">&gt;</span><span class="crayon-ta">&lt;/script&gt;</span></div><div class="crayon-line" id="crayon-589875b298f48773778536-12"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-ta">&lt;script </span><span class="crayon-e ">src</span><span class="crayon-o">=</span><span class="crayon-s">"node_modules/@angular/platform-browser-dynamic/platform-browser-dynamic.umd.js"</span><span class="crayon-o">&gt;</span><span class="crayon-ta">&lt;/script&gt;</span></div></div></td>
                    </tr>
                </table>
            </div>
        </div>
    

<!-- [Format Time: 0.0045 seconds] -->

我们开始于一个Internet Explorer填充工具。 IE需要填充工具来运行依赖于ES2015 promises和动态加载模块的应用程序。大多数应用程序需要这些功能并且能在Internet Explorer中运行。
  
接下来是Angular2的polyfills，zone.js和Reflect.js，跟随the Reactive Extensions RxJS库.

> 我们的快速入门没有使用RxJS库,但是任何实质的应用都想要RxJS库，我们在快速入门项目中加入库，以后以后忘记。

最后，我们载入了Angular2本身的web开发版本
  
以后为了提升产品质量（载入时间，内存占用）我们会做出不同的选择

### 附录： package.json

npm是一个流行的包管理器，Angular应用开发者依靠它获得和管理应用依赖的库。
  
我们在npm中指定我们需要的库文件package.json.
  
The Angular team suggests the packages listed [wholesale nfl jerseys](http://www.newenglandpatriotsjerseyspop.com) in the `dependencies` and `devDependencies` sections listed [wholesale mlb jerseys](http://www.dallascowboysjerseyspop.com) in this file:
  
Angular官方建议把包的清单列入文件的dependencies和devDependencies部分：

<!-- Crayon Syntax Highlighter v_2.7.2_beta -->

        <div id="crayon-589875b298f50834917547" class="crayon-syntax crayon-theme-sublime-text crayon-font-sourcecodepro crayon-os-pc print-yes notranslate" style="margin-top: 12px;margin-bottom: 12px;font-size: 14px !important;line-height: 24px !important">
    
            <div class="crayon-plain-wrap"></div>
            <div class="crayon-main">
                <table class="crayon-table">
                    <tr class="crayon-row">
                <td class="crayon-nums ">
                    <div class="crayon-nums-content" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-num">1</div><div class="crayon-num">2</div><div class="crayon-num">3</div><div class="crayon-num">4</div><div class="crayon-num">5</div><div class="crayon-num">6</div><div class="crayon-num">7</div><div class="crayon-num">8</div><div class="crayon-num">9</div><div class="crayon-num">10</div><div class="crayon-num">11</div><div class="crayon-num">12</div><div class="crayon-num">13</div><div class="crayon-num">14</div><div class="crayon-num">15</div><div class="crayon-num">16</div><div class="crayon-num">17</div><div class="crayon-num">18</div><div class="crayon-num">19</div><div class="crayon-num">20</div><div class="crayon-num">21</div><div class="crayon-num">22</div></div>
                </td>
                        <td class="crayon-code"><div class="crayon-pre" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-line" id="crayon-589875b298f50834917547-1"><span class="crayon-sy">{</span></div><div class="crayon-line" id="crayon-589875b298f50834917547-2"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-s">"dependencies"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-sy">{</span></div><div class="crayon-line" id="crayon-589875b298f50834917547-3"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"@angular/common"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"2.0.0-rc.1"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f50834917547-4"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"@angular/compiler"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"2.0.0-rc.1"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f50834917547-5"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"@angular/core"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"2.0.0-rc.1"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f50834917547-6"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"@angular/http"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"2.0.0-rc.1"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f50834917547-7"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"@angular/platform-browser"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"2.0.0-rc.1"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f50834917547-8"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"@angular/platform-browser-dynamic"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"2.0.0-rc.1"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f50834917547-9"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"@angular/router"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"2.0.0-rc.1"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f50834917547-10"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"@angular/router-deprecated"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"2.0.0-rc.1"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f50834917547-11"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"@angular/upgrade"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"2.0.0-rc.1"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f50834917547-12"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"reflect-metadata"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"0.1.3"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f50834917547-13"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"rxjs"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"5.0.0-beta.6"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f50834917547-14"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"zone.js"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"0.6.12"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f50834917547-15"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"angular2-in-memory-web-api"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"0.0.7"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f50834917547-16"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"bootstrap"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"^3.3.6"</span></div><div class="crayon-line" id="crayon-589875b298f50834917547-17"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-sy">}</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f50834917547-18"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-s">"devDependencies"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-sy">{</span></div><div class="crayon-line" id="crayon-589875b298f50834917547-19"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"concurrently"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"^2.0.0"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f50834917547-20"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"lite-server"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"^2.2.0"</span></div><div class="crayon-line" id="crayon-589875b298f50834917547-21"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-sy">}</span></div><div class="crayon-line" id="crayon-589875b298f50834917547-22"><span class="crayon-sy">}</span></div></div></td>
                    </tr>
                </table>
            </div>
        </div>
    

<!-- [Format Time: 0.0043 seconds] -->

> 还有一些其他的包可供选择。我们推荐这个很好使用的专门设置。现在和我们一起使用吧。以后可以随意替换来适应你的习惯和经验。
    
> 一个package.json文件有一个可供选择的script部分，方便我们定义有用的命令来进行开发和建设任务。我们已经包含了一些这样的脚本在我们的package.json：

<!-- Crayon Syntax Highlighter v_2.7.2_beta -->

        <div id="crayon-589875b298f57553495418" class="crayon-syntax crayon-theme-sublime-text crayon-font-sourcecodepro crayon-os-pc print-yes notranslate" style="margin-top: 12px;margin-bottom: 12px;font-size: 14px !important;line-height: 24px !important">
    
            <div class="crayon-plain-wrap"></div>
            <div class="crayon-main">
                <table class="crayon-table">
                    <tr class="crayon-row">
                <td class="crayon-nums ">
                    <div class="crayon-nums-content" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-num">1</div><div class="crayon-num">2</div><div class="crayon-num">3</div><div class="crayon-num">4</div><div class="crayon-num">5</div><div class="crayon-num">6</div></div>
                </td>
                        <td class="crayon-code"><div class="crayon-pre" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-line" id="crayon-589875b298f57553495418-1"><span class="crayon-sy">{</span></div><div class="crayon-line" id="crayon-589875b298f57553495418-2"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-s">"scripts"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-sy">{</span></div><div class="crayon-line" id="crayon-589875b298f57553495418-3"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"start"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"npm run lite"</span><span class="crayon-sy">,</span></div><div class="crayon-line" id="crayon-589875b298f57553495418-4"><span class="crayon-h">&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="crayon-s">"lite"</span><span class="crayon-o">:</span><span class="crayon-h"> </span><span class="crayon-s">"lite-server"</span></div><div class="crayon-line" id="crayon-589875b298f57553495418-5"><span class="crayon-h">&nbsp;&nbsp;</span><span class="crayon-sy">}</span></div><div class="crayon-line" id="crayon-589875b298f57553495418-6"><span class="crayon-sy">}</span></div></div></td>
                    </tr>
                </table>
            </div>
        </div>
    

<!-- [Format Time: 0.0011 seconds] -->

我们可以看到如何在服务器上运行这些命令

<!-- Crayon Syntax Highlighter v_2.7.2_beta -->

        <div id="crayon-589875b298f5c550724012" class="crayon-syntax crayon-theme-sublime-text crayon-font-sourcecodepro crayon-os-pc print-yes notranslate" style="margin-top: 12px;margin-bottom: 12px;font-size: 14px !important;line-height: 24px !important">
    
            <div class="crayon-plain-wrap"></div>
            <div class="crayon-main">
                <table class="crayon-table">
                    <tr class="crayon-row">
                <td class="crayon-nums ">
                    <div class="crayon-nums-content" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-num">1</div></div>
                </td>
                        <td class="crayon-code"><div class="crayon-pre" style="font-size: 14px !important;line-height: 24px !important"><div class="crayon-line" id="crayon-589875b298f5c550724012-1"><span class="crayon-e">npm </span><span class="crayon-v">start</span></div></div></td>
                    </tr>
                </table>
            </div>
        </div>
    

<!-- [Format Time: 0.0004 seconds] -->

我们使用专用的npm start命令，但是它所做的只是运行`npm run lite`。
  
我们用这样的方式执行npm脚本：`npm run` + 脚本名。下面是这些脚本所做的：

  * npm run lite &#8211; 运行 lite-server,一个轻量的静态文件服务器，由John Papa编写和维护，对Angular应用使用路由有很好的支持。

### 附录: Npm 的错误和警告

如果没有以`npm  <a href="http://www.ziwuo.com/archives/36.html">AngularJS，实现contenteditable的双向绑定</a>  ERR!`开头的消息出现在npm安装的尾部表示一切都没问题。也许会有一些`npm WARN`的消息，这是完全没问题的。
  
我们有时候会看到`npm WARN`的消息在一系列的`gyp ERR!`的消息后面。忽略它。一个包可能会使用`node-gyp`重新编译它自己。如果重新编译失败，包就会还原（通常是预发布版本）一切都能正常使用。

只要确定没有`npm ERR!`消息在`npm install`的最后面。

### 附录: main.js

#### 引导特定的平台

我们从`ng.platformBrowserDynamic`中使用`bootstrap`功能，而不是`ng.core`，这里有一个非常好的理由。
  
只有在所有平台的目标功能我们才称之为&#8221;core&#8221;。大部分Angular应用只运行在浏览器上，我们大部分时间只从这个库调用引到函数。如果我们总是为浏览器来编写这就是一个标准的&#8221;core&#8221;

但是它有可能在不同环境载入一个组件。我们可能在一个移动设备的`Apache Cordova`或者`NativeScript`上载入它。我们也许希望渲染应用的第一页来提高启动性能或便于搜索引擎优化。
  
这些目标需要我们从不同的库中引入不同的引导函数

#### 为什么要建立一个单独的main.js文件？

main.js文件很小。这只是个快速入门项目。你可以把它合并到`app.component.js`文件来避免复杂度。
  
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

当编写一个单独的main.js文件我们学习到了一个必要的Angular技巧：如何从一个模块中导出和导入到另一个途径的命名空间的概念。在以后的Angular学习中我们会做很多这样的事。