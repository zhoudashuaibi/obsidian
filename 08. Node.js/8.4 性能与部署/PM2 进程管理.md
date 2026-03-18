---
title: PM2 进程管理
tags:
  - Node.js
  - 8.4 性能与部署
  - 面试
status: active
date: 2026-03-18
---

# PM2 进程管理

## 📌 核心概念
PM2 是 Node.js 常用进程管理工具，提供守护、重启、日志、监控、集群模式和开机自启等能力。

## 💻 代码示例
```bash
pm2 start app.js -i max
pm2 logs
pm2 restart app
pm2 monit
```

## 🛠 实战场景
线上服务部署后，需要自动拉起、平滑重启、查看日志和进程状态时，PM2 很常见。

## 🎯 面试怎么问
- PM2 的 cluster 模式做了什么？
- 为什么 PM2 适合生产部署？
- pm2 reload 和 restart 的区别？

## ⚠️ 易错点 / 高阶拓展
PM2 只是进程管理，不等于完整运维方案。日志切割、配置中心、容器编排仍要单独建设。
