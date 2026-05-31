---
name: devops-news
description: 获取每日最新 DevOps/云原生资讯，从 CNCF Blog、InfoQ、Cloudflare Blog 等权威数据源抓取内容，生成赛博朋克风格的 HTML 展示页面。当用户想获取 DevOps 资讯、云原生新闻、今日技术资讯、CNCF/InfoQ/Cloudflare 最新动态，或想生成技术资讯日报时，必须使用这个 skill。关键词包括：devops资讯、云原生新闻、今日资讯、技术新闻、每日资讯、news、资讯日报、CNCF动态、InfoQ、Cloudflare新闻等。即便用户只说"帮我看看今天有什么技术新闻"也应触发此 skill。
---

# DevOps 每日资讯

你的任务是从多个技术博客抓取最新 DevOps/云原生资讯，整理成结构化数据，并生成一个视觉炫酷的赛博朋克风格 HTML 展示页面。

## 输出文件

最终需要交付两个文件（保存到当前工作目录）：
1. `devops-news-data.js` — 数据文件（JS 变量）
2. `devops-news.html` — 展示页面

---

## Step 1：抓取数据

依次用 `WebFetch` 访问以下数据源，提取文章列表：

| 数据源 | URL |
|--------|-----|
| CNCF Blog | `https://www.cncf.io/news/` |
| InfoQ | `https://www.infoq.com/continuous_delivery/` |
| Cloudflare Blog | `https://blog.cloudflare.com/tag/speed-and-reliability/` |

**抓取要点：**
- 每个数据源至少尝试抓取 5 条，三个数据源合计目标 15-20 条
- 如果某个网站无法访问（超时、403、空响应），跳过并继续处理下一个
- 确保每条资讯包含：标题、摘要/描述、完整链接
- 补全不完整链接（如 `/blog/xxx` → `https://www.cncf.io/blog/xxx`）

**每条资讯的字段说明：**
- `title`：文章标题（原文，无需翻译）
- `description`：文章主旨的中文摘要，80字以内，简洁精炼
- `link`：文章详情的完整 URL
- `tags`：2-4 个标签，根据标题和内容自动推断，第一个标签建议为来源标识（`cncf`/`infoq`/`cloudflare`）

**数据质量要求：**
- 去除明显重复（相同主题或相似标题）
- JS 文件中字符串内部的双引号必须用反斜杠 `\"` 转义
- description 不超过 80 字

---

## Step 2：保存数据文件

将抓取结果保存为 `devops-news-data.js`，格式如下：

```js
const NEWS_DATA = [
  {
    "title": "Kubernetes 1.32 Released with Enhanced Security Features",
    "description": "Kubernetes 1.32 带来了增强的安全特性，包括改进的 RBAC 策略和新的 Pod 安全标准，大幅提升集群安全性。",
    "link": "https://www.cncf.io/blog/2025/01/15/kubernetes-1-32-released/",
    "tags": ["cncf", "kubernetes", "security", "release"]
  },
  {
    "title": "GitOps Best Practices for Production Deployments",
    "description": "介绍 GitOps 在生产环境中的最佳实践，涵盖 Flux 和 ArgoCD 的配置策略，帮助团队实现声明式部署管理。",
    "link": "https://www.infoq.com/articles/gitops-best-practices/",
    "tags": ["infoq", "gitops", "devops", "deployment"]
  }
];
```

---

## Step 3：创建 HTML 展示页面

创建 `devops-news.html`，通过 `<script src>` 引入数据文件，实现数据与模板分离。

**重要：** 数据必须来自外部文件，不能内联在 HTML 中：

```html
<!-- 在 </body> 前引入 -->
<script src="devops-news-data.js"></script>
<script>
  // NEWS_DATA 变量来自 devops-news-data.js
  renderNews(NEWS_DATA);
</script>
```

### 视觉风格：赛博朋克

参考如下设计规范：

**色彩系统：**
- 背景：深黑 `#0a0a0f` + 深蓝灰 `#0d1117`
- 主色调：霓虹青 `#00ffff` / 霓虹紫 `#bf00ff` / 霓虹粉 `#ff0080`
- 文字：亮白 `#e0e0e0`，次要文字 `#888`
- 卡片背景：`#111122`，边框用霓虹色半透明

**视觉效果：**
- 标题/Logo 使用 `text-shadow` 制造霓虹发光效果
- 卡片 `hover` 时边框高亮 + `box-shadow` 光晕
- 可选：顶部添加扫描线动画（`@keyframes scanline`）
- 字体优先使用 `'Courier New', monospace` 营造终端感

**布局结构：**

```
┌─────────────────────────────────────────────┐
│  [LOGO/标题] DEVOPS DAILY NEWS  [日期] [条数] │
│  ══════════════════════════════════════════  │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  │
│  │  卡片 1   │  │  卡片 2   │  │  卡片 3   │  │
│  │ 标题      │  │ 标题      │  │ 标题      │  │
│  │ 摘要      │  │ 摘要      │  │ 摘要      │  │
│  │ [tag][tag]│  │ [tag][tag]│  │ [tag][tag]│  │
│  │ [阅读原文]│  │ [阅读原文]│  │ [阅读原文]│  │
│  └──────────┘  └──────────┘  └──────────┘  │
└─────────────────────────────────────────────┘
```

**卡片内容（每张卡片显示）：**
- 文章标题（可截断，带 title 属性）
- 描述摘要
- 标签列表（彩色 badge，不同标签不同颜色）
- "阅读原文 →" 链接（`target="_blank"`）

**响应式要求：**
- 桌面端：3 列网格
- 平板端（≤900px）：2 列
- 移动端（≤600px）：1 列

**页面顶部信息栏：**
- 显示今日日期（JS 动态获取）
- 显示资讯总条数

---

## 完成后

告知用户两个文件已生成，建议用浏览器打开 `devops-news.html`（注意：需要和 `devops-news-data.js` 在同一目录才能正常加载数据）。

如果某些数据源抓取失败，说明哪些来源成功了，共抓取了多少条资讯。
