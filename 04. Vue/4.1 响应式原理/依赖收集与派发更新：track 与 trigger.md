---
title: 依赖收集与派发更新：track 与 trigger
tags:
  - Vue
  - 响应式原理
  - 面试
status: active
date: 2026-03-18
---

# 依赖收集与派发更新：track 与 trigger

## 📌 核心概念
Vue 3 在读取响应式数据时通过 `track` 收集当前副作用函数，在写入时通过 `trigger` 找到相关依赖并重新执行。它本质上建立了“目标对象 -> key -> effects”的依赖图。

## 💻 代码示例
```js
const bucket = new WeakMap();

function track(target, key) {
  // 读取时把 activeEffect 收集起来
}

function trigger(target, key) {
  // 修改时找到依赖并重新执行
}
```

## 🛠 实战场景
computed、watch、组件渲染更新本质上都建立在依赖收集和派发更新机制之上。

## 🎯 面试怎么问
- Vue 依赖收集发生在什么时候？
- `track` 和 `trigger` 分别负责什么？
- 为什么依赖结构常用 `WeakMap -> Map -> Set`？

## ⚠️ 易错点 / 高阶拓展
面试不要把它说成“发布订阅”就结束，最好进一步说明依赖是按对象和属性维度精细追踪的。

