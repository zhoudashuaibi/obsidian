---
title: WebView 与 Native 通信 JSBridge
tags:
  - 移动端与小程序
  - 9.3 Hybrid 开发
  - 面试
status: active
date: 2026-03-18
---

# WebView 与 Native 通信 JSBridge

## 📌 核心概念
JSBridge 是 WebView 与 Native 之间的通信桥梁。JS 调用 Native 通常通过注入对象、URL Scheme、消息通道；Native 回调 JS 则通过 evaluateJavaScript 或消息派发。

## 💻 代码示例
```js
window.JSBridge.postMessage({
  method: 'chooseImage',
  params: { count: 1 }
})
```

## 🛠 实战场景
混合应用里调用相机、定位、支付、分享时，前端页面通常都要经过 JSBridge 与原生能力交互。

## 🎯 面试怎么问
- JSBridge 常见实现方式有哪些？
- 为什么 URL Scheme 方案逐渐减少？
- 桥接通信有哪些安全风险？

## ⚠️ 易错点 / 高阶拓展
桥接层是高风险入口，方法暴露过多、参数未校验、回调未做来源校验都可能带来安全问题。
