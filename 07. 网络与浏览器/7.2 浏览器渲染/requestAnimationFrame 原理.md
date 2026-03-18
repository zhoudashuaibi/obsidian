---
title: requestAnimationFrame 原理
tags:
  - 网络与浏览器
  - 7.2 浏览器渲染
  - 面试
status: active
date: 2026-03-18
---

# requestAnimationFrame 原理

## 📌 核心概念
requestAnimationFrame 会在浏览器下一次重绘前执行回调，和屏幕刷新节奏对齐，适合驱动视觉动画。相比 setTimeout，它更省电，也更不容易丢帧。

## 💻 代码示例
```js
let start = 0
function step(ts) {
  if (!start) start = ts
  const progress = Math.min((ts - start) / 300, 1)
  box.style.transform = `translateX(${progress * 200}px)`
  if (progress < 1) requestAnimationFrame(step)
}
requestAnimationFrame(step)
```

## 🛠 实战场景
前端手写动画、平滑过渡、拖拽反馈、游戏循环都更适合用 rAF。

## 🎯 面试怎么问
- rAF 和 setTimeout 做动画的区别？
- rAF 回调参数是什么？
- 页面切到后台时 rAF 会怎样？

## ⚠️ 易错点 / 高阶拓展
rAF 只是更适合动画，不代表业务逻辑也应该全部塞进去。重计算放在 rAF 里一样会掉帧。
