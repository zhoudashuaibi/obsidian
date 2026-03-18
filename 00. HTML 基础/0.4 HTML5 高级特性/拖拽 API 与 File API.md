---
title: 拖拽 API 与 File API
tags:
  - HTML
  - HTML5 高级特性
  - 面试
status: active
date: 2026-03-18
---

# 拖拽 API 与 File API

## 📌 核心概念
HTML5 原生提供拖拽 API 处理元素拖放交互，也提供 File API 读取本地文件信息与内容。两者结合后可实现拖拽上传、文件预览、客户端解析等能力。

## 💻 代码示例
```html
dropZone.addEventListener('drop', (event) => {
  event.preventDefault();
  const file = event.dataTransfer.files[0];
  console.log(file.name);
});
```

## 🛠 实战场景
文件上传、图片拖拽预览、Excel 导入、可视化编辑器拖放交互都常用到这组 API。

## 🎯 面试怎么问
- 原生拖拽上传怎么实现？
- `dataTransfer` 里通常能拿到什么？
- File API 能直接读文件内容吗？

## ⚠️ 易错点 / 高阶拓展
拖拽 API 在不同浏览器和复杂组件场景下体验并不总是稳定，很多项目会对原生能力做二次封装。

