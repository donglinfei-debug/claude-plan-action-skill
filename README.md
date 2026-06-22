<div align="center">

# 🧠 Claude Plan Action Skill

**Stop guessing. Start planning. — A structured planning framework for Claude Code**

[![GitHub Stars](https://img.shields.io/github/stars/donglinfei-debug/claude-plan-action-skill?style=flat-square&logo=github)](https://github.com/donglinfei-debug/claude-plan-action-skill/stargazers)
[![GitHub Issues](https://img.shields.io/github/issues/donglinfei-debug/claude-plan-action-skill?style=flat-square&logo=github)](https://github.com/donglinfei-debug/claude-plan-action-skill/issues)
[![GitHub Forks](https://img.shields.io/github/forks/donglinfei-debug/claude-plan-action-skill?style=flat-square&logo=github)](https://github.com/donglinfei-debug/claude-plan-action-skill/forks)
[![License](https://img.shields.io/github/license/donglinfei-debug/claude-plan-action-skill?style=flat-square)](LICENSE)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-Compatible-blue.svg?style=flat-square&logo=anthropic)](https://claude.ai)

🌏 **Language / 语言**：[🇨🇳 中文](README.zh.md) | [🇬🇧 English](README.md)

</div>

---

A structured task planning methodology packaged as a Claude Code skill. Transforms how you interact with AI for complex coding tasks — eliminating guesswork, reducing rework, and delivering production-quality code on the first try.

## 🏗️ Workflow

```mermaid
flowchart TB
    subgraph Input["📥 Input"]
        REQ[User Request]
    end
    subgraph Analyze["🔍 1. Analyze"]
        CLS[Task Classification<br/>S/A/B/C Levels]
        DEC[Requirement Breakdown<br/>Scope & Constraints]
    end
    subgraph Plan["📋 2. Plan"]
        AUD[Resource Audit<br/>Agent · Skill · MCP]
        FEA[Feasibility Assessment<br/>5-Dimension Evaluation]
        MIL[Milestone Plan<br/>Nodes · Deliverables]
    end
    subgraph Execute["⚡ 3. Execute"]
        APP[Approval → Execution<br/>Code · Review · Test]
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

## ✨ Core Features

- **🎯 5-Module Planning Framework** — Goal breakdown, resource audit, feasibility assessment, milestone plan, task orchestration
- **📊 Task Classification** — S/A/B/C levels with appropriate planning depth for each
- **✅ Human-in-the-Loop** — No code is written before you approve the plan
- **🔧 Self-Contained** — Copy the SKILL.md, register it, and it works immediately

## 📦 Requirements

| Requirement | Details |
|:------------|:--------|
| **Claude Code** | Latest version |
| **Installation** | Copy SKILL.md to `.claude/skills/` or use `/plan-action` |

## 📁 Structure

```
claude-plan-action-skill/
├── SKILL.md                    # Skill definition (copy to .claude/skills/)
├── skill-files/
│   ├── SKILL.md                # Full skill source
│   ├── PLAN_TEMPLATE.md        # Execution plan template
│   └── AGENT_REGISTRY.example.json
├── docs/
│   ├── plan-action-guide.md    # Comprehensive usage guide
│   └── scan-results.md
├── CHANGELOG.md
├── LICENSE                     # MIT
└── README.md / README.zh.md
```

## 📄 License

MIT © 2026 Ryan Dong

## 🌟 Star History

[![Star History Chart](https://api.star-history.com/svg?repos=donglinfei-debug/claude-plan-action-skill&type=Date)](https://star-history.com/#donglinfei-debug/claude-plan-action-skill&Date)

## 📬 Contact

Ryan Dong — donglinfei@gmail.com
