---
title: DOM、CSSOM、Render Tree 构建
tags:
  - 网络与浏览器
  - 7.2 浏览器渲染
  - 面试
status: active
date: 2026-03-18
---

# DOM、CSSOM、Render Tree 构建

## 📌 核心概念
浏览器解析 HTML 生成 DOM，解析 CSS 生成 CSSOM，再把可见节点与样式信息组合成 Render Tree，随后进入布局和绘制阶段。

## 💻 代码示例
```text
HTML -> DOM
CSS -> CSSOM
DOM + CSSOM -> Render Tree
Render Tree -> Layout -> Paint
```

## 🛠 实战场景
分析首屏渲染慢、样式闪烁、脚本阻塞时，通常都会回到 DOM/CSSOM/Render Tree 这条链路。

## 🎯 面试怎么问
- Render Tree 包含哪些节点？
- 为什么 CSS 会影响首屏时间？
- display: none 的节点会进 Render Tree 吗？

## ⚠️ 易错点 / 高阶拓展
Render Tree 不是把 DOM 原样复制一份。像 `display: none` 节点不会参与渲染树，而 `visibility: hidden` 仍会占位。
