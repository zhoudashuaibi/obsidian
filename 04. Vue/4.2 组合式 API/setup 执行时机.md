---
title: setup 执行时机
tags:
  - Vue
  - 组合式 API
  - 面试
status: active
date: 2026-03-18
---

# setup 执行时机

## 📌 核心概念
`setup` 是组合式 API 的入口，会在组件实例创建前、`beforeCreate` 之前执行。它拿不到组件实例的 `this`，但能访问 props、context，并在这里声明响应式状态、计算属性和副作用逻辑。

## 💻 代码示例
```js
export default {
  props: { id: Number },
  setup(props) {
    const count = ref(0);
    return { count, id: props.id };
  },
};
```

## 🛠 实战场景
理解 `setup` 的时机，才能解释为什么它没有 `this`，以及为什么组合式 API 更利于逻辑复用。

## 🎯 面试怎么问
- `setup` 在生命周期中的位置是什么？
- 为什么 `setup` 里不能使用 `this`？
- `setup` 返回对象会发生什么？

## ⚠️ 易错点 / 高阶拓展
如果混用 Options API 和 Composition API，要清楚数据暴露顺序和访问边界。`<script setup>` 只是语法糖，底层仍围绕 setup 工作。

