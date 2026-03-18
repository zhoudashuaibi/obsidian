---
title: Buffer 与字符编码
tags:
  - Node.js
  - 8.1 核心模块
  - 面试
status: active
date: 2026-03-18
---

# Buffer 与字符编码

## 📌 核心概念
Buffer 是 Node.js 用来处理二进制数据的核心类型，适合网络传输、文件读写、加解密等场景。字符编码决定字节如何映射为文本，常见有 UTF-8、Base64、Hex。

## 💻 代码示例
```js
const buf = Buffer.from('前端', 'utf8')
console.log(buf)
console.log(buf.toString('utf8'))
console.log(buf.toString('base64'))
```

## 🛠 实战场景
上传文件、处理图片、解析 TCP 数据包、生成签名时，经常会碰到 Buffer 和编码转换。

## 🎯 面试怎么问
- Buffer 和字符串的区别？
- 为什么中文字符的 byteLength 会更大？
- Base64 是加密吗？

## ⚠️ 易错点 / 高阶拓展
Base64 只是编码不是加密；字符串长度和字节长度也不能混为一谈。
