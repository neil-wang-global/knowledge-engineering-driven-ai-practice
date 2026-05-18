# Synthesis

Project: ai-work-system-speech-20260518

## Executive Narrative

本次演讲的主轴必须固定为：如何构建统一流程，以及如何构建一个高质量的统一流程。所有材料都应服务于这条主线，而不是堆叠 AI Coding、Agent、MAS、Skill、Eval、Harness 等概念。

整场演讲可以用一句话统领：AI-native workflow 是“模型推理 + 流程约束 + 状态反馈”的动态系统。模型负责推理，流程负责约束，状态负责让推理结果可以被恢复、检查和交接。强模型降低了“让模型会做”的成本，但没有取消“让系统稳定、可控、可复查地交付”的问题。工程化与 SDD 的价值从能力补丁迁移到治理工具，用来阻止模型过早开始写代码、过早收束和遗漏边界。[USER-002][SRC-011]

演讲应从软件工程基本功讲起，但不要停留在定义。SoC、抽象/面向对象、目录结构、契约和测试，在 AI 文件工程中重新变成可执行知识的组织原则：文档小而精，职责明确；依赖用 ID、链接和引用维护；目录结构成为 Agent 可导航的知识地址空间；确定性的检查交给确定性工具。[USER-003][SRC-017][SRC-018]

MindFlow 和 POMASA / MAS 是两个关键案例。MindFlow 用 Soul、Learning、Capability、Plan、Task State、Reflection 等结构说明：智能系统不是把所有上下文塞进 prompt，而是把长期原则、知识、能力、执行状态和反思分层管理，形成可恢复、可交接、可演进的知识空间。[SRC-022][SRC-023] POMASA / MAS 则说明多智能体系统不是多个 Agent 聊天，而是通过 Blueprint、Pattern、Filesystem Data Bus、Orchestrated Pipeline 和 Verifiable Data Lineage 组织多角色、多产物、多阶段协作。[USER-005][SRC-026][SRC-027]

在此基础上，演讲进入状态控制三分法：强约束固定、有建议的 AI 自主判断、完全 AI 控制。三者体现可靠性与灵活性的反向关系。Rules / Hooks、固定检查点、必读工程文件、测试和验收属于强约束；Skill、推荐流程、可选 checklist 属于建议式调度；模型自行决定读什么、做什么、何时停属于完全 AI 控制。高质量流程不是选择一种控制方式，而是按风险、成本、开放度和治理要求组合使用。[USER-006][SRC-011][SRC-013][SRC-017]

Knowledge 与 Story 的关系是本演讲的知识工程核心。Story 是动态知识，Knowledge 是静态 Story。每个 Story 像一次 Flyway Migration，携带时间性、变化意图和业务增量；Knowledge 像所有 migration 执行后的当前数据库状态。高质量流程必须把 Story 中被验证的知识回写到代码、工程文档、Skill、Capability、测试、eval case 或 workflow pattern 中。[USER-004][SRC-002][SRC-014]

团队协作部分必须围绕“角色而非人”。BA / DEV / QA / UI / Agent 是思考帽，不是固定人头。单仓库原则是关键：仓库是 BA / DEV / QA / UI / Agent 共享的强状态空间。统一流程贯穿输入到输出：需求进入，经过 Tasking、澄清、设计、计划、实现、Review、测试和验收，最后代码出去，并且验收测试通过。Tasking 是把模糊需求变成可执行、可验证、可分派任务结构的过程，是 SDD 在团队协作中的前置动作。[USER-007][SRC-002][SRC-008][SRC-014][SRC-018]

自动化与无人值守只能在强状态、角色协议、工程文件、测试与回写机制建立后再讲。它不是完全无人值守，而是长时间、低人工干预：通过明确任务边界、feature list、progress file、clean state、worktree 隔离、自动测试、浏览器验证、可观测、人工 gate 和失败回流，让 Agent 可以跨 session、跨上下文窗口持续推进。[USER-007][SRC-015][SRC-018][SRC-007]

最后的 Agent 设计、提速、测试评估、AI 编排、工具层改造和展望，必须回扣统一流程。Agent 不是万能助手，而是由角色协议定义上下文、权限、输入、输出、契约和验收的流程节点。提速不是 token 生成速度，而是流程缩短、上下文传递损耗下降、反馈更快、测试更靠前、失败更快变成资产。工具层也不能只面向人类体验，而要为 Agent 提供 JSON、schema、字段裁剪、输入防御、可观测和安全边界。[USER-008][SRC-001][SRC-004][SRC-005][SRC-006][SRC-013][SRC-014][SRC-017][SRC-018]

## Chapter Blueprint

### 0. 为什么还要工程化与 SDD
- Purpose: 用最短路径回答听众的核心疑问：模型越来越强，为什么还需要工程化、SDD、流程、规则和状态。
- Key Arguments:
  - 强模型吸收了一部分 planning、tool use 和 agentic orchestration，但工程方法并未失效，而是从能力补丁变成治理工具。
  - 现实问题不只是模型不会写代码，而是模型太快开始写代码：需求未澄清、边界未定义、验证未设计，代码已经生成。
  - SDD 的价值是把“先想清楚”制度化，把意图、约束、中间产物、检查点和验收标准显化。
  - 本场演讲关注的不是让模型多写代码，而是构建统一流程和高质量流程。
- Evidence: [USER-001][USER-002][SRC-011][SRC-002][SRC-017]
- Writing Notes:
  - 开场要短而有判断力，避免泛泛介绍 AI Coding。
  - 可使用“强模型降低了让模型会做的成本，但没有取消让系统稳定交付的问题”作为核心表达。
  - 不要把 SDD 说成提高模型智力，应说成治理、澄清和护栏前置。

### 1. 软件基本功：SoC、抽象/面向对象、文件目录结构
- Purpose: 说明 AI 编程不是推翻软件工程，而是放大软件工程基本功。
- Key Arguments:
  - SoC 迁移到 AI 文件工程，就是 Story、ADR、Spec、Plan、State、Review、Eval 各自承担清晰职责。
  - 抽象/面向对象迁移到 Skill、Rules、工程文件、Capability、Agent Blueprint 等边界清楚的知识对象。
  - 目录结构不是收纳方式，而是知识对象的地址空间，影响 Agent 是否能找到、理解、验证上下文。
  - 上下文管理不是越多越好，而是给模型低噪声、可处理、可验证的上下文。
- Evidence: [USER-003][USER-008][SRC-001][SRC-003][SRC-017][SRC-018]
- Writing Notes:
  - 本章略写，但态度必须明确。
  - 避免给 SoC/OOP 下教科书定义，直接讲它们在 AI 文件工程中的复刻方式。
  - 可自然引出 MindFlow：如果目录、引用和状态重要，就需要一个可演进的知识空间。

### 2. MindFlow 的自我演进与知识工程
- Purpose: 用 MindFlow 说明智能系统如何通过模块化、解耦、渐进加载、状态和反思形成自我演进能力。
- Key Arguments:
  - MindFlow 不应讲成项目说明书，而应讲成知识工程系统：长期原则、正式知识、能力、计划、状态和反思分层管理。
  - Lazy loading 说明上下文管理是流程设计问题，不是省 token 小技巧。
  - Task State 和 Artifact Data Flow 让任务可恢复、可检查、可交接。
  - 软件系统的本质就是知识，智能 AI Agent 系统也是知识。代码、文档、测试、规则、任务状态和运行反馈都是知识的表达。
  - AI 是未来新软件，正在降低把业务知识变成可运行系统的门槛，推动数字民主化。
- Evidence: [USER-004][USER-008][SRC-012][SRC-022][SRC-023][SRC-024][SRC-025]
- Writing Notes:
  - 少讲文件夹细节，多讲设计思想。
  - 必须保留“软件即知识、Agent 系统即知识、AI 作为未来新软件与数字民主化”。
  - 数字民主化属于用户原创判断，应作为项目观点表达，不要伪装为外部事实。

### 3. ProMaster / POMASA 与 MAS 的强状态
- Purpose: 纠正“MAS = 多个 Agent 聊天”的误解，把 MAS 讲成围绕状态推进的编排系统。
- Key Arguments:
  - MAS 的关键是：谁读取什么，谁产出什么，产物放在哪里，谁验收，失败如何回流，下一步由谁接手。
  - MindFlow 讲认知结构和自我演进，POMASA / MAS 讲多角色、多产物、多阶段组织方式。
  - POMASA 的定义层、执行层、数据层，以及文件系统数据总线，说明 MAS 需要强状态和可追踪产物谱系。
  - AI-native workflow = 模型推理 + 流程约束 + 状态反馈的动态系统。
- Evidence: [USER-005][SRC-013][SRC-026][SRC-027][SRC-028]
- Writing Notes:
  - “ProMaster / POMASA”按用户章节名保留；证据主要来自 POMASA。
  - 如果写到 ProMaster 具体事实，当前证据不足，应弱化为“这一类实践”。
  - 不要把 MAS 讲成炫技，重点讲状态、产物、验收、回流。

### 4. 状态控制三分法
- Purpose: 建立后续 Skill、工程文件、Rules、Agent 编排的控制框架。
- Key Arguments:
  - 第一类：强约束固定。适合安全边界、权限、验收、格式、提交前检查、必须执行的测试。
  - 第二类：有建议的 AI 自主判断。适合 Skill、推荐流程、可选 checklist，灵活但存在漏触发和误触发。
  - 第三类：完全 AI 控制。适合探索、低风险实验和一次性任务，灵活性最高但可靠性最低。
  - 可靠性与灵活性反向相关。高质量流程靠组合：强约束兜底，建议式能力补充，AI 自主负责开放探索。
- Evidence: [USER-006][USER-008][SRC-011][SRC-013][SRC-017]
- Writing Notes:
  - 本章是桥梁，不要展开太长。
  - 可用 workflows 与 agents 的区别支撑“固定路径更可预测，自主 agent 更灵活”。
  - 避免把三分法说成外部标准；这是用户原创工程分类，有外部材料支撑。

### 5. Skill、工程文件与 Rules
- Purpose: 把状态控制三分法落到可执行知识资产。
- Key Arguments:
  - Skill、工程文件和 Rules 本质都是可执行知识：人的经验、判断标准、流程约束和输出格式被组织成 Agent 可读取、可执行、可检查的上下文资产。
  - Skill 调度更随机，依赖触发条件与模型判断；工程文件处在流程规定位置，调度更确定；Rules / Hooks 接近强约束固定调度。
  - 成熟 Skill 不是提示词片段，而是包含触发、输入、步骤、输出、权限、副作用和验证的工程资产。
  - Skill、工程文件、Rules 要组合使用：Skill 提供可复用能力，工程文件提供结构化上下文和流程位置，Rules 提供确定性约束。
- Evidence: [USER-006][SRC-001][SRC-011][SRC-017][SRC-018][SRC-019][SRC-027]
- Writing Notes:
  - 必须明确 Skill 随机调度、工程文件确定编排、Rules Hook 式强约束的差异。
  - 可用 CLI for AI Agents 的 `SKILL.md` 思想支撑“Agent 需要结构化技能，而不是读 --help”。
  - 不要把 Skill 讲成唯一形态，要强调结构化、模块化和可验收。

### 6. Knowledge 与 Story
- Purpose: 建立知识工程中的核心概念，把代码工程、需求、设计、测试与知识沉淀统一起来。
- Key Arguments:
  - Story 是动态知识，Knowledge 是静态 Story。
  - User journey 是团队发现、验证、固化知识的过程。
  - 每次需求、设计、实现、测试和验收，都是知识被发现、修改和固化。
  - 高质量流程要求知识不能只留在对话里或个人脑中，而要沉淀为 AC、ADR、工程文档、Skill、Capability、测试、eval case 或 workflow pattern。
- Evidence: [USER-004][USER-007][SRC-002][SRC-004][SRC-012][SRC-014]
- Writing Notes:
  - 本章要为 Flyway 类比铺垫，不要提前把类比完全讲完。
  - 这是用户原创观点，应清晰保留。
  - 外部材料用于支撑工程资产回写、反馈闭环和 eval case，不替代用户观点。

### 7. Flyway Migration 类比
- Purpose: 用技术听众熟悉的 migration 类比，解释 Story 到 Knowledge 的演进。
- Key Arguments:
  - 每个 Story 像一个 migration，带着时间性、变化意图和增量。
  - Knowledge 像所有 migration 执行完后的当前数据库状态。
  - Story 有时效性，长期维护困难；被验证的增量应回写到当前 Knowledge、工程文档、Skill、测试或 eval case。
  - 流程不闭环时，资产不增长；有回写闭环时，Knowledge 随代码和文档自然增长。
- Evidence: [USER-004][USER-007][SRC-002][SRC-014]
- Writing Notes:
  - Flyway 类比是用户原创，不需要外部证明，但要避免过度延展到数据库细节。
  - 可作为全场从“知识工程”转向“验收与流程”的关键转场。

### 8. Skill 与 Story 的验收
- Purpose: 说明高质量流程的关键不是“定义了 Skill / Story”，而是它们能否被稳定验收。
- Key Arguments:
  - Skill / Rule 像函数一样验收：触发条件、输入、前置假设、步骤、输出、错误处理、权限边界、副作用、验证方式、下游可消费性。
  - Story 验收要看业务意图、AC、依赖、边界、可测试性、最终状态，以及完成后是否能沉淀到 Knowledge。
  - Agent eval 的核心是输入、grading logic、transcript / trace、outcome，不应只看模型声称完成。
  - 确定性的事交给确定性工具，推理判断交给模型或人。
- Evidence: [USER-006][USER-007][USER-008][SRC-001][SRC-014][SRC-017][SRC-027]
- Writing Notes:
  - 本章要把 Skill 验收和 Story 验收放在同一质量框架下。
  - 可强调“无法验收的 Skill 只是经验片段，还不是稳定工程资产”。
  - 不要引用未经核验的具体指标。

### 9. 角色而非人
- Purpose: 从知识资产进入团队协作，说明 BA / DEV / QA / UI / Agent 是角色协议和思考帽。
- Key Arguments:
  - 角色是能力和责任边界，不等同于固定人头；同一个人可戴多顶帽子，一个 Agent 也可承担某些帽子动作。
  - 单仓库原则：仓库是 BA / DEV / QA / UI / Agent 共享的强状态空间。
  - 传统产运研组织有部门墙、协调税和信息损耗；AI 的价值之一是压低上下文传递成本和重复解释成本。
  - 人类角色转向设定目标、边界、反馈和治理；Agent 承担执行、检索、检查和验证等动作。
- Evidence: [USER-005][USER-007][SRC-008][SRC-014][SRC-018]
- Writing Notes:
  - 避免写成“人越少越好”。重点是协作结构和知识传递方式变化。
  - 可用“思考帽”作为口语化比喻。

### 10. 统一流程与单线程协作
- Purpose: 展开全场重心：需求进来，代码出去，验收测试通过；每一步都有输入、输出、状态、角色、检查点和回写位置。
- Key Arguments:
  - 统一流程包括 Tasking、澄清、设计、计划、实现、Review、测试、验收、代码输出和知识回写。
  - Tasking 是需求分析与拆解，把业务意图、用户路径、验收标准、边界条件、依赖关系和风险变成可执行、可验证、可分派任务结构。
  - 这个流程不是 checklist，而是资产生产线。
  - 流程中必须同步更新和维护 Skill、工程文件、Knowledge 或类似 `SOUL.md` 的长期原则文件。
  - 单线程流程先保证从输入到输出的闭环质量，再谈并行和自动化。
- Evidence: [USER-007][SRC-002][SRC-014][SRC-017][SRC-018][SRC-024]
- Writing Notes:
  - 这是全稿最重要章节之一，应讲得具体。
  - 必须保留“需求进入，经过 Tasking、澄清、设计、计划、实现、Review、测试和验收，最后代码出去，并且验收测试通过”。
  - `SOUL.md` 是类比性工程文件，除 MindFlow Soul 可由 [SRC-022][SRC-023] 支撑外，不要声称所有项目都有同名文件。

### 11. 多线程协作流程
- Purpose: 在单线程闭环成立后，引出 Epic 到 User Story、依赖解析和 Worktree 并行。
- Key Arguments:
  - 多线程流程从 Epic 到 User Story，先解析 Story 依赖，再用 Worktree 等隔离机制并行推进功能增量。
  - Worktree 是隔离机制，不是随意并发；每个分支都需要状态、测试、Review、合并门禁和回写。
  - 多线程不是跳过流程，而是把统一流程复制到多个隔离工作流中，并通过依赖、状态和验收汇合。
  - 并行提速来自减少等待和协调损耗，但质量仍由强状态、测试、Review 和验收保证。
- Evidence: [USER-007][USER-008][SRC-015][SRC-018]
- Writing Notes:
  - 目前关于自动解析依赖的外部证据较少，应作为用户设计方向或工程建议表达。
  - 可结合 OpenAI per-worktree app 和 Anthropic long-running agent 的 clean state、feature list。

### 12. 自动化与无人值守
- Purpose: 说明在统一流程、强状态和验收体系成立后，如何走向长时间、低人工干预。
- Key Arguments:
  - 无人值守不是完全自主魔法，而是明确边界下的低人工介入。
  - 长时间 Agent 的核心挑战是跨上下文窗口和跨 session 的状态连续性。
  - feature list、progress file、git history、clean state、单 feature 增量推进、自动测试和浏览器验证，是可恢复、可检查的实践。
  - Agent Runtime 需要文件系统、命令执行、服务访问、长连接、隔离、安全和资源回收。
  - 自动化演进路径：单线程到多线程，手动协作到自动编排，Agent 执行到 Agent Teams；Agent Teams 放在展望。
- Evidence: [USER-007][SRC-007][SRC-015][SRC-016][SRC-018][SRC-009]
- Writing Notes:
  - 必须强调“长时间、低人工干预”，不要写成完全无人值守。
  - 失败模式也要讲：过早宣布完成、无进度记录、过早标记 done、猜测运行方式。

### 13. Agent 设计、提速、测试评估、AI 编排、工具层改造、展望
- Purpose: 把具体实践放回统一流程，说明如何构建高质量流程。
- Key Arguments:
  - Agent 设计从角色协议出发，定义上下文、权限、输入、输出、契约、验收，而不是造万能助手。
  - 提速来自上下文管理、渐进加载、分层计划、角色协议、自动验证、评估闭环、工具层改造和减少协调税，不是 token 生成速度。
  - AI 编排应从简单开始，按任务条件选择 prompt chaining、routing、parallelization、orchestrator-workers、evaluator-optimizer 或 autonomous agents；复杂不等于先进。
  - 测试评估要关注 task、trial、grader、trace、outcome、evaluation suite；失败是 eval case 的来源。
  - 可观测让推理、工具调用、轨迹和质量问题可追踪、可诊断、可迭代。
  - 工具层要区分人类体验与智能体体验：Agent 需要 JSON、schema、字段裁剪、输入防御、权限边界和结构化 Skill。
  - Agent 是不受信任的操作员，工具层要做纵深防御。
  - 展望可以讲 Agent Teams 与组织形态变化，但要克制。
- Evidence: [USER-008][SRC-001][SRC-004][SRC-005][SRC-006][SRC-007][SRC-008][SRC-013][SRC-014][SRC-017][SRC-018][SRC-020][SRC-021]
- Writing Notes:
  - 本章内容多，写作时应按“高质量流程需要什么能力”组织，不要按资料逐篇介绍。
  - pass@k vs pass^k 可轻讲，若使用具体数学解释需回查来源；当前 synthesis 不建议写成重点。
  - “框架是为了消灭自己而存在”是用户要求的 thought，可作为工程判断表达，外部支撑可用 harness not framework 相关材料，但不要当成原文引用。

### 14. 附录/Q&A
- Purpose: 收纳主线外但听众可能关心的问题，避免打断主干叙事。
- Key Arguments:
  - Promptfoo / Braintrust / LangSmith / Langfuse 可放入 Agent eval 和 observability 工具问答。
  - SWE-bench / Terminal-Bench 可放入 benchmark 问答。
  - 上下文压缩、平台差异、具体工具选型、GUI Agent 三层架构、OpenSandbox Runtime 细节可作为备选。
  - Q&A 应回到统一流程、高质量流程、证据、状态和验收。
- Evidence: [USER-008][SRC-001][SRC-005][SRC-006][SRC-007][SRC-014][SRC-018]
- Writing Notes:
  - 附录不应扩成第二篇报告。
  - 对未在 raw notes 中充分核验的工具和平台，不要给出确定性推荐。

## Evidence Map

| Chapter | Primary Evidence | Gap / Caution |
|---|---|---|
| 0. 为什么还要工程化与 SDD | [USER-001][USER-002][SRC-011][SRC-002][SRC-017] | 中低端模型“过早收束”主要来自用户判断，可作为工程经验表达，避免写成外部研究结论。 |
| 1. 软件基本功 | [USER-003][USER-008][SRC-001][SRC-003][SRC-017][SRC-018] | SoC/OOP 到 AI 文件工程是概念迁移，属于分析框架，不应声称外部资料逐字提出。 |
| 2. MindFlow | [USER-004][SRC-012][SRC-022][SRC-023][SRC-024][SRC-025] | 数字民主化是用户原创判断；MindFlow 具体描述使用 GitHub URL 或本地 web archive，不用本机绝对路径。 |
| 3. ProMaster / POMASA 与 MAS | [USER-005][SRC-013][SRC-026][SRC-027][SRC-028] | ProMaster 缺少独立证据，应弱化具体事实，主证据放在 POMASA。 |
| 4. 状态控制三分法 | [USER-006][USER-008][SRC-011][SRC-013][SRC-017] | 三分法是用户原创工程分类，外部资料只作支撑。 |
| 5. Skill、工程文件与 Rules | [USER-006][SRC-001][SRC-011][SRC-017][SRC-018][SRC-019][SRC-027] | Skill 生命周期不要采用未确认方案；强调验收标准即可。 |
| 6. Knowledge 与 Story | [USER-004][USER-007][SRC-002][SRC-004][SRC-012][SRC-014] | Knowledge/Story 定义为用户原创概念，需保留原意。 |
| 7. Flyway Migration 类比 | [USER-004][USER-007][SRC-002][SRC-014] | Flyway 类比无需外部事实支撑，但不要扩写为数据库教程。 |
| 8. Skill 与 Story 验收 | [USER-006][USER-007][USER-008][SRC-001][SRC-014][SRC-017][SRC-027] | 如写具体 eval 指标或 pass@k，应回查原文。 |
| 9. 角色而非人 | [USER-005][USER-007][SRC-008][SRC-014][SRC-018] | 避免“AI 代替团队”或“人越少越好”的结论。 |
| 10. 统一流程与单线程协作 | [USER-007][SRC-002][SRC-014][SRC-017][SRC-018][SRC-024] | `SOUL.md` 类文件应作为长期原则文件类比，避免泛化为行业标准。 |
| 11. 多线程协作流程 | [USER-007][USER-008][SRC-015][SRC-018] | 自动解析 Story 依赖外部证据不足，应作为设计方向。 |
| 12. 自动化与无人值守 | [USER-007][SRC-007][SRC-015][SRC-016][SRC-018][SRC-009] | Agent Teams 放展望，不宜写成已成熟全自治组织。 |
| 13. Agent 设计等实践 | [USER-008][SRC-001][SRC-004][SRC-005][SRC-006][SRC-007][SRC-008][SRC-013][SRC-014][SRC-017][SRC-018][SRC-020][SRC-021] | 材料很多，写作时按统一流程能力组织，不按来源堆砌。 |
| 14. 附录/Q&A | [USER-008][SRC-001][SRC-005][SRC-006][SRC-007][SRC-014][SRC-018] | 工具名和 benchmark 若要详细介绍需补充核验。 |

## Risk and Gap Notes

1. ProMaster 证据不足。用户章节要求写“ProMaster / POMASA”，但当前 source inventory 和 raw notes 中主要证据是 POMASA。写作时可保留章节名，但具体事实应围绕 POMASA；ProMaster 若无补充来源，只能作为用户语境中的并列实践提及。

2. 状态控制三分法、Knowledge / Story、Flyway Migration 类比、AI 是未来新软件、数字民主化等是用户原创观点。它们必须保留，但引用方式应标注为项目观点或用户输入，不要伪装成外部资料结论。

3. “中低端模型容易过早收束、遗漏边界”来自用户输入和工程经验。可在开场作为实践观察表达，用 [USER-002] 支撑；如果写成普遍模型研究结论，需要另行补充来源。

4. 自动解析 Story 依赖、Agent Teams、完全无人值守等方向要克制。当前证据支持 Worktree 隔离、feature list、progress file、long-running harness、per-worktree app 和低人工介入，不支持夸大为完全自治组织。

5. pass@k vs pass^k、具体平台差异、Promptfoo / Braintrust / LangSmith / Langfuse、SWE-bench / Terminal-Bench 等在 user input 中出现，但 raw notes 未充分展开。建议放附录或 Q&A；如主稿使用，需要补充核验。

6. 引用本地资料时必须使用 repository-relative paths，例如 `references/papers/CLI_for_AI_Agents.pdf`、`references/web/24-mp-weixin-qq-com-s-b4Fh-3SQyWiB1HypUxk9wA.md`。MindFlow 和 POMASA 项目资料优先使用 GitHub URL，不使用本机绝对路径。

7. 不要修改或删除 `references/papers/`、`references/paper-visual/`、`references/web/` 下的证据材料。本 synthesis 只写入 `workspace/research/synthesis.md`。

## Instructions for Speech Writer

1. 全稿始终围绕“构建统一流程、构建高质量流程”。每个概念都要回答它在流程中的位置：输入是什么、输出是什么、状态在哪里、谁负责、如何验收、失败如何回流、知识如何沉淀。

2. 保持用户要求的章节顺序：
   0. 为什么还要工程化与 SDD。
   1. 软件基本功：SoC、抽象/面向对象、文件目录结构。
   2. MindFlow 的自我演进与知识工程。
   3. ProMaster / POMASA 与 MAS 的强状态。
   4. 状态控制三分法。
   5. Skill、工程文件与 Rules。
   6. Knowledge 与 Story。
   7. Flyway Migration 类比。
   8. Skill 与 Story 的验收。
   9. 角色而非人。
   10. 统一流程与单线程协作。
   11. 多线程协作流程。
   12. 自动化与无人值守。
   13. Agent 设计、提速、测试评估、AI 编排、工具层改造、展望。
   14. 附录/Q&A。

3. 必须保留并分配用户原创观点：
   - 模型负责推理，流程负责约束，状态负责让推理结果可以被恢复、检查和交接。用于第 0、3、10 章。
   - Story 是动态知识，Knowledge 是静态 Story。用于第 6、7 章。
   - AI-native workflow = 模型推理 + 流程约束 + 状态反馈的动态系统。用于第 0、3、10 章。
   - 单仓库原则：仓库是 BA / DEV / QA / UI / Agent 共享的强状态空间。用于第 9、10、11 章。
   - AI 编程不是推翻软件工程，而是放大软件工程基本功。用于第 1 章。
   - 软件系统的本质就是知识，智能 AI Agent 系统也是知识。用于第 2、6 章。
   - AI 是未来新软件，推动数字民主化。用于第 2 章。
   - Tasking 是把模糊需求变成可执行、可验证、可分派任务结构的过程。用于第 10 章。

4. 语气要求：中文口语化、专业、有工程判断；语言干净、简单、简练；避免营销化、焦虑式表达和泛泛行业评论；减少“不是……而是……”的高频使用。

5. 引用原则：外部事实、术语、案例和具体实践必须引用 `SRC-xxx` 对应来源。用户观点用 `USER-xxx` 支撑。最终演讲稿可采用自然引用或章节后引用列表，但必须可追溯。

6. MindFlow 与 POMASA 写法：讲设计思想，不写项目说明书。MindFlow 重点是知识分层、渐进加载、Task State、Artifact Data Flow、Reflection、自我演进。POMASA 重点是 Blueprint、Pattern、Filesystem Data Bus、Orchestrated Pipeline、Verifiable Data Lineage 和强状态 MAS。

7. Skill / Rules 写法：不要把 Skill 写成提示词技巧。要写成可执行知识资产，并用函数式验收框架讲触发、输入、步骤、输出、验证、权限、副作用和下游可消费性。

8. 统一流程写法：第 10 章是全稿重心，必须具体描绘从需求进入到代码输出和验收测试通过的单线程闭环，并说明 Skill、工程文件、Knowledge、`SOUL.md` 类长期原则文件如何随流程同步维护。

9. 自动化写法：第 12 章必须强调低人工介入、长时间运行、强状态、Worktree 隔离、feature list、progress file、clean state、测试、可观测和人工 gate。禁止写成完全无人值守魔法。

10. 实践章节写法：第 13 章按“高质量流程需要的能力”组织：Agent 设计、提速、测试评估、AI 编排、工具层改造、展望。不要按来源逐篇介绍资料。

11. 禁忌：
   - 不要使用本机绝对路径。
   - 不要把未经核验的数字、指标、工具能力写成确定结论。
   - 不要堆案例。
   - 不要把 MAS 讲成多 Agent 聊天。
   - 不要把 AI 提速讲成让模型多写代码。
   - 不要把无人值守讲成完全自治。

## Blueprint Completion Standards

- [x] 综合框架覆盖用户要求的固定章节顺序。
- [x] “统一流程”和“高质量流程”是全稿主轴。
- [x] 用户原创观点被保留并分配到章节中。
- [x] 每章都有证据映射或缺口说明。
- [x] 没有把未经核验的事实写成确定结论。
- [x] 输出不包含本机绝对路径。
- [x] `workspace/research/synthesis.md` 已写入。
