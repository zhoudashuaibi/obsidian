---
title: 资源加载优先级：preload、prefetch、preconnect
tags:
  - 性能优化
  - 加载性能
  - 面试
status: active
date: 2026-03-18
---

# 资源加载优先级：preload、prefetch、preconnect

## 📌 核心概念
`preload` 用于提前加载当前页面很快就会用到的关键资源；`prefetch` 用于空闲时预取未来可能访问的资源；`preconnect` 用于提前建立 DNS、TCP、TLS 连接，减少后续请求延迟。

## 💻 代码示例
```js
<link rel="preconnect" href="https://cdn.example.com">
<link rel="preload" href="/hero.jpg" as="image">
<link rel="prefetch" href="/next-page.js">
```

## 🛠 实战场景
首屏大图、字体、下一页脚本、第三方域名接口都可以通过资源提示做更细粒度的调度优化。

## 🎯 面试怎么问
- preload 和 prefetch 的区别是什么？
- preconnect 解决了什么问题？
- 为什么 preload 用错可能适得其反？

## ⚠️ 易错点 / 高阶拓展
资源提示不是越多越好，错误的 preload 会抢占真正关键资源带宽。要结合当前页与未来页的优先级来用。

