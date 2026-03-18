---
title: Concurrent Mode 概念
tags:
  - React
  - 并发特性
  - 面试
status: active
date: 2026-03-18
---

# Concurrent Mode 概念

## 📌 核心概念
React 18 更准确的说法是“并发渲染能力”，不是一个你手动打开的单独模式。它允许 React 把渲染工作分片、可打断、可恢复，从而让高优先级交互先响应。

## 💻 代码示例
```jsx
const root = createRoot(document.getElementById('root'));
root.render(<App />);
```

## 🛠 实战场景
搜索联想、复杂过滤、大量节点更新场景下，并发能力能减少主线程被长渲染阻塞，提升交互响应。

## 🎯 面试怎么问
- React 18 的并发特性到底是什么？
- 并发是不是多线程？
- 并发渲染对用户体验改善在哪里？

## ⚠️ 易错点 / 高阶拓展
并发不是同时执行多份 JS，而是调度上更灵活。面试里不要把它讲成浏览器真的开了新线程渲染 React。

