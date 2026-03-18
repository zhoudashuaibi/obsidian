---
title: 移动端 1px 问题解决方案
tags:
  - CSS
  - 响应式设计
  - 面试
status: active
date: 2026-03-18
---

# 移动端 1px 问题解决方案

## 📌 核心概念
移动端高 DPR 屏幕下，CSS 的 `1px` 往往会映射成多个物理像素，视觉上显得更粗，所以产生所谓 1px 问题。常见方案包括缩放伪元素、边框图片、渐变背景和直接接受不同平台渲染差异。

## 💻 代码示例
```css
.divider::after {
  content: '';
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
  height: 1px;
  background: #e5e5e5;
  transform: scaleY(0.5);
  transform-origin: 0 100%;
}
```

## 🛠 实战场景
设计系统中的分割线、卡片边框、列表 item 边界在高分屏上经常需要更细的视觉效果。

## 🎯 面试怎么问
- 为什么移动端会出现 1px 看起来变粗的问题？
- 常见解决方案有哪些？
- DPR 是什么，和 CSS 像素有什么关系？

## ⚠️ 易错点 / 高阶拓展
不要盲目追求“绝对 1 物理像素”，不同设备和浏览器渲染存在差异。现代项目里很多时候统一采用淡色边线即可。

