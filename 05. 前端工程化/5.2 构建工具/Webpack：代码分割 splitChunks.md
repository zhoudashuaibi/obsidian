---
title: Webpack：代码分割 splitChunks
tags:
  - 前端工程化
  - 构建工具
  - 面试
status: active
date: 2026-03-18
---

# Webpack：代码分割 splitChunks

## 📌 核心概念
代码分割的目标是把大包拆成更合理的多个 chunk，减少首屏负担、提升缓存复用。Webpack 中常通过动态导入和 `splitChunks` 策略抽离公共依赖与异步模块。

## 💻 代码示例
```js
module.exports = {
  optimization: {
    splitChunks: {
      chunks: 'all',
    },
  },
};
```

## 🛠 实战场景
后台系统、营销页和多路由应用都非常依赖代码分割，否则首屏 JS 过大，加载和解析成本会明显增加。

## 🎯 面试怎么问
- `splitChunks` 解决了什么问题？
- 同步 chunk 和异步 chunk 有什么区别？
- 代码分割一定越细越好吗？

## ⚠️ 易错点 / 高阶拓展
切得过细会增加请求数和管理复杂度，真正合理的策略要结合缓存命中、业务模块边界和首屏路径。

