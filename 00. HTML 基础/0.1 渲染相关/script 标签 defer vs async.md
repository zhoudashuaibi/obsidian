---
title: script 标签 defer vs async
tags:
  - HTML
  - 渲染相关
  - 面试
status: active
date: 2026-03-18
---

# script 标签 defer vs async

## 📌 核心概念

`defer` 和 `async` 都用于减少脚本对 HTML 解析的阻塞，但行为不同：`defer` 会并行下载、等 HTML 解析完成后**按顺序**执行；`async` 会并行下载，下载完成后**立刻**执行，顺序不保证。

| 特性 | 普通 `<script>` | `async` | `defer` |
|------|----------------|---------|---------|
| 下载时机 | 阻塞 HTML 解析 | 并行下载 | 并行下载 |
| 执行时机 | 立即执行（阻塞） | 下载完立即执行 | HTML 解析完成后执行 |
| 执行顺序 | 按顺序 | **不保证顺序** | **保证顺序** |
| DOMContentLoaded | 在其之前执行 | 可能在其前后 | 在其之前执行 |

## 💻 代码示例

```html
<!-- 普通 script：阻塞 HTML 解析，立即执行 -->
<script src="block.js"></script>

<!-- defer：并行下载，HTML 解析完成后按顺序执行 -->
<!-- 执行顺序永远是 a → b → c，即使 c 最先下载完 -->
<script defer src="a.js"></script>
<script defer src="b.js"></script>
<script defer src="c.js"></script>

<!-- async：并行下载，谁先下载完谁先执行，顺序不保证 -->
<script async src="analytics.js"></script>
<script async src="ads.js"></script>
```

**加载时序示意：**

```
普通 script：
HTML ████░░░░████████   （░ = 被脚本阻塞）
JS        ████

async：
HTML ████████████████   （不阻塞）
JS   ════════████       （下载完就执行，可能打断 HTML 渲染）

defer：
HTML ████████████████   （不阻塞）
JS   ════════════████   （等 HTML 解析完才执行）
```

## 🛠 实战场景

**使用 `defer` 的场景（主业务代码）：**

```html
<!-- Vue / React 打包产物，依赖 DOM 且脚本间有依赖 -->
<script defer src="vendor.js"></script>
<script defer src="app.js"></script>
```

**使用 `async` 的场景（独立第三方脚本）：**

```html
<!-- 埋点统计：与页面逻辑无关，越早加载越好 -->
<script async src="https://www.googletagmanager.com/gtag/js"></script>

<!-- 错误监控：独立运行，不依赖其他脚本 -->
<script async src="sentry.js"></script>

<!-- 广告脚本：独立加载，不影响主流程 -->
<script async src="ads.js"></script>
```

> [!warning] 常见错误
> ```html
> <!-- ❌ 错误：b.js 依赖 a.js（如 jQuery 和插件），但 async 不保证顺序 -->
> <script async src="jquery.js"></script>
> <script async src="jquery-plugin.js"></script>
>
> <!-- ✅ 正确：改用 defer 保证顺序 -->
> <script defer src="jquery.js"></script>
> <script defer src="jquery-plugin.js"></script>
> ```

## 🎯 面试怎么问

**Q1：`defer` 和 `async` 的区别是什么？**
> 两者都是并行下载脚本、不阻塞 HTML 解析。区别在执行时机：`async` 下载完立即执行（执行时仍会阻塞 HTML 解析），顺序不确定；`defer` 等 HTML 全部解析完才执行，且多个 `defer` 脚本按文档顺序执行。

**Q2：为什么多个 `defer` 脚本能保持顺序？**
> 浏览器遇到 `defer` 脚本时，将其加入一个**有序队列**，不立即执行。等 HTML 解析触发 `DOMContentLoaded` 前，按脚本在文档中出现的顺序依次执行队列中的脚本。

**Q3：什么脚本更适合用 `async`？**
> 适合**完全独立、无依赖**的脚本：如埋点统计、广告投放、错误监控等第三方服务。这类脚本不依赖 DOM 结构，也不被其他业务脚本依赖，可以任意时机执行。

## ⚠️ 易错点 / 高阶拓展

**易错点 1：误以为两者都是"异步执行"**
两者下载都是并行的（不阻塞 HTML），但**执行时都会阻塞渲染**。区别只在于执行触发时机和是否保证顺序。

**易错点 2：`async` 脚本的 `DOMContentLoaded` 时机不确定**
- 如果脚本下载很快，可能在 `DOMContentLoaded` 之前执行
- 如果脚本下载慢，可能在 `DOMContentLoaded` 之后执行
- `defer` 脚本一定在 `DOMContentLoaded` 之前执行

**高阶拓展：动态插入的 `<script>` 默认是 `async`**
```javascript
const script = document.createElement('script');
script.src = 'foo.js';
// 默认 script.async === true
// 若需要保证顺序，需手动设置：
script.async = false;
document.head.appendChild(script);
```

**高阶拓展：`type="module"` 默认是 `defer`**
```html
<!-- ES Module 脚本默认具有 defer 行为 -->
<script type="module" src="app.js"></script>
```
