<div align="center">

# 🧠 Claude Plan Action Skill（结构化规划技能）

**告别 AI 的"自由发挥"—— Claude Code 结构化规划框架**

[![GitHub Stars](https://img.shields.io/github/stars/donglinfei-debug/claude-plan-action-skill?style=flat-square&logo=github)](https://github.com/donglinfei-debug/claude-plan-action-skill/stargazers)
[![GitHub Issues](https://img.shields.io/github/issues/donglinfei-debug/claude-plan-action-skill?style=flat-square&logo=github)](https://github.com/donglinfei-debug/claude-plan-action-skill/issues)
[![GitHub Forks](https://img.shields.io/github/forks/donglinfei-debug/claude-plan-action-skill?style=flat-square&logo=github)](https://github.com/donglinfei-debug/claude-plan-action-skill/forks)
[![License](https://img.shields.io/github/license/donglinfei-debug/claude-plan-action-skill?style=flat-square)](LICENSE)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-兼容-blue.svg?style=flat-square&logo=anthropic)](https://claude.ai)

🌏 **语言 / Language**：[🇨🇳 中文](README.zh.md) | [🇬🇧 English](README.md)

</div>

---

一个 Claude Code 的结构化规划框架——消除 AI 幻觉、减少返工、一次交付高质量代码。通过任务分级（S/A/B/C）、资源审计、五维评估、里程碑规划，确保复杂需求在动手编码前已有清晰的执行方案。


## 📌 为什么需要这个技能？

| 之前（直接提问） | 之后（结构化规划） |
|:----------------|:-----------------|
| 🤯 AI 猜你的意图 → 写出错的代码 → 返工循环 | 🎯 AI 分析需求 → 输出方案 → 你确认 → 一次性写对 |
| 🧠 10 轮对话后早期决定被遗忘 | 📋 所有决策写在计划里，不会丢失 |
| 🔍 最后才发现问题 | ✅ 每个里程碑检查一个，及早发现 |
| ⏱️ Token 浪费在 AI 的胡乱尝试上 | 💰 每条 Token 都在为已确认的方向工作 |

**Claude Plan Action Skill** 改变你和 Claude Code 协作的方式——消除猜测、减少返工、一次交付。

## 🏗️ 工作流程

```mermaid
flowchart TB
    subgraph Input["📥 输入"]
        REQ[用户需求]
    end
    subgraph Analyze["🔍 1. 分析"]
        CLS[任务分级<br/>S/A/B/C 四级]
        DEC[需求拆解<br/>范围与约束]
    end
    subgraph Plan["📋 2. 规划"]
        AUD[资源审计<br/>Agent · Skill · MCP]
        FEA[可行性评估<br/>五维评估]
        MIL[工作计划<br/>节点 · 交付物]
    end
    subgraph Execute["⚡ 3. 执行"]
        APP[确认 → 编码<br/>审查 · 测试]
    end

    REQ --> CLS --> DEC
    DEC --> AUD --> FEA --> MIL
    MIL --> APP

    style REQ fill:#6366f1,color:#fff,stroke:none
    style CLS fill:#0ea5e9,color:#fff,stroke:none
    style DEC fill:#0ea5e9,color:#fff,stroke:none
    style AUD fill:#0ea5e9,color:#fff,stroke:none
    style FEA fill:#0ea5e9,color:#fff,stroke:none
    style MIL fill:#0ea5e9,color:#fff,stroke:none
    style APP fill:#10b981,color:#fff,stroke:none
```

## ✨ 核心功能

- **🎯 5 模块规划框架** — 目标拆解、资源审计、可行性评估、里程碑规划、任务编排
- **📊 任务分级** — S/A/B/C 四级，按级别决定规划深度
- **✅ 人在回路** — 方案经你确认后才开始编码
- **🔧 即装即用** — 复制 SKILL.md 注册即可使用

## 📦 系统要求

| 要求 | 说明 |
|:-----|:------|
| **Claude Code** | 最新版 |
| **安装方式** | 将 SKILL.md 复制到 `.claude/skills/` 目录 |

## 📁 文件结构

```
claude-plan-action-skill/
├── SKILL.md                    # Skill 定义（复制到 .claude/skills/）
├── skill-files/
│   ├── SKILL.md                # Skill 源码
│   ├── PLAN_TEMPLATE.md        # 执行计划模板
│   └── AGENT_REGISTRY.example.json
├── docs/
│   ├── plan-action-guide.md    # 使用指南
│   └── scan-results.md
├── CHANGELOG.md
├── LICENSE                     # MIT
└── README.md / README.zh.md
```



---

## 🔍 搜索关键词

IBKR 期权自动化交易、Interactive Brokers Python API、期权交易机器人架构、铁鹰策略自动化、SPX 期权交易、IBKR API 连接管理、TWS API Python、IB Gateway 集成、期权链数据批量获取、限价单价格调整、交易风控防抖机制、飞书 Bot 消息推送、钉钉 Webhook 集成、Gmail AI 摘要通知、Google Apps Script 邮件监控、AI 字幕校对、ASR 语音识别、DeepSeek API 集成、阿里云通义听悟 fun-asr、字幕自动生成、Claude Code 规划技能、AI 结构化规划框架、GitHub 公开仓库预处理、开源项目安全清洗、密钥自动检测、公开仓库操作清单
## 📄 许可证

MIT © 2026 Ryan Dong

## 🌟 Star 历史

[![Star History Chart](https://api.star-history.com/svg?repos=donglinfei-debug/claude-plan-action-skill&type=Date)](https://star-history.com/#donglinfei-debug/claude-plan-action-skill&Date)

## 📬 联系方式

Ryan Dong — donglinfei@gmail.com
