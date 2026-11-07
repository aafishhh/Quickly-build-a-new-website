# Quickly-build-a-new-website
Quickly build a new website — skill vault (skills added later)

## 使用顺序与场景

从一个模糊想法到上线网站，按这个链路依次用（每步产出交给下一步）：

1. **new-website-ideation**（立项）— 有模糊想法时用。产出 `08-prd.md`（用户/痛点/凭什么赢/最小做啥）
2. **mvp-scoping**（构造 MVP）— 立项清楚后用。产出页面类型清单 + 导航关系（只到页面类型层）
3. **mvp-function-flow**（功能链路）— 页面类型定下后用。产出核心功能链路：动作链 + 每页承载的功能 + 功能↔页面映射（给单页块区当依据，不拆 UI）
4. **页面块区家族**（定骨架）— 页面清单+功能链路定下后用。按页面类型选：
   - `page-block-foundation`：基础页（About/Contact/Privacy/Terms）
   - `page-block-blog`：博客（列表页 + 单篇文章页）
   - `page-block-home`：首页（竞品调研 + 块区选型方法论——不写死骨架，调研前排 5 个竞品后决策块区顺序与每块样式）
5. **SEO 规范**（定 head 与新词）— 按页面类型选：
   - `blog-seo-writing`：博客文章页（防蚕食 + 长尾词 + TDK + 正文密度 + 内链 + slug/图片/OG + 发布后 GSC，与 page-block-blog 配套）
   - `homepage-seo`：SEO 落地页（产品/服务/功能页，商业意图词：判词性 + TDK + 文案密度 + 板块参考骨架 + 内链/图片/OG + GSC；板块结构交 page-block-home；博客信息意图词归 blog-seo-writing）
6. **tool-site-foundation**（待建，技术落地）— 骨架+内容定后用。技术栈/域名/部署/上线

核心原则：
- **块区=骨架**（固定复用一致），**视觉=产品皮肤**（配色/字体每产品自定）
- **导航/页脚=产品定制占位**（页面块区 skill 只标位置）
- **SEO 内容规则独立**（不归页面块区 skill）

## 当前收录

| Skill | 用途 | 状态 |
|---|---|---|
| `skills/new-website-ideation` | 新网站/新产品立项（模糊想法 → 可立项的业务决策文档） | 已放入，逐个优化完善中 |
| `skills/mvp-scoping` | 构造 MVP（立项范围 → 页面类型清单 + 导航关系，信息架构层面；单页块区/UI 由后续独立 skill 覆盖） | 已放入，逐个优化完善中 |
| `skills/mvp-function-flow` | 核心功能链路（页面清单之后：核心动作链 + 每页承载的功能 + 功能↔页面映射，给单页块区当依据；不拆 UI） | 已放入，逐个优化完善中 |
| `skills/page-block-blog` | 页面块区家族 · Blog（Blog 列表页 + 单篇文章页的块区通用模板，参考 worthcodes.com 提炼：列表=Hero+最新大卡+Popular侧栏+分类筛选+卡片网格；文章=面包屑+元信息+导语+封面+正文[左TOC目录导航（foreplay 滚动联动）\|正文\|右侧栏]+FAQ+Related+返回） | 已放入，逐个优化完善中 |
| `skills/blog-seo-writing` | 博客 SEO 写作完整规范 v2（流程含防蚕食 → 正文结构 → 密度 → 内链 → URL/图片/OG/外链/最后更新 → 发布后 24h GSC → 交付验证，来自用户调教规范） | 已放入，逐个优化完善中 |
| `skills/page-block-foundation` | 页面块区家族 · 基础页（About/Contact/Privacy/Terms 四页固定块区骨架模板） | 已放入，逐个优化完善中 |
| `skills/page-block-home` | 页面块区家族 · 首页（竞品调研 + 块区选型方法论：搜索/指定取前排 5 竞品 → 拆解块区顺序与每块样式 → 结合自家产品选型） | 已放入，逐个优化完善中 |
| `skills/homepage-seo` | SEO 落地页写作规范 v2（首页 + 销售型落地页：判词性/一页一意图/防蚕食 → TDK → 页面结构参考骨架(可调序) → 文案规则/密度 → 内链/图片/OG → 发布后 GSC → 交付验证；块区结构交 page-block-home；导航/会员等特殊类型不适用；与 blog-seo-writing 平级不共用） | 已放入，逐个优化完善中 |

> 每个 skill 都会逐个针对性地优化完善后再补充进本仓库。
