---
title: Vite：ESM Dev Server 与 Rollup 生产构建
tags:
  - 前端工程化
  - 构建工具
  - 面试
status: active
date: 2026-03-18
---

# Vite：ESM Dev Server 与 Rollup 生产构建

## 📌 核心概念
Vite 在开发环境利用浏览器原生 ESM 按需加载，只对当前请求模块做快速转换；生产环境则使用 Rollup 打包优化。这让它兼顾了本地启动速度和生产构建质量。

## 💻 代码示例
```js
import { defineConfig } from 'vite';

export default defineConfig({
  server: { port: 5173 },
});
```

## 🛠 实战场景
中大型前端项目切到 Vite 后，最直观收益往往是启动更快、热更新更快、配置更轻。

## 🎯 面试怎么问
- Vite 为什么开发时更快？
- 为什么生产构建还要打包？
- Rollup 在 Vite 里负责什么？

## ⚠️ 易错点 / 高阶拓展
“Vite 不打包”只适用于开发阶段，生产环境仍需要构建产物优化。面试里别把这点说错。

