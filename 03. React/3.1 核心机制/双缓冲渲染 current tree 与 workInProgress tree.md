---
title: 双缓冲渲染 current tree 与 workInProgress tree
tags:
  - React
  - 核心机制
  - 面试
status: active
date: 2026-03-18
---

# 双缓冲渲染 current tree 与 workInProgress tree

## 📌 核心概念
React Fiber 采用双缓冲树模型：`current tree` 代表当前已提交到页面的树，`workInProgress tree` 代表本轮正在构建的新树。渲染阶段在内存中修改 WIP，提交时再一次性切换指针。

## 💻 代码示例
```jsx
// 伪代码理解
root.current = currentTree;
const workInProgress = createWorkInProgress(root.current);
render(workInProgress);
commit(root);
root.current = workInProgress;
```

## 🛠 实战场景
这套模型能避免边算边改 DOM，保证提交阶段更集中，也方便中断后继续工作。

## 🎯 面试怎么问
- current tree 和 workInProgress tree 分别是什么？
- 为什么说 React 是双缓冲渲染？
- 提交阶段发生了什么？

## ⚠️ 易错点 / 高阶拓展
render 阶段可以被打断，commit 阶段不能。很多人会把“渲染”和“更新 DOM”混为一谈，这是面试常见失分点。

