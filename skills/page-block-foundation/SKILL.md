---
name: page-block-foundation
description: 页面块区 skill 家族之基础页（About/Contact/Privacy/Terms 四页固定骨架模板）：每页的块区数量、顺序、职责写死，供任意网站复用一致，视觉风格/主题色由产品各自定（皮肤）。参考真实站 trendtrackpromocode.com 的基础页结构提炼。适用于要建网站基础页（关于/联系/隐私/条款）时对照参考。When to use: 用户要做一个网站的 About/Contact/Privacy/Terms 基础页、想知道这四个基础页的固定块区模板（骨架）、或要基于 trendtrackpromocode.com 的基础页结构做自己的基础页。
agent_created: true
---

# 页面块区模板：基础页（About / Contact / Privacy / Terms）

## Overview

「页面块区 skill」家族按页面类型逐类覆盖**单页内部的块区结构**（这是 mvp-scoping 明确让渡给本家族的职责）。每个页面类型一个 skill：首页、Blog、About、工作台……

本 skill 覆盖 **4 个基础页**（任何网站都有的底座页，mvp-scoping 里「基础底座」类）：About / Contact / Privacy / Terms。**块区结构为固定模板**（各块数量、顺序、职责写死），所有网站复用一致。

**沿用家族铁律**：
1. **视觉是产品皮肤**：本 skill 只管「骨架」（哪些块、什么顺序、放什么），**配色/字体/圆角/间距由产品主题定**——同一骨架套不同产品可长得完全不一样
2. **导航/页脚是产品定制占位**：这两项产品级组件本 skill 只标位置，不固化内容
3. **正文写法归内容规则 skill**：如需要 SEO 内容规则（本家族主要针对内容型页面），由 blog-seo-writing / 独立内容规则 skill 管

**参考源**：`trendtrackpromocode.com` 的真实基础页（/about/ /contact/ /privacy/ /terms/）实际抓取提炼。

**与上层的衔接**：
- 输入：`mvp-scoping` 的页面清单（本 skill 细化基础页这类的块区）
- 输出：块区结构交给 `tool-site-foundation`（技术实现）或开发

## 固定块区结构（模板，直接套用）

### About 页（/about/）固定块区

| # | 块区 | 作用 | 固定内容 |
|---|---|---|---|
| 1 | **Sticky 导航（产品定制占位）** | 全站入口 | 复用产品导航组件，位置在此，内容产品定 |
| 2 | **H1 主标题** | 一句话定位 | 核心标题（品牌/定位一句话），常带副标题。文案归 SEO/内容规则 |
| 3 | **为什么存在（Why）** | 讲起源故事 | 1-2 段：为什么做这个站/产品（经历、观察、动机） |
| 4 | **我们做什么（What）** | 职责/服务 | **3 列**：三类核心职责/服务/板块，每列标题+一句说明 |
| 5 | **我们怎么赚钱（How）** | 透明声明 | 1-2 段：商业模式（联盟/订阅/广告），坦诚说明利益关系 |
| 6 | **我们不是什么（Not）** | 边界声明 | 1 段：澄清「我们不是官方/不是 X」，划清身份 |
| 7 | **终局 CTA** | 转化收尾 | 一句号召 + 按钮（如「Ready to save 20%?」） |
| 8 | **页脚（产品定制占位）** | 全站收尾 | 复用产品页脚，位置在此，内容产品定 |

### Contact 页（/contact/）固定块区

| # | 块区 | 作用 | 固定内容 |
|---|---|---|---|
| 1 | **Sticky 导航（产品定制占位）** | 全站入口 | 复用产品导航组件 |
| 2 | **H1 主标题** | 页面标题 | 如「Let's Connect!」（亲和标题） |
| 3 | **副标题** | 响应承诺 | 1 段：说明回复时效（如「一个工作日内回复」）+ 独立身份声明 |
| 4 | **留言表单区** | 提交流 | 表单块（姓名/邮箱/留言/提交按钮） |
| 5 | **我们能帮什么（分类）** | 引导分流 | 几个分类块：每类「标题 + 说明」（如：优惠券/产品/其他） |
| 6 | **页脚（产品定制占位）** | 全站收尾 | 复用产品页脚 |

### Privacy Policy 页（/privacy/）固定块区

| # | 块区 | 作用 | 固定内容 |
|---|---|---|---|
| 1 | **Sticky 导航（产品定制占位）** | 全站入口 | 复用产品导航组件 |
| 2 | **H1 标题** | 页面标题 | 固定为「Privacy Policy」 |
| 3 | **更新时间** | 时效信息 | 固定显示「Last updated : <日期>」（动态日期） |
| 4 | **引言** | 概述 | 1 段：政策适用范围 + 一句话概述 |
| 5 | **H2 条款各节** | 正文 | **固定章节序列**（见下） |
| 6 | **页脚（产品定制占位）** | 全站收尾 | 复用产品页脚 |

**Privacy 固定章节序列**：
`Interpretation and Definitions` → `Collecting and Using Your Personal Data`（含 Types of Data Collected / Tracking Technologies and Cookies）→ `Use of Your Personal Data` → `Retention` → `Transfer` → `Delete Your Personal Data` → `Disclosure`（含 Business Transactions / Law Enforcement / Other Legal Requirements）→ `Security` → `Children's Privacy` → `Links to Other Websites` → `Changes to This Privacy Policy` → `Contact Us`

### Terms and Conditions 页（/terms/）固定块区

| # | 块区 | 作用 | 固定内容 |
|---|---|---|---|
| 1 | **Sticky 导航（产品定制占位）** | 全站入口 | 复用产品导航组件 |
| 2 | **H1 标题** | 页面标题 | 固定为「Terms and Conditions」 |
| 3 | **更新时间** | 时效信息 | 固定显示「Last updated : <日期>」（动态日期） |
| 4 | **引言** | 概述 | 1 段：使用前须知 |
| 5 | **H2 条款各节** | 正文 | **固定章节序列**（见下） |
| 6 | **页脚（产品定制占位）** | 全站收尾 | 复用产品页脚 |

**Terms 固定章节序列**：
`Interpretation and Definitions` → `Acknowledgment` → `Links to Other Websites` → `Termination` → `Limitation of Liability` → `"AS IS" and "AS AVAILABLE" Disclaimer` → `Governing Law` → `Disputes Resolution` → `Severability and Waiver` → `Changes to These Terms` → `Contact Us`

## 复用共享组件

- **导航 / 页脚**：产品定制占位，产品级统一，本家族只标位置
- **表单样式**：Contact 页表单与产品其他表单用同一套样式（产品主题定）
- **条款页排版**：Privacy/Terms 的 H2 各节用统一的排版（正文段落式，不搞卡片花样）

## 视觉样式说明

- **本 skill 不提供配色/字体/圆角基线**——产品主题定
- 参考站的视觉只是示例；套骨架用产品自己的主题色/字体
- 若产品无主题规范：由 `tool-site-foundation` 或首页块区模板建立，基础页继承

## 与上层衔接

- **输入**：`mvp-scoping` 的「基础底座」页面清单（About/Contact/Privacy/Terms 必选）→ 本 skill 细化块区
- **Blog 页**：单独在 `page-block-blog` skill（本家族另一成员）
- **输出**：块区结构交给 `tool-site-foundation` / 开发实现

## 注意事项

- **只定块区，不写代码**：给「长什么样、什么顺序、放什么」，实现交给 tech skill
- **固定结构，无定制点**：各块写死，不临场取舍（要改结构是改 skill 本身）
- **视觉是产品皮肤**：本 skill 只给骨架，配色/字体/风格由产品主题定
- **导航/页脚是产品级组件**：只标位置，内容产品自定
- **条款章节固定**：Privacy/Terms 的 H2 序列是法律模板标准，**不要随意增删**（内容措辞如需专业审核另行处理）
- 与 `git-worktree-isolation` 配合：页面模块在独立 worktree/分支开发

## Resources

- 参考源：`trendtrackpromocode.com/about/` `/contact/` `/privacy/` `/terms/`（已抓取分析）
- 本家族其他 skill：`page-block-blog`（Blog 页）、`page-block-home`（首页，待建）等