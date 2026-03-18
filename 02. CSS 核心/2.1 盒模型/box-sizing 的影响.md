---
title: box-sizing 的影响
tags:
  - CSS
  - 盒模型
  - 面试
status: active
date: 2026-03-18
---

# box-sizing 的影响

## 📌 核心概念
`box-sizing` 决定元素宽高的计算范围。`content-box` 是默认值，宽高只算内容；`border-box` 把内边距和边框也算进去，更利于响应式布局和组件封装。

## 💻 代码示例
```css
.container {
  display: flex;
  gap: 16px;
}

.item {
  width: 50%;
  padding: 16px;
  border: 1px solid #ddd;
  box-sizing: border-box;
}
```

## 🛠 实战场景
做后台管理、移动端布局、组件库时，统一 `border-box` 可以减少“我明明写了 50%，为什么两列放不下”的问题。

## 🎯 面试怎么问
- `box-sizing` 有哪几个值？
- 为什么组件库常全局改成 `border-box`？
- 改成 `border-box` 后宽高计算逻辑有什么变化？

## ⚠️ 易错点 / 高阶拓展
`border-box` 不是万能的，内容区可能被压缩得更小。写固定高度组件时，要留意文本溢出和内部滚动问题。

