---
title: Webpack：HMR 原理
tags:
  - 前端工程化
  - 构建工具
  - 面试
status: active
date: 2026-03-18
---

# Webpack：HMR 原理

## 📌 核心概念
HMR 即热模块替换，在不整页刷新的情况下替换发生变化的模块。Webpack Dev Server 通过 websocket 感知变更，客户端拉取更新 chunk，再按模块边界执行替换逻辑。

## 💻 代码示例
```js
if (import.meta.webpackHot) {
  import.meta.webpackHot.accept('./module', () => {
    console.log('module updated');
  });
}
```

## 🛠 实战场景
开发环境中保留页面状态、提升反馈速度，靠的就是 HMR。它也是“为什么改一行样式不用全页刷新”的底层原因。

## 🎯 面试怎么问
- HMR 和 Live Reload 的区别是什么？
- HMR 为什么能保留部分页面状态？
- 哪些改动会导致热更新退化为整页刷新？

## ⚠️ 易错点 / 高阶拓展
不是所有模块都能无损热替换，状态边界和副作用清理都会影响热更新体验。

