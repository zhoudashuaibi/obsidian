---
title: React.memo：浅比较陷阱
tags:
  - React
  - 渲染优化
  - 面试
status: active
date: 2026-03-18
---

# React.memo：浅比较陷阱

## 📌 核心概念
`React.memo` 会对 props 做浅比较，若引用未变则跳过组件重渲染。它适合纯展示组件，但如果 props 中包含频繁新建的对象、数组、函数，浅比较往往失效。

## 💻 代码示例
```jsx
const Item = React.memo(function Item({ user, onClick }) {
  return <li onClick={onClick}>{user.name}</li>;
});

function List({ users }) {
  return users.map((user) => (
    <Item key={user.id} user={user} onClick={() => console.log(user.id)} />
  ));
}
```

## 🛠 实战场景
列表项、表格单元格、复杂卡片很容易被 `React.memo` 包起来，但如果父组件每次都创建新引用，优化就形同虚设。

## 🎯 面试怎么问
- `React.memo` 的比较规则是什么？
- 为什么包了 `memo` 还是会重渲染？
- 什么情况下不建议使用 `memo`？

## ⚠️ 易错点 / 高阶拓展
不要把 `memo` 当银弹。性能优化前先确认瓶颈，否则只会增加代码复杂度。

