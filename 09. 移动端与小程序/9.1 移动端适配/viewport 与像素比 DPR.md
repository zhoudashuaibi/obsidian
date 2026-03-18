---
title: viewport 与像素比 DPR
tags:
  - 移动端与小程序
  - 9.1 移动端适配
  - 面试
status: active
date: 2026-03-18
---

# viewport 与像素比 DPR

## 📌 核心概念
viewport 决定布局视口，DPR 表示设备物理像素与 CSS 像素的比值。移动端适配的核心就是让 CSS 尺寸、设备宽度和真实像素密度协同工作。

## 💻 代码示例
```html
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
```

## 🛠 实战场景
H5 页面在不同手机宽度下显示异常、图片发虚、1px 线粗细不一致，都和 viewport、DPR 有关。

## 🎯 面试怎么问
- CSS 像素和物理像素的区别？
- 为什么要设置 width=device-width？
- DPR 对图片清晰度有什么影响？

## ⚠️ 易错点 / 高阶拓展
不要把 DPR 当成页面缩放倍数。它描述的是像素密度，布局是否正常还受 viewport 和单位体系影响。
