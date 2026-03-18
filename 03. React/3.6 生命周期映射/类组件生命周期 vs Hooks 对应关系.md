---
title: 类组件生命周期 vs Hooks 对应关系
tags:
  - React
  - 生命周期映射
  - 面试
status: active
date: 2026-03-18
---

# 类组件生命周期 vs Hooks 对应关系

## 📌 核心概念
Hooks 不是把类组件生命周期一一翻译过去，而是用“渲染后同步副作用”的方式重新组织逻辑。通常可粗略理解为：`componentDidMount/DidUpdate/WillUnmount` 大致由 `useEffect` 及其清理函数承载。

## 💻 代码示例
```jsx
useEffect(() => {
  console.log('mount or update');
  return () => {
    console.log('cleanup before next effect or unmount');
  };
}, [dep]);
```

## 🛠 实战场景
团队做类组件迁移时，最容易犯的错就是想逐个生命周期硬映射。正确做法是按关注点重组副作用和状态。

## 🎯 面试怎么问
- 类组件生命周期如何迁移到 Hooks？
- `componentDidMount` 是否等于 `useEffect(() => {}, [])`？
- 为什么 Hooks 时代更强调按逻辑拆分？

## ⚠️ 易错点 / 高阶拓展
不要把 Hooks 回答成“只是换个写法”。它改变了代码组织方式，也让复用副作用逻辑更自然。

