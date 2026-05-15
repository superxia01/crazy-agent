# Crazy Agent 🚀

> **一句话搭建 Obsidian 知识库 + AI Agent，专为个人 IP 和内容创业者设计。**
> **One-command Obsidian Vault setup for personal IP & content creators.**

一套为「一个人就是一家公司」设计的 Obsidian 知识库模板 + Hermes Agent 配置包。支持国内版和海外版两个市场。

---

## ✨ 这是什么？

Crazy Agent 是一个 turnkey 知识库模板，包含：

- **九层 Vault 目录结构**（60+ 子目录，30+ 引导式模板）
- **10 个 Hermes Agent Skills**（文件管理、内容运营、CRM、财务、人事、项目管理等）
- **自动化定时任务**（内容提醒、数据回收、CRM 跟进等）
- **Mock 演示数据**（5 个客户、10+ 篇内容、3 篇 wiki，即装即用）
- **国内版 / 海外版** 一键切换（平台、渠道、CRM 完全不同）

**使用 Hermes Agent**：一句话搞定全部搭建。
**不用 Hermes Agent**：纯 Obsidian 也能完整使用。

---

## 🏗️ 架构设计

```
crazy-agent/
├── README.md                    ← 你在这里
├── _shared/                     ← 📦 共享骨架（两个版本共用）
│   ├── skeleton/                ←   九层目录定义 + 命名规则 + 状态流转
│   ├── templates/               ←   共享模板（00-me / 20-wiki / 30-flow / 40-agents）
│   ├── skills/                  ←   共享 Skills（7 个）
│   └── mock-data/               ←   演示数据（可删可留）
├── _variants/
│   ├── domestic/                ← 🇨🇳 国内版差集（微信/公众号/小红书/抖音）
│   │   ├── skills/              ←   CRM / 公域流量 / 私域运营（国内版）
│   │   ├── templates/           ←   国内版模板差异
│   │   └── schedules/           ←   国内版定时任务
│   └── overseas/                ← 🌍 海外版差集（WhatsApp/Email/FB/IG/TikTok/YouTube）
│       ├── skills/              ←   CRM / 公域流量 / 私域运营（海外版）
│       ├── templates/           ←   海外版模板差异
│       └── schedules/           ←   海外版定时任务
└── skills/                      ← （兼容旧版，已迁移到 _shared/skills/）
```

### 搭建逻辑：Shared + Variant = 你的 Vault

```
_shared/（通用骨架）
    ↓ 复制到 Vault 根目录
+ _variants/domestic/ 或 _variants/overseas/（市场差集）
    ↓ 覆盖对应文件
= 完整的 Vault
```

---

## 🚀 快速开始

### 前置要求

1. [Hermes Agent](https://github.com/nousresearch/hermes-agent) 已安装并配置
2. 终端或消息平台已连接 Hermes

不需要安装 Obsidian 应用。Hermes 会直接创建一个结构化的 Markdown 知识库目录，包含 Obsidian 的 `.obsidian` 配置文件。你可以随时在其他设备上用 Obsidian 桌面版/手机版打开这个目录来浏览和编辑。

### 一键搭建

**国内版（公众号/小红书/抖音）：**
```
请访问 https://github.com/superxia01/crazy-agent 的 README，按国内版搭建指令初始化我的 Vault。
```

**海外版（FB/IG/TikTok/YouTube/WhatsApp）：**
```
请访问 https://github.com/superxia01/crazy-agent 的 README，按海外版搭建指令初始化我的 Vault。
```

Hermes Agent 会自动完成全部搭建步骤。

---

## 📐 Vault 九层架构

```
Vault Root/
├── 00-me/          🧠 Identity — 你是谁、卖什么、服务谁
│   ├── 10-定位与品牌/     IP定位、品牌风格
│   ├── 20-产品与业务/     产品清单、价格体系
│   ├── 30-目标客户/       客户画像、分层标准
│   ├── 40-账号矩阵/       平台账号、人设统一
│   └── 50-目标与节奏/     商业目标、日常节奏
├── 10-raw/         📥 Input — 素材收件箱（只进不改）
├── 20-wiki/        📚 Knowledge — 你消化后的知识（只放结论）
│   ├── 10-行业与市场/
│   ├── 20-产品知识/
│   ├── 30-客户洞察/
│   ├── 40-销售与转化/
│   ├── 50-内容与流量/
│   └── 60-实战复盘/
├── 30-flow/        🔁 Workflow — 日常工作流
│   ├── 10-公域流量/       选题→创作→发布→数据
│   ├── 20-私域运营/       朋友圈/社群/数据周报
│   ├── 30-CRM/            线索→跟进→成交→归档
│   └── 40-产品交付/       交付物管理
├── 40-agents/      🤖 AI Layer — Agent 配置和 Skills
├── 50-projects/    📦 Entities — 客户档案、品牌资产
├── 60-assets/      💰 Templates — 可复用模板
└── 99-archive/     🗄️ Archive — 归档
```

### 三条铁律

| 层 | 规则 |
|----|------|
| `10-raw` | **只进不改** — 素材扔进去，永远不改原文件。改写不了的留在 raw。 |
| `20-wiki` | **只放结论** — 只写你自己消化后的结论。复制粘贴的放 raw。 |
| `30-flow` | **只做调用** — 这里的工作只调用 wiki 知识，不产出知识。 |

### 数据流

```
看到好内容 → 10-raw/inbox/（扔进去）
                ↓ 定期清理
            有价值的 → 消化提炼
                ↓
            20-wiki/（用自己的话写结论）
                ↓
            30-flow/（用 wiki 知识做日常工作）
                ↓
            50-projects/（落到真实客户/项目）
                ↓
            60-assets/（好东西变成可复用资产）
```

---

## 🤖 内置 Skills

### 共享 Skills（7 个，国内版和海外版通用）

| Skill | 触发 | 功能 |
|-------|------|------|
| **vault-rules** | 自动加载 | Vault 文件操作规范：命名、状态流转、路径路由 |
| **raw-refine** | "提炼素材" / "整理raw" | 素材消化提炼为 wiki 知识卡 |
| **finance** | "记账" / "收支" / "财务" | 收支记录、月度利润、发票管理 |
| **hr** | "员工" / "招聘" / "薪资" | 员工档案、考勤、绩效评估 |
| **project** | "项目" / "任务" / "进度" | 项目卡片、任务列表、进度追踪 |
| **inventory** | "库存" / "SKU" / "发货" | SKU 管理、订单追踪、库存预警 |
| **dashboard** | "周报" / "数据看板" / "复盘" | 多维度数据汇总、周报/月报生成 |

### 国内版 Skills（3 个）

| Skill | 触发 | 功能 |
|-------|------|------|
| **platform-traffic** | "帮我出选题" / "写文章" | 公众号/小红书/抖音/视频号：选题→创作→发布→数据 |
| **private-domain** | "发朋友圈" / "私域" | 朋友圈内容规划、社群运营、数据周报 |
| **crm** | "新客户" / "跟进" / "成交了" | 微信+电话 CRM，线索到成交全流程 |

### 海外版 Skills（3 个）

| Skill | 触发 | 功能 |
|-------|------|------|
| **platform-traffic** | "发帖" / "content" / "选题" | FB/IG/TikTok/YouTube/Blog：选题→创作→发布→数据 |
| **private-domain** | "WhatsApp" / "Email Newsletter" | WhatsApp Status/Broadcast、Newsletter、FB Groups 运营 |
| **crm** | "new lead" / "follow up" / "quotation" | WhatsApp/Email/LinkedIn CRM，多时区多币种 |

---

## 📦 仓库文件统计

```
_shared/          97 文件  — 共享骨架 + 模板 + Skills + Mock 数据
_variants/domestic/  15 文件  — 国内版差集
_variants/overseas/  19 文件  — 海外版差集
合计约 130+ 文件
```

---

## 🛠️ 搭建指令（Hermes Agent 专用）

> 以下指令由 Hermes Agent 执行。用户发送搭建请求后，Agent 按以下步骤操作。

---

### 国内版搭建指令

**触发条件**：用户说"请按照 crazy-agent 国内版搭建我的 Vault"或引用本 README。

#### Phase 1: 创建 Vault 骨架

在用户指定路径下创建 Obsidian 兼容的 Markdown 知识库目录结构，包含 `.obsidian` 配置文件：

```bash
VAULT="{用户确认的路径}"

# 创建 .obsidian 基础配置（Obsidian 核心设置）
mkdir -p "$VAULT/.obsidian"
cat > "$VAULT/.obsidian/app.json" << 'EOF'
{
  "accentColor": "",
  "baseFontSize": 16,
  "cssTheme": "",
  "interfaceFontFamily": "",
  "textFontFamily": "",
  "monospaceFontFamily": "",
  "nativeMenus": false
}
EOF

cat > "$VAULT/.obsidian/appearance.json" << 'EOF'
{
  "baseFontSize": 16,
  "interfaceFontSize": 14,
  "cssTheme": ""
}
EOF

cat > "$VAULT/.obsidian/core-plugins.json" << 'EOF'
[
  "file-explorer",
  "global-search",
  "switcher",
  "graph",
  "backlink",
  "outgoing-link",
  "tag-pane",
  "page-preview",
  "templates",
  "daily-notes",
  "starred",
  "random-note"
]
EOF

cat > "$VAULT/.obsidian/workspace.json" << 'EOF'
{
  "main": {
    "id": "",
    "type": "split",
    "children": []
  },
  "left": {
    "id": "",
    "type": "split",
    "children": [
      {
        "id": "",
        "type": "tabs",
        "children": [
          {
            "id": "",
            "type": "leaf",
            "state": {
              "type": "file-explorer",
              "state": {}
            }
          }
        ]
      },
      {
        "id": "",
        "type": "tabs",
        "children": [
          {
            "id": "",
            "type": "leaf",
            "state": {
              "type": "search",
              "state": { "query": "", "matchingCase": false, "explainSearch": false, "collapseAll": false, "extraContext": false }
            }
          }
        ]
      }
    ]
  }
}
EOF
```

> 这些配置文件确保用户在其他设备上用 Obsidian 桌面版/手机版打开此目录时，能正确识别为 Vault 并获得标准体验。

#### Phase 2: 确认信息

询问用户确认（提供默认值，回车可跳过）：

1. **Vault 路径** — 默认：`~/Documents/my-vault/`
2. **行业** — 默认：空（用户后续填写，但用于 00-me 模板的行业示例）
3. **内容平台** — 默认：`公众号`。选项：公众号/小红书/抖音/视频号/Blog（多选）
4. **是否包含 Mock 数据** — 默认：是

显示摘要，等待用户确认后继续。

#### Phase 3: 创建 Vault 结构

```bash
VAULT="{用户确认的路径}"

# 复制共享骨架
cp -r _shared/skeleton/* "$VAULT/skeleton-temp/"
cp -r _shared/templates/* "$VAULT/templates-temp/"
cp -r _shared/skills/* "$VAULT/skills-temp/"

# 创建九层目录
mkdir -p "$VAULT"/{00-me/{10-定位与品牌,20-产品与业务,30-目标客户,40-账号矩阵,50-目标与节奏},10-raw/{inbox,cleaned,tagged},20-wiki/{10-行业与市场,20-产品知识,30-客户洞察,40-销售与转化,50-内容与流量,60-实战复盘},30-flow/{10-公域流量/{10-选题池,20-内容管理,30-数据统计,40-内容资产,50-素材提炼},20-私域运营/{10-朋友圈,20-社群,30-数据周报},30-CRM/{10-线索管理,20-成交记录},40-产品交付},40-agents/{skills,schedules,10-内容创作,20-调研分析,30-运营管理,40-效率工具},50-projects/{客户,品牌,账号},60-assets/{内容模板,PPT模板,报价方案,合同},99-archive}

# 创建平台特定目录
for platform in {用户选择的平台}; do
  mkdir -p "$VAULT/30-flow/10-公域流量/20-内容管理/$platform"
done
```

#### Phase 4: 放置共享模板

将 `_shared/templates/` 下的文件复制到 Vault 对应位置：

| 源 | 目标 |
|----|------|
| `templates/me/*.md` | `00-me/` 对应子目录 |
| `templates/wiki/**/*.md` | `20-wiki/` 对应子目录 |
| `templates/flow/*.md` | `30-flow/` 对应子目录（按文件名判断） |
| `templates/agents/*.md` | `40-agents/` 对应子目录 |
| `templates/root/系统使用指南.md` | `系统使用指南.md`（Vault 根目录） |
| `templates/root/骨架设计说明.md` | `骨架设计说明.md`（Vault 根目录） |

#### Phase 5: 覆盖国内版差集

将 `_variants/domestic/` 下的文件复制到 Vault 对应位置（覆盖同名共享文件）：

| 源 | 目标 |
|----|------|
| `skills/crm.md` | `40-agents/skills/crm.md` |
| `skills/platform-traffic.md` | `40-agents/skills/platform-traffic.md` |
| `skills/private-domain.md` | `40-agents/skills/private-domain.md` |
| `templates/me/产品与服务清单.md` | `00-me/20-产品与业务/产品与服务清单.md` |
| `templates/me/目标客户画像.md` | `00-me/30-目标客户/目标客户画像.md` |
| `templates/me/平台账号信息.md` | `00-me/40-账号矩阵/平台账号信息.md` |
| `templates/flow/_template-选题卡.md` | `30-flow/10-公域流量/10-选题池/_template-选题卡.md` |
| `templates/flow/_template-线索卡.md` | `30-flow/30-CRM/10-线索管理/_template-线索卡.md` |
| `templates/flow/填写指南.md` | `30-flow/30-CRM/20-成交记录/填写指南.md` |
| `templates/assets/*.md` | `60-assets/内容模板/` |

#### Phase 6: 安装 Skills

将 `_shared/skills/` 和 `_variants/domestic/skills/` 的所有 .md 文件安装到 Hermes：

对每个 skill 文件：
1. 读取内容
2. 将 `{VAULT_ROOT}` 替换为用户的实际 Vault 路径
3. 使用 `skill_manage(action='create', name=..., content=...)` 安装

共享 Skills：`vault-rules`, `raw-refine`, `finance`, `hr`, `project`, `inventory`, `dashboard`
国内版 Skills：`crm`, `platform-traffic`, `private-domain`

共 10 个 Skills。

#### Phase 7: 配置定时任务

读取 `_variants/domestic/schedules/default-schedules.yaml`，为每个任务：
1. 替换 `{VAULT_ROOT}` 为用户 Vault 路径
2. 使用 `cronjob(action='create', ...)` 创建

国内版定时任务：朋友圈提醒 ×3 + 素材清理 + 数据回收 + CRM跟进 + 选题检查 = 7 个

#### Phase 8: 放置 Mock 数据（可选）

如果用户选择包含 Mock 数据：
```bash
cp -r _shared/mock-data/* "$VAULT/"  # 覆盖对应目录
```

将 mock 数据中所有文件的 `{VAULT_ROOT}` 替换为实际路径。

#### Phase 9: 初始化 Git

```bash
cd "$VAULT"

# 创建 .gitignore（保留 .obsidian 核心配置，忽略运行时缓存）
cat > .gitignore << 'EOF'
.obsidian/workspace*
.obsidian/graph.json
.obsidian/cache
.obsidian/hotkeys.json
.obsidian/community-plugins.json
.DS_Store
.gitkeep
*.swp
EOF

git init
git add -A
git commit -m "init: Vault initialized by Crazy Agent (domestic)"
```

#### Phase 10: 完成报告

输出：
```
════════════════════════════════════
  ✅ 国内版 Vault 搭建完成！
════════════════════════════════════

📁 Vault 路径：{VAULT_PATH}
📂 目录数：{count}
📄 文件数：{count}
🎭 包含 Mock 数据：是/否

🤖 Skills 已安装（10 个）：
   ✅ vault-rules（文件规范）
   ✅ raw-refine（素材提炼）
   ✅ finance（财务管理）
   ✅ hr（人事管理）
   ✅ project（项目管理）
   ✅ inventory（库存管理）
   ✅ dashboard（数据看板）
   ✅ crm（客户关系管理）
   ✅ platform-traffic（公域流量运营）
   ✅ private-domain（私域运营）

⏰ 定时任务（7 个）：
   ✅ 朋友圈提醒（10:00 / 14:00 / 19:00）
   ✅ 素材清理（周一 9:00）
   ✅ 数据回收（周日 20:00）
   ✅ CRM 跟进（周三 9:00）
   ✅ 选题检查（周五 15:00）

════════════════════════════════════
  下一步：
  1. 在其他设备上用 Obsidian 打开 Vault 目录（Obsidian → 打开文件夹作为仓库）
  2. 填写 00-me/ 下的 5 个配置文件
  3. 把现有素材扔进 10-raw/inbox/
  4. 如果不需要 Mock 数据，删除带 mock:true 的文件
  5. 开始创作！
════════════════════════════════════
```

---

### 海外版搭建指令

**触发条件**：用户说"请按照 crazy-agent 海外版搭建我的 Vault"或引用本 README 海外版部分。

与国内版的差异仅在以下步骤：

#### Phase 2 确认信息差异

3. **内容平台** — 默认：`Facebook`。选项：Facebook/Instagram/TikTok/YouTube/Blog（多选）
4. **目标市场时区** — 默认：`EST (UTC-5)`。选项：EST/PST/GMT/GST
5. **内容语言** — 默认：`English`

#### Phase 3 目录结构差异

平台目录创建：
```bash
for platform in {用户选择的平台}; do
  mkdir -p "$VAULT/30-flow/10-公域流量/20-内容管理/$platform"
done
```

#### Phase 5 差集差异

使用 `_variants/overseas/` 而非 `_variants/domestic/`：

| 源 | 目标 |
|----|------|
| `skills/crm.md` | `40-agents/skills/crm.md` |
| `skills/platform-traffic.md` | `40-agents/skills/platform-traffic.md` |
| `skills/private-domain.md` | `40-agents/skills/private-domain.md` |
| `templates/me/产品与服务清单.md` | `00-me/20-产品与业务/产品与服务清单.md` |
| `templates/me/目标客户画像.md` | `00-me/30-目标客户/目标客户画像.md` |
| `templates/me/平台账号信息.md` | `00-me/40-账号矩阵/平台账号信息.md` |
| `templates/flow/_template-选题卡.md` | `30-flow/10-公域流量/10-选题池/_template-选题卡.md` |
| `templates/flow/_template-线索卡.md` | `30-flow/30-CRM/10-线索管理/_template-线索卡.md` |
| `templates/flow/成交记录填写指南.md` | `30-flow/30-CRM/20-成交记录/填写指南.md` |
| `templates/assets/*.md` | `60-assets/内容模板/`（7 个海外平台模板） |

#### Phase 6 Skills 差异

海外版 Skills：`crm`, `platform-traffic`, `private-domain`（从 `_variants/overseas/skills/` 安装）
共仍为 10 个 Skills（7 共享 + 3 海外版）。

#### Phase 7 定时任务差异

读取 `_variants/overseas/schedules/default-schedules.yaml`。

海外版定时任务：WhatsApp Status 提醒 + Email Newsletter 检查 + 素材清理 + 数据回收 + CRM跟进 + 选题检查 = 6 个

#### Phase 10 完成报告差异

```
⏰ 定时任务（6 个）：
   ✅ WhatsApp Status 提醒（每日 10:00）
   ✅ Email Newsletter 检查（周一 14:00）
   ✅ 素材清理（周一 9:00）
   ✅ 数据回收（周日 20:00）
   ✅ CRM 跟进（周三 9:00）
   ✅ 选题检查（周五 15:00）
```

---

## 📝 手动搭建

不用 Hermes Agent 也可以：

1. 创建上述九层目录结构（`mkdir -p`）
2. 创建 `.obsidian/` 配置文件（参考 Phase 1）
3. 从 `_shared/templates/` 复制模板到对应位置
4. 选择 `_variants/domestic/` 或 `_variants/overseas/` 覆盖差异文件
5. 将 `_shared/skills/` 复制到 `~/.hermes/skills/`，替换 `{VAULT_ROOT}`
6. 按需配置 cron 任务

---

## 📄 License

MIT

---

## 🙏 Credits

Built by [SuperXia](https://github.com/superxia01) with ❤️
Powered by [Hermes Agent](https://github.com/nousresearch/hermes-agent) + [Obsidian](https://obsidian.md/)
