# 🧠 Claude Plan Action Skill

> **Stop guessing. Start planning.** A structured planning framework for Claude Code that eliminates AI hallucinations, reduces rework, and delivers production-quality code on the first try.

![License](https://img.shields.io/badge/license-MIT-green)
![Claude Code](https://img.shields.io/badge/Claude%20Code-Compatible-blue)

---

## 📖 What is This?

**Claude Plan Action** is a structured task planning methodology packaged as a Claude Code skill. It transforms how you interact with AI for complex coding tasks:

| Before (Direct Prompting) | After (Structured Planning) |
|:--------------------------|:----------------------------|
| AI guesses your intent → writes wrong code → rework cycle | AI analyzes requirements → produces a plan → you approve → executes correctly |
| Forgets early decisions after 10 rounds | Locks decisions in written plan before coding |
| Discovers all problems at the end | Catches issues at each milestone |

## ✨ Core Features

- **🎯 5-Module Planning Framework** — Goal breakdown, resource audit, feasibility assessment, milestone plan, task orchestration
- **📊 Task Classification** — S/A/B/C levels with appropriate planning depth for each
- **✅ Human-in-the-Loop** — No code is written before you approve the plan
- **🔧 Self-Contained** — Copy the SKILL.md, register it, and it works immediately

## 🚀 Quick Start

### 1. Copy the skill file

```bash
# Create the directory in your Claude Code workspace
mkdir -p skills/plan-action

# Copy SKILL.md from this repository
cp claude-plan-action-skill/skill-files/SKILL.md skills/plan-action/
```

### 2. Register in your project

Add this line to your project's `CLAUDE.md` skill registry:

```markdown
| plan-action | `skills/plan-action/` | Full-task planning — decompose requirements, schedule Agents and Skills, output execution plan | `/plan-action {description}` | Describe your requirement directly |
```

### 3. Use it

```bash
/plan-action Build a user authentication system for my Flask app
```

Claude will respond with a structured plan instead of jumping straight into code.

## 📂 Repository Structure

```
├── README.md                          # English homepage
├── README.zh.md                       # Chinese homepage
├── CHANGELOG.md                       # Version history
│
├── docs/
│   └── plan-action-guide.md           # ★ Full guide (10 chapters + 3 appendices)
│
└── skill-files/
    ├── SKILL.md                       # Reusable skill definition
    ├── PLAN_TEMPLATE.md               # 5-module planning template
    └── AGENT_REGISTRY.example.json    # Agent registry example
```

## 📖 Read the Full Guide

For the complete methodology, principles, and best practices:

➡️ **[Full Guide — docs/plan-action-guide.md](docs/plan-action-guide.md)**

Covers:
- Why structured planning prevents AI hallucination
- 5-step workflow with detailed explanations
- Task classification system (S/A/B/C)
- Agent + Skill resource audit
- Feasibility assessment model
- Complete examples and templates

## 🧠 Why It Works

```
AI Coding's 3 Core Problems → Structured Planning's 3 Constraints

① Vague instructions → AI free-associates
    → Requirement analysis template eliminates ambiguity

② Long context loss → AI forgets early decisions
    → Written plan locks decisions before coding starts

③ No validation gates → Hidden defects accumulate
    → Milestone-based acceptance catches issues early
```

## 📄 License

[MIT](LICENSE) © 2026

---

> Plan first. Code second. Rework never.
