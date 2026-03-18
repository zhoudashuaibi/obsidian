---
title: EventEmitter 发布订阅实现
tags:
  - Node.js
  - 8.1 核心模块
  - 面试
status: active
date: 2026-03-18
---

# EventEmitter 发布订阅实现

## 📌 核心概念
EventEmitter 是 Node.js 中最常见的发布订阅模型实现。核心是维护事件名到监听函数列表的映射，并支持 on、once、emit、off 等操作。

## 💻 代码示例
```js
class Emitter {
  constructor() {
this.events = new Map()
  }
  on(type, handler) {
const list = this.events.get(type) || []
list.push(handler)
this.events.set(type, list)
  }
  emit(type, ...args) {
;(this.events.get(type) || []).forEach((fn) => fn(...args))
  }
}
```

## 🛠 实战场景
日志上报、连接状态通知、流式处理回调、进程通信都大量使用事件模型。

## 🎯 面试怎么问
- 发布订阅和观察者模式的区别？
- once 是怎么实现的？
- 监听器过多为什么会有泄漏警告？

## ⚠️ 易错点 / 高阶拓展
EventEmitter 默认同步触发监听器，某个回调阻塞就会拖慢后续逻辑。
