---
title: 手写 Promise
tags:
  - 算法与数据结构
  - 10.3 前端高频手写题
  - 面试
status: active
date: 2026-03-18
---

# 手写 Promise

## 📌 核心概念
手写 Promise 的关键是状态机、异步回调队列、then 链式调用和 thenable 解析流程。核心状态只有 pending、fulfilled、rejected。

## 💻 代码示例
```js
class MyPromise {
  constructor(executor) {
this.state = 'pending'
this.value = undefined
this.fulfilled = []
this.rejected = []
  }
}
```

## 🛠 实战场景
这题常用于区分“会用 Promise”和“理解 Promise/A+ 规范”的候选人。

## 🎯 面试怎么问
- 为什么 Promise 状态不可逆？
- then 为什么要返回新 Promise？
- thenable 解析为什么复杂？

## ⚠️ 易错点 / 高阶拓展
如果只写出一个简化版异步包装器，却不处理链式调用和错误冒泡，严格来说还不算 Promise。
