---
title: 标准盒模型 vs IE盒模型
tags:
  - CSS
  - 盒模型
  - 面试
status: active
date: 2026-03-18
---

# 标准盒模型 vs IE盒模型

## 📌 核心概念
标准盒模型中 `width` 和 `height` 只表示内容区，元素实际占位还要加上 `padding` 和 `border`；IE 盒模型则把 `padding`、`border` 一并算进设定宽高。现代 CSS 通过 `box-sizing` 显式控制使用哪种计算方式。

## 💻 代码示例
```css
.card {
  width: 200px;
  padding: 20px;
  border: 10px solid #333;
  box-sizing: content-box;
}

.panel {
  width: 200px;
  padding: 20px;
  border: 10px solid #333;
  box-sizing: border-box;
}
```

## 🛠 实战场景
表单、卡片、栅格布局中如果不统一盒模型，宽度很容易超出父容器，导致换行、抖动或滚动条问题。

## 🎯 面试怎么问
- 标准盒模型和 IE 盒模型的区别是什么？
- `width: 100%` 配合 `padding` 为什么会撑破容器？
- 生产环境为什么经常全局设置 `box-sizing: border-box`？

## ⚠️ 易错点 / 高阶拓展
不要只背“一个算 padding 一个不算”，要能结合实际占位解释。高阶会追问根元素继承 `box-sizing` 的最佳实践。

