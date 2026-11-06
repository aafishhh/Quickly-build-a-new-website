---
name: homepage-seo
description: 常见落地页类型 SEO 规范——只针对**首页 + 销售型落地页**这类「转化门面」页。与 blog-seo-writing（博客文章页）平级但管不同类型页面：本 skill 管品牌/转化页的 SEO——品牌主词 + 核心产品词选取、页面 TDK（title/description/canonical/hreflang）、WebSite/Organization/Product schema、枢纽内链布局。**不适用**：导航/目录/索引页、会员/账户/工作台页等特殊类型页面。适用于要做或检查网站首页、销售型落地页等常见落地页面的 SEO head 与关键词策略时。When to use: 用户要做网站首页SEO、销售型落地页SEO、常见落地页怎么定关键词/写H1/布内链，或觉得首页SEO不该和博客共用一套规则时。
agent_created: true
---

# 常见落地页 SEO 规范（首页 / 销售型落地页）

> 这套规范**只针对「常见落地页类型」**——**首页 + 销售型落地页**（针对某一关键词做转化的 landing page，如"AI 图片编辑"页）。这是与 `blog-seo-writing`（仅博客文章页）**平级、互不套用**的独立规范。

## 适用范围：本 skill 管什么 / 不管什么

| 页面类型 | 用什么 skill | 代表 / 处理方式 |
|---|---|---|
| 博客文章页 | `blog-seo-writing` | /blog/xxx 单篇文章 |
| **首页** | **本 skill（homepage-seo）** | 网站门面、品牌主入口 |
| **销售型落地页** | **本 skill（homepage-seo）** | 针对某关键词做转化的 landing page |
| 导航/目录/索引页 | **不适用**（另订或不做标准化） | 网址导航、类目目录、索引页、sitemap 式页面 |
| 会员/账户/工作台页 | **不适用**（登录后页通常 noindex） | 登录、账户中心、数据工作台 |
| 工具/功能页 | **本 skill 的边界外**（交互特殊，按需另行考虑） | 在线工具、产品实际操作页 |

**本 skill 管**：首页 + 销售型落地页这类「转化门面」的 SEO head 字段 + 关键词策略 + H1 + 枢纽内链 + JSON-LD。
**本 skill 不管**：博客正文写作、长尾词文章 TDK、Article schema、文章内链（归 `blog-seo-writing`）；导航/会员等特殊类型的 SEO（另议）。

## 一、首页 vs 博客 的本质差异（为什么不能共用一套）

| 维度 | 博客文章页（blog-seo-writing） | 首页/非博客页（本 skill） |
|---|---|---|
| 目的 | 抓长尾搜索流量 | 品牌/转化门面，传达价值 |
| 关键词 | 单篇瞄准 1 个长尾词 | **品牌词 + 核心产品词**（不堆） |
| H1 | 文章标题 | 品牌主张（主标语），简洁有力 |
| 内链 | 大量互链到相关文 | **枢纽**：往下导到内页/功能/博客 |
| schema | Article / BlogPosting | WebSite + Organization（+ 页面级 Product/FAQ） |
| Title | 长尾词前置 | **品牌名 + 核心产品词 + 价值** |
| canonical | 单篇规范 URL | 全站 x-default 主入口 |

## 二、关键词策略（品牌主词 + 核心产品词）

非博客页不追长尾，用「**一个品牌主关键词 + 少量核心产品词**」：

1. **品牌词**：产品名/网站名（例：TextEditImage）。全网唯一，首页必须有。
2. **核心产品词**：用户怎么描述你要解决的问题（例：AI 图片文字编辑）。选 1–2 个，不堆。
3. **每个常见落地页一个焦点词**：首页聚焦品牌词；销售型落地页聚焦该页的产品词（对应 `mvp-scoping` 的页面职责）。

> 核心词进 Title + Description + H1，各自然出现 1 次即可，**不追求密度**（那是博客的事）。

## 三、TDK 规范

### Title（≤60 字符）
- 前置核心词（品牌词或产品词，前 30 字符内出现）
- 带上品牌名 + 一句价值/行动点
- 首页：`核心产品词 + 品牌名`（例：`AI 图片文字在线编辑 | TextEditImage`）

### Description（≤160 字符）
- `是什么 + 价值 + 行动点`
- 首页可直接复用 Hero 副标题
- 不堆关键词，写清给用户的好处

### canonical + hreflang
- **canonical**：当前页规范 URL（消除重复页）
- **hreflang**：多语言站加 alternate（各 locale）+ `x-default`。**首页的 x-default 指向 en 版**（全站主入口）
- 模式：`urlFor(loc) => localizeUrl(base, {locale: loc}).href`

> 字段写法（head 长什么样 / 怎么调 API）按项目技术栈交给 `tool-site-foundation`；本 skill 定「每个字段填什么、作用」。

## 四、JSON-LD 结构化数据

常见落地页按类型加，**不用 Article**：

| 页面 | schema |
|---|---|
| 全站 | `WebSite`（站点名 + 品牌词）|
| 首页 | `WebSite` + `Organization`（logo/联系方式）|
| 销售型落地页 | + `SoftwareApplication` / `Product` |
| 落地页带 FAQ 区块 | + `FAQPage`（问题与页面可见文本逐字一致）|

> 结构化数据随页面类型增减，别一张站点 schema 到处套。

## 五、枢纽内链布局（常见落地页 = 枢纽，不是终点）

与博客相反——落地页**往外导**：

- **首页**：向核心产品词对应的销售型落地页/功能页各导 1 条（锚文本用目标页主题词）
- **销售型落地页**：向首页（锚文本=品牌名）、相关功能页、以及相关博客文章导航
- **页脚导航**：品牌词锚文本指向首页（天然枢纽）
- 所有内链指向真实 URL，发前逐一验证

## 六、交付与验证

- 交付时列出：TDK 及字符数、焦点词、H1、canonical/hreflang/schema、内链清单（锚文本→URL）
- **校验不过（字符数越界、canonical 重复、内链 404）停下改，不许带病交付**
- 用 `len()` 校验 Title/Description 字符数

## 与页面块区家族衔接

- `page-block-home` 定首页块区（竞品调研选型）；块区定了之后，本 skill 定这块的 SEO 怎么写
- `blog-seo-writing` 只管博客文章页，本 skill 只管首页 + 销售型落地页，**两者不交叉**
- 特殊类型（导航/目录/索引、会员/账户/工作台）的 SEO 不在本 skill 覆盖范围，需另订**

## 注意事项

- **不与博客共用一套**：品牌词 vs 长尾词、WebSite vs Article、枢纽内链 vs 文章互链——完全不同
- **常见落地页不追密度**：核心词自然出现即可，不堆砌（堆词是博客那套）
- **一个页面一个焦点词**：首页=品牌词，销售型落地页=该页产品词
- **枢纽导向**：常见落地页负责把用户往下导，不是被链的终点
- **只对常见落地页**：导航/索引页、会员/账户/工作台页不套这套规则
- 与 `git-worktree-isolation` 配合：页面 SEO 在独立 worktree/分支开发
