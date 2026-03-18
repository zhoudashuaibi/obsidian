---
title: HTTP 1.1 vs HTTP 2 vs HTTP 3
tags:
  - 网络与浏览器
  - 7.1 HTTP
  - 面试
status: active
date: 2026-03-18
---

# HTTP 1.1 vs HTTP 2 vs HTTP 3

## 📌 核心概念
HTTP/1.1 以文本协议和串行请求为主，常靠长连接、管线化勉强提升效率；HTTP/2 引入二进制分帧、多路复用、头部压缩；HTTP/3 基于 QUIC 跑在 UDP 上，把传输层重传与拥塞控制前移，重点解决队头阻塞和弱网切换问题。

## 💻 代码示例
```bash
curl --http1.1 https://example.com
curl --http2 https://example.com
curl --http3 https://example.com
```

## 🛠 实战场景
首屏资源很多、接口并发高、用户网络波动大时，经常会被问为什么升级到 HTTP/2 或 HTTP/3，以及升级后真正改善了哪类瓶颈。

## 🎯 面试怎么问
- HTTP/2 比 HTTP/1.1 快在哪里？
- HTTP/3 为什么不用 TCP？
- HTTP/2 是否彻底解决了队头阻塞？

## ⚠️ 易错点 / 高阶拓展
HTTP/2 的多路复用只能解决应用层队头阻塞，底层仍受 TCP 丢包影响；HTTP/3 不是简单“更快”，它主要提升高延迟、弱网和连接迁移场景的体验。
