# 5 模块方案模板

在执行 `/plan-action` 时，AI 按照以下模板输出完整方案。

## 模板

```markdown
[L1] Controller | 任务分级：S/A/B/C 级

① 目标理解与拆分
   核心需求：xxx
   拆解子目标：
     1. xxx
     2. xxx
     3. xxx
   边界与约束：
     • 技术栈：xxx
     • 兼容性：xxx
     • 安全要求：xxx
     • 性能要求：xxx

② 技术路径与资源调度
   L2 Agent 链：planner → architect → deployer
   L3 SubAgent：xxx
   Skill：xxx
   MCP：xxx

③ 缺口与需协助事项
   ❌ 缺失 Skill：xxx → 影响说明
   ⚠️ 需你决策：xxx
   ⚠️ 需你提供：xxx（API Key、账号权限等）

④ 工作计划和节点
   节点 1：xxx
     目标：xxx
     验收标准：xxx
     交付物：xxx
     负责人：xxx
     预估工作量：xxx
   节点 2：xxx
     ...

⑤ 任务编排
   [串联] xxx → xxx → xxx
   [并行] xxx / xxx
   风险：xxx → 兜底：xxx
```

## 填写说明

| 模块 | 说明 | 关键要点 |
|:-----|:-----|:---------|
| **① 目标理解** | 确认你和 AI 对"做什么"达成一致 | 每个子目标必须独立可验证 |
| **② 技术路径** | 列出具体谁用什么来完成 | Agent ≠ 人，是角色定义 |
| **③ 缺口** | 诚实面对能力短板 | 缺什么一次性说清楚 |
| **④ 计划** | 可独立交付的工作单元 | 每个节点必须有验收标准 |
| **⑤ 编排** | 节点间的依赖关系 | 每个风险点要有具体兜底措施 |

## 示例

```
[L1] Controller | 任务分级：A 级

① 目标理解与拆分
   核心需求：为现有 Flask 博客系统添加 Markdown 文章导入功能
   拆解子目标：
     1. 文件上传接口（支持 .md 文件）
     2. Markdown 解析和 HTML 转换
     3. 导入预览和确认流程
     4. 导入结果展示
   边界与约束：
     • 使用现有 Flask 框架，不引入新框架
     • 数据库仍用 SQLite

② 技术路径与资源调度
   L2 Agent：architect → coder → reviewer
   Skill：无（纯代码实现）
   MCP：filesystem（操作项目文件）

③ 缺口与需协助事项
   ⚠️ 需你确认：上传文件大小限制设为多少？

④ 工作计划和节点
   节点 1：后端接口
     验收标准：POST /api/import-markdown 接受 .md 文件
     交付物：routes/import.py
     预估工作量：~80 行
   节点 2：前端界面
     验收标准：可选择文件、预览解析结果、确认导入
     预估工作量：~150 行

⑤ 任务编排
   [串联] 节点 1 → 节点 2
   风险：无
```
