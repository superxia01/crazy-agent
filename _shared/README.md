# _shared/ — 共享骨架

本目录包含 Crazy Agent Vault 的所有共享文件：国内版和海外版完全相同的部分。

## 搭建流程

搭建 Vault 时，按以下顺序操作：

1. **复制 _shared 到 vault 根目录** — 将 `_shared/templates/` 下的文件展开到 vault 对应目录，`_shared/skills/` 复制到 `40-agents/skills/`
2. **叠加 variant** — 根据 variant（国内版/海外版）复制 `_variants/{variant}/` 下的差集文件，覆盖或补充共享文件
3. **填充用户数据** — 用户按照填写指南填写 00-me 和各模板

## 目录说明

```
_shared/
├── README.md                 # 本文件
├── skeleton/                 # 九层目录骨架定义
│   ├── directory-structure.md  # mkdir -p 命令
│   ├── naming-rules.md        # 文件命名规则
│   └── status-flow.md         # 状态流转规则
├── templates/                 # 共享模板文件
│   ├── me/                    # 00-me 模板（8个）
│   ├── wiki/                  # 20-wiki 模板（21个内容 + 6个README）
│   ├── flow/                  # 30-flow 填写指南（11个）
│   ├── agents/                # 40-agents 助手（4个）
│   └── root/                  # 根目录文件（2个）
└── skills/                    # 共享 Skills（2个）
    ├── vault-rules.md
    └── raw-refine.md
```
