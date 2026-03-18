---
title: 长任务优化：任务切片与 requestIdleCallback
tags:
  - 性能优化
  - 运行时性能
  - 面试
status: active
date: 2026-03-18
---

# 长任务优化：任务切片与 requestIdleCallback

## 📌 核心概念
单个 JS 任务执行过久会阻塞主线程，导致点击无响应、输入卡顿。常见优化是把大任务拆成多个小片段执行，或在空闲时机用 `requestIdleCallback` 处理低优先级工作。

## 💻 代码示例
```js
function chunk(tasks) {
  function run(deadline) {
    while (deadline.timeRemaining() > 0 && tasks.length) {
      tasks.shift()();
    }
    if (tasks.length) requestIdleCallback(run);
  }
  requestIdleCallback(run);
}
```

## 🛠 实战场景
大数据渲染、批量计算、埋点整理、离线预处理都适合做任务切片，避免页面“假死”。

## 🎯 面试怎么问
- 什么是长任务？
- 为什么任务切片能提升交互流畅度？
- `requestIdleCallback` 有哪些限制？

## ⚠️ 易错点 / 高阶拓展
空闲回调并不可靠，浏览器可能长时间不给空闲窗口。重要逻辑不能完全依赖它，还要有兜底调度策略。

