---
id: 205
title: angular-cli lazy loading 懒加载
date: 2017-04-26T10:59:23+00:00
author: crazy4x
layout: post
categories:
  - Angular
---

### **安装 angular-cli**

<pre class="">npm install -g @angular/cli</pre>

如果你使用的的是 `beta.28`或更以前的版本升级前需要先卸载 angular-cli，因为 `angular-cli` 已经变成了 `@angular/cli`

升级 Angular CLI，你需要同时升级全局的和项目本地目录中的，避免出现一些难以排查的问题

<!--more-->

安装完成后运行命令?`ng version?`我现在使用的版本是 1.0.0 ，安装时候请注意 node 的版本

&nbsp;

### 新建项目

使用命令

<pre class="lang:default decode:true">ng new angular-cli-lazyloading</pre>

<span style="color: #ff0000;">注意：npm 包下载安装会需要一段时间，请耐心等待出现 successfully created</span>

&nbsp;

### 路由

我们参照官方的教程（<https://www.angular.cn/docs/ts/latest/tutorial/toh-pt5.html>）来配置一下路由实现 home 页和 about 页面的切换

我们创建两个组件，home 和 about

在这里我还创建了一个 about 的 module，随后的懒加载会用到

app.module.ts

```javascript
import { BrowserModule } from "@angular/platform-browser";
import { NgModule } from "@angular/core";
import { FormsModule } from "@angular/forms";
import { HttpModule } from "@angular/http";

import { AppComponent } from "./app.component";
import { HomeComponent } from "./home/home.component";
import { RouterModule, Routes } from "@angular/router";
import { AboutComponent } from "./about/about.component";

const rootRoutes: Routes = [
  { path: "", redirectTo: "/home", pathMatch: "full" },
  { path: "home", component: HomeComponent },
  { path: "about", component: AboutComponent },
];

@NgModule({
  declarations: [AppComponent, HomeComponent, AboutComponent],
  imports: [
    BrowserModule,
    FormsModule,
    HttpModule,
    RouterModule.forRoot(rootRoutes),
  ],
  providers: [],
  bootstrap: [AppComponent],
})
export class AppModule {}
```

&nbsp;

app.component.html

```html
<nav>
  <a routerLink="/home">Home</a>
  <a routerLink="/about">About</a>
</nav>
<router-outlet></router-outlet>
```

&nbsp;

修改以上代码就可以实现一个简单的路由功能

&nbsp;

### 懒加载 Lazy Loading

现在开始我们修改代码来实现懒加载

首先我们来修改稍早建立的 about.module.ts

<img class="alignnone size-full wp-image-214" src="http://www.ziwuo.com/wp-content/uploads/2017/04/TIM截图20170426103107.png" alt="" width="650" height="385" srcset="https://www.ziwuo.com/wp-content/uploads/2017/04/TIM截图20170426103107.png 650w, https://www.ziwuo.com/wp-content/uploads/2017/04/TIM截图20170426103107-300x178.png 300w" sizes="(max-width: 650px) 100vw, 650px" />

&nbsp;

然后修改 app.module.ts 的路由部分

<img class="alignnone size-full wp-image-215" src="http://www.ziwuo.com/wp-content/uploads/2017/04/TIM截图20170426104758.png" alt="" width="953" height="589" srcset="https://www.ziwuo.com/wp-content/uploads/2017/04/TIM截图20170426104758.png 953w, https://www.ziwuo.com/wp-content/uploads/2017/04/TIM截图20170426104758-300x185.png 300w, https://www.ziwuo.com/wp-content/uploads/2017/04/TIM截图20170426104758-768x475.png 768w" sizes="(max-width: 767px) 89vw, (max-width: 1000px) 54vw, (max-width: 1071px) 543px, 580px" />

**完成！**就是这么简单，通过 loadChildren 来实现懒加载

&nbsp;

现在运行 ng serve 看看效果

<img class="alignnone size-full wp-image-216" src="http://www.ziwuo.com/wp-content/uploads/2017/04/TIM截图20170426105705.png" alt="" width="878" height="466" srcset="https://www.ziwuo.com/wp-content/uploads/2017/04/TIM截图20170426105705.png 878w, https://www.ziwuo.com/wp-content/uploads/2017/04/TIM截图20170426105705-300x159.png 300w, https://www.ziwuo.com/wp-content/uploads/2017/04/TIM截图20170426105705-768x408.png 768w" sizes="(max-width: 767px) 89vw, (max-width: 1000px) 54vw, (max-width: 1071px) 543px, 580px" /><img class="alignnone size-full wp-image-217" src="http://www.ziwuo.com/wp-content/uploads/2017/04/TIM截图20170426105723.png" alt="" width="866" height="451" srcset="https://www.ziwuo.com/wp-content/uploads/2017/04/TIM截图20170426105723.png 866w, https://www.ziwuo.com/wp-content/uploads/2017/04/TIM截图20170426105723-300x156.png 300w, https://www.ziwuo.com/wp-content/uploads/2017/04/TIM截图20170426105723-768x400.png 768w" sizes="(max-width: 767px) 89vw, (max-width: 1000px) 54vw, (max-width: 1071px) 543px, 580px" />

可以看到在加载 about 的时候多了一个 0.chunk.js 的文件
