# Changelog

## v1.1.1 (2026-06-20)

### 📝 文档增强

- **README.zh.md**：新增「🚀 方法论全景」板块，可视化展示任务分级体系、两阶段执行流程（Mermaid 流程图）、三层 Agent 架构、五模块方案模板，降低新用户理解门槛

## v1.1.0 (2026-06-20)

### ✨ Workflow 驱动升级

- **SKILL.md**：从手动提示词驱动升级为 Workflow 工具驱动
  - 规划阶段：调用 `pre-planning-orchestrator`，显示 `[L1] Controller` 实时标签
  - 执行阶段：调用 `controller-workflow`，显示 L1→L2→L3 全链路标签
  - 用户确认关卡保留：规划后等待确认，确认后进入执行
- **文档**：`docs/plan-action-guide.md` 第八章更新安装说明、目录结构和配置步骤
- **示例**：`AGENT_REGISTRY.example.json` 新增 L1 Controller 角色

## v1.0.0 (2026-06-20)

### ✨ 初始发布

- 首次发布 plan-action 公开指南
- 文档 `docs/plan-action-guide.md`：10 章 + 3 附录完整指南
- 配套文件：可复用的 SKILL.md、PLAN_TEMPLATE.md、AGENT_REGISTRY.example.json
- 仓库首页：中英双语 README（README.md + README.zh.md）
