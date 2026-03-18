---
title: Canvas vs SVG 选型
tags:
  - HTML
  - HTML5 高级特性
  - 面试
status: active
date: 2026-03-18
---

# Canvas vs SVG 选型

## 📌 核心概念
Canvas 是位图绘制，适合高频重绘和大量像素级操作；SVG 是基于 XML 的矢量图，适合可缩放、结构化、可交互的图形。选型关键在于“渲染模式”和“交互需求”。

## 💻 代码示例
```html
<canvas id="chart" width="300" height="150"></canvas>
<svg width="300" height="150">
  <circle cx="75" cy="75" r="50" fill="tomato" />
</svg>
```

## 🛠 实战场景
图表、白板、小游戏更偏 Canvas；图标、流程图、地图、可点击图形更偏 SVG。

## 🎯 面试怎么问
- Canvas 和 SVG 的核心区别是什么？
- 哪些场景适合 Canvas，哪些适合 SVG？
- 为什么 SVG 更容易做 DOM 级交互？

## ⚠️ 易错点 / 高阶拓展
不要简单地说“Canvas 性能更好”。节点量、交互需求、缩放质量、可访问性都要一起考虑。

