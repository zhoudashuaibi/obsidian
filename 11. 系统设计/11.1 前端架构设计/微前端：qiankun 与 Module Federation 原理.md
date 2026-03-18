---
title: 微前端：qiankun 与 Module Federation 原理
tags:
  - 系统设计
  - 11.1 前端架构设计
  - 面试
status: active
date: 2026-03-18
---

# 微前端：qiankun 与 Module Federation 原理

## 📌 核心概念
微前端把大型前端系统拆成多个可独立开发、部署、运行的子应用。qiankun 更偏运行时沙箱与应用编排，Module Federation 更偏构建时/运行时共享模块能力。

## 💻 代码示例
```js
// webpack module federation
new ModuleFederationPlugin({
  name: 'host',
  remotes: { app1: 'app1@http://localhost:3001/remoteEntry.js' }
})
```

## 🛠 实战场景
多团队并行开发、老系统平滑迁移、主子应用独立发版是微前端常见诉求。

## 🎯 面试怎么问
- qiankun 的 JS 沙箱解决了什么问题？
- Module Federation 如何共享依赖？
- 微前端适合什么组织场景？

## ⚠️ 易错点 / 高阶拓展
微前端不是银弹。应用间通信、样式隔离、公共依赖版本治理和调试成本都会明显上升。
