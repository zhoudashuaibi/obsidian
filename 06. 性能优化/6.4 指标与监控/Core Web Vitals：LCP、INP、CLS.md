---
title: Core Web Vitals：LCP、INP、CLS
tags:
  - 性能优化
  - 指标与监控
  - 面试
status: active
date: 2026-03-18
---

# Core Web Vitals：LCP、INP、CLS

## 📌 核心概念
Core Web Vitals 是 Google 关注的核心用户体验指标。LCP 衡量主要内容加载完成时间，INP 衡量交互响应延迟，CLS 衡量视觉稳定性。它们分别对应“看得快、点得动、不乱跳”。

## 💻 代码示例
```js
// 可通过 web-vitals 库上报
import { onLCP, onINP, onCLS } from 'web-vitals';
```

## 🛠 实战场景
性能优化不该只停留在“感觉更快”，而要落实到指标监控与目标值管理，Core Web Vitals 就是常见基准。

## 🎯 面试怎么问
- LCP、INP、CLS 分别衡量什么？
- 为什么 FID 逐渐被 INP 替代？
- 如何降低 CLS？

## ⚠️ 易错点 / 高阶拓展
指标要结合真实用户监控（RUM）看，实验室数据只能辅助定位，不代表真实线上体验。

