---
title: Three.js UV贴图方法 一张图贴6个面
date: 2021-01-12 16:50:33
tags:
    - Three.js
    - 贴图
    - uv贴图
    - 一张图贴6个面
---


## 前言

在开发过程中遇到给盒子贴图，常规方式是使用6个贴图来贴6个面，这样一来导致不好去控制box的颜色，因为Material是6个面的数组，后来找文档学到了UV来贴图的方法

<!--more-->

## 代码

```javascript
  const vertices = new Float32Array([
    0.5, 0, 1, 0, 0.5, 0.2, 1, 0.2,  //  左上、右上、左下、右下
    1, 0, 0.5, 0, 1, 0.2, 0.5, 0.2,
    1, 0, 0.5, 0, 1, 0.6, 0.5, 0.6,
    1, 0.6, 0.5, 0.6, 1, 0, 0.5, 0,
    0.5, 0.8, 1, 0.8, 0.5, 0.6, 1, 0.6,
    0.5, 1, 1, 1, 0.5, 0.8, 1, 0.8,
  ])

  const box = new THREE.BoxBufferGeometry(6, rackUnitSize, 6)
  box.setAttribute('uv', new THREE.BufferAttribute(vertices, 2))
  const boxMaterial = new THREE.MeshBasicMaterial({
    map: new THREE.TextureLoader().load('statics/textures/server.jpg'),
  })

  return new THREE.Mesh(box, boxMaterial)
```

## 说明

![20210112170806](https://cdn.jsdelivr.net/gh/onyz4x/PicGoBed/images/20210112170806.png)

6排参数对应BoxBufferGeometry的6个面，顺序是右左上下前后

每排参数对应一个面的4个点的x,y值，4点对应面的左上、右上、左下、右下

x,y的值为贴图图片的坐标，如下图，注意起始坐标（0,0）是从图片的左下角开始

![20210112171224](https://cdn.jsdelivr.net/gh/onyz4x/PicGoBed/images/20210112171224.png)


### 简单来说，就是取一张图片上的任意4个点作为BoxBufferGeometry的一个面