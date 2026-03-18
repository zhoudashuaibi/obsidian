---
title: storeToRefs 响应式解构
tags:
  - Vue
  - 状态管理
  - 面试
status: active
date: 2026-03-18
---

# storeToRefs 响应式解构

## 📌 核心概念
`storeToRefs` 用于把 Pinia store 上的状态和 getter 转成 ref，避免直接解构后丢失响应式。它只处理响应式字段，不会把 actions 也包进去。

## 💻 代码示例
```js
const userStore = useUserStore();
const { user, isLogin } = storeToRefs(userStore);
const { logout } = userStore;
```

## 🛠 实战场景
在 `<script setup>` 中直接解构 store 非常常见，若不了解 `storeToRefs`，很容易出现页面不更新的隐蔽 bug。

## 🎯 面试怎么问
- 为什么直接解构 store 会丢失响应式？
- `storeToRefs` 和 `toRefs` 有什么关系？
- actions 为什么通常直接从 store 上取？

## ⚠️ 易错点 / 高阶拓展
状态和方法要分开处理：状态用 `storeToRefs`，方法直接解构原 store。否则可读性和类型推导都会变差。

