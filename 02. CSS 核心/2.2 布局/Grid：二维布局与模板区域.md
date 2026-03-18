---
title: Grid：二维布局与模板区域
tags:
  - CSS
  - 布局
  - 面试
status: active
date: 2026-03-18
---

# Grid：二维布局与模板区域

## 📌 核心概念
Grid 是二维布局系统，能同时控制行和列，非常适合整体页面区域划分。通过 `grid-template-columns`、`grid-template-rows` 和 `grid-template-areas`，可以把布局语义化地描述出来。

## 💻 代码示例
```css
.page {
  display: grid;
  grid-template-columns: 240px 1fr;
  grid-template-rows: 64px 1fr;
  grid-template-areas:
    'header header'
    'aside main';
}

.header { grid-area: header; }
.aside { grid-area: aside; }
.main { grid-area: main; }
```

## 🛠 实战场景
后台系统、Dashboard、营销页复杂栅格区块比 Flex 更适合用 Grid，因为它不需要写太多嵌套容器就能表达行列关系。

## 🎯 面试怎么问
- Grid 和 Flex 的适用场景差异是什么？
- `1fr` 代表什么？
- `grid-template-areas` 有什么优势？

## ⚠️ 易错点 / 高阶拓展
Grid 很强，但移动端兼容策略、自动布局行为、隐式网格和最小内容尺寸都容易被忽略。不要为了简单一维排列强上 Grid。

