---
name: page-block-home
description: 页面块区 skill 家族之首页（Home/Landing）：首页的三个层面——① 应该有哪些块区（固定骨架序列）、② 整站风格设计（设计方向库 + 反 AI 模板化）、③ 首页 SEO（head/meta/canonical/hreflang）。参考 shipany-pixany-template 的 index.tsx/blocks 与 design-theme skill 提炼。适用于要设计或检查网站首页的场景。When to use: 用户要做网站首页/落地页、想知道首页该有哪些区块、首页风格怎么定、首页 SEO 怎么写，或觉得首页长得像模板要换风格时。
agent_created: true
---

# 页面块区模板：首页（Home / Landing）

## Overview

首页是网站门面，「页面块区 skill 家族」里最重要的一页。它涉及三个层面，本 skill 一并覆盖：

1. **块区**：首页应该有哪几块、什么顺序（固定骨架序列）
2. **风格设计**：整站视觉风格怎么定（设计方向库，避免做出来千篇一律像模板）
3. **首页 SEO**：head/meta/canonical/hreflang 怎么写

参考源：`aafishhh/shipany-pixany-template` 的首页结构（`src/routes/index.tsx` + `src/blocks/*`）和 `design-theme` skill（反 AI 模板化的成熟方法论）。

**沿袭家族铁律**：
- **块区=固定骨架**（复用一致），**视觉=产品皮肤**（配色/字体每产品自定）
- **导航/页脚=产品定制占位**（本 skill 只标位置）
- **SEO 内容规则独立**（首页 SEO 的文案/关键词写法，涉及更细内容规则时交给 blog-seo-writing 或独立 SEO skill）

**与上层衔接**：
- 输入：`mvp-scoping` 的页面清单（首页是核心用例页，必在清单里）
- 输出：块区结构 + 风格方向 + SEO head 交给 `tool-site-foundation` 实现

## 第一层：首页块区（固定骨架序列）

### 标准首页块区（参考 shipany 模板 + 落地页实践）

| # | 块区 | 作用 | 固定内容 |
|---|---|---|---|
| 1 | **Header 导航（产品定制占位）** | 全站入口 | 复用产品导航（Logo+栏目+CTA），位置在此，内容产品定 |
| 2 | **Hero** | 首页门面/第一印象 | 标题(H1) + 副标题 + 主 CTA + 可选输入/展示位。这是最定制的一块 |
| 3 | **Features（特性）** | 讲清功能 | 几个特性卡片/网格，说明产品能做什么 |
| 4 | **Showcase（场景/示例）** | 讲清用途 | 场景、示例、截图或用户故事，让用户看到「用了会怎样」 |
| 5 | **Pricing（定价）**（如有收费） | 转化 | 定价档位表（对应 mvp-scoping 商业模式页） |
| 6 | **FAQ**（可按块区选） | 打消疑虑 | 常见问答，可复用 FAQ 块区 |
| 7 | **CTA（终局号召）** | 转化收尾 | 一句号召 + 按钮（如「Get Started」） |
| 8 | **Footer 页脚（产品定制占位）** | 全站收尾 | 复用产品页脚 |
| 9 | **辅助组件** | 用户体验 | cookie-consent（欧盟合规）、support-widget（客服入口）等，产品自定 |

> 参考站 shipany 的默认首页是 `Header→Hero→Features→Showcase→Pricing→Footer`（+SupportWidget）；落地页实践常再加 FAQ + CTA 收尾。**FAQ/CTA 是否加入看你产品需要**——但 Hero/Features/Showcase/Footer 是必有的主骨架。

### Hero 是首页的灵魂

Hero 是整个首页（也是全站）最重要的块，它承载第一印象。设计 Hero 时应想清楚：
- 一句主标题（H1，含核心关键词——关键词写法归 SEO 内容规则）
- 副标题（一句话说清价值）
- 主 CTA（一个，别铺太多按钮）
- 可选：产品截图/演示/输入条（工具站常放核心输入入口，复用产品自己的组件）

## 第二层：整站风格设计（设计方向库）

> 这部分借鉴 `design-theme` skill 的成熟方法论。核心：**绝不出默认模板的样子**，每个产品的视觉必须从它自己的产品/受众/brief 推导。

### 步骤

1. **定方向**（从产品本身推导，不用「现代简洁」这种空话）：
   - 产品是什么、给谁用、气质如何
   - 给一句方向，如「AI 视频站 → 影院暗场：近黑底、荧光青点缀、宽银幕卡片」而非「modern and clean」
2. **选方向库**（pick ONE，再按产品定制）：
   1. Cinematic still（视频/影像工具）— 近黑、宽银幕媒介、单个暖高光；`Bebas Neue`/`Anton`
   2. Terminal/mono（开发者工具）— 纸或近黑、等宽字体点缀、打字机 Hero、边框优于阴影
   3. Soft brutalism（创作工具/独立）— 单一饱和底色、2px 边框、硬偏移阴影；`Space Grotesk`
   4. Editorial magazine（内容/博客/机构）— 墨色温白、网格线、超大衬线标题；`Fraunces`
   5. Product-first light（SaaS 仪表盘）— 白底、产品截图即 Hero 论点；`Plus Jakarta Sans`
   6. Swiss data（分析/金融）— 白底、12 列网格可见、单红/钴强调、超大数字
   7. Playful geometric（消费/教育）— 2-3 个明亮块、超大圆角、贴纸卡片
   8. Luxury dark（高端/工具）— 炭黑（非纯黑）、金属细线、宽松字距；`Cormorant Garamond`
   9. Organic/natural（健康/食品/生活）— 大地色调、人文衬线、柔软不规则形状
3. **反 AI 模板化禁区**（绝不用，除非 brief 明确要求）：
   - 渐变标题文字（尤其青→紫/粉）
   - 近黑底 + 霓虹光效胶囊按钮
   - 「AI」默认紫色强调色
   - 奶油底 + 高对比衬线 + 陶土强调（模板默认 look）
   - 近黑 + 一个酸性绿/朱红作为整个身份
   - 环境渐变光晕 / 光束当背景填充
   - Hero 徽章/标题里用 emoji 装饰
   - 「Elevate/Seamless/Unleash」等空泛动词、假数据截图、装饰性状态圆点
4. **落地 tokens**（交给技术层）：配色、字体对（一个特色展示体 + 一个互补正文，别用默认 Inter+衬线对）、一个 signature 元素（一个让人记住的记忆点，其余的保持安静）
5. **校验**：看一眼会不会被误认成模板/任何禁区项——会就再迭代。

## 第三层：首页 SEO

### head 基本要素（每个首页都要有）

- **title**：核心关键词前置（写法归 SEO 内容规则 skill）
- **description**：`是什么 + 用户好处 + 行动点`（可复用 Hero 副标题作为 description）
- **canonical**：当前地的规范 URL
- **hreflang**：多语言站要加 alternate（各 locale）+ `x-default`

### 参考实现（shipany 首页 head 模式）

```
head() 返回：
  meta: [
    { name: 'description', content: <description> },   // 可用 hero 副标题
  ],
  links: [
    { rel: 'canonical', href: <当前locale规范URL> },
    ...locales.map(loc => ({ rel: 'alternate', hrefLang: loc, href: <那locale URL> })),
    { rel: 'alternate', hrefLang: 'x-default', href: <en URL> },   // 多语言时
  ]
```

> 说明：首页具体 key 词、H1 写什么、description 字数等**内容规则**涉及 SEO 写作规范——交给 `blog-seo-writing`（或独立 SEO 内容规则 skill），本 skill 只定「首页 head 有哪些字段、各自作用」。

## 与上层衔接

- **输入**：`mvp-scoping` 的页面清单（首页是核心用例页）
- **FAQ/CTA 块区**：如需可引用落地页实践或单独细化
- **输出**：块区 + 风格方向 + SEO head 结构交给 `tool-site-foundation` 实现
- **其余页面**：博客页 → `page-block-blog`，基础页 → `page-block-foundation`

## 注意事项

- **只定结构，不写代码**：块区/风格方向/SEO head 结构给「是什么样」，「怎么做」交给技术 skill
- **块区=固定骨架 + 产品皮肤**：Hero/Features/Showcase/Footer 是主骨架；FAQ/CTA 按需加
- **风格绝不出模板样**：每个产品从自身推导视觉，禁用 AI 模板化清单
- **首页 SEO head 字段固定**：title/description/canonical/hreflang 都该有；具体文案归内容规则 skill
- 与 `git-worktree-isolation` 配合：首页/落地页在独立 worktree/分支开发
