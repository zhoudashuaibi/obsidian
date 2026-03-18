---
title: link preload vs prefetch vs preconnect
tags:
  - HTML
  - 渲染相关
  - 面试
status: active
date: 2026-03-18
---

# link preload vs prefetch vs preconnect

## 📌 核心概念
`preload` 用于当前页面即将用到的关键资源，`prefetch` 用于未来可能访问页面的低优先级资源，`preconnect` 用于提前建立与目标域的连接。它们都是资源提示，不是普通样式或脚本引入。

## 💻 代码示例
```html
<link rel="preconnect" href="https://cdn.example.com">
<link rel="preload" href="/main.css" as="style">
<link rel="prefetch" href="/next-page.js">
```

## 🛠 实战场景
首屏图片、字体、核心 CSS 可以用 preload；下一页路由资源可以用 prefetch；第三方 CDN 和接口域名可以用 preconnect。

## 🎯 面试怎么问
- 三者分别解决什么问题？
- preload 为什么要写 `as`？
- 为什么 prefetch 不适合首屏关键资源？

## ⚠️ 易错点 / 高阶拓展
资源提示用错会抢占带宽。当前页关键资源优先 preload，未来页资源才考虑 prefetch。

