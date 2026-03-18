---
title: z-index 失效场景
tags:
  - CSS
  - 层叠与优先级
  - 面试
status: active
date: 2026-03-18
---

# z-index 失效场景

## 📌 核心概念
`z-index` 只对已定位元素或 flex/grid item 生效，而且比较范围受层叠上下文限制。很多“失效”并不是属性没用，而是比较对象不在同一上下文，或者元素根本没参与 z-index 排序。

## 💻 代码示例
```css
.tooltip {
  position: absolute;
  z-index: 1000;
}

.parent {
  position: relative;
  z-index: 1;
  transform: translateZ(0);
}
```

## 🛠 实战场景
弹窗、下拉框、日期选择器、吸顶头部和地图组件叠层冲突时，`z-index` 失效是最常见排障题。

## 🎯 面试怎么问
- `z-index` 为什么有时不起作用？
- 哪些前提条件下 `z-index` 才生效？
- 如何系统排查层级问题？

## ⚠️ 易错点 / 高阶拓展
优先检查是否创建了新的层叠上下文、是否有 `position`、是否被父级裁切。真正稳妥的弹层方案往往还要结合 Portal 或挂载到更高层 DOM。

