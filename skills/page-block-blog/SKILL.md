---
name: page-block-blog
description: 页面块区 skill 家族之 Blog 页：把 Blog 两类页面（列表页 /blog 与 单篇文章页 /blog/<slug>）的块区结构固定为统一模板——块区数量、顺序、职责写死，供任意网站复用一致。参考真实站 worthcodes.com 的块区结构提炼（列表 = Hero + 最新大卡 + Popular 侧栏 + 分类筛选 + 卡片网格；文章 = 面包屑 + 元信息 + 导语 + 封面 + 正文[左TOC目录导航|正文|右侧栏] + FAQ + Related guides + 返回，TOC 滚动联动参考 foreplay.co）。视觉风格/主题色不在此定（由产品各自定）。适用于要建网站博客模块、需要确定 Blog 列表页和文章页固定块区长什么样的场景。When to use: 用户要做一个网站的博客模块、想知道 Blog 列表页和文章页的统一块区模板（固定结构），或要基于 worthcodes.com 的博客结构做自己的博客页。
agent_created: true
---

# 页面块区模板：Blog（列表页 + 文章页）

## Overview

「页面块区 skill」家族按页面类型逐类覆盖**单页内部的块区结构**（这是 mvp-scoping 明确让渡给本家族的职责）。每个页面类型一个 skill：首页、Blog、About、工作台……

本 skill 覆盖 **Blog 两类页面**，**块区结构为固定模板**（各块的数量、顺序、职责写死），所有网站复用一致：
1. **Blog 列表页**（`/blog/`）：博客入口，文章卡片聚合
2. **单篇文章页**（`/blog/<slug>/`）：单篇内容阅读页

**两个铁律**：
1. **视觉风格/主题色不在此定**：块区模板是「骨架」（哪些块、什么顺序、放什么），**配色/字体/圆角/间距等视觉由每个产品各自定**——同一套块区套在不同产品上，外观可以完全不一样。参考站的配色/字体只是示例，不是模板规定
2. **产品定制组件与 SEO 内容不归此 skill**：
   - Sticky 导航、页脚是产品级组件（不同产品栏目/CTA/法律链接不同），本 skill **只标位置**，不固化内容
   - H1 标题、导语、正文、FAQ、元信息日期等的**写法**涉及 SEO（关键词/密度/结构），由**独立的 SEO 内容规则 skill** 管辖（博客文章页 → `blog-seo-writing`），本 skill 只定「块存在、在哪、什么顺序」

**与上层的衔接**：
- 输入：`mvp-scoping` 的页面清单（本文档细化 Blog 页这一类的块区）
- 输出：块区结构可直接交给 `tool-site-foundation`（技术实现）或开发
- 本 skill 只定「块区长什么样（位置/顺序/作用）」，不写代码、不定视觉色、不定 SEO 内容

## 固定块区结构（模板，直接套用）

> 参考源：**worthcodes.com**（`/blog/` 列表页 + `/blog/<slug>` 文章页）。这是折扣码/促销站博客的成熟结构，块区数量、顺序、职责如下表写死，**无定制点**。

### Blog 列表页（/blog/）固定块区

| # | 块区 | 作用 | 固定内容 |
|---|---|---|---|
| 1 | **Sticky 导航（产品定制占位）** | 全站入口 | 复用产品导航组件（Logo+栏目+CTA），位置在此，内容产品定 |
| 2 | **Hero 标题区**（居中 `text-center`，`max-w-[820px]`） | 确立博客定位 | **Eyebrow 标签**（小号等宽「Blog」）+ **H1 标题**（博客定位语）+ **intro 副标题**（`max-w-[640px]` 一句话说明）。文案写法归 SEO skill |
| 3 | **「最新文章」双栏区**（`grid` 左大卡 + 右侧栏） | 头条曝光 + 热门引流 | **左 = 最新文章大卡**：封面图（h-240）+ H2 标题 + 摘要（2 行截断）+ 作者/阅读时间行。**右 = `aside` Popular posts**：小标题「Popular posts」+ 文章列表（H3 标题 + 摘要 + 作者/阅读时间） |
| 4 | **「Explore more」区块**（`mt-20`） | 全量内容入口 | **小标题区**（「Explore more blogs」H2 + 副标题）+ **Topic 分类筛选 pills**（All / 各分类如 Brands / Coupon Codes / Reviews / Tutorials）+ **文章卡片网格**（3 列：封面图 + H3 标题 + 摘要 + 作者/阅读时间） |
| 5 | **页脚（产品定制占位）** | 全站收尾 | 复用产品页脚（品牌简介/栏目列/版权/法律链接），位置在此，内容产品定 |

### 单篇文章页（/blog/<slug>/）固定块区

| # | 块区 | 作用 | 固定内容 |
|---|---|---|---|
| 1 | **Sticky 导航（产品定制占位）** | 全站入口 | 复用产品导航组件，位置在此，内容产品定 |
| 2 | **面包屑 `dc-crumb`** | 层级定位 | **固定为：`Blog / <当前文章标题>`**（标题可截断 `truncate`），Blog 链接回列表页 |
| 3 | **H1 标题**（居中，`max-w-[680px]`） | 文章标题 | 位置在此；写法归 SEO 内容规则 skill（与 Title 一致） |
| 4 | **导语**（`text-lg`，一句话回答） | 摘要/开局 | 位置在此；文案归 SEO 内容规则 skill（开头 100 字内回答核心问题） |
| 5 | **元信息行** | 阅读前信息 | **固定字段：作者头像 + 作者名 + `Published 日期` · `Updated 日期` + `✓ Last verified 日期` + `阅读时间`**（多段用分隔符隔开）。Last verified（绿色）徽章是可信度加分项 |
| 6 | **封面大图**（居中 `h-[280px]`，`max-w-[680px]`） | 视觉入口 | 圆角、居中、宽幅。文件名/alt 归 SEO 规范 |
| 7 | **正文**（居中列 + 左右 `aside`） | 核心内容 | 桌面三栏网格 `[左TOC | 正文 | 右侧栏]`，移动端左右侧栏隐藏。**左侧 `aside` = 目录导航（TOC，必须有）**：标题「Table of contents」+ 有序列表，每项 = H2 锚点链接（`#<h2-id>`），滚动联动高亮当前段落（`.is-active`，IntersectionObserver 实现，参考 foreplay.co）。**正文固定层级：`H2(带#锚点) → 段落 → 无序/有序列表 → 加粗关键值`**。正文写法归 SEO 内容规则 skill |
| 8 | **FAQ 区**（`pt-10` 分隔线后） | 打消疑虑 | **固定：H2「Frequently asked questions」+ 每个问答 = H3 问题 + 段落答案**。需与页面 JSON-LD `FAQPage` 逐字一致（保富摘要） |
| 9 | **Related guides** | 留住读者 | **固定：区头（eyebrow「Keep reading」+ H2「Related guides」+ 右侧「View all posts →」链接）+ 3 列文章卡片**（封面图 + H3 标题 + 摘要 + 作者/阅读时间） |
| 10 | **返回链接** | 回到列表 | **固定：`← Back to all guides`**，链接回 `/blog/` |
| 11 | **页脚（产品定制占位）** | 全站收尾 | 复用产品页脚（品牌简介/栏目列/版权/法律链接），位置在此，内容产品定 |

> 本模板**无定制点**：以上各块是固定的，不做「可选/可加/按需」。若要改结构，是改这个 skill 本身，不是每次项目临场发挥。

## 复用共享组件

- **导航 / 页脚**：**产品定制占位**——应在产品级（`tool-site-foundation` 或首页块区模板）统一，博客页只引用位置，不在本 skill 固化内容
- **文章卡片**：列表页「Explore more」卡片、文章页 Related 卡片、侧栏 Popular 列表用**同一套卡片样式**，保持一致
- **Blog 艺术封面**：worthcodes 用纯色块 + 大写字标 + 标签（如「Brand」+「WorthCodes · Evidence log」）替代真实图片，产品可换用真实封面图，位置不变

## 视觉样式说明

- **本 skill 不提供配色/字体/圆角基线**——那些是产品主题（theme）的事
- 参考站（worthcodes.com）的视觉只是**示例**：产品要用自己的主题色/字体风格，套骨架即可
- 若产品没有主题规范：由 `tool-site-foundation` 或首页块区模板建立一套，博客继承

## 与上层衔接

- **输入**：`mvp-scoping` 的页面清单已包含 Blog 页 → 本 skill 细化其块区
- **SEO**：博客文章页的写法（H1/导语/正文/FAQ/slug/图片/internal-link）→ 交给 `blog-seo-writing`
- **输出**：块区结构交给 `tool-site-foundation` / 开发实现

## 注意事项

- **只定块区，不写代码**：本 skill 给「长什么样、什么顺序、放什么」，实现交给 tech skill
- **固定结构，无定制点**：各块写死，不临场取舍
- **视觉是产品皮肤**：本 skill 只给骨架，配色/字体/风格由产品主题定，套不同产品可长不一样
- **导航/页脚是产品级组件**：产品自定内容，博客只标位置
- **SEO 内容不在本 skill**：H1/导语/正文/FAQ 写法归独立 SEO 内容规则 skill
- **卡片一致性**：列表页卡片 = Related 卡片 = Popular 列表用同一套样式
- **Last verified / Evidence log**：促销/折扣类博客的信任要素（验证徽章 + 证据标签），普通内容博客可省，但块结构位置保留
- **左侧 TOC 必须有**：桌面端目录导航（Table of contents）是文章页固定块区，正文每个 H2 需带 `id` 锚点，TOC 项滚动联动高亮（参考 foreplay.co）
- 与 `git-worktree-isolation` 配合：博客模块在独立 worktree/分支开发

## Resources

- 参考源：`worthcodes.com/blog/` 与 `/blog/winninghunter-discount-code-2026`（已抓取分析）；左侧 TOC 目录导航参考 `foreplay.co/post/the-2026-super-bowl-ads`（Table of contents + H2 锚点 + `.is-active` 滚动高亮 + IntersectionObserver 联动）
- 本家族其他 skill：`page-block-home`、`page-block-foundation`（基础页）等（建一个页面类型一个 skill）
