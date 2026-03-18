---
title: 实时消息：长轮询、SSE、WebSocket 选型
tags:
  - 系统设计
  - 11.2 场景设计题
  - 面试
status: active
date: 2026-03-18
---

# 实时消息：长轮询、SSE、WebSocket 选型

## 📌 核心概念
实时通信方案按实时性、双向性、实现复杂度和基础设施要求不同。长轮询兼容性好但开销大，SSE 单向推送简单，WebSocket 适合高频双向通信。

## 💻 代码示例
```js
const ws = new WebSocket('wss://example.com/socket')
ws.onmessage = (event) => console.log(event.data)
```

## 🛠 实战场景
IM、报价推送、协同编辑、任务进度通知都需要根据业务特性做实时方案选型。

## 🎯 面试怎么问
- SSE 和 WebSocket 的差异？
- 长轮询为什么成本高？
- 弱网下连接断开如何重连？

## ⚠️ 易错点 / 高阶拓展
不是所有“实时”都要 WebSocket。低频通知、服务端单向推送场景，SSE 往往更简单。
