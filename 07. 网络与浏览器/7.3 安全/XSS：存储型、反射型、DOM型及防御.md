---
title: XSS：存储型、反射型、DOM型及防御
tags:
  - 网络与浏览器
  - 7.3 安全
  - 面试
status: active
date: 2026-03-18
---

# XSS：存储型、反射型、DOM型及防御

## 📌 核心概念
XSS 的本质是把不可信数据当成代码执行。按来源常分存储型、反射型、DOM 型，核心防御是输出编码、输入校验、CSP、避免危险 API。

## 💻 代码示例
```js
function escapeHtml(str) {
  return str
.replace(/&/g, '&amp;')
.replace(/</g, '&lt;')
.replace(/>/g, '&gt;')
.replace(/"/g, '&quot;')
.replace(/'/g, '&#39;')
}
```

## 🛠 实战场景
评论区、富文本、搜索关键字回显、第三方脚本接入都属于高风险区域。

## 🎯 面试怎么问
- 三种 XSS 的区别是什么？
- innerHTML 为什么危险？
- 仅靠 CSP 能防住所有 XSS 吗？

## ⚠️ 易错点 / 高阶拓展
不要把“过滤 script 标签”当成完整方案。事件属性、URL 协议、SVG、模板注入都可能成为入口。
