# 🧠 Claude Plan Action Skill（结构化规划技能）

> **告别 AI 的"自由发挥"。** 一个 Claude Code 的结构化规划框架——消除 AI 幻觉、减少返工、一次交付高质量代码。

![License](https://img.shields.io/badge/license-MIT-green)
![Claude Code](https://img.shields.io/badge/Claude%20Code-Compatible-blue)

---

## 📖 这是什么？

**Claude Plan Action** 是一个结构化的任务规划方法论，打包为 Claude Code 技能。它改变了你与 AI 协作复杂任务的方式——

| 传统做法（直接提问） | 结构化规划 |
|:--------------------|:-----------|
| AI 猜测你的意图 → 写错代码 → 反复返工 | AI 分析需求 → 输出方案 → 你确认 → 正确执行 |
| 聊了 10 轮后忘记早期决策 | 用书面方案在编码前锁定决策 |
| 最后才发现所有问题 | 每个节点分阶段验收 |

## ✨ 核心亮点

- **🎯 5 模块规划框架** — 目标拆解、资源审计、可行性评估、工作计划、任务编排
- **📊 任务分级** — S/A/B/C 四级，不同复杂度匹配不同的规划深度
- **✅ 人在回路中** — 方案未经你确认，AI 不得写一行代码
- **🔧 开箱即用** — 复制 SKILL.md 文件、注册到技能清单，立刻可用

## 🚀 快速开始

### 1. 克隆仓库

```bash
git clone https://github.com/donglinfei-debug/claude-plan-action-skill.git
cd claude-plan-action-skill
```

### 2. 复制技能文件到你的 Claude Code 工作区

```bash
mkdir -p /path/to/your/skills/plan-action
cp skill-files/SKILL.md /path/to/your/skills/plan-action/
```

### 3. 注册到项目

在项目 `CLAUDE.md` 的技能清单中添加一行：

```markdown
| plan-action | `skills/plan-action/` | 全盘任务规划 — 分析需求、拆解子任务、调度 Agent 和 Skill、输出执行方案 | `/plan-action {描述}` | 直接在对话中描述需求 |
```

### 4. 使用

```
/plan-action 给我的 Flask 项目加一个用户认证系统
```

Claude 会输出结构化方案，而不是直接写代码。

## 📂 仓库结构

```
├── README.md                          # 英文首页
├── README.zh.md                       # 中文首页
├── CHANGELOG.md                       # 版本历史
│
├── docs/
│   └── plan-action-guide.md           # ★ 完整指南（10章 + 3附录）
│
└── skill-files/
    ├── SKILL.md                       # 可复用的技能定义
    ├── PLAN_TEMPLATE.md               # 5 模块方案模板
    └── AGENT_REGISTRY.example.json    # Agent 注册表示例
```

## 📖 阅读完整指南

完整的方法论、原理和最佳实践请阅读：

➡️ **[完整指南 — docs/plan-action-guide.md](docs/plan-action-guide.md)**

包含：
- 结构化规划如何防止 AI 幻觉
- 5 步流程详解
- 任务分级系统（S/A/B/C）
- Agent + Skill 资源审计方法
- 可行性评估模型
- 完整示例和模板

## 🧠 核心原理

```
AI 编程的 3 大问题 → 结构化规划的 3 个约束

① 指令模糊 → AI 自由发挥
    → 需求解析模板消除模糊性

② 长上下文丢失 → AI 忘记早期决策
    → 书面方案在编码前锁定决策

③ 缺乏校验节点 → 隐藏缺陷累积
    → 节点验收标准在早期捕获问题
```

## 📄 许可证

[MIT](LICENSE) © 2026 Ryan Dong

## 📬 联系方式

- **作者**: Ryan Dong
- **邮箱**: donglinfei@gmail.com
- **GitHub**: [donglinfei-debug](https://github.com/donglinfei-debug)

---

> 先规划，后编码。一次做对，绝不返工。
