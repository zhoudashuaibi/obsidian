---
title: CommonJS vs ESM vs AMD vs UMD 规范
tags:
  - 前端工程化
  - 模块化
  - 面试
status: active
date: 2026-03-18
---

# CommonJS vs ESM vs AMD vs UMD 规范

## 📌 核心概念
这些规范都在解决“代码如何拆分与复用”问题，但适用时代和运行环境不同。CommonJS 偏 Node 运行时加载，ESM 是语言标准、支持静态分析；AMD 和 UMD 则更多是浏览器无打包时代的历史产物。

## 💻 代码示例
```js
// CommonJS
const util = require('./util');
module.exports = { util };

// ESM
import { util } from './util.js';
export { util };
```

## 🛠 实战场景
理解模块规范差异，才能解释为什么构建工具能做 Tree Shaking、为什么 Node 和浏览器对导入导出的处理方式不同。

## 🎯 面试怎么问
- 四种模块规范分别解决什么问题？
- 为什么 ESM 更适合现代前端构建？
- UMD 为什么说是兼容型方案？

## ⚠️ 易错点 / 高阶拓展
面试里不用死背历史细节，但要能说清 ESM 的静态特征和 CommonJS 的运行时特征，这是高频考点。

