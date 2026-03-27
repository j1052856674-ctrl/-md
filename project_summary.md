# 项目总结报告中心 (Project Summary Hub)

> **全局协作底座**：[AI 协作准则 v2.2](./AI协作准则.md)  
> **核心机制**：合规闸门 | 每日单一备份 | 变更同步更新 | 异步分析降本

---

## 🧰 项目一：Groovy 自动化协作工具
> **状态**：执行中 | **工作目录**：`./groovy-auto/`

### 1. 核心架构与规范 (Architecture & Specs)
- **技术栈**：Groovy 4.x。
- **编码约束**：禁止使用 `import`；必须使用全限定名（Fully Qualified Name）；离线 Mock 仅关注 `@服务` 返回对象。

### 2. 关键决策 (Key Decisions)
- [2026-03-26] 确立全限定名调用规范与 Mock 场景覆盖策略，确保脚本环境无关性。

### 3. 进展记录 (Progress)
- **2026-03-26**：项目初始化，产出核心规范文档并生成首个示例脚本 [gift_card_status.groovy](./generated/gift_card_status.groovy)。

### 4. 未来计划 (Roadmap)
1. 定义从“业务需求”到“生成配置”的标准化结构化输入格式。
2. 制定针对异常、边界值的离线 Mock 数据模版。

---

## 📊 项目二：金融 DataAgent 智能问数平台
> **状态**：方案设计 (v3.1 Final) | **工作目录**：`./data_agent/`

### 1. 核心架构与规范 (Architecture & Specs)
- **Agent 矩阵**：Router/Semantic/SQL/Insight/Report 五位一体。
- **闭环逻辑**：SQL 执行自愈闭环 | 歧义确认环 (Router↔Semantic) | 迭代安全阀 (Max 5)。
- **降本设计**：IntentClassifier 分流；SchemaRetriever 压缩上下文；先出数后分析。

### 2. 关键决策 (Key Decisions)
- [2026-03-27] 架构演进至 v3.1，重点解决归因死循环与语义歧义风险。
- [2026-03-27] 确立“异步洞察”模式，将 Token 消耗从固定开销转为按需触发。

### 3. 进展记录 (Progress)
- [2026-03-27] **架构模块化极简 v4.0**：四泳道垂直布局、节点名称标准化`中文(English)`、知识层封装为单一语义知识库节点、用户层精简为Web界面、调度层移除Insight/Report平铺、Mermaid Tooltips交互式降噪挂载子组件信息、安全阀解耦为悬浮红色虚线标注；已更新架构图；已备份 `DataAgent_Architecture_bak_20260327_6.html`。
- [2026-03-27] **架构视觉重构 v3.2**：四泳道聚合分层（用户交互层青色/调度中枢黄色/知识层蓝色/执行层红色）、移除连线杂讯文本、安全阀视觉解耦、连线规范化（粗实线主流程/细虚线反馈流）、增加交互图例模块、更新数据流表和时序图；已更新架构图；已备份 `DataAgent_Architecture_bak_20260327_5.html`。
- [2026-03-27] **架构工业级微调 v3.1**：增加调度-语义双向反馈环（RouterAgent↔SemanticAgent歧义确认）、多轮归因安全阀（Max Iterations=5）、知识库层级化关联（SKB→SchemaRetriever知识实时注入虚线）；已更新架构图；已备份 `DataAgent_Architecture_bak_20260327_4.html`。
- **2026-03-27**：完成工业级架构闭环微调，更新 v3.1 架构图并同步技术决策。

### 4. 未来计划 (Roadmap)
1. 定义 `SemanticAgent`（指标专家）的“指标字典”接口规范。
2. 开发 Chat-as-a-Dashboard 交互式 MVP 原型。

---

## 🏗️ 项目三：AI 协作体系 (基础设施)
> **状态**：常态化运行 | **文档**：[AI协作准则.md](./AI协作准则.md)

### 1. 核心架构与规范 (Architecture & Specs)
- **流程规范**：【合规检查】+【方案设计】->【长官批准】->【实质执行】。
- **备份规范**：修改前创建 `.backups/` 备份，每日一更，后缀 `bak_YYYYMMDD`。

### 2. 关键决策 (Key Decisions)
- [2026-03-27] 引入上下文管理（Rule 17）与回滚机制（Rule 18），提升长周期协作稳定性。

### 3. 进展记录 (Progress)
- **2026-03-27**：总结中心标准化重构。强制执行五段式项目模版，移除冗余信息流。
- **2026-03-27**：准则升级 v2.2。整合性能与安全评估准则，优化工程化规则。

### 4. 未来计划 (Roadmap)
1. 建立针对 Agent 响应质量的自动化评估日志。