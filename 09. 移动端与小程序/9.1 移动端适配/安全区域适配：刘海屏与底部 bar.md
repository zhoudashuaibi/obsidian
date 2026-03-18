---
title: 安全区域适配：刘海屏与底部 bar
tags:
  - 移动端与小程序
  - 9.1 移动端适配
  - 面试
status: active
date: 2026-03-18
---

# 安全区域适配：刘海屏与底部 bar

## 📌 核心概念
全面屏设备存在刘海、圆角、底部 Home Indicator 等安全区域，页面若不适配，内容可能被遮挡。iOS 通常依赖 `env(safe-area-inset-*)`。

## 💻 代码示例
```css
.page {
  padding-bottom: calc(16px + env(safe-area-inset-bottom));
  padding-top: env(safe-area-inset-top);
}
```

## 🛠 实战场景
底部 Tab、弹窗按钮、顶部导航栏最容易被安全区域影响。

## 🎯 面试怎么问
- safe-area-inset-bottom 是什么？
- 为什么 viewport-fit=cover 要一起配置？
- 安卓和 iOS 适配有什么差异？

## ⚠️ 易错点 / 高阶拓展
只适配底部不适配顶部，或者把安全区值写死，都会导致不同设备表现不一致。
