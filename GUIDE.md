# Crazy Agent — AI 搭建指令

> 本文件是给 Hermes Agent（或任何 AI）看的搭建指南。
> 用户说"按照 crazy-agent 搭建"时，按本文件执行。

---

## 架构概览

```
_shared/（通用骨架）
    ↓ 复制到 Vault
+ _variants/domestic/ 或 overseas/（市场差集）
    ↓ 覆盖对应文件
= 完整的 Vault
```

---

## 1. 国内版搭建指令

**触发条件**：用户说"请按照 crazy-agent 国内版搭建我的 Vault"。

### Phase 1: 确认信息

询问用户（提供默认值，回车可跳过）：

1. **Vault 路径** — 默认：`~/Documents/my-vault/`
2. **行业** — 默认：空（后续填写，影响模板示例）
3. **内容平台** — 默认：`公众号`。选项：公众号/小红书/抖音/视频号/Blog（多选）
4. **是否包含 Mock 数据** — 默认：是

### Phase 2: 创建 Vault 骨架

创建 `.obsidian` 基础配置和八层目录结构：

```bash
VAULT="{用户确认的路径}"

# .obsidian 配置
mkdir -p "$VAULT/.obsidian"
cat > "$VAULT/.obsidian/app.json" << 'EOF'
{"accentColor":"","baseFontSize":16,"cssTheme":"","interfaceFontFamily":"","textFontFamily":"","monospaceFontFamily":"","nativeMenus":false}
EOF

cat > "$VAULT/.obsidian/appearance.json" << 'EOF'
{"baseFontSize":16,"interfaceFontSize":14,"cssTheme":""}
EOF

cat > "$VAULT/.obsidian/core-plugins.json" << 'EOF'
["file-explorer","global-search","switcher","graph","backlink","outgoing-link","tag-pane","page-preview","templates","daily-notes","starred","random-note"]
EOF

# 八层目录
mkdir -p "$VAULT"/{00-me/{10-定位与品牌,20-产品与业务,30-目标客户,40-账号矩阵,50-目标与节奏},10-AI/{10-schemas,20-templates,30-dataview,40-automations,50-mcp,60-prompts,70-integrations,80-rules},20-raw/{inbox,cleaned,tagged},30-wiki/{10-行业与市场,20-产品知识,30-客户洞察,40-销售与转化,50-内容与流量,60-实战复盘},40-flow/{10-公域流量/{10-选题池,20-内容管理,30-数据统计,40-内容资产,50-素材提炼},20-私域运营/{10-朋友圈,20-社群,30-数据周报},30-CRM/{10-线索管理,20-成交记录},40-产品交付,45-项目管理/{进行中,已完成,已暂停},50-人事管理/{员工档案,考勤记录,绩效评估,招聘管理},50-财务管理/{收支记录,发票管理,月度利润报表},55-库存管理/{SKU管理,订单追踪,库存预警,物流跟踪},60-数据看板/{周报,月报,复盘报告}},50-assets/{品牌,账号,内容模板,PPT模板,报价方案,合同},60-events/{10-company,20-ai},99-archive}

# 平台目录
for platform in {用户选择的平台}; do
  mkdir -p "$VAULT/40-flow/10-公域流量/20-内容管理/$platform"
done
```

### Phase 3: 放置 README + GUIDE

| 源 | 目标 |
|----|------|
| `README.md`（本仓库根目录） | `$VAULT/README.md` |
| `GUIDE.md`（本仓库根目录） | `$VAULT/GUIDE.md` |

将 `{VAULT_ROOT}` 替换为用户实际 Vault 路径。

### Phase 4: 放置共享模板

| 源 | 目标 |
|----|------|
| `_shared/templates/me/*.md` | `00-me/` 对应子目录 |
| `_shared/templates/wiki/**/*.md` | `30-wiki/` 对应子目录 |
| `_shared/templates/flow/*.md` | `40-flow/` 对应子目录 |
| `_shared/templates/agents/*.md` | `10-AI/` 对应子目录 |
| `_shared/templates/root/系统使用指南.md` | `系统使用指南.md`（Vault 根目录） |
| `_shared/templates/root/骨架设计说明.md` | `骨架设计说明.md`（Vault 根目录） |

### Phase 5: 覆盖国内版差集

| 源 | 目标 |
|----|------|
| `_variants/domestic/templates/me/产品与服务清单.md` | `00-me/20-产品与业务/` |
| `_variants/domestic/templates/me/目标客户画像.md` | `00-me/30-目标客户/` |
| `_variants/domestic/templates/me/平台账号信息.md` | `00-me/40-账号矩阵/` |
| `_variants/domestic/templates/flow/_template-选题卡.md` | `40-flow/10-公域流量/10-选题池/` |
| `_variants/domestic/templates/flow/_template-线索卡.md` | `40-flow/30-CRM/10-线索管理/` |
| `_variants/domestic/templates/flow/填写指南.md` | `40-flow/30-CRM/20-成交记录/` |
| `_variants/domestic/templates/assets/*.md` | `50-assets/内容模板/` |

### Phase 6: 安装 Skills（10 个）

将 `{VAULT_ROOT}` 替换为用户 Vault 路径后安装：

**共享 Skills（7 个）：**
`vault-rules`, `raw-refine`, `finance`, `hr`, `project`, `inventory`, `dashboard`

**国内版 Skills（3 个）：**
`crm`, `platform-traffic`, `private-domain`

### Phase 7: 配置定时任务

读取 `_variants/domestic/schedules/default-schedules.yaml`，创建 cron 任务：

| 任务 | 时间 |
|------|------|
| 朋友圈提醒 | 10:00 / 14:00 / 19:00 |
| 素材清理 | 周一 9:00 |
| 数据回收 | 周日 20:00 |
| CRM 跟进 | 周三 9:00 |
| 选题检查 | 周五 15:00 |

### Phase 8: 放置 Mock 数据（可选）

```bash
cp -r _shared/mock-data/* "$VAULT/"
```

将所有文件中的 `{VAULT_ROOT}` 替换为实际路径。

### Phase 9: 初始化 Git

```bash
cd "$VAULT"
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

git init && git add -A && git commit -m "init: Vault initialized by Crazy Agent (domestic)"
```

### Phase 10: 完成报告

```
════════════════════════════════════
  ✅ 国内版 Vault 搭建完成！
════════════════════════════════════

📁 Vault 路径：{VAULT_PATH}
📂 目录数：{count}
📄 文件数：{count}
🎭 包含 Mock 数据：是/否

🤖 Skills 已安装（10 个）：
   ✅ vault-rules / raw-refine / finance / hr
   ✅ project / inventory / dashboard
   ✅ crm / platform-traffic / private-domain

⏰ 定时任务（7 个）：
   ✅ 朋友圈提醒（10:00 / 14:00 / 19:00）
   ✅ 素材清理（周一 9:00）
   ✅ 数据回收（周日 20:00）
   ✅ CRM 跟进（周三 9:00）
   ✅ 选题检查（周五 15:00）

════════════════════════════════════
  下一步：
  1. 用 Obsidian 打开 Vault 目录
  2. 填写 00-me/ 下的配置文件
  3. 把现有素材扔进 20-raw/inbox/
  4. 开始用！
════════════════════════════════════
```

---

## 2. 海外版搭建指令

**触发条件**：用户说"请按照 crazy-agent 海外版搭建我的 Vault"。

与国内版的差异：

### Phase 1 确认信息差异

3. **内容平台** — 默认：`Facebook`。选项：Facebook/Instagram/TikTok/YouTube/Blog
4. **目标市场时区** — 默认：`EST (UTC-5)`
5. **内容语言** — 默认：`English`

### Phase 5 差集差异

使用 `_variants/overseas/` 而非 `_variants/domestic/`：

| 源 | 目标 |
|----|------|
| `_variants/overseas/templates/me/产品与服务清单.md` | `00-me/20-产品与业务/` |
| `_variants/overseas/templates/me/目标客户画像.md` | `00-me/30-目标客户/` |
| `_variants/overseas/templates/me/平台账号信息.md` | `00-me/40-账号矩阵/` |
| `_variants/overseas/templates/flow/_template-选题卡.md` | `40-flow/10-公域流量/10-选题池/` |
| `_variants/overseas/templates/flow/_template-线索卡.md` | `40-flow/30-CRM/10-线索管理/` |
| `_variants/overseas/templates/flow/成交记录填写指南.md` | `40-flow/30-CRM/20-成交记录/` |
| `_variants/overseas/templates/assets/*.md` | `50-assets/内容模板/`（7 个海外平台模板） |

### Phase 6 Skills 差异

海外版 Skills：`crm`, `platform-traffic`, `private-domain`（从 `_variants/overseas/skills/` 安装）

### Phase 7 定时任务差异

| 任务 | 时间 |
|------|------|
| WhatsApp Status 提醒 | 每日 10:00 |
| Email Newsletter 检查 | 周一 14:00 |
| 素材清理 | 周一 9:00 |
| 数据回收 | 周日 20:00 |
| CRM 跟进 | 周三 9:00 |
| 选题检查 | 周五 15:00 |

### Phase 10 完成报告差异

```
⏰ 定时任务（6 个）：
   ✅ WhatsApp Status 提醒（每日 10:00）
   ✅ Email Newsletter 检查（周一 14:00）
   ✅ 素材清理 / 数据回收 / CRM跟进 / 选题检查
```

---

## 3. 八层目录详细规范

### 路径判断决策树

```
用户要创建什么？

├─ 个人决策信息？ → 00-me/
├─ AI/系统配置？ → 10-AI/
├─ 原始素材？ → 20-raw/inbox/
├─ 消化后的知识？ → 30-wiki/
├─ 日常工作产出？ → 40-flow/
│   ├─ 选题 → 40-flow/10-公域流量/10-选题池/
│   ├─ 内容（按平台） → 40-flow/10-公域流量/20-内容管理/{平台}/
│   ├─ 朋友圈 → 40-flow/20-私域运营/10-朋友圈/
│   ├─ 社群 → 40-flow/20-私域运营/20-社群/
│   ├─ 客户线索 → 40-flow/30-CRM/10-线索管理/
│   ├─ 产品交付 → 40-flow/40-产品交付/
│   ├─ 项目 → 40-flow/45-项目管理/
│   ├─ 人事 → 40-flow/50-人事管理/
│   ├─ 财务 → 40-flow/50-财务管理/
│   ├─ 库存 → 40-flow/55-库存管理/
│   └─ 数据看板 → 40-flow/60-数据看板/
├─ 公司资产？ → 50-assets/
│   ├─ 品牌 → 50-assets/品牌/
│   ├─ 账号 → 50-assets/账号/
│   ├─ 内容模板 → 50-assets/内容模板/
│   ├─ 合同 → 50-assets/合同/
│   └─ 报价方案 → 50-assets/报价方案/
├─ 事件日志？ → 60-events/
│   ├─ 公司事件 → 60-events/10-company/
│   └─ AI 事件 → 60-events/20-ai/
└─ 已归档？ → 99-archive/
```

### 文件命名规则

| 类型 | 格式 | 示例 |
|------|------|------|
| 内容文件 | `{emoji}{YYYY-MM-DD}-{标题}.md` | `📋2026-05-16-AI工具效率提升.md` |
| 客户卡片 | `{状态emoji}{客户名}.md` | `📋张伟-华创科技.md` → `✅张伟-华创科技.md` |
| 系统文件 | `{标题}.md` | `IP定位.md` |
| 模板文件 | `_template-{用途}.md` | `_template-公众号文章.md` |
| 事件日志 | `{YYYY-MM-DD}-{事件}.md` | `2026-05-16-品牌升级发布.md` |

### 状态流转

```
图文：📋待选 → 📝草稿 → 📤待发布 → ✅已发布 → 🚫Closed
视频：📋待选 → 📝草稿 → 🎥拍摄中 → ✂️剪辑中 → 📤待发布 → ✅已发布 → 🚫Closed
CRM：📋新线索 → 📝跟进中 → 📤报价中 → ✅已成交 / 🚫已流失
```

**铁律：文件不搬家，状态变更只改文件名 emoji + frontmatter status 字段。**

---

## 4. 手动搭建

不用 Hermes Agent 也可以：

1. 创建上述八层目录结构（Phase 2 的 mkdir 命令）
2. 创建 `.obsidian/` 配置文件
3. 从 `_shared/templates/` 复制模板
4. 选择 `_variants/domestic/` 或 `_variants/overseas/` 覆盖差异
5. 将 `_shared/skills/` 安装到 `~/.hermes/skills/`，替换 `{VAULT_ROOT}`
6. 按需配置 cron 任务
