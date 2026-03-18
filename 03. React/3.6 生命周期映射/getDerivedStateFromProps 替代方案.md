---
title: getDerivedStateFromProps 替代方案
tags:
  - React
  - 生命周期映射
  - 面试
status: active
date: 2026-03-18
---

# getDerivedStateFromProps 替代方案

## 📌 核心概念
`getDerivedStateFromProps` 常被滥用来“同步 props 到 state”，但这往往制造双数据源。函数组件时代更推荐直接从 props 计算渲染结果，或在事件发生时显式更新，而不是每次渲染都镜像一份状态。

## 💻 代码示例
```jsx
function Profile({ user }) {
  const fullName = `${user.firstName} ${user.lastName}`;
  return <h1>{fullName}</h1>;
}
```

## 🛠 实战场景
表单初始值、受控/非受控切换、缓存上一次 props 计算结果，是这类问题最常出现的地方。

## 🎯 面试怎么问
- 为什么不推荐把 props 再存进 state？
- `getDerivedStateFromProps` 常见替代方案有哪些？
- 什么场景下确实需要根据 props 重置内部状态？

## ⚠️ 易错点 / 高阶拓展
如果确实需要“key 变化时重置状态”，可以考虑改变组件 key 或在特定 effect 中显式处理，而不是默认镜像所有 props。

