---
title: CSS Modules vs CSS-in-JS vs Tailwind 对比
tags:
  - CSS
  - CSS 工程化
  - 面试
status: active
date: 2026-03-18
---

# CSS Modules vs CSS-in-JS vs Tailwind 对比

## 📌 核心概念
这三类方案分别解决样式隔离和组织问题，但思路不同：CSS Modules 走编译时类名局部化；CSS-in-JS 把样式与组件逻辑更紧耦合；Tailwind 用原子类直接组合界面。没有绝对优劣，关键看团队规模、性能要求和开发体验。

## 💻 代码示例
```css
.card {
  padding: 16px;
  border-radius: 12px;
  background: #fff;
}
```

## 🛠 实战场景
组件库、设计系统、SSR、多人协作项目都要选样式方案。面试更看重你是否理解“隔离、复用、运行时成本、心智负担”这些维度。

## 🎯 面试怎么问
- 三种方案分别适合什么项目？
- CSS-in-JS 的运行时成本体现在哪里？
- Tailwind 为什么在团队里会很有争议？

## ⚠️ 易错点 / 高阶拓展
不要只站队，要能说清 trade-off。高阶追问可能延伸到原子化 CSS、零运行时 CSS-in-JS、设计 Token。

