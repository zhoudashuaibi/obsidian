---
title: cluster 模块：多进程利用多核
tags:
  - Node.js
  - 8.4 性能与部署
  - 面试
status: active
date: 2026-03-18
---

# cluster 模块：多进程利用多核

## 📌 核心概念
Node.js 单进程单线程执行 JS，cluster 通过主进程 fork 多个 worker，把请求分发到多个子进程，从而利用多核 CPU。

## 💻 代码示例
```js
const cluster = require('cluster')
const os = require('os')
if (cluster.isPrimary) {
  os.cpus().forEach(() => cluster.fork())
} else {
  require('./server')
}
```

## 🛠 实战场景
CPU 核数多、接口并发高、需要提升单机吞吐时，经常会考虑 cluster 或 PM2 cluster 模式。

## 🎯 面试怎么问
- 为什么 Node 需要 cluster？
- 多进程之间如何通信？
- cluster 和 worker_threads 有什么区别？

## ⚠️ 易错点 / 高阶拓展
cluster 解决的是多核利用，不解决单个请求内部的 CPU 重计算问题。CPU 密集型任务仍要考虑拆分或下沉。
