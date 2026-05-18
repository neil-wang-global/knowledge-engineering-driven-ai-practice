# Source Inventory

Project: ai-work-system-speech-20260518

## USER Sources

### USER-001 — 项目主题、标题与交付约束
- Source type: User input
- Source path: `user_input_template.md`
- Core content summary: 演讲标题确定为《知识工程驱动的 AI 实践》；目标是 60-90 分钟中文演讲；最终稿应聚焦技术团队与客户技术听众，语言干净、简单、简练，避免营销化和泛泛评论。
- Usable paraphrase: 本项目不是工具教程，也不是研究报告，而是围绕“如何构建统一流程与高质量流程”的工程化演讲。
- Credibility assessment: High; project framing and original intent.
- Speech support: 约束最终叙事、风格、章节顺序和验收标准。

### USER-002 — 强模型时代仍需要工程化与 SDD
- Source type: User input
- Source path: `user_input_template.md`
- Core content summary: 强模型会内化部分 planning、tool use 和 orchestration，但工程方法价值从“能力补丁”迁移到“治理工具”。现实问题是 AI 太快开始写代码，需求、边界、验证还没澄清就过早执行。
- Usable paraphrase: SDD 的价值不是神秘增强模型智力，而是把“先想清楚”制度化，把意图、约束、中间产物、检查点和验收标准显化。
- Credibility assessment: High as user original argument; external support见 SRC-011.
- Speech support: 开场章节核心判断。

### USER-003 — 软件工程基本功迁移到 AI 文件工程
- Source type: User input
- Source path: `user_input_template.md`
- Core content summary: SoC、抽象/面向对象、文件目录结构、接口契约、测试验证应迁移到 AI 文件工程。文档小而精，依赖通过 ID、链接、引用维护，目录结构是知识对象的地址空间。
- Usable paraphrase: AI 编程不是推翻软件工程，而是放大软件工程基本功。
- Credibility assessment: High as user original argument.
- Speech support: 第 1 章“软件基本功”。

### USER-004 — 知识工程、Story / Knowledge 与 Flyway 类比
- Source type: User input
- Source path: `user_input_template.md`
- Core content summary: Story 是动态知识，Knowledge 是静态 Story；user journey 是发现、验证、固化知识的过程；每个 Story 可类比 Flyway Migration，Knowledge 像所有 Migration 执行后的当前数据库状态。
- Usable paraphrase: 代码工程本质是知识工程，每次需求、设计、实现、测试和验收都是知识被发现、修改和固化。
- Credibility assessment: High as user original argument.
- Speech support: Knowledge / Story、Flyway 章节主线。

### USER-005 — AI-native workflow 与强状态空间
- Source type: User input
- Source path: `user_input_template.md`
- Core content summary: AI-native workflow = 模型推理 + 流程约束 + 状态反馈的动态系统；模型负责推理，流程负责约束，状态负责让推理结果可恢复、可检查、可交接。
- Usable paraphrase: 单仓库原则：仓库是 BA / DEV / QA / UI / Agent 共享的强状态空间。
- Credibility assessment: High as user original argument.
- Speech support: MAS、团队流程、统一流程章节。

### USER-006 — Skill、工程文件、Rules 与验收标准
- Source type: User input
- Source path: `user_input_template.md`
- Core content summary: Skill 与工程文件本质上都是可执行知识，但 Skill 调度更随机，工程文件通常处在更确定的流程编排中；Rules 类似 Hook 式强约束。Skill / Rule 应像函数一样验收触发、输入、步骤、输出、验证、权限、副作用和下游可消费性。
- Usable paraphrase: 无法验收的 Skill 只是经验片段，还不是稳定工程资产。
- Credibility assessment: High as user original argument; external support见 SRC-004、SRC-018、SRC-021。
- Speech support: Skill、工程文件与 Rules 章节。

### USER-007 — 角色思考帽、统一流程与自动化
- Source type: User input
- Source path: `user_input_template.md`
- Core content summary: BA / DEV / QA / UI / Agent 是角色而非人，围绕同一仓库协作；统一流程从需求进入，经过 Tasking、澄清、设计、计划、实现、Review、测试和验收，最后代码出去且验收测试通过。自动化与无人值守应定义为长时间、低人工干预，而非完全自主魔法。
- Usable paraphrase: Tasking 是需求分析与拆解，把模糊需求变成可执行、可验证、可分派的任务结构。
- Credibility assessment: High as user original argument.
- Speech support: 角色流程、单线程、多线程、无人值守章节。

### USER-008 — 必须纳入的工程 thought
- Source type: User input
- Source path: `user_input_template.md`
- Core content summary: 必须纳入上下文管理、渐进加载、契约驱动跨层一致性、确定性的事交给确定性工具、反思循环带证据、失败是 eval case 来源、Agent 是不受信任的操作员、人类体验 vs 智能体体验、设计杠杆等 thought。
- Usable paraphrase: 提速来自上下文管理、分层计划、角色协议、测试验证、评估闭环和工具层改造，而不是盲目让模型多写代码。
- Credibility assessment: High as user original requirement.
- Speech support: 后续实践章节与 Q&A 素材。

## PDF and Visual Extraction Sources

### SRC-001 — CLI for AI Agents
- Source type: PDF original + visual extraction
- Source path: `references/paper-visual/extracted/CLI-for-AI-Agents.md`
- PDF path: `references/papers/CLI_for_AI_Agents.pdf`
- Core content summary: 面向 AI Agent 的 CLI 要优化可预测性、纵深防御、JSON 载荷、运行时架构自省、上下文窗口管控、输入防御、Skill 分发和单一信源多终端架构。
- Usable paraphrase: 人类体验优化发现性与容错性，智能体体验优化可预测性与纵深防御；Agent 不是受信任的操作员，工具层必须做输入防御。
- Credibility assessment: Medium-high; local PDF extraction,可回查原 PDF。
- Speech support: 工具层改造、Agent 文档验收、人类体验 vs 智能体体验、确定性工具章节。

### SRC-002 — 让 AI 运行在工程资产上：从 PRD 到上线的交付闭环
- Source type: PDF original + visual extraction
- Source path: `references/paper-visual/extracted/李文鹏-让-AI-运行在工程资产上-从-PRD-到上线的交付闭环-Hybrid-执行-Doc-与-Code-联动.md`
- PDF path: `references/papers/李文鹏-让 AI 运行在工程资产上：从 PRD 到上线的交付闭环、Hybrid 执行、 Doc 与 Code 联动.pdf`
- Core content summary: AI 写代码已不是唯一问题；“个人提效”不等于“组织提效”。从 Prompt Engineering 到 Context Engineering 再到 Harness Engineering，需要资产完备、验证闭环和全链路 SOP。
- Usable paraphrase: SOP 是资产生产线；Spec 不是文档，是需求契约；从 PRD 到上线每一环都可能是断点。
- Credibility assessment: Medium-high; slide extraction, metrics should be verified before precise quotation.
- Speech support: 统一流程、工程资产、Spec / Design / Implement / Review / Release、组织提效章节。

### SRC-003 — 尽在上下文：JoyCode 的企业级 AI Coding 实践
- Source type: PDF original + visual extraction
- Source path: `references/paper-visual/extracted/徐翔-尽在上下文-mdash-mdash-JoyCode-的企业级-AI-Coding-实践.md`
- PDF path: `references/papers/徐翔-尽在上下文&mdash;&mdash;JoyCode 的企业级 AI Coding 实践.pdf`
- Core content summary: 企业级编码场景面临业务复杂、角色多样、长任务和超大代码仓导致的上下文爆炸；JoyCode 提出企业知识增强、RepoWiki、“代码在哪里，知识就在哪里”等方向。
- Usable paraphrase: 企业 AI Coding 的核心挑战之一是上下文迅速膨胀，远超模型处理能力。
- Credibility assessment: Medium-high; slide extraction.
- Speech support: 上下文管理、知识地址空间、企业知识增强章节。

### SRC-004 — 构建 Coding Agent 的飞轮：Feedback Loop、Benchmark、Agent Engineers
- Source type: PDF original + visual extraction
- Source path: `references/paper-visual/extracted/牛万鹏-构建-Coding-Agent-的飞轮-Feedback-Loop-Benchmark-Agent-Engineers.md`
- PDF path: `references/papers/牛万鹏-构建 Coding Agent 的飞轮：Feedback Loop、Benchmark、Agent Engineers.pdf`
- Core content summary: Coding Agent 落地需要 Agent Loop、Feedback Loop、Benchmark 与 Agent Engineers；制约效率的不只是 token 消耗速度，而是提出好问题和把人放入 Loop 的能力。
- Usable paraphrase: Coding Agent 的成熟形态依靠可观测反馈、评测集和人类工程师持续调校形成飞轮。
- Credibility assessment: Medium-high; slide extraction.
- Speech support: 反馈闭环、Benchmark、失败转 eval case、Agent Engineer 角色。

### SRC-005 — 从盲目调优到数据驱动：大规模 Agent 的评估工程实践
- Source type: PDF original + visual extraction
- Source path: `references/paper-visual/extracted/章平-从盲目调优到数据驱动-大规模-Agent-的评估工程实践.md`
- PDF path: `references/papers/章平-从盲目调优到数据驱动-大规模 Agent 的评估工程实践.pdf`
- Core content summary: 旅游搜索 Agent 案例显示，传统技术指标可能正常，但用户体验持续恶化；缺乏系统化评估会导致隐形降级。自动化评估可把发现和诊断周期大幅缩短。
- Usable paraphrase: Agent 评估要关注业务标准、用户体验、工具选择准确性、响应有用性，而不只看 P95、错误率和 API 延迟。
- Credibility assessment: Medium-high; slide extraction.
- Speech support: Agent Eval、pass@k、数据驱动调优、提速评估标准。

### SRC-006 — 给 Agent 做 CT：大规模 Agent 的可观测与质量保障体系
- Source type: PDF original + visual extraction
- Source path: `references/paper-visual/extracted/钱世俊-给-Agent-做-ldquo-CT-rdquo-大规模-Agent-的可观测与质量保障体系.md`
- PDF path: `references/papers/钱世俊-给 Agent 做&ldquo;CT&rdquo;：大规模 Agent 的可观测与质量保障体系.pdf`
- Core content summary: 大规模 Agent 面临黑盒困境，需要统一观测底座、深度观测、从可观测到可迭代的工程闭环。
- Usable paraphrase: Agent 可观测不是附加仪表盘，而是让推理、工具调用、轨迹、质量问题可追踪、可诊断、可迭代。
- Credibility assessment: Medium-high; slide extraction.
- Speech support: 可观测、质量保障、反思循环带证据。

### SRC-007 — OpenSandbox：重新思考 Agent 时代的 Runtime
- Source type: PDF original + visual extraction
- Source path: `references/paper-visual/extracted/陶宇田-OpenSandbox-重新思考-Agent-时代的-Runtime.md`
- PDF path: `references/papers/陶宇田-OpenSandbox：重新思考 Agent 时代的 Runtime.pdf`
- Core content summary: Agent Workload 需要文件系统、命令执行、服务访问、长连接、大规模并发、短生命周期环境、可控联网、统一执行与统一访问；传统 Docker / K8s 不完全适配 Agent 执行模式。
- Usable paraphrase: Agent Runtime 应先定义生命周期和执行能力，再决定底层承载，让 SDK 面向稳定抽象而不是基础设施细节。
- Credibility assessment: Medium-high; slide extraction.
- Speech support: 工具层、运行时、隔离环境、无人值守章节。

### SRC-008 — 打破“人月神话”：Agent 重塑风控场景产运研职能
- Source type: PDF original + visual extraction
- Source path: `references/paper-visual/extracted/打破-ldquo-人月神话-rdquo-Agent-重塑风控场景产运研职能-王东旭.md`
- PDF path: `references/papers/打破&ldquo;人月神话&rdquo;，Agent 重塑风控场景产运研职能-王东旭.pdf`
- Core content summary: 传统产运研固态组织分工明确但有部门墙；从风险感知、需求分析、PRD、研发交付到配置规则存在协调税和信息损耗。
- Usable paraphrase: AI 提速的组织价值不是简单减少人，而是压低协调税、上下文传递成本和 PRD 信息损耗。
- Credibility assessment: Medium-high; slide extraction.
- Speech support: 人月神话、角色而非人、组织协作结构重塑。

### SRC-009 — 黄闻欣：超级团队进行时：从用 AI 到 AI 自己找活干
- Source type: PDF original + visual extraction
- Source path: `references/paper-visual/extracted/黄闻欣-超级团队进行时-从用-AI-到-AI-自己找活干.md`
- PDF path: `references/papers/黄闻欣-超级团队进行时：从用 AI 到 AI 自己找活干.pdf`
- Core content summary: 讨论从使用 AI 到 AI 主动发现工作、超级团队和组织形态变化。
- Usable paraphrase: Agent Teams 可作为展望，不宜作为主干夸大为完全自治组织。
- Credibility assessment: Medium; slide extraction,需在写作时回读具体页。
- Speech support: 展望章节、Agent Teams。

### SRC-010 — 曹偲：DSL-Spec：TocoAI 的后端 Harness Engineering 实践
- Source type: PDF original + visual extraction
- Source path: `references/paper-visual/extracted/曹偲-DSL-Spec-TocoAI-的后端-Harness-Engineering-实践.md`
- PDF path: `references/papers/曹偲-DSL-Spec：TocoAI 的后端 Harness Engineering 实践.pdf`
- Core content summary: 后端 Harness Engineering 与 DSL / Spec 实践材料，可支持契约驱动、Spec、结构化输入输出和后端工程闭环。
- Usable paraphrase: Spec / DSL 可作为需求、设计和代码之间的契约面，降低跨层理解偏差。
- Credibility assessment: Medium; slide extraction,需在写作时回读具体页。
- Speech support: 契约驱动跨层一致性、Spec 章节。

## Web Archive Sources

### SRC-011 — 当顶尖 Agent 模型越来越会自己干活，Prompt Engineering、SDD、MAS 还剩什么价值
- Source type: Web archive
- Source path: `references/web/24-mp-weixin-qq-com-s-b4Fh-3SQyWiB1HypUxk9wA.md`
- Source URL: `https://mp.weixin.qq.com/s/b4Fh-3SQyWiB1HypUxk9wA`
- Core content summary: 强模型会吸收一部分 planning、tool use、agentic orchestration，但方法论不是失效，而是必要性分层；Prompt Engineering 变成任务接口设计，SDD 变成需求澄清与护栏前置，MAS 变成上下文、权限、并行和审计架构，hooks 承担 deterministic control。
- Usable paraphrase: 工程方法价值从替模型补智力迁移到治理工具。
- Credibility assessment: High for project argument support; includes citations to OpenAI / Anthropic docs.
- Speech support: 开场第 0 章核心外部支撑。

### SRC-012 — 不是提示词工程，是知识工程
- Source type: Web archive
- Source path: `references/web/01-mp-weixin-qq-com-s-MGnWz2b2H63lC8tK7UbrDA.md`
- Source URL: `https://mp.weixin.qq.com/s/MGnWz2b2H63lC8tK7UbrDA`
- Core content summary: AI 协作的关键不只是提示词，而是知识工程；人需要主导问题导向、价值/视角、信息储备、理论方法和表现形式。
- Usable paraphrase: 高质量 AI 使用依赖人类对问题、知识、方法和表达的结构化组织。
- Credibility assessment: Medium-high; archived article.
- Speech support: 知识工程立论、人类角色。

### SRC-013 — Building Effective AI Agents
- Source type: Web archive
- Source path: `references/web/13-www-anthropic-com-engineering-building-effective-agents.md`
- Source URL: `https://www.anthropic.com/engineering/building-effective-agents`
- Core content summary: Anthropic 区分 workflows 与 agents；建议从最简单方案开始，复杂度只在必要时增加；常见模式包括 prompt chaining、routing、parallelization、orchestrator-workers、evaluator-optimizer。workflows 适合可预测和一致性，agents 适合需要灵活模型决策的任务。
- Usable paraphrase: 编排选择应服务任务条件，不应默认把所有问题做成复杂 agent 系统。
- Credibility assessment: High; primary vendor engineering article.
- Speech support: Agent 设计、AI 编排、状态控制三分法。

### SRC-014 — Demystifying evals for AI agents
- Source type: Web archive
- Source path: `references/web/14-www-anthropic-com-engineering-demystifying-evals-for-ai-agents.md`
- Source URL: `https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents`
- Core content summary: Agent eval 是给定输入并用 grading logic 衡量输出和最终状态；关键概念包括 task、trial、grader、transcript、outcome、evaluation harness、agent harness、evaluation suite。Agent eval 需结合 code-based、model-based、human graders。
- Usable paraphrase: 评估 Agent 时，最终状态比模型声称“完成了”更重要；transcript / trace 记录是诊断和改进的基础。
- Credibility assessment: High; primary vendor engineering article.
- Speech support: Eval、可观测、验收测试、失败回流。

### SRC-015 — Effective harnesses for long-running agents
- Source type: Web archive
- Source path: `references/web/15-www-anthropic-com-engineering-effective-harnesses-for-long-running-agents.md`
- Source URL: `https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents`
- Core content summary: 长时间 Agent 的核心挑战是跨上下文窗口的状态连续性。Anthropic 使用 initializer agent 和 coding agent：初始化环境、feature list、progress file、git history、每次只做一个 feature、保持 clean state、用浏览器自动化进行端到端测试。
- Usable paraphrase: 长时间运行的 Agent 需要进度文件、功能清单、干净状态、单 feature 增量推进和明确测试工具，而不能只靠模型记忆。
- Credibility assessment: High; primary vendor engineering article.
- Speech support: 自动化与无人值守、强状态、测试验证、Worktree / progress file 思路。

### SRC-016 — Harness design for long-running application development
- Source type: Web archive
- Source path: `references/web/16-www-anthropic-com-engineering-harness-design-long-running-apps.md`
- Source URL: `https://www.anthropic.com/engineering/harness-design-long-running-apps`
- Core content summary: 长时间应用开发 harness 设计相关材料，与 SRC-015 一起支撑多 session、可恢复、可验证的 Agent 开发流程。
- Usable paraphrase: Harness 的价值在于让 Agent 有可持续工作的环境、状态和反馈机制。
- Credibility assessment: High; primary vendor engineering article,需在写作时回读细节。
- Speech support: Harness Engineering 与无人值守章节。

### SRC-017 — Harness engineering for coding agent users
- Source type: Web archive
- Source path: `references/web/17-martinfowler-com-articles-exploring-gen-ai-harness-engineering-html.md`
- Source URL: `https://martinfowler.com/articles/harness-engineering.html`
- Core content summary: Harness 可理解为模型之外的环境和控制面。外层 harness 的目标是提高 Agent 首次做对概率，并通过反馈环在到达人类审查前尽量自我修正。区分 feedforward controls / feedback controls，以及 computational / inferential controls。
- Usable paraphrase: 质量应尽量左移；确定性的检查如测试、lint、类型检查可作为快速可靠的 feedback sensors。
- Credibility assessment: High; Martin Fowler / Thoughtworks article.
- Speech support: Harness Engineering、确定性工具、反馈闭环、质量左移。

### SRC-018 — Harness engineering: leveraging Codex in an agent-first world
- Source type: Web archive
- Source path: `references/web/19-openai-com-index-harness-engineering.md`
- Source URL: `https://openai.com/index/harness-engineering/`
- Core content summary: OpenAI 团队描述用 Codex 构建内部产品；人的角色转向设计环境、说明意图、构建反馈循环。仓库知识成为 system of record，短 AGENTS.md 作为目录，结构化 docs 承载真相；还通过 per-worktree app、Chrome DevTools、日志指标让应用对 Agent 可读。
- Usable paraphrase: 给 Codex 一张地图，而不是一千页手册；知识库应成为仓库中的系统记录。
- Credibility assessment: High; primary vendor engineering article.
- Speech support: 工程文件、知识地址空间、可观测、Worktree、工具层改造。

### SRC-019 — Skill Issue: Harness Engineering for Coding Agents
- Source type: Web archive
- Source path: `references/web/21-www-humanlayer-dev-blog-skill-issue-harness-engineering-for-coding-agents.md`
- Source URL: `https://www.humanlayer.dev/blog/skill-issue-harness-engineering-for-coding-agents`
- Core content summary: Skill 与 coding agent harness 相关实践材料，可辅助说明技能、工具和 harness 的边界。
- Usable paraphrase: Skill 应被看成 Agent 可使用的结构化能力，而不是零散提示词片段。
- Credibility assessment: Medium-high; archived technical blog,需在写作时回读细节。
- Speech support: Skill 与 Harness 章节。

### SRC-020 — The Anatomy of an Agent Harness
- Source type: Web archive
- Source path: `references/web/22-blog-langchain-com-the-anatomy-of-an-agent-harness.md`
- Source URL: `https://blog.langchain.com/the-anatomy-of-an-agent-harness/`
- Core content summary: Agent harness 架构材料，可补充 agent loop、工具、状态、运行环境等概念。
- Usable paraphrase: Agent harness 是让模型持续执行、使用工具并管理状态的周边系统。
- Credibility assessment: Medium-high; archived technical blog,需在写作时回读细节。
- Speech support: Agent 设计与运行时章节。

### SRC-021 — Your Agent Needs a Harness, Not a Framework
- Source type: Web archive
- Source path: `references/web/23-www-inngest-com-blog-your-agent-needs-a-harness-not-a-framework.md`
- Source URL: `https://www.inngest.com/blog/your-agent-needs-a-harness-not-a-framework`
- Core content summary: 区分 harness 与 framework 的材料，可支持“框架是为了消灭自己而存在”和简单可控优先的判断。
- Usable paraphrase: 可靠 Agent 系统的关键不只是选框架，而是构建可观测、可恢复、可控制的执行环境。
- Credibility assessment: Medium-high; archived technical blog,需在写作时回读细节。
- Speech support: 框架、Harness、工具层改造章节。

## GitHub Project Sources

### SRC-022 — MindFlow README-CN
- Source type: GitHub project material + local web archive
- Source URL: `https://github.com/neil-wang-global/MindFlow/blob/main/README-CN.md`
- Archive path: `references/web/04-github-com-neil-wang-global-MindFlow-blob-main-README-CN-md.md`
- Core content summary: MindFlow 是面向知识管理、认知演化与任务执行的 AI-native 自主决策系统；通过 Soul、Learning、Mind、Capability、Plan + Step、Task State 等层，让知识从正式读取到任务执行、反省、学习、审核、固化。
- Usable paraphrase: MindFlow 不是“先做任务再记笔记”，而是把长期标准、知识、能力、执行状态和反思固化为一个可演进系统。
- Credibility assessment: High; project self-description.
- Speech support: MindFlow 自我演进、知识工程、状态与能力模块化。

### SRC-023 — MindFlow SYSTEM
- Source type: GitHub project material + local web archive
- Source URL: `https://github.com/neil-wang-global/MindFlow/blob/main/SYSTEM.md`
- Archive path: `references/web/05-github-com-neil-wang-global-MindFlow-blob-main-SYSTEM-md.md`
- Core content summary: MindFlow 系统协议强调 lazy loading、模块 README 按需加载、Soul auto-load、Required Main Flow、Artifact Data Flow、Task State 等。正式主流程是 Task -> Learning(Read) -> Recognition -> Analysis -> Planning -> Execution Control -> Reflection -> Learning。
- Usable paraphrase: 渐进加载不是省 token 小技巧，而是用流程和状态管理上下文噪声，保证每个模块规则在真正需要时被读取。
- Credibility assessment: High; project self-description.
- Speech support: 渐进加载、强状态、流程约束、状态可恢复。

### SRC-024 — MindFlow tasks README
- Source type: GitHub project material + local web archive
- Source URL: `https://github.com/neil-wang-global/MindFlow/blob/main/tasks/README.md`
- Archive path: `references/web/06-github-com-neil-wang-global-MindFlow-blob-main-tasks-README-md.md`
- Core content summary: MindFlow task 资料，用于理解任务目录、任务状态和交接方式。
- Usable paraphrase: 任务不应只存在于对话里，而应落到文件状态中，使中断恢复和交接成为可能。
- Credibility assessment: High; project self-description,需在写作时回读细节。
- Speech support: Tasking、状态与交接章节。

### SRC-025 — MindFlow capabilities README
- Source type: GitHub project material + local web archive
- Source URL: `https://github.com/neil-wang-global/MindFlow/blob/main/capabilities/README.md`
- Archive path: `references/web/07-github-com-neil-wang-global-MindFlow-blob-main-capabilities-README-md.md`
- Core content summary: Capability 作为 MindFlow 的可执行能力单元，用于说明学习结果如何内化为可调用能力。
- Usable paraphrase: 知识沉淀的目标不是堆文档，而是形成可执行、可调用、可验证的能力。
- Credibility assessment: High; project self-description,需在写作时回读细节。
- Speech support: Capability、Skill、知识到能力。

### SRC-026 — POMASA README.zh-CN
- Source type: GitHub project material + local web archive
- Source URL: `https://github.com/eXtremeProgramming-cn/pomasa/blob/main/README.zh-cn.md`
- Archive path: `references/web/09-github-com-eXtremeProgramming-cn-pomasa-blob-main-README-zh-cn-md.md`
- Core content summary: POMASA 是用于构建声明式多智能体系统的模式语言和生成工具包。架构分为定义层、执行层、数据层；文件系统作为数据总线，数据从素材到草稿到最终输出逐步完善。核心原则包括模式是知识载体、模式有必要性等级、AI 是执行者、持续演进。
- Usable paraphrase: MAS 的价值不是多个 Agent 聊天，而是用模式语言、阶段管道、文件系统数据总线和可追踪产物组织协作。
- Credibility assessment: High; project self-description.
- Speech support: POMASA / MAS 强状态编排。

### SRC-027 — POMASA SKILL
- Source type: GitHub project material + local web archive
- Source URL: `https://github.com/eXtremeProgramming-cn/pomasa/blob/main/skills/pomasa/SKILL.md`
- Archive path: `references/web/10-github-com-eXtremeProgramming-cn-pomasa-blob-main-skills-pomasa-SKILL-md.md`
- Core content summary: POMASA Skill 生成 declarative MAS，强调 Prompt-Defined Agent、Orchestrated Pipeline、Filesystem Data Bus、Verifiable Data Lineage；要求读取 pattern catalog 和必需模式，遵循标准子智能体调用方式，并按 Blueprint completion criteria 核验结果。
- Usable paraphrase: 一个可用的 MAS 不是临时角色扮演，而是以 Blueprint、Pattern、参数、产物、验收标准构成的可执行系统。
- Credibility assessment: High; project self-description.
- Speech support: Skill、Blueprint、强状态、多智能体流程。

### SRC-028 — POMASA pattern catalog README
- Source type: GitHub project material + local web archive
- Source URL: `https://github.com/eXtremeProgramming-cn/pomasa/blob/main/skills/pomasa/pattern-catalog/README.md`
- Archive path: `references/web/11-github-com-eXtremeProgramming-cn-pomasa-blob-main-skills-pomasa-pattern-catalog-README-md.md`
- Core content summary: POMASA 模式目录，为多智能体系统设计提供可复用架构模式分类。
- Usable paraphrase: 模式语言把隐性的多智能体架构经验转为可共享、可组合的工程资产。
- Credibility assessment: High; project self-description,需在写作时回读细节。
- Speech support: 模式语言、可复用知识、MAS 架构。

## Source Coverage Notes

- 用户输入已拆分为 USER-001 至 USER-008，覆盖标题、主线、原创观点、必须纳入的 thought、流程和验收约束。
- PDF 原件与逐页视觉摘取已覆盖：CLI for AI Agents、PRD 到上线闭环、JoyCode、Coding Agent 飞轮、Agent Eval、Agent 可观测、OpenSandbox Runtime、人月神话与组织协调税、超级团队、DSL-Spec。
- Web 归档已覆盖：核心微信文章、知识工程文章、Anthropic Agent / Eval / long-running harness、Martin Fowler Harness Engineering、OpenAI Harness Engineering，以及 HumanLayer / LangChain / Inngest 的 harness 资料。
- GitHub 项目资料已覆盖 MindFlow 与 POMASA 的 README、SYSTEM、Skill 和 pattern catalog。引用时使用 GitHub URL，不使用本机绝对路径。
- 本清单优先引用 `references/paper-visual/extracted/`、`references/web/`、`references/papers/` 和 `user_input_template.md`；未新增或修改 `references/papers/`、`references/paper-visual/`、`references/web/` 下证据材料。
