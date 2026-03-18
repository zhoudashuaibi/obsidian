---
title: 自动批处理 Automatic Batching
tags:
  - React
  - 并发特性
  - 面试
status: active
date: 2026-03-18
---

# 自动批处理 Automatic Batching

## 📌 核心概念
React 18 扩大了批处理范围，不再只局限于 React 事件回调内。Promise、定时器、原生事件中的多次状态更新，在许多情况下也会合并到一次渲染中。

## 💻 代码示例
```jsx
setTimeout(() => {
  setCount((c) => c + 1);
  setVisible((v) => !v);
}, 0);
```

## 🛠 实战场景
这能减少无意义重复渲染，让异步流程中的多次更新更自然地合并，提高整体性能。

## 🎯 面试怎么问
- React 18 的自动批处理和旧版本有什么区别？
- 哪些场景会被批处理？
- 如果必须立即拿到 DOM 更新结果怎么办？

## ⚠️ 易错点 / 高阶拓展
需要强制同步刷新的极少数场景可以用 `flushSync`，但应谨慎，因为它会破坏调度收益。

