---
title: 靶向更新 PatchFlags
tags:
  - Vue
  - 虚拟 DOM 与 Diff
  - 面试
status: active
date: 2026-03-18
---

# 靶向更新 PatchFlags

## 📌 核心概念
Vue 3 编译器会给动态节点打上 PatchFlags，运行时更新时可直接知道哪些部分可能变化，比如文本、class、style、props，从而避免做无意义的全量比较。

## 💻 代码示例
```js
// 伪理解：
// vnode.patchFlag = TEXT | CLASS
// 更新时只检查文本和 class，而不是整个节点全部 diff
```

## 🛠 实战场景
这让 Vue 3 的运行时更依赖编译结果，实现“编译时多做、运行时少做”的性能思路。

## 🎯 面试怎么问
- PatchFlags 是什么？
- Vue 3 为什么更新更“精准”？
- 编译优化和运行时优化是什么关系？

## ⚠️ 易错点 / 高阶拓展
Vue 3 的性能提升不只是 Proxy，还包括编译器层面的大量优化。面试能主动提到这点会更完整。

