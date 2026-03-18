---
title: key 的作用与错误使用
tags:
  - React
  - 渲染优化
  - 面试
status: active
date: 2026-03-18
---

# key 的作用与错误使用

## 📌 核心概念
key 用于帮助 React 在同级节点间建立稳定身份，从而在协调时正确复用、移动或销毁节点。正确的 key 能保留状态，错误的 key 会导致输入框错乱、动画异常、组件状态串位。

## 💻 代码示例
```jsx
{list.map((item) => (
  <Row key={item.id} item={item} />
))}

// 不推荐
{list.map((item, index) => (
  <Row key={index} item={item} />
))}
```

## 🛠 实战场景
可编辑列表、拖拽排序、表单数组项尤其依赖稳定 key。如果用 index，插入或删除后组件状态就可能错位。

## 🎯 面试怎么问
- key 的真正作用是什么？
- 为什么不推荐用 index 作为 key？
- key 改变后组件会发生什么？

## ⚠️ 易错点 / 高阶拓展
key 只在兄弟节点范围内有意义，不会作为 prop 传给子组件。高阶追问常会考“强制重置组件状态”的用法。

