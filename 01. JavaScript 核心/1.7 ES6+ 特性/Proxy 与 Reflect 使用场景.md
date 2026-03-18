---
title: Proxy 与 Reflect 使用场景
tags:
  - JavaScript
  - ES6+
  - 面试
status: active
date: 2026-03-18
---

# Proxy 与 Reflect 使用场景

## 📌 核心概念
Proxy 可拦截对象的读取、设置、删除、函数调用等行为，是元编程能力核心入口；Reflect 提供与这些底层操作对应的标准方法，常与 Proxy 搭配保证默认行为和返回值一致性。

## 💻 代码示例
```js
const state = new Proxy({ count: 0 }, {
  get(target, key, receiver) {
    console.log('get', key);
    return Reflect.get(target, key, receiver);
  },
  set(target, key, value, receiver) {
    console.log('set', key, value);
    return Reflect.set(target, key, value, receiver);
  },
});

state.count += 1;
```

## 🛠 实战场景
Vue 3 响应式、权限控制、数据校验、日志埋点、懒代理对象都可能基于 Proxy。Reflect 则让拦截逻辑更接近语言默认语义。

## 🎯 面试怎么问
- Proxy 能拦截哪些操作？
- 为什么 Proxy 常和 Reflect 一起使用？
- Proxy 相比 `Object.defineProperty` 强在哪里？

## ⚠️ 易错点 / 高阶拓展
Proxy 无法直接 polyfill 到旧环境；代理对象和原对象不是全等。对数组长度、`this` 绑定、私有字段等细节要特别小心。

