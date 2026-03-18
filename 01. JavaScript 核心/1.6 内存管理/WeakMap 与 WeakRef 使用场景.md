---
title: WeakMap 与 WeakRef 使用场景
tags:
  - JavaScript
  - 内存管理
  - 面试
status: active
date: 2026-03-18
---

# WeakMap 与 WeakRef 使用场景

## 📌 核心概念
`WeakMap` 的键必须是对象，且对键是弱引用；当键对象被回收后，对应记录也会消失。`WeakRef` 则允许你弱引用某个对象，在需要时尝试读取，但不能保证对象仍存在。

## 💻 代码示例
```js
const wm = new WeakMap();
let el = { id: 1 };
wm.set(el, { mounted: true });

console.log(wm.get(el)); // { mounted: true }
el = null; // 键对象若无其他强引用，可被回收

const ref = new WeakRef({ name: 'cache' });
console.log(ref.deref());
```

## 🛠 实战场景
给 DOM 节点、实例对象挂元信息时，使用 `WeakMap` 可避免生命周期结束后仍被普通 `Map` 强引用住。`WeakRef` 更适合做非强保证缓存。

## 🎯 面试怎么问
- `WeakMap` 和 `Map` 最大区别是什么？
- 为什么 `WeakMap` 不能遍历？
- `WeakRef` 适合解决什么问题？

## ⚠️ 易错点 / 高阶拓展
弱引用并不等于“马上回收”，GC 仍由引擎决定。业务上优先用清晰的生命周期管理，弱引用只是在特定场景下辅助降风险。

