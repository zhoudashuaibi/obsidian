---
title: ESM vs CommonJS 模块化区别
tags:
  - JavaScript
  - ES6+
  - 面试
status: active
date: 2026-03-18
---

# ESM vs CommonJS 模块化区别

## 📌 核心概念
ESM 是 ECMAScript 标准模块系统，支持静态分析、按需导入、顶层语法；CommonJS 是 Node.js 早期主流方案，运行时加载，通过 `require` 和 `module.exports` 工作。

## 💻 代码示例
```js
// ESM
import { sum } from './math.js';
export const answer = 42;

// CommonJS
const { sum: cjsSum } = require('./math.cjs');
module.exports = { cjsSum };
```

## 🛠 实战场景
构建工具做 Tree Shaking、代码分割、服务端与浏览器双端兼容时，经常需要处理两套模块规范的差异与互操作。

## 🎯 面试怎么问
- 两者在加载时机和导出机制上有什么不同？
- 为什么 ESM 更利于 Tree Shaking？
- Node 中如何同时处理 `.mjs`、`.cjs`、`type: module`？

## ⚠️ 易错点 / 高阶拓展
ESM 输出的是“实时绑定”，CommonJS 更像导出对象快照。循环依赖、默认导出互转、路径扩展名处理都是高频坑点。

