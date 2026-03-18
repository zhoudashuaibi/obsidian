---
title: Pinia：核心概念与 Vuex 对比
tags:
  - Vue
  - 状态管理
  - 面试
status: active
date: 2026-03-18
---

# Pinia：核心概念与 Vuex 对比

## 📌 核心概念
Pinia 是 Vue 官方推荐的状态管理方案，强调更轻的心智负担、更好的 TypeScript 支持和组合式 API 风格。相比 Vuex，它不再强制 mutation，store 定义也更直观。

## 💻 代码示例
```js
export const useCounterStore = defineStore('counter', {
  state: () => ({ count: 0 }),
  actions: {
    increment() {
      this.count += 1;
    },
  },
});
```

## 🛠 实战场景
Vue 3 新项目基本都会优先选 Pinia。面试常拿它和 Vuex 做对比，考察你是否理解状态管理演进方向。

## 🎯 面试怎么问
- Pinia 和 Vuex 的核心区别是什么？
- 为什么 Pinia 不再强调 mutation？
- Pinia 为什么更适合 Vue 3？

## ⚠️ 易错点 / 高阶拓展
不要只说“更简单”，最好补充类型推导、模块定义方式、组合式 API 配合等具体差异。

