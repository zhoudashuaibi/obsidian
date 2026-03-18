---
title: computed vs watch vs watchEffect 区别
tags:
  - Vue
  - 组合式 API
  - 面试
status: active
date: 2026-03-18
---

# computed vs watch vs watchEffect 区别

## 📌 核心概念
`computed` 适合基于已有响应式数据派生新值，带缓存；`watch` 适合精确监听某个源并拿到新旧值；`watchEffect` 立即执行，自动收集依赖，适合副作用快速联动。

## 💻 代码示例
```js
const total = computed(() => price.value * count.value);

watch(() => route.params.id, (id) => {
  fetchUser(id);
});

watchEffect(() => {
  console.log(theme.value, locale.value);
});
```

## 🛠 实战场景
表单联动、路由参数变化请求、展示层派生值都常用到这三个 API，选错会导致冗余副作用或性能问题。

## 🎯 面试怎么问
- `computed` 和 `watch` 的核心区别是什么？
- `watchEffect` 为什么不需要写依赖？
- 什么场景下不该用 `watch`？

## ⚠️ 易错点 / 高阶拓展
“能用 computed 就别用 watch”是常见经验。watch 更适合副作用，不适合把本可声明式推导的值手动同步一份。

