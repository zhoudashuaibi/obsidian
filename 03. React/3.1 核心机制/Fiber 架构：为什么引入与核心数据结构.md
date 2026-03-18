---
title: Fiber 架构：为什么引入与核心数据结构
tags:
  - React
  - 核心机制
  - 面试
status: active
date: 2026-03-18
---

# Fiber 架构：为什么引入与核心数据结构

## 📌 核心概念
Fiber 是 React 16 引入的新协调架构，本质上是可中断、可恢复的链表树结构。它解决了旧栈协调器无法打断长任务的问题，为优先级调度、并发渲染、Suspense 等能力打基础。

## 💻 代码示例
```jsx
const fiberNode = {
  type: App,
  key: null,
  stateNode: null,
  child: null,
  sibling: null,
  return: null,
  pendingProps: {},
  memoizedProps: {},
  memoizedState: null,
  flags: 0,
};
```

## 🛠 实战场景
回答 React 18 并发特性前，通常都要先补 Fiber。只有理解“为什么要把递归树改成链表结构”，后面的调度模型才讲得顺。

## 🎯 面试怎么问
- React 为什么要引入 Fiber？
- Fiber 和传统递归 Diff 的区别是什么？
- Fiber 节点上常见字段有哪些？

## ⚠️ 易错点 / 高阶拓展
Fiber 不是浏览器线程，也不是虚拟 DOM 的替代物，而是 React 内部的执行单元。高阶会追问 lanes、flags、双缓存树。

