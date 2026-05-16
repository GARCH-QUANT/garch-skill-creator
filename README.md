# Skill Creator — Hermes Agent 技能包制作工具

快速创建标准格式 Hermes Agent Skills，包含 SKILL.md 骨架、脚本打包与校验工具。

## 工具链

| 脚本 | 功能 |
|------|------|
| `scripts/init_skill.py` | 初始化新技能包（SKILL.md 模板 + 目录结构）|
| `scripts/package_skill.py` | 打包技能包为可分发格式 |
| `scripts/quick_validate.py` | 校验 SKILL.md 格式规范 |

## SKILL.md 标准格式

```yaml
---
name: skill-name
description: >-
  One-line description. Use when [trigger conditions].
version: 1.0.0
---

# Skill Title

Description...

## Core Workflow

1. Step 1
2. Step 2

## Pitfalls

- Gotcha 1
- Gotcha 2

## Verification

```bash
python scripts/verify.py
```
```

## 核心原则

- **简洁优先**：只写入 Model 不已有的知识，不重复系统 prompt
- **适度自由**：文本指令用于开放任务，脚本用于固定流程
- **Tokens 意识**：每段文字都应证明其 Token 成本合理

## 快速开始

```bash
# 初始化新技能
python scripts/init_skill.py --name my-new-skill --category finance

# 打包技能包
python scripts/package_skill.py --skill-dir ./my-new-skill

# 校验格式
python scripts/quick_validate.py --skill-dir ./my-new-skill
```