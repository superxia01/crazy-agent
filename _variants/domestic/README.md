# 国内版差集 (Domestic Variant)

本目录包含国内版（中国市场）特有的文件，搭建时覆盖到 _shared/ 对应位置。

## 差异说明

相比通用骨架，国内版主要差异：
- **平台**：公众号、小红书、抖音、视频号
- **私域**：微信朋友圈、微信群、知识星球
- **CRM**：微信 + 电话为主
- **行业示例**：AI博主/知识付费
- **Skills**：适配国内平台的 CRM、公域流量、私域运营

## 搭建时操作

1. 先复制 _shared/ 到 vault 根目录
2. 将本 variant 的 skills/ 复制到 10-AI/skills/（覆盖共享版 vault-rules/raw-refine 之外的 skills）
3. 将本 variant 的 templates/me/ 复制到 00-me/ 对应子目录（覆盖共享版同名文件）
4. 将本 variant 的 templates/flow/ 复制到 40-flow/ 对应子目录
5. 将本 variant 的 templates/assets/ 复制到 50-assets/内容模板/
6. 创建平台特定内容目录：公众号/小红书/抖音/视频号
