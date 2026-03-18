---
title: workspace 依赖管理
tags:
  - 前端工程化
  - Monorepo
  - 面试
status: active
date: 2026-03-18
---

# workspace 依赖管理

## 📌 核心概念
workspace 机制允许多个包在同一仓库中统一安装依赖、互相引用本地包并共享 lockfile。它是 Monorepo 的基础能力，能简化版本协同和本地联调。

## 💻 代码示例
```js
{
  "private": true,
  "workspaces": ["apps/*", "packages/*"]
}
```

## 🛠 实战场景
设计系统、业务应用、工具包同时迭代时，workspace 能避免频繁本地发布试装，提高协作效率。

## 🎯 面试怎么问
- workspace 解决了什么问题？
- 本地包引用和发布到 npm 的包有何不同？
- 为什么 Monorepo 通常只保留一个 lockfile？

## ⚠️ 易错点 / 高阶拓展
workspace 解决的是依赖组织，不直接解决任务缓存、影响范围分析、发布流程这些更高阶问题。

