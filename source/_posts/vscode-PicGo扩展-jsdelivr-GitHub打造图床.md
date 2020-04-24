---
title: vscode+PicGo扩展+jsdelivr+GitHub打造图床
date: 2020-04-23 21:25:16
tags:
  - vscode
  - PicGo扩展
  - jsdelivr
  - GitHub图床
  - markdown图床
---

## 前言

使用 Hexo 打造个人博客的时候你总会发现需要一个图床，免费又限制少的当属 GitHub，当然免费存在的问题，GitHub 的问题就是访问速度慢，这时候使用 jsDelivr 作为 GitHub 的免费 CDN 解决方案，就能打造一个即快速又免费的图床了，而 vscode 的扩展 PicGo 的优势就在于能像复制粘贴一样高效快速的进行截图、上传、返回图片 url、插入 markdown 格式，从而让你的关注点一直集中在 markdown 内容本身，而不是分散关注到上传图片，获取地址返回，书写 markdown 的图片。

<!--more-->

## GitHub 设置

### 创建一个仓库

例如我们创建了一个名为`PicGoBed`的仓库，用来存放我们的图片，注意仓库必须是 public 的，这样才能作为图库访问

![20200423213623](https://cdn.jsdelivr.net/gh/onyz4x/PicGoBed/images/20200423213623.png)

### 生成 GitHub 的 token

#### 目的

生成 token 的目的是为了让 PicGo 能有访问我们仓库的权限

#### 方法

进入你 GitHub 的 settings（注意是账号的 settings 不是你仓库的 settings），依次进入`Settings > Developer settings > Personal access tokens`，点击`Generate new token`进入页面，填写 Note，勾选 repo 的权限，然后生成 token。

![20200423224204](https://cdn.jsdelivr.net/gh/onyz4x/PicGoBed/images/20200423224204.png)

生成完成后会出现一个唯一 token，请记录下来，这个 token 在页面刷新后就会消失并且不能找回

![20200423224623](https://cdn.jsdelivr.net/gh/onyz4x/PicGoBed/images/20200423224623.png)

## vscode 的 PicGo 安装和配置

### 安装 PicGo 扩展

![20200423224945](https://cdn.jsdelivr.net/gh/onyz4x/PicGoBed/images/20200423224945.png)

### 配置 PicGo 扩展

打开 vscode 的设置，搜索`picgo`, 定位到如下设置, 按照图片中的说明来设置,其中需要注意的是自定义 url,在这里我们就用到了 jsdelivr 的免费 CDN 支持,规则就是`https://cdn.jsdelivr.net/gh/<username>/<repo>`,如果你的仓库使用 release 来区分不同版本的话可以使用`https://cdn.jsdelivr.net/gh/<username>/<repo>@<release version>`规则来导入

![20200423230532](https://cdn.jsdelivr.net/gh/onyz4x/PicGoBed/images/20200423230532.png)

## 使用

以上配置完成后,我们就能愉快的使用 PicGo 来为我们 markDown 自动上传图片并生成代码了,我们看一下 picgo 扩展的使用方法

### 快捷键

**You can change all the shortcuts below as you wish.**

| 操作系统     | 从剪贴板上传图片                                | 从文件管理器中上传图片                          | 从 input box 中上传图片                         |
| ------------ | ----------------------------------------------- | ----------------------------------------------- | ----------------------------------------------- |
| Windows/Unix | <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>U</kbd> | <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>E</kbd> | <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>O</kbd> |
| OsX          | <kbd>Cmd</kbd> + <kbd>Opt</kbd> + <kbd>U</kbd>  | <kbd>Cmd</kbd> + <kbd>Opt</kbd> + <kbd>E</kbd>  | <kbd>Cmd</kbd> + <kbd>Opt</kbd> + <kbd>O</kbd>  |

### 功能

<details open>
<summary>从剪贴板上传图片</summary>
<img src="https://i.loli.net/2019/04/09/5cac17d2d2265.gif" alt="clipboard.gif">
</details>

<details open>
<summary>从文件管理器中上传图片</summary>
<img src="https://i.loli.net/2019/04/09/5cac17eea0d65.gif" alt="explorer.gif">
</details>

<details open>
<summary>从input box中上传图片</summary>
<img src="https://i.loli.net/2019/04/09/5cac17fe52a86.gif" alt="input box.gif">
</details>

<details open>
<summary>使用选中的文字作为上传图片的文件名</summary>
<img src="https://i.loli.net/2019/04/09/5cac180fb1dc7.gif" alt="selection.gif">
<b>注意: 这些字符: <code>\$</code>, <code>:</code>, <code>/</code>, <code>?</code> 和换行将会在图片名中被忽略 . </b>(Because they are invalid for file names.)
</details>
