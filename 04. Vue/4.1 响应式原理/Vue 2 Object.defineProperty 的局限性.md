---
title: Vue 2 Object.defineProperty 的局限性
tags:
  - Vue
  - 响应式原理
  - 面试
status: active
date: 2026-03-18
---

# Vue 2 Object.defineProperty 的局限性

## 📌 核心概念
Vue 2 通过 `Object.defineProperty` 劫持对象已有属性的 getter/setter 实现响应式，但它无法直接监听属性新增删除、数组索引修改和长度变化，因此需要 `Vue.set`、重写数组方法等额外补丁。

## 💻 代码示例
```js
const obj = {};
Object.defineProperty(obj, 'name', {
  get() {
    return value;
  },
  set(newValue) {
    value = newValue;
    console.log('trigger update');
  },
});
```

## 🛠 实战场景
阅读 Vue 2 老项目时，常会碰到“对象新增字段不更新视图”“数组改索引不生效”等问题，本质都来自这套实现边界。

## 🎯 面试怎么问
- Vue 2 为什么监听不到对象新增属性？
- 为什么数组要特殊处理？
- `Vue.set` 解决了什么问题？

## ⚠️ 易错点 / 高阶拓展
不要只记“defineProperty 不行”，要能说清它是“逐个属性劫持”的方案。Vue 3 用 Proxy 很大程度上就是为了解决这些问题。

