---
title: Stream：可读、可写、双工、转换流
tags:
  - Node.js
  - 8.1 核心模块
  - 面试
status: active
date: 2026-03-18
---

# Stream：可读、可写、双工、转换流

## 📌 核心概念
Stream 用来处理分块数据，核心价值是边读边处理，避免一次性把大数据全部加载进内存。Node.js 常见四类流：Readable、Writable、Duplex、Transform。

## 💻 代码示例
```js
const fs = require('fs')
fs.createReadStream('big.log')
  .pipe(fs.createWriteStream('backup.log'))
```

## 🛠 实战场景
大文件上传下载、日志处理、视频转码、HTTP 请求响应本质上都和流式处理密切相关。

## 🎯 面试怎么问
- 四种流分别是什么？
- pipe 做了什么事？
- 背压 backpressure 为什么重要？

## ⚠️ 易错点 / 高阶拓展
流不是只为了“写法优雅”，更关键是控制内存峰值和消费速率。忽略背压时，Writable 缓冲区可能持续膨胀。
