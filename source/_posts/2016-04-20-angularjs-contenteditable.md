---
title: AngularJS，实现contenteditable的双向绑定
date: 2016-04-20T14:37:32+00:00
tags:
  - angularjs
  - contenteditable
  - web前端
  - 双向绑定
---

## 前言

在项目中遇到需要使用标签属性`contenteditable`来替代`<textarea>`，实现输入内容的自动高度，但是`<div>`或者`<p>`标签并不是一个输入控件，不能直接被 ngModel 绑定，这个时候就需要把 contenteditable 做成一个 directive 来实现双向绑定：

<!--more-->

## 代码

```javascript
app.directive("contenteditable", function () {
  return {
    require: "ngModel",
    link: function (scope, element, attrs, ctrl) {
      /*输入回车的时候会转义成<br>被提交，所以去掉回车的输入*/
      function deleteBr(sHtml) {
        return sHtml.replace(/<br>/g, "");
      }
      // view -> model
      element.bind("input", function () {
        scope.$apply(function () {
          element.html(deleteBr(element.html()));
          ctrl.$setViewValue(element.html());
        });
      });

      // model -> view
      ctrl.$render = function () {
        element.html(ctrl.$viewValue);
      };

      // load init value from DOM
      ctrl.$render();
    },
  };
});
```

## 注意

- 在 div 中输入回车是会被转义成`<br>`，而在实际使用中可能需要禁止回车，所以在 directive 中需要把回车产生的`<br>`过滤掉；
- 在 html 中需要设置`contenteditable="plaintext-only"`控制输入的内容为纯文本，因为复制过来的一些内容可能会被带上一些文字样式；
- 在 model 中输入<>  会被转义，解决办法是在 controller 里面先过滤一遍数据（输出的时候也需要过滤一次）

```javascript
function html2Escape(sHtml) {
  return sHtml.replace(/[<>&"]/g, function (c) {
    return { "<": "&lt;", ">": "&gt;", "&": "&amp;", '"': "&quot;" }[c];
  });
}
$scope.text = html2Escape($scope.text);
```
