---
title: AngularJS,自定义filter实现文字和拼音的双过滤
date: 2016-04-20T13:42:33+00:00
image: /wp-content/uploads/2016/04/angularjs-for-header-only.svg
tags:
  - angularjs
  - filter
  - 数据过滤
---

## 前言

这个功能在 ng-repeat 中过滤内容的时候会用到

这个 filter 简单来说就是同时过滤两个字段或者多个字段达到我们想要的实际效果：文字和拼音双过滤；

<!--more-->

## 代码</p>

```javascript
keeApp.filter("filterPinyin", function () {
  return function (inputArray, value) {
    var array = []; //定义返回的新数组；
    if (value == undefined || value == null) {
      array = inputArray; //当过滤条件为空的时候返回全部的内容；
    } else {
      for (var i = 0; i < inputArray.length; i++) {
        if (inputArray[i].aliasName.indexOf(value) != -1) {
          array.push(inputArray[i]); //过滤第一个字段，如果不符合条件则判断第二个字段
        } else {
          if (inputArray[i].spelling.indexOf(value) != -1) {
            array.push(inputArray[i]);
          }
        }
      }
    }
    return array;
  };
});
```
