---
title: transform 代替 top 和 left 的原因
tags:
  - CSS
  - 动画与性能
  - 面试
status: active
date: 2026-03-18
---

# transform 代替 top 和 left 的原因

## 📌 核心概念
用 `top`、`left` 改位置通常会影响布局，可能触发重排和重绘；`transform` 更多是合成阶段处理，常常只触发合成，不改文档流，因此动画更流畅。

## 💻 代码示例
```css
.ball {
  position: absolute;
  will-change: transform;
  transform: translate3d(120px, 0, 0);
}

.ball:hover {
  transform: translate3d(180px, 0, 0);
}
```

## 🛠 实战场景
拖拽、轮播、悬浮动效、抽屉动画中如果频繁改 `top/left`，很容易掉帧；改用 `transform` 往往能明显改善体验。

## 🎯 面试怎么问
- 为什么推荐用 `transform` 做位移动画？
- `top/left` 一定比 `transform` 慢吗？
- 什么是重排、重绘、合成？

## ⚠️ 易错点 / 高阶拓展
不是所有 transform 都零成本，过多合成层也可能吃内存。回答时要避免绝对化，说“通常更利于性能”更准确。

