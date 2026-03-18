---
title: transition vs animation
tags:
  - CSS
  - 动画与性能
  - 面试
status: active
date: 2026-03-18
---

# transition vs animation

## 📌 核心概念
`transition` 适合状态变化时的过渡，必须有触发前后两个状态；`animation` 适合更复杂、自动播放、可循环的关键帧动画。前者轻量直观，后者表达能力更强。

## 💻 代码示例
```css
.btn {
  transition: transform 0.2s ease, opacity 0.2s ease;
}

.btn:hover {
  transform: translateY(-2px);
}

@keyframes pulse {
  0%, 100% { transform: scale(1); }
  50% { transform: scale(1.05); }
}

.badge {
  animation: pulse 1.2s infinite;
}
```

## 🛠 实战场景
按钮 hover、展开收起、页面进入过渡适合 transition；骨架屏闪烁、loading、无限循环装饰动画更适合 animation。

## 🎯 面试怎么问
- `transition` 和 `animation` 的区别是什么？
- 什么场景更适合 keyframes？
- 为什么说动画属性选择会影响性能？

## ⚠️ 易错点 / 高阶拓展
动画不是越多越好。业务中更重要的是控制节奏、减少干扰，并优先使用不会触发重排的大多数 transform/opacity 动画。

