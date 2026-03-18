---
title: path、fs、os 常用 API
tags:
  - Node.js
  - 8.1 核心模块
  - 面试
status: active
date: 2026-03-18
---

# path、fs、os 常用 API

## 📌 核心概念
path 负责路径处理，fs 负责文件系统读写，os 提供当前操作系统信息。这三个模块是写脚本、构建工具、CLI 的基础能力。

## 💻 代码示例
```js
const path = require('path')
const fs = require('fs')
const os = require('os')

console.log(path.resolve('src', 'index.js'))
console.log(fs.existsSync('package.json'))
console.log(os.cpus().length)
```

## 🛠 实战场景
脚手架生成文件、扫描目录、获取 CPU 核数做并行构建，都是高频场景。

## 🎯 面试怎么问
- path.join 和 path.resolve 的区别？
- fs 同步 API 与异步 API 什么时候选？
- os 模块常拿来做什么？

## ⚠️ 易错点 / 高阶拓展
服务端长链路业务里应谨慎使用 fs 同步 API，否则会阻塞事件循环。
