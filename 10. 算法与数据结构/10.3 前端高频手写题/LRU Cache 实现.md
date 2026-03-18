---
title: LRU Cache 实现
tags:
  - 算法与数据结构
  - 10.3 前端高频手写题
  - 面试
status: active
date: 2026-03-18
---

# LRU Cache 实现

## 📌 核心概念
LRU 最近最少使用缓存需要同时支持 O(1) 查询和 O(1) 更新，经典做法是哈希表 + 双向链表。

## 💻 代码示例
```js
class LRUCache {
  constructor(capacity) {
this.capacity = capacity
this.map = new Map()
  }
  get(key) {
if (!this.map.has(key)) return -1
const value = this.map.get(key)
this.map.delete(key)
this.map.set(key, value)
return value
  }
}
```

## 🛠 实战场景
页面级缓存、接口结果缓存、图片缓存淘汰策略都能类比到 LRU。

## 🎯 面试怎么问
- 为什么单用数组实现不够高效？
- Map 在 JS 里怎么近似实现 LRU？
- LRU 和 LFU 有什么区别？

## ⚠️ 易错点 / 高阶拓展
面试里如果用 `Map`，要说明它利用了插入顺序特性；如果追问复杂度，再补充链表版实现。
