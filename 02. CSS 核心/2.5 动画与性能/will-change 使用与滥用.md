---
title: will-change 使用与滥用
tags:
  - CSS
  - 动画与性能
  - 面试
status: active
date: 2026-03-18
---

# will-change 使用与滥用

## 📌 核心概念
`will-change` 是给浏览器的性能提示，表示某个属性即将变化，浏览器可提前做优化准备，如创建合成层。但这不是性能开关，乱用会增加内存和渲染开销。

## 💻 代码示例
```css
.drawer {
  will-change: transform;
}

.drawer.is-open {
  transform: translateX(0);
}
```

## 🛠 实战场景
复杂动画开始前短暂加上 `will-change`，有时能减少首帧卡顿；但长期挂在大量元素上，会让页面资源占用飙高。

## 🎯 面试怎么问
- `will-change` 是做什么的？
- 为什么不能把它写成全局通用优化？
- 哪些属性最常和 `will-change` 一起出现？

## ⚠️ 易错点 / 高阶拓展
最佳实践是“少量、短时、明确目标”。如果只是机械地给所有元素加 `will-change: transform`，通常是在制造新问题。

