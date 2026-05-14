# 文件状态流转

## 内容生命周期
```
📋选题中 → 📝草稿 → 📤待发布 → ✅已发布 → 🚫Closed
```

视频类额外步骤：
```
📋选题中 → 📝草稿 → 📸拍摄中 → ✂️剪辑中 → 📤待发布 → ✅已发布 → 🚫Closed
```

## 状态变更规则
1. 文件从生到死不搬家，状态变更只改文件名前缀 + frontmatter status 字段
2. frontmatter 中必须包含 `status` 字段，与文件名前缀保持一致
3. Closed 状态的文件移到 99-archive/ 目录

## Frontmatter 状态字段
所有内容文件的 frontmatter 必须包含：
```yaml
---
status: 选题中  # 或：草稿/拍摄中/剪辑中/待发布/已发布/Closed
---
```
