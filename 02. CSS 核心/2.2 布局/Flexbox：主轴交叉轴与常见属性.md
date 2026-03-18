---
title: Flexbox：主轴交叉轴与常见属性
tags:
  - CSS
  - 布局
  - 面试
status: active
date: 2026-03-18
---

# Flexbox：主轴交叉轴与常见属性

## 📌 核心概念
Flex 布局是一维布局模型，核心是主轴和交叉轴。主轴方向由 `flex-direction` 决定，主轴上的分配由 `justify-content` 控制，交叉轴上的对齐由 `align-items`、`align-self` 控制。

## 💻 代码示例
```css
.list {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  gap: 12px;
}

.item {
  flex: 1;
}
```

## 🛠 实战场景
导航栏、按钮组、卡片列表、左右布局几乎都能用 Flex 快速解决，尤其适合内容数量不固定但只在一个方向排列的场景。

## 🎯 面试怎么问
- 主轴和交叉轴分别是什么？
- `flex: 1` 到底等价于什么？
- `justify-content` 和 `align-items` 容易混在哪？

## ⚠️ 易错点 / 高阶拓展
很多人记属性靠死背，最好结合主轴方向去理解。高频坑点包括子元素最小宽度、换行后对齐、`margin: auto` 与对齐属性的关系。

