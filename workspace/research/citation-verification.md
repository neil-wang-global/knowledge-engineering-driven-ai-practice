# Citation Verification

Project: ai-work-system-speech-20260518

## Verification Summary

本次核验读取了 `references/methodology/data-sources.md`、`references/methodology/output-template.md`、`workspace/research/source-inventory.md`、`workspace/research/raw-notes.md`、`workspace/research/synthesis.md`，并抽查了关键本地归档与视觉摘取材料。`source-inventory.md` 中登记的本地证据路径均存在；MindFlow 与 POMASA 资料使用 GitHub URL 与本地 web archive，未使用本机绝对路径。

总体判断：`synthesis.md` 的主线可支撑最终写作，但其中相当一部分是用户原创工程框架，不能写成外部资料已有结论。外部来源能支撑工程化、harness、eval、上下文管理、长时间 agent、POMASA 强状态、MindFlow 知识分层等事实与实践；已移除材料 已从本轮写作范围移除；对数字民主化、状态控制三分法、Knowledge / Story / Flyway 类比、自动解析 Story 依赖、完全无人值守、具体指标与工具选型的证据较弱，需要降级或明确标为用户观点。

Completion standards: passed with cautions. 关键来源均有状态判断；关键外部事实和案例有来源 ID；用户原创观点已标为 USER；不可核验内容已列出降级、修改或删除建议；输出未包含本机绝对路径。

## Source Status Table

| ID | Source | Status | Notes |
| --- | --- | --- | --- |
| USER-001 | `user_input_template.md` | Keep | 项目标题、交付约束、风格和主线的最高优先级来源。 |
| USER-002 | `user_input_template.md` | Keep | “强模型时代工程化与 SDD 迁移为治理工具”是用户原创判断，可由 SRC-011 辅助支撑。 |
| USER-003 | `user_input_template.md` | Keep | SoC、抽象、目录结构迁移到 AI 文件工程属于用户原创分析框架。 |
| USER-004 | `user_input_template.md` | Keep | Knowledge / Story、Flyway 类比、软件即知识、数字民主化均为用户原创观点。 |
| USER-005 | `user_input_template.md` | Keep | AI-native workflow 与单仓库强状态空间为用户原创工程定义。 |
| USER-006 | `user_input_template.md` | Keep | Skill、工程文件、Rules 差异与验收标准为用户原创分类，可用外部材料辅助。 |
| USER-007 | `user_input_template.md` | Keep | 角色而非人、统一流程、Tasking、多线程和无人值守边界来自用户需求。 |
| USER-008 | `user_input_template.md` | Keep | 上下文管理、确定性工具、反思证据、Agent 不可信操作员等 thought 的项目约束来源。 |
| SRC-001 | `references/paper-visual/extracted/CLI-for-AI-Agents.md`; `references/papers/CLI_for_AI_Agents.pdf` | Keep | 支持人类体验 vs 智能体体验、JSON、schema、自省、上下文窗口、输入防御、Skill 分发；精确页码或原文需回查 PDF/图像。 |
| SRC-002 | `references/paper-visual/extracted/李文鹏-让-AI-运行在工程资产上-从-PRD-到上线的交付闭环-Hybrid-执行-Doc-与-Code-联动.md` | Keep with caution | 支持“个人提效不等于组织提效”、SOP、Spec、回写闭环；其中具体百分比和研究结论若用于主稿必须回查原页，避免误引。 |
| SRC-003 | `references/paper-visual/extracted/徐翔-尽在上下文-mdash-mdash-JoyCode-的企业级-AI-Coding-实践.md` | Keep | 支持企业级 AI Coding 的上下文爆炸、业务复杂、知识增强。 |
| SRC-004 | `references/paper-visual/extracted/牛万鹏-构建-Coding-Agent-的飞轮-Feedback-Loop-Benchmark-Agent-Engineers.md` | Keep | 支持 Feedback Loop、Benchmark、Agent Engineers 与失败回流；不要扩展为所有组织通用成熟模型。 |
| SRC-005 | `references/paper-visual/extracted/章平-从盲目调优到数据驱动-大规模-Agent-的评估工程实践.md` | Keep with caution | 支持旅游搜索 Agent 隐形降级、传统监控不足、系统化 eval；具体“节省时间/百分比”需回查原页。 |
| SRC-006 | `references/paper-visual/extracted/钱世俊-给-Agent-做-ldquo-CT-rdquo-大规模-Agent-的可观测与质量保障体系.md` | Keep | 支持 Agent 可观测、统一观测底座、质量闭环；建议作为类比和实践方向，不作精确技术标准引用。 |
| SRC-007 | `references/paper-visual/extracted/陶宇田-OpenSandbox-重新思考-Agent-时代的-Runtime.md` | Keep | 支持 Agent Runtime 对文件系统、命令执行、服务访问、隔离、联网和资源控制的需求。 |
| SRC-008 | `references/paper-visual/extracted/打破-ldquo-人月神话-rdquo-Agent-重塑风控场景产运研职能-王东旭.md` | Keep | 支持部门墙、协调税、PRD 信息损耗与组织协作问题；不能推导为“人越少越好”。 |
| SRC-009 | `references/paper-visual/extracted/黄闻欣-超级团队进行时-从用-AI-到-AI-自己找活干.md` | Downgrade | 仅适合展望 Agent Teams，不足以支撑“完全自治组织已成熟”。 |
| SRC-010 | `references/paper-visual/extracted/曹偲-DSL-Spec-TocoAI-的后端-Harness-Engineering-实践.md` | Keep with caution | 可辅助 Spec / DSL / Harness Engineering；`synthesis.md` 当前很少直接使用，若主稿展开需回读细节。 |
| SRC-011 | `references/web/24-mp-weixin-qq-com-s-b4Fh-3SQyWiB1HypUxk9wA.md` | Keep | 支持强模型吸收部分能力、方法论必要性分层、SDD 护栏前置、MAS 治理、hooks deterministic control。 |
| SRC-012 | `references/web/01-mp-weixin-qq-com-s-MGnWz2b2H63lC8tK7UbrDA.md` | Keep | 支持“不是提示词工程，是知识工程”的外部论述；仍需把用户的 Knowledge / Story 概念标为 USER。 |
| SRC-013 | `references/web/13-www-anthropic-com-engineering-building-effective-agents.md` | Keep | 高可信来源；支持 workflows vs agents、从简单开始、prompt chaining/routing/parallelization/orchestrator-workers/evaluator-optimizer。 |
| SRC-014 | `references/web/14-www-anthropic-com-engineering-demystifying-evals-for-ai-agents.md` | Keep | 高可信来源；支持 task/trial/grader/transcript/outcome/evaluation harness/evaluation suite、最终状态优先于自述完成。 |
| SRC-015 | `references/web/15-www-anthropic-com-engineering-effective-harnesses-for-long-running-agents.md` | Keep | 高可信来源；支持 long-running agents、feature list、progress file、git history、clean state、单 feature 增量、浏览器验证。 |
| SRC-016 | `references/web/16-www-anthropic-com-engineering-harness-design-long-running-apps.md` | Keep with caution | 与 SRC-015 共同支撑 harness 设计；若写具体做法需回读细节。 |
| SRC-017 | `references/web/17-martinfowler-com-articles-exploring-gen-ai-harness-engineering-html.md` | Keep | 高可信来源；支持 harness、feedforward/feedback controls、computational/inferential controls、质量左移。 |
| SRC-018 | `references/web/19-openai-com-index-harness-engineering.md` | Keep with caution | 高可信来源；支持 repository knowledge as system of record、AGENTS.md 作为地图、per-worktree app、CDP、可观测、Humans steer/Agents execute。具体生产力数字可引用但应谨慎并说明是 OpenAI 团队自述案例。 |
| SRC-019 | `references/web/21-www-humanlayer-dev-blog-skill-issue-harness-engineering-for-coding-agents.md` | Keep with caution | 可支持 Skill 与 harness 边界；当前 raw notes 未深入摘记，主稿使用需弱讲。 |
| SRC-020 | `references/web/22-blog-langchain-com-the-anatomy-of-an-agent-harness.md` | Keep with caution | 可补充 agent harness 概念；当前仅做背景，不宜承担关键论点。 |
| SRC-021 | `references/web/23-www-inngest-com-blog-your-agent-needs-a-harness-not-a-framework.md` | Keep with caution | 可辅助“harness 优先于框架”；“框架是为了消灭自己而存在”应标为用户工程判断。 |
| SRC-022 | GitHub MindFlow README-CN; archive `references/web/04-github-com-neil-wang-global-MindFlow-blob-main-README-CN-md.md` | Keep | 高可信项目自述；支持 MindFlow 定义、Soul/Learning/Mind/Capability/Plan/Task State 等结构。 |
| SRC-023 | GitHub MindFlow SYSTEM; archive `references/web/05-github-com-neil-wang-global-MindFlow-blob-main-SYSTEM-md.md` | Keep | 高可信项目自述；支持 lazy loading、Required Main Flow、Artifact Data Flow、状态更新和渐进加载。 |
| SRC-024 | GitHub MindFlow tasks README; archive `references/web/06-github-com-neil-wang-global-MindFlow-blob-main-tasks-README-md.md` | Keep with caution | 可支持任务目录与状态交接；主稿若展开任务机制需回读细节。 |
| SRC-025 | GitHub MindFlow capabilities README; archive `references/web/07-github-com-neil-wang-global-MindFlow-blob-main-capabilities-README-md.md` | Keep with caution | 可支持 Capability 概念；主稿若写细节需回读。 |
| SRC-026 | GitHub POMASA README.zh-CN; archive `references/web/09-github-com-eXtremeProgramming-cn-pomasa-blob-main-README-zh-cn-md.md` | Keep | 高可信项目自述；支持 POMASA 定义、模式语言、定义/执行/数据层、文件系统数据总线。 |
| SRC-027 | GitHub POMASA SKILL; archive `references/web/10-github-com-eXtremeProgramming-cn-pomasa-blob-main-skills-pomasa-SKILL-md.md` | Keep | 高可信项目自述；支持 Blueprint、Pattern、Prompt-Defined Agent、Orchestrated Pipeline、Filesystem Data Bus、Verifiable Data Lineage、completion criteria。 |
| SRC-028 | GitHub POMASA pattern catalog README; archive `references/web/11-github-com-eXtremeProgramming-cn-pomasa-blob-main-skills-pomasa-pattern-catalog-README-md.md` | Keep with caution | 支持模式语言与分类；主稿若引用具体模式需回读对应模式。 |

## Claim Verification

| Claim | Source IDs | Status | Required Action |
| --- | --- | --- | --- |
| 演讲标题、60-90 分钟中文演讲、面向技术团队与客户技术听众、语言干净简练。 | USER-001 | Keep | 按项目约束执行，不需要外部引用。 |
| 主轴是“构建统一流程与高质量流程”。 | USER-001, USER-007 | Keep | 可作为项目 framing 明确写出。 |
| AI-native workflow 是“模型推理 + 流程约束 + 状态反馈”的动态系统。 | USER-005 | Keep | 用户原创定义；不要写成行业通用定义。 |
| 强模型会吸收部分 planning、tool use、orchestration，但工程方法从能力补丁迁移到治理工具。 | USER-002, SRC-011 | Keep | 可强讲；若提 OpenAI/Anthropic 具体模型能力，需按 SRC-011 内部引用或补源。 |
| 现实问题是模型太快开始写代码，需求、边界、验证未澄清就开始实现。 | USER-002, SRC-011 | Keep | 可作为实践观察和项目判断；避免写成统计研究结论。 |
| SDD 的价值是把“先想清楚”制度化，而不是增强模型智力。 | USER-002, SRC-011 | Keep | 可强讲，标为工程判断。 |
| SoC、抽象/OOP、目录结构、契约、测试应迁移到 AI 文件工程。 | USER-003, USER-008, SRC-017, SRC-018 | Keep | 用户原创框架；外部材料只支撑上下文、harness、结构化 docs 和确定性检查。 |
| 目录结构是 Agent 可导航的知识地址空间。 | USER-003, SRC-018, SRC-003 | Keep | 可强讲为项目观点；OpenAI “map not manual” 可做支撑。 |
| 确定性的检查应交给确定性工具。 | USER-008, SRC-017, SRC-014 | Keep | 可强讲；可用 code-based graders、lint/type/test 等支撑。 |
| MindFlow 是知识管理、认知演化与任务执行的 AI-native 自主决策系统。 | SRC-022 | Keep | 可作为项目自述引用；避免把外部独立验证说得过满。 |
| MindFlow 通过 Soul、Learning、Mind、Capability、Plan + Step、Task State 分层管理知识、能力与状态。 | SRC-022, SRC-023 | Keep | 可强讲；使用 GitHub URL 或 repository-relative archive。 |
| MindFlow lazy loading 是按阶段加载上下文、减少噪声。 | SRC-023 | Keep | 可强讲。 |
| 软件系统本质是知识，智能 Agent 系统也是知识。 | USER-004, SRC-012 | Keep | 用户原创判断；SRC-012 只能辅助知识工程立论。 |
| AI 是未来新软件，推动数字民主化。 | USER-004 | Downgrade | 仅作为演讲者观点或愿景表达，不作外部事实。 |
| POMASA 是构建声明式 MAS 的模式语言和生成工具包。 | SRC-026 | Keep | 可强讲。 |
| POMASA 架构包含定义层、执行层、数据层，文件系统作为数据总线。 | SRC-026 | Keep | 可强讲。 |
| POMASA Skill 强调 Prompt-Defined Agent、Orchestrated Pipeline、Filesystem Data Bus、Verifiable Data Lineage。 | SRC-027 | Keep | 可强讲。 |
| MAS 不是多个 Agent 聊天，而是强状态、多阶段、多产物编排。 | USER-005, SRC-026, SRC-027, SRC-013 | Keep | 可强讲为项目判断；外部材料支撑 workflows/agents 和 POMASA 机制。 |
| POMASA 与 MAS 章节。 | USER-005, SRC-026, SRC-027 | Keep | 已移除材料 已移除；本章只写 POMASA 与强状态 MAS。 |
| 状态控制三分法：强约束固定、有建议的 AI 自主判断、完全 AI 控制。 | USER-006, USER-008, SRC-011, SRC-013, SRC-017 | Keep with attribution | 用户原创分类；外部资料支撑控制思想，不是三分法来源。 |
| 可靠性与灵活性反向相关。 | USER-006, SRC-013 | Revise | 可作为工程经验表达；不要写成严格定律。 |
| Skill、工程文件、Rules 都是可执行知识。 | USER-006, SRC-001, SRC-017, SRC-018, SRC-027 | Keep | 可强讲为项目框架。 |
| Skill 调度更随机，工程文件调度更确定，Rules/Hooks 接近强约束。 | USER-006, SRC-011, SRC-017 | Keep with attribution | 用户原创区分；外部 hooks/control 材料可辅助。 |
| 成熟 Skill 应包含触发、输入、步骤、输出、权限、副作用、验证和下游可消费性。 | USER-006, SRC-001, SRC-027 | Keep | 可强讲；POMASA SKILL 与 CLI for AI Agents 可作案例。 |
| Story 是动态知识，Knowledge 是静态 Story。 | USER-004 | Keep with attribution | 用户原创概念，必须标为项目观点。 |
| 每个 Story 像 Flyway migration，Knowledge 像所有 migration 后的当前数据库状态。 | USER-004 | Keep with attribution | 用户原创类比；不要扩展为 Flyway 官方语义。 |
| 被验证的 Story 增量应回写到 AC、ADR、工程文档、Skill、Capability、测试、eval case 或 workflow pattern。 | USER-004, USER-007, SRC-002, SRC-014, SRC-004 | Keep | 可强讲；外部材料支撑资产回写和 eval。 |
| Story 验收不能只看 Agent 声称完成，要看最终状态、AC、测试、trace/outcome。 | USER-007, SRC-014, SRC-017 | Keep | 可强讲。 |
| BA / DEV / QA / UI / Agent 是角色而非固定人头。 | USER-007, SRC-008, SRC-018 | Keep | 用户原创流程设计；外部材料支撑角色变化和协调损耗。 |
| 仓库是 BA / DEV / QA / UI / Agent 共享的强状态空间。 | USER-005, USER-007, SRC-018 | Keep with attribution | 用户原创“单仓库原则”；OpenAI repository knowledge as system of record 可辅助。 |
| 传统产运研存在部门墙、协调税和 PRD 信息损耗。 | SRC-008, SRC-002 | Keep | 可使用；不要推导为组织缩编结论。 |
| 统一流程从需求进入，经 Tasking、澄清、设计、计划、实现、Review、测试、验收，代码出去且验收测试通过。 | USER-007, SRC-002, SRC-014, SRC-017, SRC-018 | Keep | 可强讲；这是全稿主轴。 |
| Tasking 是把模糊需求变成可执行、可验证、可分派任务结构的过程。 | USER-007 | Keep with attribution | 用户原创定义；外部 Spec/eval 支撑但不替代。 |
| `SOUL.md` 类长期原则文件应在流程中维护。 | USER-007, SRC-022, SRC-023 | Revise | 可讲“类似长期原则文件”；不要声称所有项目都有 `SOUL.md`。 |
| 多线程流程可从 Epic 到 User Story，解析依赖后用 Worktree 并行。 | USER-007, USER-008, SRC-015, SRC-018 | Revise | Worktree/隔离有支撑；“自动解析 Story 依赖”证据不足，作为设计方向表达。 |
| 无人值守是长时间、低人工干预，而非完全自主魔法。 | USER-007, SRC-015, SRC-018 | Keep | 可强讲。 |
| 长时间 Agent 需要 feature list、progress file、git history、clean state、单 feature 推进、浏览器验证。 | SRC-015 | Keep | 高可信，可强讲。 |
| Agent Runtime 需要文件系统、命令执行、服务访问、隔离、安全和资源控制。 | SRC-007 | Keep | 可强讲；避免脱离材料添加未核验细节。 |
| Agent Teams 可作为展望。 | SRC-009, SRC-018, USER-007 | Downgrade | 仅弱讲，不写成已成熟、通用、完全自治。 |
| Agent 设计应从角色协议定义上下文、权限、输入、输出、契约、验收。 | USER-008, SRC-013, SRC-014, SRC-017 | Keep | 用户原创设计框架，外部资料支持 agentic system 与 eval/harness。 |
| 提速来自流程缩短、上下文传递损耗下降、反馈更快、测试更靠前、失败更快变成资产，而不是 token 速度。 | USER-008, SRC-002, SRC-004, SRC-005, SRC-008, SRC-014, SRC-017 | Keep | 可强讲；避免未经核验的具体数字。 |
| AI 编排应按任务选择 prompt chaining、routing、parallelization、orchestrator-workers、evaluator-optimizer 或 agents。 | SRC-013 | Keep | 可强讲。 |
| Agent eval 关注 task、trial、grader、trace/transcript、outcome、evaluation suite。 | SRC-014 | Keep | 可强讲。 |
| 失败是 eval case 的来源。 | USER-008, SRC-004, SRC-014 | Keep | 可强讲为工程实践。 |
| 可观测让推理、工具调用、轨迹、质量问题可追踪、可诊断、可迭代。 | SRC-006, SRC-014, SRC-018 | Keep | 可强讲。 |
| 工具层要区分人类体验与智能体体验，Agent 需要 JSON、schema、字段裁剪、输入防御、安全边界。 | SRC-001 | Keep | 可强讲。 |
| Agent 是不受信任的操作员，工具层要做纵深防御。 | SRC-001, USER-008 | Keep | 可强讲。 |
| Promptfoo / Braintrust / LangSmith / Langfuse、SWE-bench / Terminal-Bench 等工具和 benchmark 推荐。 | USER-008 | Downgrade | 当前 raw notes 未充分核验；只放 Q&A 或列为“可进一步调研”，不要推荐或比较。 |
| pass@k vs pass^k 或具体数学解释。 | USER-008 | Downgrade | 当前证据不足；主稿不建议展开，若使用需补充来源。 |
| OpenAI 0 手写代码、约 1/10 时间、百万行、1500 PR 等案例数字。 | SRC-018 | Revise | 来源存在但为 OpenAI 团队自述；若引用，必须标注为“OpenAI 文章中的自述案例”，不要泛化。 |
| 李文鹏材料中 20%、-19%、518 家企业、11.4 万工程师等数字。 | SRC-002 | Revise | 视觉摘取可见，但来源链与细节复杂；除非回查原页和背景来源，否则不建议主稿使用精确数字。 |
| 旅游搜索 Agent 7 周质量隐形降级。 | SRC-005 | Keep with caution | 可讲案例方向；若使用“7 周”与诊断周期数字，回查原页。 |

## Writing Constraints

### 可强讲

- 统一流程和高质量流程是全稿主轴：每个概念都要落到输入、输出、状态、角色、检查点、验收和回写。
- 强模型没有取消工程化问题；工程方法的价值从能力补丁迁移到治理工具。[USER-002][SRC-011]
- SDD 是需求澄清、护栏前置和验收显化，不是提高模型智力的魔法。[USER-002][SRC-011]
- MindFlow 的知识分层、lazy loading、Task State、Artifact Data Flow、自我演进可作为高可信项目自述。[SRC-022][SRC-023]
- POMASA 的模式语言、定义/执行/数据层、文件系统数据总线、Blueprint、Pattern、Verifiable Data Lineage 可作为高可信项目自述。[SRC-026][SRC-027]
- Anthropic workflows vs agents、从简单开始、常见 workflow 模式可作为 AI 编排主证据。[SRC-013]
- Agent eval 的 task、trial、grader、transcript/trace、outcome、evaluation suite 可作为验收章节主证据。[SRC-014]
- long-running agents 的 feature list、progress file、git history、clean state、单 feature 推进、浏览器验证可作为无人值守章节主证据。[SRC-015]
- Harness Engineering 的 feedforward / feedback、computational / inferential controls、质量左移可作为高质量流程证据。[SRC-017]
- OpenAI repository knowledge as system of record、AGENTS.md 作为地图、per-worktree app、Agent 可读 observability 可作为工程文件与工具层证据。[SRC-018]
- CLI for AI Agents 的人类体验 vs 智能体体验、JSON、schema、自省、上下文窗口、输入防御、Agent 不可信操作员可作为工具层证据。[SRC-001]

### 只能弱讲或标为用户观点

- 状态控制三分法、Knowledge / Story、Flyway Migration 类比、单仓库原则、AI-native workflow 定义、Tasking 定义、数字民主化，均应明确为项目观点或演讲者工程框架。[USER-004][USER-005][USER-006][USER-007]
- SoC/OOP 到 AI 文件工程的迁移可以强讲为工程判断，但不能说外部文献逐字提出。
- “可靠性与灵活性反向相关”可作为经验性判断，不作为严格定律。
- “框架是为了消灭自己而存在”可作为演讲者表达，不可当作外部原文引用。

### 必须附来源或避免精确化

- 任何具体案例数字、百分比、PR 数、时间节省、企业样本量、benchmark 结果，必须附具体来源，并最好回查 PDF 原页或文章段落。
- OpenAI 自述案例可引用，但需标明“OpenAI 文章中的团队实践”，不得泛化为行业平均效果。
- PDF 视觉摘取材料可支撑页内可见文字；若要逐字引用或引用精确数字，需回查 `references/papers/` 原 PDF 或页面图像。

### 不得使用或必须删除

- 不得使用本机绝对路径；MindFlow 与 POMASA 引用 GitHub URL 或本地 archive repository-relative path。
- 已移除材料 已从本轮写作范围移除；不得再在正文或 HTML 中使用。
- 不得把 Agent Teams、自动化、无人值守写成完全自治组织或完全无需人工 gate。
- 不得把“AI 提速”写成 token 生成更快或代码量更多。
- 不得把未经核验的工具/平台能力、pass@k vs pass^k、Promptfoo/Braintrust/LangSmith/Langfuse、SWE-bench/Terminal-Bench 写成确定推荐或详细对比。

## Removal or Revision List

1. 已移除材料：Remove。本轮写作不再使用 已移除材料 相关材料，章节统一为 POMASA 与 MAS。
2. 数字民主化：Downgrade。作为用户原创愿景表达，不作为外部事实。
3. 状态控制三分法：Revise。标明为演讲者工程分类，外部材料只作支撑。
4. Knowledge / Story / Flyway 类比：Revise。标明为用户原创类比，不需外部证明，但不能延伸为 Flyway 官方定义。
5. 自动解析 Story 依赖：Downgrade。当前证据不足；写成设计方向或团队可探索实践。
6. Agent Teams：Downgrade。只放展望，不写成成熟全自治模式。
7. 完全无人值守：Remove。统一替换为“长时间、低人工干预、有边界、有测试、有人工 gate”。
8. 具体指标与百分比：Revise。除非回查原页并明确出处，否则不进入主稿或只作模糊背景。
9. Promptfoo / Braintrust / LangSmith / Langfuse、SWE-bench / Terminal-Bench：Downgrade。放 Q&A 的“可继续调研工具/benchmark”，不做推荐排名。
10. pass@k vs pass^k：Remove from main body。当前不建议进入主稿；若用户坚持，需要补充专门来源。
11. `SOUL.md` 泛化：Revise。写成“类似长期原则文件”；只有 MindFlow 的 Soul 可由 SRC-022/SRC-023 支撑。
12. “人越少越好”“AI 代替团队”：Remove。来源只支持角色变化、协调税下降和 agent 执行动作，不支持组织缩编结论。
