---
title: Webpack：核心概念 Loader、Plugin、Tapable
tags:
  - 前端工程化
  - 构建工具
  - 面试
status: active
date: 2026-03-18
---

# Webpack：核心概念 Loader、Plugin、Tapable

## 📌 核心概念
Webpack 本质是一个模块打包器。Loader 负责把非 JS 资源转成模块可处理形式，Plugin 负责在构建生命周期各阶段扩展能力，而 Tapable 是 Webpack 插件机制背后的钩子系统。

## 💻 代码示例
```js
module.exports = {
  module: {
    rules: [{ test: /\.css$/, use: ['style-loader', 'css-loader'] }],
  },
  plugins: [new HtmlWebpackPlugin()],
};
```

## 🛠 实战场景
理解 Loader 和 Plugin 的职责边界，是阅读构建配置、排查构建问题、写自定义扩展的基础。

## 🎯 面试怎么问
- Loader 和 Plugin 的区别是什么？
- Tapable 在 Webpack 中扮演什么角色？
- 为什么说 Webpack 一切皆模块？

## ⚠️ 易错点 / 高阶拓展
不要把所有扩展都归到 Plugin。资源转换链路优先看 Loader，构建流程扩展再看 Plugin。

