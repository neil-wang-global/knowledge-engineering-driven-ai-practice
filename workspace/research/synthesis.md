# Synthesis

## 核心论点

AI Coding 的关键不是“让模型多写代码”，而是把软件工程基本功放大成可运行、可验证、可复盘的 AI 工作系统。SoC、抽象、目录结构、接口契约和测试验证不是旧时代遗产，而是 AI 时代控制上下文、角色边界、状态反馈和代码产出水平的底层机制。

## 演讲逻辑

1. 从反直觉开场：不要从提示词技巧讲起，而从软件工程基本功讲起。
2. SoC、抽象、目录结构分别对应关注点边界、上下文压缩、作为数据结构的工程空间；讲述时使用 `STORY-ENT-001`、`ADR-012`、API spec、code、test、review、eval 的链路示例。
3. MindFlow 略讲思维：它把目标约束、学习材料、能力单元、计划步骤和任务状态文件化，用工程结构降低 AI 理解任务的成本。
4. 知识工程说明知识不是文档仓库，而是把问题、判断标准、信息来源、方法和交付形式组织成可执行资产。
5. Skill 与工程文档是可执行知识，不是说明书；它们定义 Agent 的运行约束、输入输出 schema、校验规则和链接规则。
6. 敏捷与单仓库协作：BA/DEV/QA/UI/Agent 是角色，不是固定人；Story 是动态知识，Knowledge 是静态 Story；敏捷工件变成可执行、可检查、可回流的强状态。
7. POMASA 略讲思维：作为声明式 MAS 样本，说明 Agent 系统需要 Blueprint、references、workspace、输出边界和可追溯数据血缘。
8. Agent 设计从角色协议开始，定义上下文、权限、输入、输出、契约、验收。
9. 提速来自控制代码产出水平：任务粒度、上下文、边界、验证，而不是盲目加速。
10. 测试/eval/检测让提速可持续。
11. 对比 Vibe Coding、轻量 SDD、Sub-agent、分层 Plan、强状态编排。
12. 工具层改造：CLI for Agents、MCP、Skill 注入。
13. 无人值守：责任不是消失，而是前置到 workflow、权限、状态、测试、review。
14. 展望：Agent Teams、架构形态变化、框架为了消灭自己而存在。

## 第 9 章敏捷与单仓库展开

敏捷不是被 AI 绕过的“流程负担”，而是天然的强状态生成机制。Story 记录业务意图，AC 记录可验收边界，Backlog 记录优先级与未解决问题，Sprint 记录节奏，DoR 记录能否开始，DoD 记录是否完成，Review 记录 outcome，Retro 记录如何吸收失败。这些工件原本为人类协作服务；AI 加入后，它们变成 Agent 可读、可检查、可回流的状态层。

Story 是动态知识，因为它会随着 BA 澄清、DEV 设计、QA 测试、UI 走查和客户验收不断变化。Knowledge 是静态 Story，因为一旦这些变化被确认，就应该沉淀成 AC、ADR、测试、Skill、eval case、review checklist。单仓库中的关键链路示例是：`STORY-ENT-001` → `ADR-012` → `API-ENT-001` → code → test → review → eval。

单仓库不是代码集中管理，而是 BA / DEV / QA / UI / Agent 共享同一个强状态空间。仓库中应包含 PRD/user story、UX/UI spec、domain model、plan、task state、implementation、test cases、review notes、eval cases、release notes、knowledge updates。每个角色既贡献产物，也检查其他角色产物：BA 检查实现是否符合业务意图；DEV 检查需求是否可实现；QA 检查验收是否可测试；UI 检查用户路径；DEV 检查 UI 技术约束；Agent 在边界内执行、生成、检查和回填。

## 引用映射

- MindFlow：第 6 章，引用 [SRC-001][SRC-002][SRC-003][SRC-004]。
- POMASA：第 10 章，引用 [SRC-005][SRC-006][SRC-007][SRC-008]。
- 上下文管理：第 5 章，引用 [SRC-024][SRC-002]。
- Harness Engineering：第 11、13、14 章，引用 [SRC-020][SRC-021][SRC-050][SRC-053][SRC-054]。
- Eval：第 12 章，引用 [SRC-026][SRC-052]。
- 敏捷/单仓库：第 9 章，引用 [USER-INPUT][SRC-025]。
