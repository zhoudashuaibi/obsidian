---
title: 虚拟 DOM 与 Reconciliation
tags:
  - React
  - 核心机制
  - 面试
status: active
date: 2026-03-18
---

# 虚拟 DOM 与 Reconciliation

## 📌 核心概念
虚拟 DOM 是对 UI 的 JavaScript 对象描述，方便 React 在内存中比较新旧树差异。Reconciliation 则是 React 的协调过程，它根据类型、key 等信息决定节点复用、更新还是销毁。

## 💻 代码示例
```jsx
function List({ items }) {
  return (
    <ul>
      {items.map((item) => (
        <li key={item.id}>{item.name}</li>
      ))}
    </ul>
  );
}
```

## 🛠 实战场景
列表渲染、条件渲染、表单切换状态时，组件为什么重渲染、DOM 为什么复用或重建，本质都和协调过程有关。

## 🎯 面试怎么问
- 虚拟 DOM 的价值是什么？
- React Diff 为什么不是完整树编辑最优算法？
- key 在协调过程中起什么作用？

## ⚠️ 易错点 / 高阶拓展
虚拟 DOM 不是“比真实 DOM 快”，而是提供了更可控的声明式更新模型。性能关键仍然在于减少无效渲染和合理切分组件。

