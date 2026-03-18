---
title: Turborepo 与 nx 使用场景
tags:
  - 前端工程化
  - Monorepo
  - 面试
status: active
date: 2026-03-18
---

# Turborepo 与 nx 使用场景

## 📌 核心概念
Turborepo 和 Nx 都是在 Monorepo 场景下管理多包、多应用、多任务依赖的工具。它们提供任务编排、缓存、依赖图分析等能力，帮助大型仓库保持构建效率。

## 💻 代码示例
```js
{
  "pipeline": {
    "build": {
      "dependsOn": ["^build"],
      "outputs": ["dist/**"]
    }
  }
}
```

## 🛠 实战场景
组件库、主站、管理后台、Node 服务放在同一仓库时，单靠 package manager workspace 往往不够，还需要更强的任务调度能力。

## 🎯 面试怎么问
- Monorepo 为什么需要 Turborepo 或 Nx？
- 远程缓存能带来什么收益？
- 两者的定位有什么差异？

## ⚠️ 易错点 / 高阶拓展
不是所有仓库都需要上重型工具。仓库规模、团队人数、任务复杂度不高时，workspace 就可能够用了。

