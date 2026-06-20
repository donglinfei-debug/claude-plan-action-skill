---
name: plan-action
description: 全盘任务规划 — 分析需求、拆解子任务、调度 Agent 和 Skill、输出执行方案
---

# /plan-action — 全盘任务规划

当用户输入 `/plan-action` 时，进入**结构化规划模式**。规划阶段通过 Workflow 工具调度 `pre-planning-orchestrator` 实现，规划完成经你确认后，转入 `controller-workflow` 执行。

## 执行流程（两个 Workflow 阶段）

### 前置准备：收集审计数据

在调 Workflow 之前，先读取以下数据作为 Workflow 的输入参数：

1. 读取 `AGENT_REGISTRY.json` → 得到 `agentRegistry`
2. 扫描 `skills/` 目录（含 `CLAUDE.md` 技能表）→ 得到 `availableSkills`
3. 判断 `projectType`（新项目 / 已有项目变更）

### 第 1-4 步：调用 Workflow( pre-planning-orchestrator )

调用 Workflow 工具，执行前置规划编排：

```
Workflow({
  name: "pre-planning-orchestrator",
  args: {
    userRequest: "<用户原始需求>",
    projectType: "新项目 / 已有项目变更",
    availableSkills: [...],
    agentRegistry: { agents: [...] },
    techConstraints: "<技术约束>",
    hasCodebase: true/false
  }
})
```

Workflow 执行过程中将依次显示：
- `[L1] Controller: 需求解析与Agent分解中...`
- `[L1] Controller: 技能审计中...`
- `[L1] Controller: 可行性评估中...`
- `[L1] Controller: 执行计划生成中...`

Workflow 返回结构化结果后，按以下 5 模块格式呈现给你：

```
[L1] Controller | 任务分级：X 级

① 目标理解与拆分
   核心需求：<plan.taskSummary.coreGoal>
   拆解子目标：<plan.agentPlan 中各 Agent 职责>
   边界与约束：<techConstraints>

② 技术路径与资源调度
   L2 链：<decomposition.agentChain>
   L3 SubAgent：<decomposition.l3Breakdown>
   Skill 覆盖：<skillReport.coverageRate>（缺失：<missingItems>）
   风险项：<risks.length> 项

③ 缺口与需协助事项
   ❌ 缺失 Skill：[缺失清单] → 影响/建议
   ⚠️ 需你决策：[决策点]

④ 工作计划和节点
   <phases 中每个阶段：阶段名 / 验收标准 / 交付物 / 预估轮次>

⑤ 任务编排
   执行顺序：<callingOrder>
   风险与兜底：[风险清单]
```

### 第 5 步：等待确认

- 你确认 → 进入执行阶段（第 6 步）
- 你要求调整 → 重新生成或修改参数后重跑
- 你否决 → 结束

### 第 6 步：调用 Workflow( controller-workflow ) 执行

收到确认后，调用 Workflow 工具执行完整任务编排：

```
Workflow({
  name: "controller-workflow",
  args: {
    userRequest: "<用户原始需求>",
    prePlan: {
      level: "<分级>",
      agentChain: "<L2链>",
      l3Breakdown: "<L3分解>"
    }
  }
})
```

Workflow 执行过程中将依次显示：
- `[L1] Controller: 任务分级判断中...`
- `[L2] Planner: 产品域工作中...`（仅 S/A 级需要）
- `[L2] Architect: 研发域工作中...`
  - `[L3] Coder: 编码中... (节点 N)`
  - `[L3] Reviewer: 审查中... (节点 N)`
  - `[L3] Tester: 测试中... (节点 N)`
- `[L2] Deployer: 运维域工作中...`（仅 S 级需要）

## 重要规则

1. **规划阶段不编码** — pre-planning-orchestrator 只输出方案，不写代码
2. **必须等待你书面确认后才进入执行阶段**
3. **你确认后 controller-workflow 全权执行**，中间不再打断
4. B 级以下任务可简化：pre-planning 会跳过技能审计和可行性评估阶段
5. C 级任务 pre-planning 直接返回，无需走 controller-workflow 执行

## 任务分级参考

| 级别 | 适用场景 | 规划深度 | 执行链 |
|:----:|:---------|:---------|:-------|
| S | 新项目、架构变更 | 完整 4 阶段 | planner→architect→deployer |
| A | 多文件、有决策 | Agent分解+审计+评估 | planner→architect |
| B | 单文件修改 | Agent 分解（跳过审计/评估） | architect |
| C | 纯执行 | 直接返回 | 无 |

## 文件依赖

- `AGENT_REGISTRY.json` — Agent 注册表，传给 pre-planning-orchestrator
- `CLAUDE.md` — 技能清单，用于扫描 availableSkills
- `.claude/workflows/pre-planning-orchestrator.js` — 规划阶段 Workflow 脚本
- `.claude/workflows/controller-workflow.js` — 执行阶段 Workflow 脚本
