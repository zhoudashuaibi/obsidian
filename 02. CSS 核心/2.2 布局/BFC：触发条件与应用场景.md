---
title: BFC：触发条件与应用场景
tags:
  - CSS
  - 布局
  - 面试
status: active
date: 2026-03-18
---

# BFC：触发条件与应用场景

## 📌 核心概念
BFC 即块级格式化上下文，是页面中的一块独立布局区域。开启 BFC 后，内部布局不会影响外部，常用于清除浮动、防止外边距重叠、隔离浮动元素。

## 💻 代码示例
```css
.wrapper {
  overflow: hidden;
}

.sidebar {
  float: left;
  width: 200px;
}

.content {
  overflow: hidden;
}
```

## 🛠 实战场景
老项目中大量浮动布局问题都能通过 BFC 理解和修复；即便现代用 Flex/Grid，多数面试仍会拿它考基础布局原理。

## 🎯 面试怎么问
- 什么是 BFC？
- 哪些方式可以触发 BFC？
- BFC 能解决哪些经典布局问题？

## ⚠️ 易错点 / 高阶拓展
不要把 `overflow: hidden` 当成万能药，它可能顺带裁切内容。现代项目更常用 `flow-root` 明确表达“我要一个新的 BFC”。

