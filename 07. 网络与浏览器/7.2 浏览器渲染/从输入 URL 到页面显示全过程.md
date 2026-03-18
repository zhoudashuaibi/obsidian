---
title: 从输入 URL 到页面显示全过程
tags:
  - 网络与浏览器
  - 7.2 浏览器渲染
  - 面试
status: active
date: 2026-03-18
---

# 从输入 URL 到页面显示全过程

## 📌 核心概念
从输入 URL 到页面显示，大致经历 URL 解析、缓存判断、DNS 解析、TCP/TLS 建连、HTTP 请求、服务端响应、浏览器解析 HTML、构建 DOM/CSSOM、生成 Render Tree、布局、绘制、合成显示。

## 💻 代码示例
```text
1. 解析 URL
2. 查缓存 / DNS
3. TCP / TLS 握手
4. 发送 HTTP 请求
5. 解析 HTML / CSS / JS
6. 布局 Layout
7. 绘制 Paint
8. 合成 Composite
```

## 🛠 实战场景
这是浏览器综合题，常用于考察网络、缓存、渲染、性能优化是否能串起来讲。

## 🎯 面试怎么问
- 输入 URL 后先发生什么？
- DNS、TCP、TLS、HTTP 的顺序是什么？
- 为什么 CSS 会阻塞渲染？

## ⚠️ 易错点 / 高阶拓展
回答时不要只讲网络或只讲渲染。面试官更看重你能否按时间线串成完整链路，并顺手指出可优化点。
