---
title: '''flutter的环境安装（windows）'''
date: 2020-04-23 14:37:19
tags: flutter,vscode,android-sdk
---
因为本人是前端开发人员，已经在用webstorm，不想在安装一个Android studio这么重的IDE，会导致卡顿，所以想使用vscode安装flutter插件作为开发工具，只安装android-sdk

## 安装环境
首先准备一个文件夹专门用来放sdk，命名`Android`，把所有环境有关的sdk都可以装到这里方便管理。

注意：Android文件夹不要使用`C:\Program Files\`这种需要权限的路径

### JDK

https://github.com/AdoptOpenJDK/openjdk8-binaries/releases

选择OpenJDK8U-jdk_x64_windows_hotspot_8u252b09.msi或者OpenJDK8U-jdk_x64_windows_hotspot_8u252b09.zip下载

msi安装的时候选中生成环境变量JAVA_HOME；zip格式的可以解压到`Android`目录，然后自己去添加环境变量JAVA_HOME


###  Flutter Sdk

https://flutter.dev/docs/get-started/install/windows#get-the-flutter-sdk

flutter官方文档，注意路径为`Android/flutter`

### Android SDK 

#### 1. Android command tools(Android-sdk-tool)

https://developer.android.com/studio#command-tools

##### 注意

> 这里有个巨大的坑， 我下载的`commandlinetools-win-6200805_latest.zip`解压`tools`文件放到`Android`目录下后，环境变量中添加`Android/tools/bin`运行sdkmanager会不正常，原因是新版的路径必须是`Android\cmdline-tools\latest`下，但是`Android\cmdline-tools\latest`这个路径会导致另外一个问题`flutter doctor --licenses`命令在解决授权问题的时候找不到sdkmanger。这个坑以后flutter更新版本后可能会解决掉，但是现在只能work around

##### 解决方法

下载老版本`android-sdk-26-1-1.zip`，然后解压到`Android`目录下，然后将`Android\tools\bin`添加到`path`环境变量，设置环境变量`ANDROID_HOME`的地址是`Android`目录 

#### 2. 通过sdkmanager安装其他Android SDK工具

```bash 
sdkmanager “system-images;android-27;default;x86_64”
sdkmanager “platform-tools”
sdkmanager “build-tools;27.0.3”
sdkmanager “platforms;android-27”
sdkmanager emulator
```

> 工具的具体版本可以通过 `sdkmanager --list`命令查询，然后安装对应的最新版本

## 检查运行环境

上面步骤如果没有出现错误，那么恭喜你flutter应该已经安装好了。
为了验证环境是否正常，flutter提供了一个命令` flutter doctor`去检查环境，(可以在vscode中`ctrl+shift+p`输入`flutter`选择`flutter doctor`)
检查结果中可以忽略Android SDK没有安装的警告，你只需要安装vscode和flutter插件，
连接上手机（打开usb调试，允许usb安装应用）

## 运行

在vscode中使用`ctrl+shift+p`输入`flutter`使用`Flutter: New project`来新建一个项目。
输入项目名后，flutter会自动开始初始化项目。
初始化完成后直接按F5即可运行
手机会提示安装一个应用，完成后自动打开就能看到一个点击计数的app了

注意：
> 运行中如果长时间卡在Running Gradle task 'assembleDebug'...。
> 是因为gradle国内下载太慢，解决办法是自己下载，然后放到gradle的下载目录里，让它接着执行之后的操作。
> gradle的目录是类似`C:\Users\xxxx\.gradle\wrapper\dists\gradle-5.6.2-all\9st6wgf78h16so49nn74lgtbb`。
> 下载对应版本的zip直接放到目录中即可，例：`gradle-5.6.2-all.zip`
