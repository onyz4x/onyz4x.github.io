---
title: three.js 获取模型的尺寸
date: 2021-01-12 16:19:18
tags: 
    - three.js 
    - gltf尺寸
    - 模型尺寸
---

## 思路

利用THREE.Box3()来获取加载模型的size 

<!--more-->

## 代码

```javascript
    loader.load(path, function(gltf) {
      // 使用THREE.Box3()来获取整个模型的大小
      const box = new THREE.Box3().setFromObject(gltf.scene)
      const center = box.getCenter(new THREE.Vector3())
      const size = box.getSize(new THREE.Vector3())

      const aspect = targetSize ? new THREE.Vector3().copy(targetSize.divide(size)) : new THREE.Vector3(1, 1, 1)

      // 通过位置需要根据缩放比例进行调整
      gltf.scene.position.copy(position.sub(center).multiply(aspect))
      gltf.scene.scale.copy(aspect)
      resolve(gltf.scene)
    }, undefined, function(error) {
      reject(error)
    })
```
