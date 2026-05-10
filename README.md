# Crazy Agent 🚀

> **One-command Obsidian Vault setup for personal IP & content creators.**
> 
> **一句话版 Obsidian 知识库搭建工具，专为个人IP和内容创作者设计。**

---

## ✨ What is this? / 这是什么？

Crazy Agent is a turnkey Obsidian Vault template designed for **solo entrepreneurs and content creators** who want to run their business like a one-person company.

一套为「一个人就是一家公司」设计的 Obsidian 知识库模板 + Hermes Agent 配置包。

**What you get / 你将得到：**

- A complete 7-layer Vault structure (directory + 30+ guided templates)
- 5 built-in Hermes Agent Skills (file management, content ops, CRM, etc.)
- 7 automated cron jobs (social media reminders, data collection, etc.)
- Git-ready with conventions built in

**使用 Hermes Agent 的话**：一句话搞定全部搭建。
**不用 Hermes Agent**：纯 Obsidian 也能完整使用。

---

## 🚀 Quick Start / 快速开始

### Prerequisites / 前置要求

1. [Hermes Agent](https://github.com/nousresearch/hermes-agent) installed and configured
2. A terminal / messaging platform connected to Hermes
3. Obsidian environment — see [Step 0 in Setup Instructions](#step-0-detect-os--install-obsidian-environment) below (auto-handled by Hermes)

### One Command / 一键搭建

Send this message to your Hermes Agent:

```
请访问 https://github.com/superxia01/crazy-agent 的 README，按里面的搭建指令初始化我的 Vault。
```

Your Hermes Agent will automatically:

1. ✅ Detect your OS and install Obsidian CLI / Headless
2. ✅ Ask you for your Vault path, industry, and content platforms
3. ✅ Create the complete 7-layer directory structure
4. ✅ Generate 5 guided config files (`00-me/`) with industry-specific examples
5. ✅ Generate 25 knowledge base templates (`20-wiki/`)
6. ✅ Install 5 Skills from this repo into `~/.hermes/skills/`
7. ✅ Configure 7 cron jobs for daily/weekly automation
8. ✅ Register vault with Obsidian CLI / Headless and initialize Git

### Without Hermes Agent / 纯手动版

If you don't use Hermes Agent, follow the **[Manual Setup Guide](#-manual-setup--手动搭建)** below.

---

## 🏗️ Vault Architecture / Vault 架构

```
Vault Root/
├── 00-me/          🧠 Identity — Who you are, what you sell, who you serve
├── 10-raw/         📥 Input — Raw materials inbox (read-only, never modify)
├── 20-wiki/        📚 Knowledge — Your digested insights (conclusions only)
├── 30-flow/        🔁 Workflow — Daily operations (create, publish, follow up)
├── 40-agents/      🤖 AI Layer — Agent configs and prompts (optional)
├── 50-projects/    📦 Entities — Client files, brand assets, account profiles
├── 60-assets/      💰 Templates — Reusable templates and deliverables
└── 99-archive/     🗄️ Archive — Completed and retired content
```

### Three Iron Rules / 三条铁律

| Layer | Rule / 规则 |
|-------|-------------|
| `10-raw` | **只进不改** — Materials go in, never get modified. If you can't rewrite it in your own words, it stays here. |
| `20-wiki` | **只放结论** — Only your own conclusions. If you're copy-pasting, it belongs in raw. |
| `30-flow` | **只做调用** — Work here calls on wiki knowledge, never produces it. |

### Data Flow / 数据流

```
See good content → 10-raw/inbox/ (throw it in)
                     ↓ periodic cleanup
              Valuable ones → Digest and refine
                     ↓
              20-wiki/ (write conclusions in your own words)
                     ↓
              30-flow/ (use wiki knowledge for daily work)
                     ↓
              50-projects/ (land on real clients/projects)
                     ↓
              60-assets/ (good stuff becomes reusable assets)
```

---

## 🤖 Built-in Skills / 内置技能

Located in the [`skills/`](skills/) directory. These are Hermes Agent Skill files that get installed during setup.

| Skill | Trigger / 触发方式 | Description / 功能 |
|-------|-------------------|-------------------|
| **vault-rules** | Auto-loaded | Vault file operation conventions: naming, status flow, path routing |
| **platform-traffic** | "帮我出选题" / "写文章" | Topic generation → Content creation → Publishing → Data tracking |
| **private-domain** | "发朋友圈" / "私域" | WeChat Moments planning, community management, weekly reports |
| **crm** | "新客户" / "跟进" | Lead entry, client tiering, follow-up tracking, deal archiving |
| **raw-refine** | "提炼素材" / "整理raw" | Digest raw materials into wiki knowledge cards |

### Adding More Skills / 添加更多 Skill

To add a new universal skill:

1. Create a new `.md` file in [`skills/`](skills/)
2. Follow the [Hermes Skill format](#skill-file-format)
3. Add an entry to the setup instructions (Step 5 below)
4. Submit a PR

### Skill File Format / Skill 文件格式

```markdown
---
name: skill-name
description: What this skill does
trigger: When to auto-load this skill
---

# Skill Title

> One-line description

---

## Instructions
...
```

Replace `{VAULT_ROOT}` with the user's actual Vault path during installation.

---

## ⏰ Cron Schedules / 定时任务

Located in [`schedules/default.yaml`](schedules/default.yaml). Configured during setup.

| Task / 任务 | Schedule / 时间 | Description / 说明 |
|-------------|----------------|-------------------|
| Moments reminder (AM) / 朋友圈提醒 | Daily 10:00 | Check today's content, suggest directions |
| Moments reminder (PM) / 朋友圈提醒 | Daily 14:00 | Follow up on AM publish status |
| Moments reminder (EVE) / 朋友圈提醒 | Daily 19:00 | End-of-day check, count today's posts |
| Raw cleanup / 素材清理 | Mon 9:00 | Scan raw inbox, assess material value |
| Data collection / 数据回收 | Sun 20:00 | Remind to report content performance data |
| CRM follow-up / CRM跟进 | Wed 9:00 | Check overdue client follow-ups |
| Topic pool check / 选题检查 | Fri 15:00 | Assess topic inventory, suggest refills |

---

## 📦 Repo Structure / 仓库结构

```
crazy-agent/
├── README.md                    ← You are here / 产品文档 + 搭建指令
├── skills/                      ← Hermes Agent Skill files
│   ├── vault-rules.md           ← File operation conventions
│   ├── platform-traffic.md      ← Content operations workflow
│   ├── private-domain.md        ← Private domain & social media
│   ├── crm.md                   ← Customer relationship management
│   └── raw-refine.md            ← Raw material refinement
└── schedules/
    └── default.yaml             ← Default cron job configurations
```

---

## 🛠️ Setup Instructions / 搭建指令

> **For Hermes Agent only.** The following is the complete instruction set that Hermes Agent executes when a user says "setup my Vault from crazy-agent".

---

### For Hermes Agent: Execute the following steps when triggered

**Trigger**: User sends a message like "请按照 crazy-agent 搭建我的 Vault" or references this repo's README.

#### Step 0: Detect OS & Install Obsidian Environment

Detect the user's operating system and set up accordingly:

**Linux server (no desktop / headless)** — Install [Obsidian Headless](https://obsidian.md/zh/help/headless) (official, no GUI needed):

```bash
# Requires Node.js 22+
npm install -g obsidian-headless

# Login to your Obsidian account
ob login

# Register vault (Hermes will run this after vault creation)
# Obsidian Headless uses Sync — the vault must be linked to your Obsidian Sync account
```

> Obsidian Headless is a public beta. It provides CLI-based Sync and Publish without the desktop app. Requires an Obsidian account with Sync enabled.

**Windows / macOS / Linux (with desktop)** — Install Obsidian desktop + enable [Obsidian CLI](https://obsidian.md/zh/help/cli):

1. Install [Obsidian](https://obsidian.md/) 1.12.7+:
   - **macOS**: `brew install --cask obsidian`
   - **Windows**: `winget install Obsidian.Obsidian`
   - **Linux (deb)**: Download from https://obsidian.md/download
2. Launch Obsidian → **Settings → General → Enable Command Line Interface**
3. Follow the registration prompt

```bash
# Verify installation
obsidian help

# Register vault (Hermes will run this after vault creation)
# The CLI auto-detects vaults opened in the desktop app
```

> **Note**: Obsidian CLI requires the desktop app to be running. If you need a fully headless setup, use Obsidian Headless above.

#### Step 1: Confirm Information

Ask the user to confirm (provide defaults, allow Enter to skip):

1. **Vault path** — Default: `~/Documents/my-vault/`
2. **Industry** — Default: empty (user fills in later). If provided, use it for `00-me` template examples.
3. **Content platforms** — Default: `公众号`. Options: 公众号/小红书/抖音/视频号/Blog

Show a summary plan, wait for user confirmation before proceeding.

#### Step 2: Create Directory Structure

```bash
VAULT="{user_confirmed_path}"
mkdir -p "$VAULT"/{00-me/{10-定位与品牌,20-产品与业务,30-目标客户,40-账号矩阵,50-目标与节奏},10-raw/{inbox,cleaned,tagged},20-wiki/{10-行业与市场,20-产品知识,30-客户洞察,40-销售与转化,50-内容与流量,60-实战复盘},30-flow/{10-公域流量/{10-选题池,20-内容管理,30-数据统计,40-内容资产,50-素材提炼},20-私域运营/{10-朋友圈,20-社群,30-数据周报},30-CRM/{10-线索管理,20-成交记录},40-产品交付},40-agents/{skills,schedules,10-内容创作,20-调研分析,30-运营管理,40-效率工具},50-projects/{客户,品牌,账号},60-assets/{内容模板,PPT模板,报价方案,合同},99-archive}

# Create platform-specific content directories
for platform in {user_selected_platforms}; do
  mkdir -p "$VAULT/30-flow/10-公域流量/20-内容管理/$platform"
done
```

#### Step 3: Create 00-me Guided Files

Create 5 three-section template files in `00-me/`. Each file follows this structure:

```
📌 填写指南 (How to fill in — 2-3 paragraphs, conversational tone)
✏️ 你的内容 (Your content — fill-in-the-blank format with hints)
📖 参考：[Industry]示例 (Reference example from a real industry)
```

Files to create:
1. `00-me/10-定位与品牌/IP定位.md`
2. `00-me/10-定位与品牌/品牌风格指南.md`
3. `00-me/20-产品与业务/产品与服务清单.md`
4. `00-me/30-目标客户/目标客户画像.md`
5. `00-me/50-目标与节奏/日常工作节奏.md`

Each file includes:
- YAML frontmatter with `title`, `type: config`, `category`, `created`, `updated`
- Three-section body with industry-specific examples (if user provided industry)
- `{TODAY}` replaced with actual date

#### Step 4: Create 20-wiki Templates

Create 25 empty knowledge templates in `20-wiki/` subdirectories:

| Directory | Files |
|-----------|-------|
| `10-行业与市场/` | 行业全景.md, 竞争格局.md, 行业趋势.md, 行业术语表.md |
| `20-产品知识/` | 产品深度解析.md, 竞品对比分析.md, 客户常见疑问FAQ.md, 产品话术.md |
| `30-客户洞察/` | 客户痛点地图.md, 客户决策路径.md, 异议处理手册.md, 客户类型画像.md |
| `40-销售与转化/` | 谈单方法论.md, 跟进话术库.md, 报价策略.md, 成交信号识别.md, 转介绍方法论.md |
| `50-内容与流量/` | 平台玩法总结.md, 爆款内容拆解.md, 标题公式库.md, 内容形式指南.md, 发布节奏与时机.md |
| `60-实战复盘/` | 成功案例库.md, 失败复盘.md, 数据规律沉淀.md |

Each wiki file includes:
```yaml
---
title: {title}
type: wiki
category: {category}
created: {YYYY-MM-DD}
updated: {YYYY-MM-DD}
tags: []
---
```

Plus a usage section explaining when to write, how to write, and related directories.

#### Step 5: Create Auxiliary Files

1. `系统使用指南.md` — Quick start guide with directory lookup table
2. `.gitignore` — Standard ignores (`.obsidian/`, `.DS_Store`, `.gitkeep`)
3. `.gitkeep` in all empty directories

```bash
find "$VAULT" -type d -empty -exec touch {}/.gitkeep \;
```

#### Step 6: Install Skills

For each skill file in this repo's [`skills/`](skills/) directory:

1. **Fetch the raw content** from GitHub:
   ```
   https://raw.githubusercontent.com/superxia01/crazy-agent/main/skills/{skill-name}.md
   ```
2. **Replace** `{VAULT_ROOT}` with the user's actual Vault path
3. **Install** using `skill_manage(action='create', name='{skill-name}', content=<content>)`
4. **Verify** installation by loading the skill

Skills to install: `vault-rules`, `platform-traffic`, `private-domain`, `crm`, `raw-refine`

> **Fallback**: If GitHub fetch fails, read the skill content directly from this README's embedded versions below.

#### Step 7: Configure Cron Jobs

Read [`schedules/default.yaml`](schedules/default.yaml) from this repo:
```
https://raw.githubusercontent.com/superxia01/crazy-agent/main/schedules/default.yaml
```

For each schedule entry:
1. Replace `{VAULT_ROOT}` with user's Vault path
2. Replace `{DELIVERY}` with `"origin"` (deliver back to current conversation)
3. Replace `{TODAY}` with current date
4. Create using `cronjob(action='create', name=..., schedule=..., prompt=..., skills=...)`

#### Step 8: Git Init

```bash
cd "$VAULT"
git init
git add -A
git commit -m "init: Vault initialized by Crazy Agent"
```

#### Step 9: Completion Report

Output:
```
════════════════════════════════════
  ✅ Vault Setup Complete!
════════════════════════════════════

📁 Vault Path: {VAULT_PATH}
📂 Directories created: {count}
📄 Files created: {count}

🤖 Skills installed (5):
   ✅ vault-rules
   ✅ platform-traffic
   ✅ private-domain
   ✅ crm
   ✅ raw-refine

⏰ Cron jobs configured (7):
   ✅ Moments reminders (10:00 / 14:00 / 19:00)
   ✅ Raw cleanup (Mon 9:00)
   ✅ Data collection (Sun 20:00)
   ✅ CRM follow-up (Wed 9:00)
   ✅ Topic pool check (Fri 15:00)

════════════════════════════════════
  Next steps:
  1. Fill in the 5 files in 00-me/
  2. Throw all your existing materials into 10-raw/inbox/
  3. (Optional) Install Obsidian desktop for GUI: https://obsidian.md/
  4. Start creating!
════════════════════════════════════
```

---

## 📝 Manual Setup / 手动搭建

If you don't use Hermes Agent:

1. Create the directory structure shown above using `mkdir -p`
2. Create 00-me guided files following the three-section format (📌 填写指南 / ✏️ 你的内容 / 📖 参考)
3. Create wiki template files following the format shown in Step 3 above
4. Copy skill files to `~/.hermes/skills/` and replace `{VAULT_ROOT}` with your path
5. Configure cron jobs manually following `schedules/default.yaml`

---

## 📄 License

MIT

---

## 🙏 Credits

Built by [SuperXia](https://github.com/superxia01) with ❤️
Powered by [Hermes Agent](https://github.com/nousresearch/hermes-agent) + [Obsidian](https://obsidian.md/)
