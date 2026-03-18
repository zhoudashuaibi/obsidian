---
title: 关键渲染路径 CRP 优化
tags:
  - 性能优化
  - 加载性能
  - 面试
status: active
date: 2026-03-18
---

# 关键渲染路径 CRP 优化

## 📌 核心概念
关键渲染路径描述浏览器从拿到 HTML 到首屏可见的关键步骤，包括构建 DOM、CSSOM、Render Tree、布局与绘制。优化 CRP 的目标是减少阻塞资源、缩短首屏渲染链路。

## 💻 代码示例
```js
<link rel="preload" href="/main.css" as="style">
<script type="module" src="/main.js"></script>
```

## 🛠 实战场景
首页白屏时间长、首屏内容慢、SSR/CSR 首屏体验差时，通常都要回到 CRP 去拆解问题。

## 🎯 面试怎么问
- 什么是关键渲染路径？
- 哪些资源会阻塞首屏渲染？
- 怎么优化白屏时间？

## ⚠️ 易错点 / 高阶拓展
不要只背名词，回答时最好按“HTML 解析 -> CSS 阻塞 -> JS 执行 -> 渲染”顺序讲。首屏优化核心是减少阻塞和提前关键资源到位。

