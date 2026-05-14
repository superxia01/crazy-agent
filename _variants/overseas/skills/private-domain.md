---
name: 海外私域运营 Private Domain Operations (Overseas)
description: |
  跨境电商/外贸海外私域运营全流程技能。覆盖 WhatsApp Business、Email Newsletter、Facebook Groups、Instagram DM 四大渠道的内容策划、生成、发布与数据分析。
  English-primary content for cross-border ecommerce private domain management across WhatsApp, Email, FB Groups, and Instagram DM.
trigger: |
  当用户涉及以下场景时激活此技能：
  - 私域内容策划 / private domain content planning
  - WhatsApp Status / Broadcast / DM 话术
  - Email Newsletter 撰写与排期
  - Facebook Group 帖子 / 社区运营
  - Instagram DM 回复 / 客户跟进
  - 私域数据周报 / private domain analytics report
  - 客户分层 / segmentation
  - 跨时区内容排期 / timezone-aware scheduling
  - 社群活跃度提升 / engagement boost
---

# 海外私域运营技能 Private Domain Operations (Overseas)

## 1. 核心认知 Core Framework

### 1.1 海外私域 vs 国内私域关键差异

| 维度 | 国内 (WeChat) | 海外 (Overseas) |
|------|--------------|-----------------|
| 主阵地 | 微信朋友圈 + 微信群 | WhatsApp Status + Email + FB Group |
| 内容时效 | 朋友圈长期可见 | WhatsApp Status 仅 24h |
| 社群形态 | 微信群（扁平、信息易沉） | FB Groups（可搜索、可置顶、可投票） |
| 触达方式 | 公众号推送 + 群发 | Email Newsletter + WhatsApp Broadcast |
| 客服通道 | 微信 1v1 | IG DM + WhatsApp DM |
| 内容语言 | 中文 | 英文为主，可辅以西语/葡语等 |
| 时区 | 单一时区（CST） | 多时区（需覆盖美东/美西/欧洲/中东等） |
| 隐私合规 | 相对宽松 | GDPR / CAN-SPAM / WhatsApp Business Policy 严格 |

### 1.2 四大渠道定位

```
WhatsApp Business  ──→  实时触达层（1v1、Broadcast、Status、Quick Replies）
                         风格：Short & Visual，快速成交与售后

Email Newsletter ──→  价值沉淀层（Weekly/Biweekly，深度内容、促销、品牌故事）
                       风格：Structured & Valuable，长尾转化

Facebook Groups   ──→  社区共建层（UGC、Q&A、投票、Exclusive content）
                       风格：Conversational & Community-driven

Instagram DM      ──→  关系维护层（客服、订单咨询、售后跟进、种草）
                       风格：Personal & Quick，温度感
```

### 1.3 私域漏斗（海外版）

```
公域引流（FB/IG Ads、TikTok、SEO）
  │
  ▼
触点捕获（WhatsApp Click-to-Chat / Email Opt-in / IG Follow）
  │
  ▼
分层运营（VIP / Active / Cold / New）
  │
  ▼
价值传递（Status + Email + FB Group + DM）
  │
  ▼
转化复购（DM 促销 / Group Flash Sale / Email Exclusive Offer）
  │
  ▼
裂变增长（Referral Program / Share-to-Unlock）
```

---

## 2. 工作流程 Workflow

### 2.1 总体流程

```
Step 1: 理解用户风格 → Step 2: 内容规划 → Step 3: 内容生成 → Step 4: 发布与排期 → Step 5: 数据复盘
```

### 2.2 Step 1 — 理解用户品牌风格 Understand Brand Voice

**执行动作：**

1. 读取用户配置文件 `[VAULT_ROOT]/00-me/` 目录下的品牌资料：
   - 品牌定位（高端 / 性价比 / 潮流 / 专业）
   - Tone of Voice（Formal / Casual / Playful / Professional）
   - 目标市场与核心时区
   - 产品品类与核心卖点

2. 确认以下关键参数：
   - **目标市场时区**（如：EST / PST / GMT / GST）
   - **主力渠道**（哪些渠道为主，哪些为辅）
   - **内容语言**（English primary，是否需要多语言）
   - **发布频率**（每天 / 每周几次 / 每周一次）
   - **用户分层策略**（是否已做 segmentation）

3. 生成「品牌风格卡 Brand Voice Card」，包含：
   - 3 个 Tone 关键词（如：Friendly, Expert, Trustworthy）
   - 禁用词列表（No-no words）
   - Emoji 使用规范（适量 / 不用 / 根据渠道调整）
   - 称呼规范（First name / Hi + name / Dear customer）

### 2.3 Step 2 — 内容规划 Content Planning

**执行动作：**

1. 根据渠道特性制定内容矩阵：

   | 渠道 | 频率 | 内容类型 | 时长/篇幅 |
   |------|------|---------|----------|
   | WhatsApp Status | 1-3次/天 | 产品图、限时优惠、幕后花絮、客户评价 | 图片+短文案(≤80字) |
   | WhatsApp Broadcast | 1-2次/周 | 促销通知、新品预告、活动邀请 | 简洁(≤150字)+CTA |
   | Email Newsletter | 1次/周 或 1次/2周 | 行业干货、品牌故事、深度评测、Exclusive Offer | 500-1200字 |
   | FB Group Post | 3-5次/周 | 讨论、投票、AMA、UGC征集、教程 | 自由长度 |
   | IG DM (主动) | 按需 | 售后跟进、订单确认、满意度调查 | 简短(≤100字) |
   | IG DM (被动) | 即时回复 | 客服、产品咨询、物流查询 | 快速精准 |

2. 规划当周/当月内容日历，存入对应渠道目录。

3. 标注每条内容的：
   - 目标（拉新 / 促活 / 转化 / 裂变）
   - 对应用户分层（All / VIP / New / Cold）
   - CTA（Call to Action）类型

### 2.4 Step 3 — 内容生成 Content Generation

**执行原则：**

- **英文为主**，语法自然地道，避免中式英语
- **每条内容必须有 CTA**（哪怕只是"Reply if you agree"）
- **视觉优先**：WhatsApp Status 和 IG 必须配图/视频描述
- **个性化**：使用变量标签 `{first_name}` `{product_name}` `{order_number}`
- **合规优先**：Email 需包含 Unsubscribe 链接；WhatsApp 遵循 24h 窗口规则

**各渠道内容模板规范详见第 3 节。**

### 2.5 Step 4 — 发布与排期 Publish & Scheduling

**时区感知排期原则：**

```
核心原则：按目标市场当地时间安排，而非运营者所在时区

推荐发布时间（当地时间）：
┌─────────────────────────────────────────────────┐
│ WhatsApp Status:  9:00 AM / 12:30 PM / 7:00 PM  │
│ Email Newsletter: Tuesday or Thursday 9:00-10:00 AM │
│ FB Group Post:    Tuesday-Thursday 10:00 AM / 6:00 PM │
│ IG DM (主动):     避免当地早8点前和晚9点后       │
└─────────────────────────────────────────────────┘

多时区策略：
- 如果覆盖美东+欧洲：Email 发美东时间，欧洲用户会看到隔夜邮件（可接受）
- WhatsApp Status：24h 有效期，发布时间灵活
- FB Group Post：发一次即可，算法会分发给活跃时段的用户
- 旺季（Black Friday 等）：增加频次，覆盖更多时段
```

**排期工具：**
- 存入内容日历文件：`[VAULT_ROOT]/30-flow/20-私域运营/00-内容日历/content-calendar.md`
- 使用 UTC 时间标注，备注目标市场本地时间

### 2.6 Step 5 — 数据复盘 Data Review

每周生成数据周报（详见第 6 节），驱动下周优化。

---

## 3. 各渠道内容规范 Channel Content Guidelines

### 3.1 WhatsApp Business

#### 3.1.1 WhatsApp Status（替代朋友圈）

**特点：** 24 小时自动消失，适合轻量、高频、强视觉内容。

**内容类型：**

| 类型 | 说明 | 示例 |
|------|------|------|
| 🖼️ Product Spotlight | 单品展示 + 短卖点 | "New arrival 🔥 [Product] — now in [color]. Tap to order!" |
| ⏰ Flash Sale / Limited Offer | 限时优惠制造紧迫感 | "⏳ 24h only: 20% off [Product]. Reply 'DEAL' to claim." |
| 📦 Behind the Scenes | 仓库/打包/团队日常，增加信任感 | "Your orders are packed and ready! 📦 Shipping out today 🚀" |
| ⭐ Customer Review | 用户好评截图/引用 | "[Customer name] loves her new [Product]! ⭐⭐⭐⭐⭐" |
| 📢 New Collection Preview | 新品预告 | "Sneak peek 👀 Drop 3 coming Friday. Stay tuned!" |
| 🎉 Milestone / Celebration | 店铺里程碑、节日祝福 | "🎉 10,000 orders shipped! Thank you for trusting us." |

**格式规范：**
- 文案 ≤ 80 词，简洁有力
- 必须配图或短视频（15s以内效果最佳）
- 最后一句放 CTA（"Reply to order" / "Tap link in bio" / "Save this for later"）
- 每天发布 1-3 条，间隔 4 小时以上
- 可使用 WhatsApp 自带字体格式（*bold*, _italic_, ~strikethrough~）

#### 3.1.2 WhatsApp Broadcast Lists

**特点：** 一次发送给最多 256 人，类似群发但更私密（接收者看到的是 1v1 消息）。

**内容类型：**

| 类型 | 说明 | 频率 |
|------|------|------|
| 🏷️ Weekly Deal Alert | 本周精选优惠 | 每周 1 次 |
| 🆕 New Arrival Notification | 新品上架通知 | 按需 |
| 🎂 Birthday / Anniversary Offer | 个性化节日优惠 | 自动触发 |
| 📋 Order Confirmation | 订单确认 + 物流更新 | 事件触发 |
| 🔔 Abandoned Cart Reminder | 购物车挽回 | 事件触发（24h后） |

**格式规范：**
- 文案 ≤ 150 词
- 开头个性化：`Hi {first_name}!`
- 正文清晰：What → Why → How（产品→卖点→行动步骤）
- 结尾明确 CTA + 链接
- 遵守 WhatsApp Business Policy：不发送垃圾信息，尊重 Opt-out

#### 3.1.3 WhatsApp Quick Reply Templates

预置常见客服场景的快速回复模板，提升响应速度：

| 场景 | 模板 |
|------|------|
| 问候 | "Hi {first_name}! 👋 Thanks for reaching out. How can I help you today?" |
| 物流查询 | "Your order #{order_number} is currently {status}. Track it here: {tracking_link}" |
| 退换货 | "Sorry to hear that! 😔 We'd love to make it right. Could you share a photo of the issue?" |
| 价格咨询 | "Great question! [Product] is ${price} with free shipping. Want me to send you the payment link?" |
| 批量询价 | "Thanks for your interest! For wholesale pricing (50+ units), here's our tier sheet: {link}" |
| 节日问候 | "Merry Christmas! 🎄 Wishing you and your family a wonderful holiday season! 🎁" |

#### 3.1.4 WhatsApp Catalog

- 维护 WhatsApp Business Catalog（商品目录）
- 每个产品包含：图片、名称、价格、描述、商品链接
- 定期更新库存状态（售罄标记）
- 目录链接嵌入 Quick Reply 和 Broadcast 中

---

### 3.2 Email Newsletter

#### 3.2.1 定位与策略

- **频率：** 每周 1 封（核心）或 每两周 1 封（轻量）
- **最佳发送日：** Tuesday / Thursday
- **最佳时间：** 目标市场 9:00-10:00 AM（本地时间）
- **工具建议：** Mailchimp / Klaviyo / Sendinblue / Omnisend

#### 3.2.2 用户分层 Segmentation

| 分层 | 标签 | 内容策略 |
|------|------|---------|
| 🌟 VIP Customers | `vip` | Exclusive early access, loyalty rewards, personal recommendations |
| 🔥 Recent Buyers | `recent_buyer` (30天内) | Cross-sell / upsell, review request, referral program |
| 👶 New Subscribers | `new_subscriber` (未购买) | Welcome series (3-5封), brand story, bestseller intro |
| ❄️ Cold Leads | `cold` (90天+未打开) | Re-engagement campaign, special "We miss you" offer |
| 🏢 Wholesale / B2B | `b2b` | Bulk pricing, new catalog, trade show invites |

#### 3.2.3 Newsletter 内容类型

| 类型 | 说明 | 建议频率 |
|------|------|---------|
| 📰 Weekly Roundup | 本周精选：1个产品推荐 + 1个行业洞察 + 1个客户故事 | 每周 |
| 📖 Brand Story / Value Piece | 品牌理念、产品溯源、可持续发展故事 | 每月 1-2 次 |
| 🔬 Product Deep Dive | 单品深度评测/对比/使用教程 | 每周或每两周 |
| 🎁 Subscriber Exclusive | 仅限邮件订阅者的专属优惠/早鸟价 | 每月 1-2 次 |
| 📊 Industry Trends | 行业趋势、市场洞察（定位专家型） | 每月 |
| 🗓️ Seasonal / Holiday Special | 节日促销、换季推荐 | 节庆节点 |

#### 3.2.4 邮件结构模板

```
Subject Line: [Emoji optional] [Hook: benefit or curiosity] (≤ 50 chars)

Preview Text: 补充说明，增加打开率 (≤ 80 chars)

---

[Header: Brand logo + consistent banner]

Greeting: Hi {first_name},

Opening Hook: 1-2 sentences connecting to reader's pain point / desire

Main Content:
  Section 1: Hero Product / Core Message (image + 2-3 bullet points)
  Section 2: Value Add (tip / story / insight)
  Section 3: Social Proof (review / testimonial / UGC)

CTA Button: [Shop Now] / [Read More] / [Claim Your Offer]
  (clear, action-oriented, single focus)

Footer:
  - Brand tagline
  - Social links (IG / FB / WhatsApp)
  - Unsubscribe link (required by CAN-SPAM)
  - Company address (required by CAN-SPAM/GDPR)
```

#### 3.2.5 Subject Line 写法原则

- **利益型：** "Save $20 on your summer essentials 🌴"
- **好奇型：** "We made a mistake... here's your gift 🎁"
- **紧迫型：** "⏰ 6 hours left: 30% off everything"
- **个性化：** "{first_name}, your exclusive preview is inside"
- **数字型：** "5 ways to style [Product] this summer"
- **避免：** ALL CAPS、过多 emoji（≤1个）、misleading clickbait

#### 3.2.6 合规要点 Compliance Checklist

- [ ] 每封邮件包含清晰的 Unsubscribe 链接
- [ ] 发件人名称一致且可识别
- [ ] Subject Line 不具有误导性
- [ ] 包含发件人真实物理地址（Post Office Box 可接受）
- [ ] GDPR 用户需有 Opt-in 记录（Double Opt-in 推荐）
- [ ] 不购买或租用邮箱列表（Only organic or legitimate lead magnets）

---

### 3.3 Facebook Groups

#### 3.3.1 定位与策略

- **类型选择：**
  - `Public Group`：用于品牌曝光、公域引流
  - `Private Group (Approved Members)`：用于 VIP 社区、深度运营（推荐）
- **命名规范：** "[Brand Name] Community" / "[Brand Name] Insiders" / "[Niche] Hub by [Brand]"
- **规模目标：** 500+ 活跃成员起为健康社区

#### 3.3.2 社区运营框架

```
每日 (Daily):
  - 早上 1 条互动帖子（Question / Poll / This or That）
  - 及时回复成员问题（< 4h 响应时间目标）
  - 点赞/回复成员发帖

每周 (Weekly):
  - 1-2 条价值帖子（Tutorial / Tip / Industry News）
  - 1 条 UGC 征集或客户故事
  - 1 条 Exclusive Offer（仅限群成员）

每月 (Monthly):
  - 1 次 Live Q&A / AMA
  - 1 次 Group Exclusive Flash Sale
  - 成员里程碑庆祝（新增100人 / 满半年等）
  - 社区数据回顾与策略调整
```

#### 3.3.3 Group 帖子类型

| 类型 | 说明 | 示例 |
|------|------|------|
| ❓ Question / Discussion | 引发讨论，提升 Engagement | "What's your biggest challenge with [topic]? Let's discuss 👇" |
| 📊 Poll / This or That | 低门槛互动，高参与率 | "Which color do you prefer? 🔴 Red or 🔵 Blue? Comment below!" |
| 📚 Tutorial / How-To | 价值输出，建立专家形象 | "📖 How to choose the right [product category]: A 3-step guide" |
| 🎉 Win / Celebration | 庆祝里程碑，增强归属感 | "🎉 We just hit 1,000 members! Here's a special gift for everyone..." |
| 💬 AMA (Ask Me Anything) | 定期互动，答疑解惑 | "Live AMA this Friday at 3 PM EST! Drop your questions below 👇" |
| 📸 UGC Campaign | 用户内容征集，社交证明 | "Show us how you style [Product]! Tag us + use #[BrandHashtag]" |
| 🏷️ Group Exclusive | 群内专属优惠，增加价值感 | "🔑 Members-only: 25% off this weekend with code GROUP25" |
| 📰 Industry News / Trend | 展示专业度，内容差异化 | "Did you see this trend in [industry]? Here's what it means for you..." |

#### 3.3.4 社区管理规范

- **入群欢迎：** 设置 Auto-Question（如："What brings you here?"）筛选质量成员
- **群规公告：** 置顶群规（禁止 spam / self-promotion without permission / hate speech）
- **置顶内容：** 每周更新 Pinned Post（本周活动 + 热门讨论 + 专属优惠码）
- **Moderator：** 指定 1-2 名管理员（可从活跃 VIP 中招募）
- **Engagement Booster：** 使用 Facebook Group Insights 识别最佳发布时间
- **讨论引导：** 对成员帖子及时互动（点赞 + 有意义回复），避免"官方冷场"

---

### 3.4 Instagram DM

#### 3.4.1 定位与策略

- **核心功能：** 客服第一线 + 关系维护 + 成交促单
- **响应速度目标：** < 1 小时（工作时段）
- **工具：** Instagram 自带 DM + ManyChat / Chatfuel（自动化）

#### 3.4.2 DM 场景与话术

**场景 A：新关注者欢迎（自动/半自动）**

```
"Hey {first_name}! 👋 Welcome to [Brand Name]!
Thanks for following — we're excited to have you here.

Here's what you can expect from us:
✨ Daily product inspiration
🔥 Exclusive followers-only deals
📦 Behind-the-scenes content

Want to say hi? We'd love to hear from you! 😊"
```

**场景 B：产品咨询回复**

```
"Great choice! 👏 [Product] is one of our bestsellers.

Here are the details:
- Price: ${price} (free shipping!)
- Colors available: [list]
- Material: [material]

Would you like me to send you the direct link to order? 🛒"
```

**场景 C：订单查询**

```
Hi {first_name}! 👋
Your order #{order_number} has been shipped! 📦

Tracking: {tracking_number}
Estimated delivery: {date}

Track your package here: {tracking_link}

Let me know if you have any questions! 😊"
```

**场景 D：售后跟进（发货后 7-14 天）**

```
"Hey {first_name}! 👋 Just checking in — how are you liking your [Product]?

We'd love to hear your feedback! If you're happy with your order,
a quick review would mean the world to us: {review_link}

(And if anything isn't perfect, just reply — we'll make it right! 😊)"
```

**场景 E：购物车挽回**

```
"Hey {first_name}! 👋 We noticed you left something behind...

Your [Product] is still waiting in your cart! 🛒
Good news: you can still use code COMEBACK15 for 15% off!

Ready to complete your order? 👉 {cart_link}"
```

**场景 F：大客户/B2B 询价**

```
"Thanks for your interest in our products, {first_name}! 🤝

For bulk / wholesale orders (50+ units), we offer:
- Tiered pricing (the more you order, the more you save)
- Custom packaging options
- Dedicated account manager
- Flexible payment terms

Could you share:
1. Which product(s) are you interested in?
2. Estimated quantity?
3. Shipping destination?

I'll prepare a custom quote for you! 📋"
```

#### 3.4.3 Instagram DM 自动化策略

| 触发条件 | 自动化动作 |
|----------|-----------|
| 新关注 | 发送欢迎消息（延迟 1-5 分钟，避免像机器人） |
| 评论关键词（如 "link" "price" "how much"） | 自动回复相关链接或引导至 DM |
| Story Reply | 自动回复引导至商品页或 DM 深入沟通 |
| 私信关键词 | 路由到不同话术模板（"order" → 订单查询，"return" → 退换货流程） |
| 购物车放弃 | 24h 后自动发送挽回 DM |

#### 3.4.4 DM 注意事项

- **温度感优先：** 即使是模板回复，也要有个性化元素（称呼、引用对方的话）
- **避免过度营销：** DM 不是广告位，价值 > 推销的比例应 ≥ 7:3
- **Story 互动：** 定期发互动 Story（Poll / Question / Quiz），增加触达
- **Close Friends List：** 维护 VIP 客户的 Close Friends List，发专属 Story
- **合规：** Instagram 对自动 DM 有频率限制，避免被标记为 spam

---

## 4. 内容目录结构 Content Directory Structure

所有私域运营相关文件存储在 `[VAULT_ROOT]/30-flow/20-私域运营/` 下：

```
30-flow/20-私域运营/
├── 00-内容日历/
│   ├── content-calendar.md          # 总内容日历（所有渠道汇总）
│   ├── 2026-WXX-plan.md             # 当周内容计划
│   └── monthly-themes.md            # 月度主题规划
│
├── 01-WhatsApp/
│   ├── status-ideas.md              # Status 内容灵感库
│   ├── broadcast-templates.md       # Broadcast 话术模板
│   ├── quick-replies.md             # Quick Reply 模板库
│   ├── catalog-notes.md             # 商品目录维护备注
│   └── campaign-log.md              # 发送记录与效果追踪
│
├── 02-Email-Newsletter/
│   ├── newsletter-calendar.md       # Newsletter 排期
│   ├── subscriber-segments.md       # 用户分层定义与标签
│   ├── subject-line-swipe-file.md   # 优秀 Subject Line 积累
│   ├── email-templates/             # 邮件模板
│   │   ├── welcome-series-1.md
│   │   ├── welcome-series-2.md
│   │   ├── weekly-roundup-template.md
│   │   ├── product-deep-dive-template.md
│   │   └── seasonal-promo-template.md
│   └── campaign-log.md              # 发送记录与效果追踪
│
├── 03-Facebook-Group/
│   ├── group-rules.md               # 群规公告
│   ├── pinned-post-template.md      # 每周置顶帖模板
│   ├── engagement-ideas.md          # 互动灵感库
│   ├── member-milestones.md         # 成员里程碑记录
│   ├── ama-questions-log.md         # AMA 问题收集
│   └── campaign-log.md              # 发帖记录与效果追踪
│
├── 04-Instagram-DM/
│   ├── dm-templates.md              # DM 话术模板库
│   ├── automation-flows.md          # 自动化流程配置
│   ├── faq-responses.md             # 常见问题回复库
│   ├── story-ideas.md               # Story 内容灵感
│   └── campaign-log.md              # DM 记录与效果追踪
│
├── 05-数据分析/
│   ├── weekly-report-template.md    # 周报模板
│   ├── kpi-dashboard.md             # 核心指标看板
│   └── monthly-review.md            # 月度复盘
│
└── 06-参考资料/
    ├── competitor-newsletter-swipe.md   # 竞品 Newsletter 拆解
    ├── subject-line-formulas.md         # Subject Line 公式库
    ├── cta-best-practices.md            # CTA 最佳实践
    └── compliance-checklist.md          # 合规检查清单
```

---

## 5. 时区感知排期 Timezone-Aware Scheduling

### 5.1 核心原则

1. **一切以目标市场本地时间为准**，而非运营者所在地时间
2. **UTC 时间标注**：所有排期文件使用 UTC 标注，同时备注目标市场本地时间
3. **多时区覆盖**：如果客户覆盖多个时区，选择最大客群所在时区为主时间，其他时区适当补发

### 5.2 各市场推荐时间表

| 目标市场 | 时区 | Email 最佳时间 | WhatsApp Status 最佳时间 | FB Group 最佳时间 |
|---------|------|---------------|------------------------|------------------|
| 🇺🇸 美东 | EST (UTC-5) | Tue/Thu 9:00 AM | 8:00 AM / 12:30 PM / 7:00 PM | Tue-Thu 10:00 AM / 7:00 PM |
| 🇺🇸 美西 | PST (UTC-8) | Tue/Thu 9:00 AM | 8:00 AM / 12:30 PM / 7:00 PM | Tue-Thu 10:00 AM / 7:00 PM |
| 🇬🇧 英国 | GMT (UTC+0) | Tue/Thu 9:00 AM | 8:30 AM / 1:00 PM / 6:30 PM | Tue-Thu 10:00 AM / 7:00 PM |
| 🇩🇪 德国/中欧 | CET (UTC+1) | Tue/Thu 9:00 AM | 8:30 AM / 1:00 PM / 6:30 PM | Tue-Thu 10:00 AM / 7:00 PM |
| 🇦🇪 中东 | GST (UTC+4) | Sun/Wed 10:00 AM | 9:00 AM / 2:00 PM / 8:00 PM | Sun-Wed 11:00 AM / 7:00 PM |
| 🇦🇺 澳洲 | AEST (UTC+10) | Tue/Thu 9:00 AM | 8:00 AM / 12:30 PM / 7:00 PM | Tue-Thu 10:00 AM / 7:00 PM |
| 🇧🇷 巴西 | BRT (UTC-3) | Tue/Thu 9:00 AM | 8:00 AM / 12:30 PM / 7:00 PM | Tue-Thu 10:00 AM / 7:00 PM |

### 5.3 多时区策略

```
场景：品牌同时覆盖美国和欧洲

Email Newsletter:
  → 选择欧洲时间周二 9:00 AM CET = 美东凌晨 3:00 AM（美国用户醒来看到邮件）
  → 或分两次发送：欧洲版 + 美国版（不同 Subject Line，相同核心内容）

WhatsApp Status:
  → 24h 有效期，无需担心时区。发布 2-3 次覆盖不同活跃时段即可

FB Group Post:
  → 发 1 次即可，Facebook 算法会在用户活跃时段推送
  → 可选择欧洲/美国重叠活跃时段：欧洲下午 = 美国上午

Instagram DM (主动):
  → 分时段处理：先回复欧洲客户（欧洲白天 = 美国深夜）
  → 再处理美国客户（美国白天时段）
```

### 5.4 特殊日期排期

| 节日/节点 | 市场 | 提前预热时间 | 内容重点 |
|-----------|------|-------------|---------|
| Valentine's Day (Feb 14) | 全球 | 提前 2 周 | Gift Guide, Romantic Bundle |
| Ramadan / Eid | 中东/东南亚 | 提前 2-3 周 | Festival Greetings, Gift Sets, Respect cultural tone |
| Mother's Day (May) | 美/欧(3月) | 提前 3 周 | Emotional content, Gift bundles |
| Prime Day (Jul) | 全球(亚马逊) | 提前 1 周 | Price matching, Alternative deals |
| Back to School (Aug-Sep) | 美/欧 | 提前 2 周 | Kids/Student collections |
| Black Friday / Cyber Monday | 全球 | 提前 2-3 周 | Biggest deals, Countdown, FOMO |
| Christmas / Holiday Season | 全球 | 提前 3-4 周 | Gift Guide, Shipping deadlines, Last-minute deals |
| Chinese New Year | 全球(华人) | 提前 2 周 | 可选：如果目标客群包含海外华人 |

---

## 6. 数据周报 Weekly Data Report

### 6.1 周报结构

每周一生成上周数据报告，存入 `[VAULT_ROOT]/30-flow/20-私域运营/05-数据分析/weekly-report-template.md`

```markdown
# Private Domain Weekly Report
**Period:** [Start Date] — [End Date]

## 📊 Executive Summary
- 本周核心亮点（1-2 句话）
- 需要关注的问题（1-2 句话）

## WhatsApp Business
| Metric | This Week | Last Week | WoW Change |
|--------|-----------|-----------|------------|
| New Contacts Added | | | |
| Broadcast Sent (Count) | | | |
| Broadcast Open Rate | | | |
| Broadcast Reply Rate | | | |
| Status Views (Avg) | | | |
| DM Conversations | | | |
| Orders from WhatsApp | | | |
| Revenue from WhatsApp | | | |

## Email Newsletter
| Metric | This Week | Last Week | WoW Change |
|--------|-----------|-----------|------------|
| Total Subscribers | | | |
| New Subscribers | | | |
| Unsubscribes | | | |
| Emails Sent | | | |
| Open Rate | | | |
| Click Rate (CTR) | | | |
| Click-to-Open Rate (CTOR) | | | |
| Revenue from Email | | | |
| Top Performing Subject Line | | | |
| Top Performing CTA | | | |

## Facebook Group
| Metric | This Week | Last Week | WoW Change |
|--------|-----------|-----------|------------|
| Total Members | | | |
| New Members | | | |
| Posts Published | | | |
| Comments / Replies | | | |
| Reactions | | | |
| Engagement Rate | | | |
| Top Post (by engagement) | | | |

## Instagram DM
| Metric | This Week | Last Week | WoW Change |
|--------|-----------|-----------|------------|
| DM Conversations | | | |
| Average Response Time | | | |
| New Followers | | | |
| Story Views (Avg) | | | |
| Orders from IG | | | |
| Revenue from IG | | | |

## 📈 Insights & Action Items
1. [Insight] → [Action]
2. [Insight] → [Action]
3. [Insight] → [Action]

## 🎯 Next Week Plan
- [ ] Content 1: [Channel] [Type] [Scheduled Time]
- [ ] Content 2: [Channel] [Type] [Scheduled Time]
- [ ] Content 3: [Channel] [Type] [Scheduled Time]
- [ ] Focus: [This week's priority]
```

### 6.2 核心 KPI 基准线 Benchmarks

| 渠道 | 指标 | 健康范围 | 优秀 |
|------|------|---------|------|
| WhatsApp Broadcast | Reply Rate | 5-15% | > 20% |
| WhatsApp Broadcast | Open Rate | 50-70% | > 75% |
| Email Newsletter | Open Rate | 20-30% | > 35% |
| Email Newsletter | CTR | 2-5% | > 6% |
| Email Newsletter | Unsubscribe Rate | < 0.5% | < 0.2% |
| FB Group | Engagement Rate | 3-7% | > 10% |
| FB Group | Weekly Active Members | 10-20% | > 30% |
| IG DM | Response Time | < 4h | < 1h |
| IG Story | View Rate (Views/Followers) | 5-15% | > 20% |

---

## 7. 常见陷阱与避坑指南 Pitfalls & Common Mistakes

### 7.1 WhatsApp Business 坑

| ❌ 坑 | ✅ 正确做法 |
|--------|-----------|
| 用 Personal WhatsApp 发业务消息 | 使用 WhatsApp Business App（免费）或 WhatsApp Business API |
| 对未 opt-in 的号码发送 Broadcast | 只对主动联系或明确同意的用户发送 |
| 忽视 24h 消息窗口规则 | 用户最后一条消息起 24h 内可自由发送；超时需用 Message Template |
| Broadcast 发长篇大论 | 控制在 150 词以内，图片 + 短文案 + CTA |
| Status 全是广告 | 7:3 原则：70% 价值/幕后/生活 + 30% 推广 |
| 不维护 Catalog | 保持 Catalog 更新，方便客户直接在 WhatsApp 内浏览下单 |

### 7.2 Email Newsletter 坑

| ❌ 坑 | ✅ 正确做法 |
|--------|-----------|
| 购买邮箱列表 | 只使用 organic opt-in 列表 |
| Subject Line 全大写 + emoji 过多 | 最多 1 个 emoji，正常大小写 |
| 没有 Unsubscribe 链接 | 每封邮件必须包含，否则违规 |
| 频率不稳定（想起来才发） | 固定频率，建立期待感 |
| 一封邮件多个 CTA | 每封邮件聚焦 1 个核心 CTA |
| 发送前不测试 | 必须发送测试邮件，检查在 Gmail / Outlook / Mobile 的显示效果 |
| 忽视移动端 | 60%+ 邮件在手机打开，确保 mobile-friendly |
| 不做 A/B 测试 | 定期测试 Subject Line、CTA 文案、发送时间 |

### 7.3 Facebook Group 坑

| ❌ 坑 | ✅ 正确做法 |
|--------|-----------|
| 建群后不运营（变成僵尸群） | 至少每天 1 次互动，每周 3-5 条内容 |
| 允许成员随意打广告 | 制定清晰群规，及时删除 spam |
| 只有官方内容（无 UGC） | 鼓励成员分享，定期做 UGC 活动 |
| 不回复成员问题 | 目标 < 4h 响应，维护信任感 |
| 一次性大量拉人 | 自然增长为主，Quality > Quantity |
| 群名过于宽泛 | 垂直精准定位，如 "[Brand] | [Niche] Community" |

### 7.4 Instagram DM 坑

| ❌ 坑 | ✅ 正确做法 |
|--------|-----------|
| DM 里发长篇推销 | DM 保持简短（< 100 词），引导至链接 |
| 机器人感太强（无个性化） | 即使模板也加入 {first_name} 和上下文 |
| 响应太慢 | 工作时段 < 1h，设置自动回复告知响应时间 |
| 过度自动化 | 核心互动保留人工，自动化用于初步分流 |
| 把 DM 当广告位 | 价值 > 推销，7:3 原则 |
| 不利用 Story 互动 | 定期发 Poll / Question / Quiz Story，增加触达与互动 |

### 7.5 通用跨文化坑

| ❌ 坑 | ✅ 正确做法 |
|--------|-----------|
| 直译中文内容到英文 | 用 native speaker 思维重写，语感自然 |
| 不了解目标市场节日 | 提前规划当地重要节日（如美国 Thanksgiving、中东 Ramadan） |
| 颜色/符号文化差异 | 了解目标市场文化禁忌（如中东避免某些手势 emoji） |
| 忽视 GDPR 合规 | 欧洲客户必须 Double Opt-in，提供数据删除选项 |
| 定价不包含当地税费/VAT | 明确标示是否含税，避免售后纠纷 |
| 忽视当地物流习惯 | 不同市场有不同的物流期望（如美国习惯 3-5 天，中东可能接受 7-14 天） |

---

## 8. 进阶策略 Advanced Strategies

### 8.1 全渠道协同 Cross-Channel Synergy

```
典型协同场景：

1️⃣ 新品发布
   Day 1: Email → 品牌故事 + 新品预告（预热）
   Day 2: WhatsApp Status → 新品实拍/开箱视频
   Day 3: FB Group → 新品讨论帖 + Member Exclusive 早鸟价
   Day 4: IG Story → 投票 "Which one is your favorite?"
   Day 5: Email → 正式上线 + Exclusive Discount Code
   Day 7: WhatsApp Broadcast → 限时 48h 追加优惠

2️⃣ 大促活动（Black Friday 等）
   D-14: Email → Save the Date
   D-7: FB Group → 预热讨论 + Wish List 征集
   D-3: WhatsApp Status → 每日倒计时
   D-Day: 全渠道同步爆发
   D+1: Email → 销量捷报 + FOMO
   D+3: WhatsApp Broadcast → Last Chance 提醒
```

### 8.2 客户生命周期自动化 Customer Lifecycle Automation

```
New Lead (未购买)
  │ Welcome Email Series (Day 0, 3, 7)
  │ WhatsApp Broadcast: 介绍品牌 + Bestseller
  │ IG: 自动欢迎 DM
  ▼
First Purchase
  │ Email: Order Confirmation + Thank You
  │ WhatsApp: 订单更新 + 物流通知
  │ IG: 感谢 Story Tag
  ▼
Post-Purchase (Day 7-14)
  │ Email: Product Review Request
  │ WhatsApp: 使用满意度跟进
  │ IG: 主动 DM 跟进
  ▼
Repeat Customer
  │ Email: 加入 VIP Segment
  │ FB Group: 邀请加入 VIP Community
  │ WhatsApp: VIP Broadcast（专属优惠）
  ▼
Brand Advocate
  │ Referral Program 邀请
  │ UGC 合作
  │ 社群 Moderator 邀请
```

### 8.3 内容复用策略 Content Repurposing

```
一篇核心内容 → 多渠道分发：

Email Newsletter 长文 (1000字)
  │
  ├→ WhatsApp Status: 提取核心观点 → 1张图文卡片 (≤80词)
  ├→ FB Group Post: 简化版 + 引导讨论问题 (200词)
  ├→ IG Story: 3-5 页 Swipe 精华总结
  └→ IG DM: 私信核心链接给 VIP 客户

反之：
WhatsApp Status 热门内容
  │
  └→ 展开为 Email Newsletter 深度文章
```

---

## 9. 工具推荐 Tool Recommendations

| 用途 | 推荐工具 | 备注 |
|------|---------|------|
| WhatsApp Business | WhatsApp Business App / WATI / Trengo | App 免费；API 付费，适合大volume |
| Email Marketing | Klaviyo (电商首选) / Mailchimp / Omnisend / Brevo | Klaviyo 与 Shopify 深度集成 |
| Facebook Group | Facebook Groups (原生) / Metisa (社群CRM) | 原生功能已足够 |
| Instagram DM | ManyChat / Chatfuel / 原生 DM | ManyChat 自动化功能最强 |
| 内容日历 | Notion / Trello / Google Sheets | 选择团队习惯的工具 |
| 数据分析 | 各平台原生 Analytics + Google Sheets 周报 | 统一模板便于对比 |
| 图片设计 | Canva / Figma | 维护品牌模板，提高效率 |
| 视频编辑 | CapCut / InShot | 手机端快速出片 |
| 时区转换 | TimeAndDate.com / World Time Buddy | 排期必备 |

---

## 10. 快速启动检查清单 Quick Start Checklist

- [ ] 定义品牌风格卡（Tone, 禁用词, Emoji 规范）
- [ ] 确认目标市场与核心时区
- [ ] 创建 WhatsApp Business Profile（头像、简介、Catalog）
- [ ] 设置 Email Marketing 平台 + 导入现有列表
- [ ] 创建/优化 Facebook Group（群名、群规、封面图、置顶帖）
- [ ] 配置 Instagram DM 自动化（欢迎消息 + 关键词回复）
- [ ] 创建用户分层标签体系
- [ ] 制作各渠道内容模板（首月内容排期）
- [ ] 建立内容日历文件
- [ ] 设置周报模板
- [ ] 执行第一周内容计划
- [ ] 第一周末完成首次数据周报
