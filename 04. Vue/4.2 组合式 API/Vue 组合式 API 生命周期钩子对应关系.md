---
title: Vue 组合式 API 生命周期钩子对应关系
tags:
  - Vue
  - 组合式 API
  - 面试
status: active
date: 2026-03-18
---

# Vue 组合式 API 生命周期钩子对应关系

## 📌 核心概念
组合式 API 提供 `onMounted`、`onUpdated`、`onUnmounted` 等钩子，对应 Options API 的生命周期方法，但更适合按逻辑关注点组织，而不是把所有逻辑堆在一个大钩子里。

## 💻 代码示例
```js
onMounted(() => {
  console.log('mounted');
});

onUnmounted(() => {
  console.log('cleanup');
});
```

## 🛠 实战场景
从 Vue 2 迁移到 Vue 3 时，理解这些钩子的映射关系能帮助团队平滑升级代码组织方式。

## 🎯 面试怎么问
- `mounted` 对应哪个组合式钩子？
- 组合式钩子为什么更利于逻辑拆分？
- 生命周期钩子能否在条件语句中调用？

## ⚠️ 易错点 / 高阶拓展
和 Hooks 类似，生命周期注册应保持稳定调用顺序。不要在异步回调或条件分支里随意注册钩子。

