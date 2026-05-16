---
name: "海外客户关系管理 (Overseas CRM)"
description: "跨境电商/外贸客户全生命周期管理技能。管理海外客户从线索到成交的全流程，涵盖 WhatsApp/Email/LinkedIn 等海外沟通渠道，支持 B2B/B2C 双模式、多币种、时区感知的跟单提醒、物流追踪及外贸单证管理。"
trigger:
  - "新建客户|新建线索|new lead|new customer|create lead"
  - "跟单|跟进|follow up|follow-up"
  - "报价|quotation|quote"
  - "客户分级|客户分类|customer segmentation"
  - "成交|close deal|closed won"
  - "丢单|lost deal|closed lost"
  - "PI|proforma invoice|商业发票|packing list"
  - "客户归档|archive customer"
  - "物流追踪|shipping track|logistics"
  - "时区|timezone"
---

# 海外客户关系管理 (Overseas CRM)

> 本技能适用于跨境电商与外贸从业者，替代国内微信 + CRM 模式，基于 WhatsApp、Email、LinkedIn、Zoom 等海外主流沟通渠道，实现海外客户的全生命周期管理。

---

## 1. 总体工作流

```
理解业务需求 → 新建线索卡片 → 跟进记录 → 推进状态 → 成交/归档 → 售后复购
```

### 1.1 核心原则

- **一切客户资产沉淀在 Vault 中**：每个客户一张卡片，所有沟通记录、报价单、合同均以笔记形式关联
- **渠道统一管理**：WhatsApp、Email、LinkedIn、Phone 等沟通记录统一汇总到客户卡片
- **时区感知**：所有跟单提醒基于客户当地时间，避免打扰客户休息时间
- **B2B/B2C 区分**：根据客户类型自动适配不同工作流和文档模板
- **多币种支持**：报价和交易金额标注币种（USD/EUR/GBP 或本地货币）

---

## 2. 线索卡片模板 (Lead Card Template)

当用户说"新建客户""new lead"等触发词时，使用以下模板创建客户卡片：

```markdown
---
contact:
  name: ""
  company: ""
  email: ""
  whatsapp: ""
  country: ""
  timezone: ""
  language: ""       # English / Spanish / Arabic / French / Portuguese / etc
  linkedin: ""
  phone: ""
  notes: ""

business:
  type: ""           # B2B / B2C
  deal_size: ""      # estimated USD
  currency: ""       # USD / EUR / GBP / local
  payment_method: "" # PayPal / Stripe / Bank Transfer / Western Union
  shipping_method: "" # DHL / FedEx / UPS / EMS / Sea freight / Air freight
  product_interest: ""
  source: ""         # Alibaba / LinkedIn / Trade show / Referral / Google Ads / Organic / etc

status:
  stage: "New Lead"  # New Lead → Following Up → Intent Confirmed → Quoting → Negotiation → Closed Won / Closed Lost
  grade: ""          # A / B / C / D
  created_date: ""
  last_contact_date: ""
  next_follow_up: ""
  next_follow_up_timezone: ""

tags:
  - "客户"
  - ""
---

# {{contact.name}} — {{contact.company}}

## 客户概要

| 字段 | 信息 |
|------|------|
| 国家/地区 | {{contact.country}} |
| 时区 | {{contact.timezone}} |
| 语言 | {{contact.language}} |
| 客户类型 | {{business.type}} |
| 预估金额 | {{business.currency}} {{business.deal_size}} |
| 来源渠道 | {{business.source}} |
| 当前阶段 | {{status.stage}} |
| 客户分级 | {{status.grade}} |

## 沟通渠道

- **WhatsApp**: {{contact.whatsapp}}
- **Email**: {{contact.email}}
- **LinkedIn**: {{contact.linkedin}}
- **Phone**: {{contact.phone}}

## 跟进记录

### {{date}} — {{channel}}
- 内容：
- 下一步：
- 跟单提醒：{{next_follow_up}} ({{contact.timezone}})

## 报价与文档

| 文档类型 | 日期 | 金额 | 文件链接 |
|----------|------|------|----------|
| Quotation | | | |
| PI (Proforma Invoice) | | | |
| Commercial Invoice | | | |
| Packing List | | | |
| Contract | | | |

## 物流追踪

| 订单号 | 物流方式 | 快递单号 | 状态 | 预计到达 |
|--------|----------|----------|------|----------|
| | | | | |

## 备注

{{contact.notes}}
```

### 2.1 创建规则

1. **必填字段**：`name`、`country`、`type`（B2B/B2C）、`source`
2. **尽量补全**：`email`、`whatsapp`、`timezone`、`language`
3. **自动推断**：根据国家自动建议 timezone 和常用语言
4. **文件命名**：`{状态emoji}{{name}}-{{company}}.md`，存放在 `[VAULT_ROOT]/30-flow/30-CRM/10-线索管理/` 目录下（与国内版统一）
5. **自动标签**：添加"客户"标签 + 国家/地区标签 + 业务类型标签（B2B/B2C）

---

## 3. 客户状态流转 (Status Flow)

```
┌─────────────┐
│  New Lead    │  新线索入库
└──────┬──────┘
       ▼
┌─────────────┐
│ Following Up │  初次联系/多次触达
└──────┬──────┘
       ▼
┌─────────────────┐
│ Intent Confirmed │  客户明确表达采购意向
└──────┬──────────┘
       ▼
┌─────────────┐
│   Quoting    │  发送报价单/PI
└──────┬──────┘
       ▼
┌──────────────┐
│ Negotiation  │  价格/条款/付款方式协商
└──────┬───────┘
       ▼
  ┌────────────────┐
  │                │
┌─▼────────┐  ┌───▼──────────┐
│Closed Won│  │  Closed Lost  │
└──────────┘  └──────────────┘
```

### 3.1 各阶段定义

| 阶段 | 英文 | 定义 | 典型操作 | B2B 额外操作 |
|------|------|------|----------|-------------|
| 新线索 | New Lead | 获取客户信息，尚未主动联系 | 查阅公司背景、LinkedIn profile | 研究公司规模、采购历史 |
| 跟进中 | Following Up | 已联系，等待回复或持续沟通 | WhatsApp/Email/LinkedIn 跟进 | 发送产品目录、公司介绍 |
| 意向确认 | Intent Confirmed | 客户明确表达采购兴趣 | 确认需求细节、数量、规格 | 安排 Zoom/Google Meet 视频会议 |
| 报价中 | Quoting | 已发送报价单或 PI | 跟进报价反馈 | PI + 合同签署流程 |
| 谈判中 | Negotiation | 就价格/条款/交期进行协商 | 调整报价、确认付款方式 | MOQ、交期、质保条款谈判 |
| 成交 | Closed Won | 客户已付款/下单 | 创建订单、安排发货 | 签署合同、生产排期 |
| 丢单 | Closed Lost | 客户明确拒绝或失联 | 记录原因、设置未来回访 | 分析竞品原因、关系维护 |

### 3.2 阶段推进规则

- 每次状态变更必须**记录原因和时间**
- 从 Quoting 到 Negotiation 需确认**客户已收到并审阅报价**
- Closed Won 必须关联**付款记录**
- Closed Lost 必须记录**丢单原因**（price / competitor / no response / budget / timing / other）

---

## 4. 客户分级 (Customer Segmentation)

### 4.1 分级标准（国际版）

| 等级 | 标准 | 跟进频率 | 响应时间 | 策略 |
|------|------|----------|----------|------|
| **A** | 大客户：年采购额 >$50K 或单笔 >$10K；行业头部企业；已合作客户 | 每周 1-2 次 | 2h 内 | 1v1 专属服务；定期 Zoom meeting；优先排产；提供定制方案 |
| **B** | 中等客户：年采购额 $10K-$50K；明确需求；有决策权 | 每周 1 次 | 6h 内 | 主动推荐新品；提供阶梯报价；安排季度回访 |
| **C** | 小客户：年采购额 <$10K；需求明确但量小；可能成长 | 每 2 周 1 次 | 12h 内 | 标准化服务；引导线上下单；节日问候维护 |
| **D** | 潜在/无效：询价后无回复；信息不全；需求不匹配 | 每月 1 次 | 24h 内 | 批量邮件营销；节日触达；低成本维护 |

### 4.2 分级自动评估

根据以下维度综合评分（每项 1-5 分）：

1. **采购能力**（company size, annual revenue, industry）
2. **需求匹配度**（product fit, specification match）
3. **沟通响应度**（reply speed, engagement level）
4. **决策权**（purchasing manager / owner / end user）
5. **付款能力**（payment history, country risk）

> A级: 20-25分 | B级: 15-19分 | C级: 10-14分 | D级: <10分

### 4.3 升降级规则

- **升级**：连续 2 次跟进有积极反馈 → 考虑升级
- **降级**：连续 30 天无回复 → 自动降一级；60 天无回复 → 降至 D 级
- **A 客户保护**：A级客户不会因短期无回复自动降级

---

## 5. 时区感知的跟单管理 (Timezone-Aware Follow-up)

### 5.1 时区数据库

常用市场时区参考：

| 国家/地区 | 时区 (UTC) | 最佳联系时间 (当地时间) | 最佳联系时间 (北京时间) |
|-----------|-----------|----------------------|----------------------|
| 美国 (东部) | UTC-5 | 09:00-17:00 | 21:00-05:00(+1) |
| 美国 (西部) | UTC-8 | 09:00-17:00 | 00:00-08:00(+1) |
| 英国 | UTC+0 | 09:00-17:00 | 17:00-01:00(+1) |
| 德国/法国 | UTC+1 | 09:00-17:00 | 16:00-00:00(+1) |
| 阿联酋/沙特 | UTC+4 | 09:00-17:00 | 13:00-21:00 |
| 印度 | UTC+5:30 | 10:00-18:00 | 12:30-20:30 |
| 东南亚 (印尼/泰国) | UTC+7 | 09:00-17:00 | 09:00-17:00 |
| 澳大利亚 (东部) | UTC+10 | 09:00-17:00 | 07:00-15:00 |
| 巴西 | UTC-3 | 09:00-17:00 | 20:00-04:00(+1) |
| 尼日利亚 | UTC+1 | 09:00-17:00 | 16:00-00:00(+1) |
| 墨西哥 | UTC-6 | 09:00-17:00 | 21:00-05:00(+1) |

### 5.2 跟单提醒规则

- **提醒时间**：自动转换为客户当地工作时间（09:00-17:00）
- **提前量**：提前 30 分钟（北京时间）发出提醒
- **显示格式**：`⏰ 跟进提醒: John Smith (UTC-5, New York) — 建议北京时间 21:00-05:00 联系`
- **跨日提醒**：如果联系时间跨越北京时间的日期，明确标注"明天"

### 5.3 跟单间隔建议

| 客户分级 | 首次跟进 | 第2次 | 第3次 | 第4次 | 第5次 |
|----------|---------|-------|-------|-------|-------|
| A | 24h | 3天 | 5天 | 7天 | 10天 |
| B | 24h | 3天 | 7天 | 14天 | 21天 |
| C | 48h | 5天 | 14天 | 21天 | 30天 |
| D | 72h | 7天 | 21天 | 30天 | 60天 |

---

## 6. 跟进建议生成 (Follow-up Suggestion Engine)

### 6.1 基于销售方法论的建议

根据客户当前阶段和跟进次数，自动生成个性化的跟进策略建议：

#### 🔄 New Lead → Following Up

**第 1 次跟进（初次接触）**：
> 建议渠道：WhatsApp / Email
> 
> **WhatsApp**："Hi [Name], this is [Your Name] from [Company]. I noticed you're looking for [product category]. We've been supplying to [country/region] for [X] years. Would you like me to send our latest catalog?"
> 
> **Email**：专业格式，附公司介绍 PDF + 产品目录，Subject line 需包含客户关注的产品关键词
> 
> **LinkedIn**：先建立连接，发送简短 message 介绍公司

**第 2 次跟进（未回复）**：
> 建议渠道：切换到未使用的渠道（如 WhatsApp 未回则尝试 Email）
> 
> **内容方向**：分享行业洞察 / 客户案例 / 新品信息，避免重复催促

**第 3 次跟进（仍未回复）**：
> 建议渠道：Email
> 
> **内容方向**：限时优惠 / 免费样品方案 / 行业报告白皮书作为价值交换

#### 🔄 Following Up → Intent Confirmed

**客户表现出兴趣时**：
> 1. 确认具体需求：产品规格、数量、MOQ、交期
> 2. 了解客户背景：采购频率、当前供应商、痛点
> 3. B2B 客户：建议安排 Zoom/Google Meet 视频会议
> 4. B2C 客户：引导至线上店铺或直接报价

**WhatsApp 确认模板**：
> "Great to hear from you, [Name]! To prepare the best quote for you, could you please share:
> 1. Required specifications (size, color, material)?
> 2. Estimated quantity?
> 3. Any specific delivery deadline?
> 
> If it's convenient, I'd love to have a quick 10-min call on Zoom to discuss in detail."

#### 🔄 Intent Confirmed → Quoting

**报价单要素**：
> - 报价有效期（通常 30 天）
> - EXW / FOB / CIF / DDP 等贸易术语明确标注
> - 包含包装规格、毛重、净重、体积
> - 付款条件（T/T, PayPal, etc）
> - 交货期（production lead time）
> - PI 编号和日期

**B2B 特有**：需要同时准备 PI（Proforma Invoice）供客户用于外汇付款申请

**B2C 特有**：直接发送带付款链接的报价单（Stripe / PayPal invoice）

#### 🔄 Quoting → Negotiation

**常见谈判策略**：

| 客户异议 | 应对策略 | WhatsApp/Email 话术要点 |
|---------|---------|------------------------|
| "Your price is too high" | 突出价值差异 | 强调质量认证、质保、售后服务、对比方案 |
| "Competitor offers lower" | 差异化竞争 | 对比细节（材质、工艺、包装、认证） |
| "Can you do a smaller MOQ?" | 弹性方案 | 提供 trial order 方案 + 加价说明 |
| "We need better payment terms" | 灵活付款 | 分期付款方案：30% deposit + 70% before shipment |
| "Delivery is too long" | 加急方案 | 部分发货 / 加急排产 / 现货优先 |

#### 🔄 Negotiation → Closed Won

**B2B 成交流程**：
1. 确认最终价格和条款 → 更新 PI
2. 客户签字/回签 PI 或合同
3. 收到 deposit（电汇通常 3-5 个工作日到账）
4. 安排生产 → 定期更新进度
5. 生产完成 → 发送产品照片/视频确认
6. 收到 balance → 安排发货
7. 提供物流单号 → 跟踪到货
8. 到货后跟进 → 收集反馈 → 售后服务

**B2C 成交流程**：
1. 确认订单详情
2. 发送 PayPal/Stripe 付款链接
3. 收到付款 → 安排发货
4. 提供物流追踪号
5. 到货后请求评价/反馈

### 6.2 节日营销日历

利用国际节日进行友好触达（非硬性推销）：

| 月份 | 节日 | 适用市场 | 建议动作 |
|------|------|----------|---------|
| 1月 | New Year | 全球 | 新年问候 + 年度新品预告 |
| 2月 | Eid al-Fitr | 中东/东南亚 | 节日问候（注意日期每年不同） |
| 3月 | Holi | 印度 | 彩色节问候 |
| 4月 | Easter | 欧美 | 节日问候 |
| 5月 | Eid al-Adha | 中东/非洲 | 节日问候（注意日期每年不同） |
| 7月 | Independence Day | 美国（7/4）| 促销活动 |
| 8月 | National Day | 各国不同 | 客户所在国国庆问候 |
| 9月 | Diwali | 印度 | 提前备货提醒 |
| 10月 | Halloween | 北美 | 促销活动 |
| 11月 | Black Friday | 全球 | 大促活动 |
| 12月 | Christmas | 全球 | 节日问候 + 年度回顾 |

> ⚠️ 注意：发送节日问候前确认客户的宗教和文化背景，避免冒犯。

---

## 7. B2B vs B2C 工作流对比

| 维度 | B2B (企业客户) | B2C (终端消费者) |
|------|---------------|-----------------|
| **典型周期** | 2周 - 6个月 | 1天 - 2周 |
| **决策人** | 采购经理/老板 | 个人 |
| **沟通渠道** | Email → Zoom → WhatsApp | WhatsApp → Email |
| **报价方式** | PI (Proforma Invoice) + 合同 | PayPal/Stripe Invoice / 线上商城 |
| **付款方式** | T/T (30/70)、L/C | PayPal、Stripe、信用卡 |
| **单据需求** | PI、合同、商业发票、装箱单 | 简化发票、物流追踪 |
| **MOQ** | 通常有最低起订量 | 通常无或很低 |
| **售后** | 质保、返修、长期合作 | 退换货政策 |
| **复购频率** | 高（定期采购） | 中等（取决于产品） |
| **关键文档** | PI / Contract / Commercial Invoice / Packing List / BL / CO | Invoice / Tracking Number |

---

## 8. 付款方式管理 (Payment Methods)

### 8.1 付款方式对比

| 方式 | 适用场景 | 手续费 | 到账时间 | 风险等级 | 备注 |
|------|---------|--------|---------|---------|------|
| **T/T (电汇)** | B2B 大额 | $20-50 (中间行) | 3-5 工作日 | 低 | 最常用，需提供 SWIFT Code |
| **PayPal** | B2C 小额 | 2.9% + $0.30 | 即时 | 中 | 客户信任度高，有买家保护 |
| **Stripe** | B2C 线上 | 2.9% + $0.30 | 即时 | 中 | 需要技术对接，适合商城 |
| **Western Union** | 非洲/中东/拉美 | 按金额浮动 | 即时-1天 | 中 | 某些国家/地区唯一选择 |
| **L/C (信用证)** | B2B 大额大单 | 银行费用 | 严格按条款 | 低 | 银行信用背书，但流程复杂 |
| **阿里巴巴信保** | 阿里巴巴平台 | 订单金额 0.5%+ | 按平台规则 | 低 | 平台担保交易 |

### 8.2 付款条款建议

| 客户类型 | 建议条款 | 说明 |
|---------|---------|------|
| 新客户 B2B | 30% deposit + 70% before shipment | 标准条款 |
| 信任老客户 B2B | 30% deposit + 70% after BL copy | 体现信任 |
| 大客户 B2B | L/C at sight 或 O/A 30天 | 需评估信用 |
| B2C | 100% prepayment | PayPal / Stripe 全额 |
| B2C 退货 | 退款至原支付方式 | 7-14 个工作日 |

---

## 9. 物流与追踪 (Shipping & Logistics)

### 9.1 物流方式选择

| 方式 | 时效 | 适用场景 | 追踪 | 备注 |
|------|------|---------|------|------|
| **DHL Express** | 3-7天 | 急件、高价值 | 完整 | 价格高，服务好 |
| **FedEx** | 3-7天 | 北美市场 | 完整 | 北美线路优势 |
| **UPS** | 3-7天 | 欧美市场 | 完整 | 欧美线路优势 |
| **TNT** | 5-10天 | 欧洲/中东 | 完整 | 欧洲线路优势 |
| **EMS** | 7-15天 | 低预算 | 部分 | 清关能力强，部分国家免关税额度高 |
| **空运 (Air Freight)** | 5-10天 | 大批量紧急 | 部分 | 100kg+ 更经济 |
| **海运 (Sea Freight)** | 20-45天 | 大批量不急 | 部分 | 最经济，适合 >1CBM |
| **专线 (Special Line)** | 7-20天 | 特定国家 | 部分 | 如中东专线、俄罗斯专线 |

### 9.2 物流追踪记录格式

```markdown
## 物流追踪

### 订单号: PO-2026-001

| 日期 | 事件 | 物流方式 | 单号 | 状态 |
|------|------|---------|------|------|
| 2026-05-10 | 付款确认 | — | — | ✅ Paid |
| 2026-05-11 | 生产排期 | — | — | 🔄 In Production |
| 2026-05-20 | 生产完成 | — | — | ✅ Ready |
| 2026-05-21 | 发货 | DHL | 1234567890 | 🚚 In Transit |
| 2026-05-25 | 到达目的地 | DHL | 1234567890 | 📦 Customs |
| 2026-05-27 | 签收 | DHL | 1234567890 | ✅ Delivered |
```

### 9.3 清关注意事项

- **商业发票 (Commercial Invoice)**：务必准确填写货物名称、HS Code、数量、单价、原产国
- **装箱单 (Packing List)**：详细列出每箱毛重、净重、尺寸
- **原产地证 (CO)**：部分市场享受关税优惠（如 Form A、Form E）
- **特殊认证**：CE（欧盟）、FDA（美国）、SASO（沙特）等

---

## 10. 外贸单证管理 (Trade Documentation)

### 10.1 核心单证清单

| 单证 | 英文 | 用途 | 何时提供 |
|------|------|------|---------|
| 形式发票 | Proforma Invoice (PI) | 供客户付款、申请外汇 | 报价确认后 |
| 商业发票 | Commercial Invoice (CI) | 清关用正式发票 | 发货时 |
| 装箱单 | Packing List (PL) | 清关 + 物流用 | 发货时 |
| 提单 | Bill of Lading (B/L) | 货权凭证 | 海运发货后 |
| 原产地证 | Certificate of Origin (CO) | 关税优惠 | 发货前申请 |
| 保险单 | Insurance Policy | 货物保险 | 按客户要求 |
| 合同 | Sales Contract | 法律保障 | B2B 成交时 |

### 10.2 PI (Proforma Invoice) 必要内容

```
PROFORMA INVOICE

PI No.: PI-2026-XXXX
Date: YYYY-MM-DD
Valid Until: YYYY-MM-DD

Seller:
  [Company Name]
  [Address]
  [Phone] | [Email]

Buyer:
  [Contact Name]
  [Company Name]
  [Address]
  [Phone] | [Email]

Payment Terms: 30% T/T deposit, 70% T/T before shipment
Delivery Terms: FOB Shenzhen / CIF [Port]
Lead Time: XX days after deposit received

| No. | Product Description | Spec | Qty | Unit Price (USD) | Amount (USD) |
|-----|-------------------|------|-----|-----------------|--------------|
| 1   |                   |      |     |                 |              |

Total Amount: USD XXXX.XX

Bank Information:
  Bank Name:
  SWIFT Code:
  Account Name:
  Account Number:

Authorized Signature: _________________
```

---

## 11. 常见陷阱与避坑指南 (Pitfalls)

### 11.1 沟通陷阱

| 陷阱 | 说明 | 避坑策略 |
|------|------|---------|
| ❌ 时区混乱 | 凌晨给美国客户发 WhatsApp | 始终查看客户 timezone，使用时区转换工具 |
| ❌ 文化冒犯 | 不了解客户宗教节日 | 维护节日日历，敏感话题（政治、宗教）避开 |
| ❌ 语言障碍 | 使用 Chinglish 或过于正式 | 保持专业简洁的 Business English，避免俚语 |
| ❌ 渠道错配 | 用 LinkedIn 发长篇报价 | Email 报价、WhatsApp 短沟通、LinkedIn 建关系 |
| ❌ 过度跟进 | 客户未回就连续轰炸 | 遵循跟进间隔表，每次提供新价值 |

### 11.2 交易陷阱

| 陷阱 | 说明 | 避坑策略 |
|------|------|---------|
| ❌ 付款未到先发货 | 信任客户口头承诺 | **款到再发货**，电汇需确认实际到账 |
| ❌ PI 金额含糊 | 未注明币种、贸易术语 | PI 明确币种 + Incoterm + 有效期 |
| ❌ 忽略目的国关税 | 报价不含税导致客户不满 | 报价注明是否含税，提前沟通清关费用 |
| ❌ 样品免费无限制 | 样品成本失控 | 样品收费或设置快递费到付，大客户可免 |
| ❌ 合同条款不清 | 口头协议无书面记录 | B2B 大单务必签署正式合同，明确条款 |

### 11.3 物流陷阱

| 陷阱 | 说明 | 避坑策略 |
|------|------|---------|
| ❌ HS Code 错误 | 清关延误或关税异常 | 与货代确认正确 HS Code |
| ❌ 低报货值 | 客户要求低报以避税 | 风险自担，建议如实申报并告知客户风险 |
| ❌ 包装不当 | 运输途中损坏 | B2B 确认包装要求，B2C 标准化包装 |
| ❌ 未确认收货地址 | 地址错误导致退回 | 发货前邮件/WhatsApp 确认完整地址 |

### 11.4 数据管理陷阱

| 陷阱 | 说明 | 避坑策略 |
|------|------|---------|
| ❌ 客户信息散落 | WhatsApp/Email/笔记本各一处 | **所有客户信息集中到 Vault 卡片** |
| ❌ 无跟进记录 | 凭记忆做事，容易遗漏 | 每次沟通后立即更新跟进记录 |
| ❌ 不分级管理 | 所有客户一视同仁 | 按分级投入不同精力，避免浪费 |
| ❌ 忽视老客户 | 只关注新客户 | 定期回访老客户，复购成本远低于获客 |

---

## 12. 快捷指令 (Quick Commands)

| 指令 | 功能 | 示例 |
|------|------|------|
| `新建客户 [姓名] [公司] [国家]` | 创建客户卡片 | `新建客户 John Smith ABC Inc. 美国` |
| `跟进 [客户名] [内容]` | 添加跟进记录 | `跟进 John Smith 已发送报价单等待回复` |
| `改状态 [客户名] [阶段]` | 更新客户状态 | `改状态 John Smith Quoting` |
| `分级 [客户名] [等级]` | 设置客户等级 | `分级 John Smith A` |
| `报价 [客户名]` | 生成报价建议 | `报价 John Smith` |
| `物流更新 [客户名] [状态]` | 更新物流信息 | `物流更新 John Smith 已发货 DHL 1234567890` |
| `下次跟进 [客户名] [日期]` | 设置跟单提醒 | `下次跟进 John Smith 2026-05-15` |
| `客户汇总` | 生成所有客户状态报表 | `客户汇总` |
| `本周任务` | 生成本周待跟进客户清单 | `本周任务` |
| `丢单分析 [客户名]` | 分析丢单原因并建议挽回 | `丢单分析 John Smith` |
