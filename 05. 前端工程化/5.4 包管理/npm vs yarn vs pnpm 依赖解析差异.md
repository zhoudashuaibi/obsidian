---
title: npm vs yarn vs pnpm 依赖解析差异
tags:
  - 前端工程化
  - 包管理
  - 面试
status: active
date: 2026-03-18
---

# npm vs yarn vs pnpm 依赖解析差异

## 📌 核心概念
三者都能安装依赖，但在 lockfile、依赖提升、磁盘复用、安装速度和幽灵依赖控制上差异明显。pnpm 借助内容寻址存储和链接机制，能显著节省空间并减少扁平化副作用。

## 💻 代码示例
```js
# npm
npm install

# yarn
yarn install

# pnpm
pnpm install
```

## 🛠 实战场景
团队统一包管理工具时，最常讨论的就是速度、稳定性、磁盘占用和 Monorepo 支持能力。

## 🎯 面试怎么问
- 三者最大的工程化差异是什么？
- pnpm 为什么更省磁盘？
- lockfile 在协作中有什么意义？

## ⚠️ 易错点 / 高阶拓展
不要把工具差异只讲成“命令不同”。面试更关心底层依赖组织方式和对项目稳定性的影响。

