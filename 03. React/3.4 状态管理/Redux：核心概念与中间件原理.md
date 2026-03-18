---
title: Redux：核心概念与中间件原理
tags:
  - React
  - 状态管理
  - 面试
status: active
date: 2026-03-18
---

# Redux：核心概念与中间件原理

## 📌 核心概念
Redux 通过单一状态树、不可变更新、纯函数 reducer 和 action 描述状态变化。中间件位于 dispatch 链路中，可拦截 action 以实现异步、日志、埋点、异常处理等扩展能力。

## 💻 代码示例
```jsx
const logger = (store) => (next) => (action) => {
  console.log('dispatch', action);
  const result = next(action);
  console.log('state', store.getState());
  return result;
};
```

## 🛠 实战场景
中大型项目需要可预测状态流、调试能力和团队协作约束时，Redux 仍然是很强的方案。

## 🎯 面试怎么问
- Redux 三大原则是什么？
- reducer 为什么必须是纯函数？
- 中间件是如何串起来的？

## ⚠️ 易错点 / 高阶拓展
现代 Redux Toolkit 已经降低了模板代码成本。面试别只背传统样板代码，也要知道 RTK 的现实价值。

