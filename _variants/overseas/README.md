# 海外版差集 (Overseas Variant)

本目录包含海外版（跨境/外贸市场）特有的文件，搭建时覆盖到 _shared/ 对应位置。

## 差异说明

相比通用骨架，海外版主要差异：
- **平台**：Facebook、Instagram、TikTok、YouTube、Google Blog
- **私域**：WhatsApp Status/Broadcast、Email Newsletter、Facebook Groups、Instagram DM
- **CRM**：WhatsApp/Email/LinkedIn 为主，支持多时区、多币种
- **行业示例**：跨境电商（宠物用品卖家）
- **Skills**：适配海外平台的 CRM、公域流量、私域运营

## 搭建时操作

1. 先复制 _shared/ 到 vault 根目录
2. 将本 variant 的 skills/ 复制到 10-AI/skills/
3. 将本 variant 的 templates/me/ 复制到 00-me/ 对应子目录
4. 将本 variant 的 templates/flow/ 复制到 40-flow/ 对应子目录
5. 将本 variant 的 templates/assets/ 复制到 50-assets/内容模板/
6. 创建平台特定内容目录：Facebook/Instagram/TikTok/YouTube/Blog
