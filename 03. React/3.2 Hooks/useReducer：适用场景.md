---
title: useReducer：适用场景
tags:
  - React
  - Hooks
  - 面试
status: active
date: 2026-03-18
---

# useReducer：适用场景

## 📌 核心概念
`useReducer` 适合状态变化逻辑复杂、多个子状态相互关联、更新路径需要显式建模的场景。它通过 `state + action -> newState` 的方式，把状态转移规则集中管理。

## 💻 代码示例
```jsx
function reducer(state, action) {
  switch (action.type) {
    case 'start':
      return { ...state, loading: true };
    case 'success':
      return { loading: false, data: action.payload, error: null };
    case 'error':
      return { ...state, loading: false, error: action.payload };
    default:
      return state;
  }
}
```

## 🛠 实战场景
复杂表单、异步请求状态机、多人协作中需要统一 action 语义的组件，非常适合 `useReducer`。

## 🎯 面试怎么问
- `useReducer` 比 `useState` 强在哪？
- 什么场景适合用 reducer？
- reducer 为什么要求纯函数？

## ⚠️ 易错点 / 高阶拓展
不要为了“像 Redux”而强行上 reducer。简单布尔值或单字段状态用 `useState` 更直接。

