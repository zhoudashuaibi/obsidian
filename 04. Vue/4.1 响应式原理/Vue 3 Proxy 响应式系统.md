---
title: Vue 3 Proxy 响应式系统
tags:
  - Vue
  - 响应式原理
  - 面试
status: active
date: 2026-03-18
---

# Vue 3 Proxy 响应式系统

## 📌 核心概念
Vue 3 使用 `Proxy` 代理整个对象，可以拦截读取、设置、删除、`in`、遍历等操作，天然支持属性新增删除和数组索引变化，响应式能力更完整，代码结构也更统一。

## 💻 代码示例
```js
const state = new Proxy({ count: 0 }, {
  get(target, key, receiver) {
    console.log('track', key);
    return Reflect.get(target, key, receiver);
  },
  set(target, key, value, receiver) {
    console.log('trigger', key);
    return Reflect.set(target, key, value, receiver);
  },
});
```

## 🛠 实战场景
理解 Vue 3 响应式系统后，很多 API 的行为就更容易解释，比如 `reactive`、`readonly`、`shallowReactive`。

## 🎯 面试怎么问
- Vue 3 为什么改用 Proxy？
- Proxy 比 `Object.defineProperty` 强在哪里？
- Vue 3 的响应式还能监听哪些操作？

## ⚠️ 易错点 / 高阶拓展
Proxy 代理的是对象整体，但仍需要配合依赖收集系统工作。高阶会追问 ReactiveFlags、缓存代理、raw 与 proxy 的映射关系。

