# Raw Notes

Project: ai-work-system-speech-20260518

## Opening: Why Engineering and SDD Still Matter

- [USER-002] 开场应直接回应强模型时代的疑问：模型越来越会 planning、tool use 和 orchestration，为什么还需要工程化与 SDD。用户给出的核心判断是：工程方法的价值从“能力补丁”迁移到“治理工具”。工程化要解决的问题不是“模型不会写代码”，而是“模型太快开始写代码”：需求未澄清、边界未定义、验证未设计，模型已经流畅地产出实现。

- [SRC-011] 微信文章《当顶尖 Agent 模型越来越会自己干活，Prompt Engineering、SDD、MAS 还剩什么价值》提供了开场外部支撑。文章指出，顶尖模型确实吸收了部分原本外置的能力，但这不等于方法论失效，而是必要性开始分层。Prompt Engineering 更像任务接口设计，SDD 是需求澄清和护栏前置，MAS 是上下文、权限、并行和审计的系统架构，hooks 提供 deterministic control。

- [SRC-011] 可化用的表达：过去这些方法像给模型装外骨骼；强模型把部分规划、拆解、工具调用和自我修正吃回模型内部后，外部方法的角色变为系统治理。演讲中可压缩为：强模型降低了“让模型会做”的成本，但没有取消“让系统稳定、可控、可复查地交付”的问题。

- [USER-002] SDD 的价值不是神秘增强模型智力，而是把“先想清楚”制度化。它把意图、约束、验收、中间产物和检查点显化，让“想清楚”和“开始干”分开。这一点可作为从开场转入软件工程基本功的桥：如果工程结构仍重要，就要回到 SoC、抽象、目录结构、契约和测试。

- [SRC-002] 李文鹏材料支持“个人体感快不等于组织提效”。第 4-5 页显示 AI 写代码不是唯一问题，Review 成本、PRD 歧义、上下文留在对话里消失、需求交付效率未必提升，提示“用 AI 开发工具 ≠ 个人提效 ≠ 组织提效”。这可用于提醒听众：提速不应只看模型输出速度，要看从 PRD 到上线的整体断点。

- [SRC-017] Martin Fowler 的 Harness Engineering 文章给出工程化语言：外层 harness 的目标是提高 Agent 首次做对概率，并通过 feedback loop 在到达人类眼前前尽量自我修正。Feedforward controls 预防偏差，feedback controls 观测并帮助自我修正。可用于把“工程化”讲成可操作的控制系统，而不是抽象方法论。

## Software Engineering Fundamentals

- [USER-003] 软件基本功章节应略写但态度明确：SoC、抽象/面向对象、文件目录结构不是过时概念，而是 AI 文件工程的底层能力。文档也需要单一职责：Story、ADR、Spec、Plan、State、Review、Eval 各有边界，避免重复和事实分叉。

- [USER-003] 目录结构不是收纳方式，而是知识对象的地址空间。Agent 能否找到、理解、验证上下文，取决于文件是否在正确位置、命名是否稳定、引用关系是否清晰。这一点可与 [SRC-018] 的“给 Codex 一张地图，而不是一千页手册”连接。

- [SRC-018] OpenAI Harness Engineering 文章中，仓库知识被作为 system of record：短 AGENTS.md 作为目录，结构化 docs/ 作为真相来源。可用于支持“工程文件不是文档堆，而是可导航的知识系统”。同文还指出巨型 AGENTS.md 会挤占上下文、规则失焦、快速腐烂、难以验证。

- [SRC-003] JoyCode 材料指出企业级编码面临业务复杂、用户画像丰富、复杂长任务和超大代码仓等挑战，导致上下文迅速膨胀并形成“上下文爆炸”。这可以支撑“AI 文件工程需要结构化目录和引用，不是把所有信息塞进 prompt”。

- [SRC-001] CLI for AI Agents 强调严格管控上下文窗口，巨大 API 返回包会摧毁推理能力，需要字段掩码、分页、结构化输出等方式维持高效推理。可化用到文件工程：上下文管理不是越多越好，而是给模型可处理、可验证、低噪声的上下文。

- [SRC-017] Harness Engineering 中 computational controls（测试、lint、类型检查、结构分析）与 inferential controls（AI review、LLM judge）的区分，可映射到软件基本功中的测试验证：确定性问题应优先交给确定性工具，推理判断再交给模型或人。

## MindFlow and Knowledge Engineering

- [SRC-022] MindFlow README-CN 将 MindFlow 定义为面向知识管理、认知演化与任务执行的 AI-native 自主决策系统，不只是多智能体编排器或普通知识库，而像一个可持续编辑的数字人格系统。它包括 Soul、Learning、Mind、Capability、Plan + Step、Task State 等层。

- [SRC-022] MindFlow 的设计把长期标准、正式知识、系统级认知过程、可执行能力、任务计划和运行状态拆成稳定层。可化用为：它不靠把所有材料复制进一个超长上下文维持智能，而是用模块化、引用、状态和能力来组织知识。

- [SRC-022] 关键摘记：MindFlow 不要求“先做任务，再顺便记笔记”，而是要求先按 Soul 读取正式知识，再识别和分析任务，生成正式 Plan，调用 Capability 执行，最后复盘、学习、审核、固化并形成能力升级。用于说明“自我演进”不是玄学，而是有知识进入、任务执行、反思和能力升级的闭环。

- [SRC-023] MindFlow SYSTEM 强调 lazy loading：SYSTEM.md 只定义流程骨架和跨模块规则，模块 README 在进入模块时才加载，TEMPLATE 在产出特定 artifact 时加载。可作为“渐进加载”的直接证据：上下文不是一次性铺满，而是按流程阶段加载。

- [SRC-023] MindFlow 主流程 Task -> Learning(Read) -> Recognition -> Analysis -> Planning -> Execution Control -> Reflection -> Learning 与 Artifact Data Flow（learning-read.md → task-profile.md → analysis.md → plan.md → cache/_output → reflection-report 等）说明其强状态和可交接特征。可用于讲“状态让任务可恢复、可检查、可交接”。

- [USER-004] 用户原创观点：软件系统的本质就是知识，智能 AI Agent 系统也是知识。代码、文档、测试、规则、任务状态和运行反馈都是知识在不同阶段的表达形式。演讲中应把 MindFlow 从文件夹设计上升到知识工程：文件只是载体，目录、引用、状态、能力和复盘构成 Agent 可操作的知识空间。

- [USER-004] 必须保留的判断：AI 是未来的新软件，它打破了“软件只能由开发人员制作”的知识垄断，推动数字民主化。可放在 MindFlow / 知识工程章节中，作为为什么知识工程重要的根本背景。

- [SRC-012] 《不是提示词工程，是知识工程》提出 AI 协作需要人主导问题导向、价值/视角、信息储备、理论方法和表现形式。这支持“知识工程不是提示词调参，而是人类对问题、知识、方法和表达的结构化组织”。

## POMASA, MAS, and Strong State

- [USER-005] MAS 不应讲成多个 Agent 聊天，而应讲成围绕状态推进的编排系统：谁读取什么，谁产出什么，产物放在哪里，谁验收，失败如何回流，下一步由谁接手，都必须可追踪。

- [SRC-026] POMASA README.zh-CN 将 POMASA 定义为用于构建声明式多智能体系统的模式语言和生成工具包。架构分为定义层、执行层、数据层：蓝图定义 Agent 行为，参考数据提供领域知识和方法论，运行时执行蓝图，编排器通过阶段化管道协调工作者，文件系统作为数据总线，数据从素材到草稿到最终输出逐步完善。

- [SRC-026] POMASA 核心原则：模式是知识载体，模式有必要性等级，AI 是执行者，系统持续演进。可用于讲 MAS 的成熟形态：不是“多叫几个模型一起想”，而是把隐性架构经验转成显性模式，把数据和产物放入可追踪文件系统。

- [SRC-027] POMASA SKILL 描述其支持 Prompt-Defined Agent、Orchestrated Pipeline、Filesystem Data Bus、Verifiable Data Lineage。它要求一个任务实例对应一次子 Agent 调用，调用者只传参数，不改写 Blueprint，并按 Blueprint completion criteria 验证结果。这直接支持“强状态 + 可验证谱系”的 MAS 观点。

- [SRC-013] Anthropic Building Effective AI Agents 将 workflows 与 agents 区分：workflows 通过预定义路径编排 LLM 和工具，agents 由 LLM 动态决定流程和工具使用。可用于引出状态控制三分法：固定 workflow 更可预测，agent 自主更灵活，工程上要按任务条件组合。

- [SRC-013] Orchestrator-workers workflow 适合复杂任务，由中心 LLM 动态拆分、委派并综合结果。演讲可强调：这类编排要成功，必须有上下文边界、产物协议、权限和验收，不然只是更多不可控对话。

- [USER-005] MindFlow 和 POMASA 可形成互补叙事：MindFlow 讲认知结构和自我演进，POMASA / MAS 讲多角色、多产物、多阶段的组织方式。两者结合指向 AI-native 系统的强状态、可编排、可演进。

## Skill, Engineering Files, and Rules

- [USER-006] Skill 与工程文件本质都是可执行知识：把人的经验、判断标准、流程约束和输出格式变成 Agent 可读取、可执行、可检查的上下文资产。差异在调度方式：Skill 往往是建议式和随机触发，工程文件处在流程规定的位置，调度更确定；Rules / Hooks 则接近强约束固定调度。

- [SRC-011] 核心微信文章支持该三分法：Prompt Engineering 是任务接口设计，SDD 是需求澄清与护栏前置，MAS 是上下文、权限、并行和审计架构，hooks 提供 deterministic control，确保某些动作总会发生，而不是交给模型临场决定。

- [SRC-001] CLI for AI Agents 第 7 页提出“分发智能体技能，而不仅仅是命令”：Agent 不看 `--help`，依赖对话开启前注入的上下文，通过结构化 `SKILL.md` 传递无法被直觉推断的硬性规则。例如 mutating operations 要 dry-run、list call 要 fields。可用于说明 Skill 是带规则的可执行接口。

- [SRC-027] POMASA SKILL 是一个完整可执行 Skill 示例：它定义 name、description、使用条件、用户输入处理、模式选择、必读模式、生成流程和验收原则。可用于说明成熟 Skill 不只是提示词片段，而是包含触发、输入、步骤、输出和验证的工程资产。

- [USER-006] Skill / Rule 验收标准必须写入演讲：什么时候触发；输入是否明确；执行步骤是否可稳定复现；输出是否能被下游消费；是否内置验证动作；是否减少重复解释；是否防止同类错误复发；权限和副作用是否受限。

- [SRC-017] Harness Engineering 把 AGENTS.md、Skills 作为 feedforward inferential controls 的例子，把结构测试、lint、类型检查作为 feedback computational controls。可用于说明 Skill、Rules、测试、hooks 不是同一层东西，而是共同构成“前馈 + 反馈”的 harness。

- [SRC-018] OpenAI 文章支持工程文件的确定编排：短 AGENTS.md 作为目录，结构化 docs/ 承载系统记录；日志、指标、DOM 快照、截图等也被做成 Agent 可读资源。可用于说明工程文件和工具环境共同构成 Agent 可执行上下文。

- [SRC-001] “Agent 不是受信任的操作员”可用于权限边界与副作用控制。演讲中可说：Skill 和 Rules 的验收不能只看能否完成任务，还要看是否限制了危险动作、校验了输入、让副作用可审计。

## Story, Knowledge, and Flyway Analogy

- [USER-004] Knowledge 是静态 Story，Story 是流动 Knowledge。代码工程本质是知识工程，因为每一次需求、设计、实现、测试和验收，都是知识被发现、修改、固化的过程。

- [USER-004] Flyway 类比：每个 Story 像一个 migration，带着时间性和变化意图；Knowledge 像所有 migration 执行完之后的当前数据库状态。Story 本身有时效性，长期维护困难；Story 带来的增量一旦被验证，就应该回写到当前 Knowledge、工程文档、Skill、测试或 eval case 中。

- [SRC-002] 李文鹏材料中的“Skill 化 + 回写闭环”“协同协议 + 资产自动生长”“SOP 就是资产生产线”可支撑 Story 到 Knowledge 的转化。流程不闭环时，资产不积累；有回写闭环时，迭代后 Knowledge 随代码和文档自然增长。

- [SRC-002] 第 8-10 页可作为流程证据：SOP 阶段包括 OnBoard、Spec、Design & Plan、Implement、Review、Release；Spec 被定义为需求契约，包含用户故事、功能需求、成功标准、待确认项。演讲中可把 Spec / Story 看成知识增量进入系统的入口。

- [SRC-014] Anthropic eval 文章指出 eval task 是带输入和成功标准的测试，outcome 是最终环境状态而不只是模型声称完成。可用于 Story 验收：一个 Story 是否完成，不能只看 Agent 的总结，而要看业务意图、AC、测试、状态结果是否成立。

- [USER-007] Skill 必须在流程中同步更新和维护，并通过类似 `SOUL.md` 的文件承载长期原则、流程约束、知识更新规则和 Skill 维护机制。可放入 Story / Knowledge 之后，说明“完成一个 Story 后，知识必须回写到长期资产”。

## Role-Based Team Workflow

- [USER-007] 角色而非人：BA / DEV / QA / UI / Agent 是思考帽，同一个人可以戴不同帽子，一个 Agent 也可承担部分帽子动作。关键是所有角色围绕同一仓库和同一强状态空间协作。

- [USER-007] 统一流程必须写清：需求进入，经过 Tasking、澄清、设计、计划、实现、Review、测试和验收，最后代码出去，并且验收测试通过。它不是 checklist，而是资产生产线：每步有输入、输出、状态、负责人角色、检查点和回写位置。

- [USER-007] Tasking 是需求分析与拆解，接近 SDD：把业务意图、用户路径、验收标准、边界条件、依赖关系和风险拆出来，再进入实现。它不是 TODO 列表，而是把模糊需求转成可执行、可验证、可分派任务结构。

- [SRC-002] “SOP 就是资产生产线”可直接支撑统一流程。其阶段从 OnBoard / Spec / Design & Plan / Implement / Review / Release 贯穿 PRD、Spec、Design、OpenAPI、Work Items、代码、测试、Review 报告、Release 归档和基座回写。可作为演讲中流程图的材料来源。

- [SRC-008] “人月神话”材料展示传统产运研固态组织：运营感知风险、产品做需求分析和 PRD、研发编写代码测试上线，中间存在部门墙和信息损耗。这可用于说明为什么要把 BA / DEV / QA / UI / Agent 视为围绕同一仓库运转的角色，而不是部门墙后的交接人。

- [SRC-018] OpenAI 文章中 humans steer, agents execute；人的工作转向设计环境、说明意图、构建 feedback loops。可用于角色章节：Agent 不是替代所有角色，而是承担执行、检查、检索、验证等动作，人负责设定目标、边界、反馈和治理。

- [SRC-014] Eval 文章强调 eval suite 可以解决两个工程师对同一初始 spec 边界理解不同的问题，早期 eval 强迫产品团队定义成功是什么。可用于 BA / QA 角色：BA 澄清业务意图，QA 把验收标准变成可测标准和 eval。

- [USER-007] 多线程流程：从 Epic 到 User Story，自动解析 Story 依赖，通过 Worktree 并行推进功能增量。此处应强调 Worktree 是隔离机制，不是随意并发；每个分支都要有状态、测试、Review 和合并门禁。

## Automation and Long-Running Agents

- [USER-007] 自动化与无人值守应在角色流程后讲，因为一旦强状态、角色协议、工程文件、测试与回写都建立，才能讨论长时间、低人工干预的功能编码开发。不要讲成完全无人值守，而是讲成在明确边界下的低人工介入。

- [SRC-015] Anthropic long-running agents 文章指出跨上下文窗口是长时间 Agent 的核心挑战：每个新 session 像新工程师接班但没有记忆。解决方案是 initializer agent 初始化环境，coding agent 每次增量推进并留下清晰 artifact。

- [SRC-015] 可直接化用的模式：feature list 文件把功能需求展开并标记通过状态；progress file 记录 Agent 做过什么；git history 帮助恢复；coding agent 每次只做一个 feature；结束时保持 clean state；不能删除或修改测试来掩盖缺陷；用浏览器自动化做人类用户路径验证。

- [SRC-015] 这篇文章还指出常见失败模式：Agent 过早宣布整个项目完成；留下有 bug 或无文档进展的环境；过早标记 feature done；浪费时间猜测如何运行 app。对应解法是 feature list、progress notes、git log、init.sh、基本端到端测试。

- [SRC-018] OpenAI 文章补充工具环境：app 可按 git worktree 启动，Agent 能通过 Chrome DevTools Protocol、DOM 快照、截图和导航验证 UI；日志、指标、trace 通过本地 observability stack 暴露给 Agent；单个 Codex run 可运行六小时以上。可用于讲无人值守依赖可读环境，而不是盲信模型。

- [SRC-007] OpenSandbox 材料说明 Agent Runtime 需要文件系统、命令执行、服务访问、长连接、高并发、短生命周期、可控联网、统一执行与访问。可用于说明长时间 Agent 不只是 prompt 问题，还需要运行时、隔离、安全和资源回收。

- [USER-007] 自动化演进路径：单线程到多线程，手动协作到自动编排，Agent 执行到 Agent Teams。这里应保持克制，把 Agent Teams 放在展望，不把它讲成已成熟的全自治组织。

## Evaluation, Observability, and Tooling

- [SRC-014] Agent eval 的基本结构：给 AI 一个输入，再用 grading logic 衡量输出和最终状态。关键对象包括 task、trial、grader、transcript / trace、outcome、evaluation harness、agent harness、evaluation suite。演讲中可用这组术语建立评估章节的准确性。

- [SRC-014] 重要判断：Agent 会跨多轮使用工具、修改状态、根据中间结果调整，因此错误会传播和复合；评估不能只看最后回答，必须看轨迹、工具调用、中间状态和最终环境 outcome。适合连接“反思循环必须带证据”。

- [SRC-005] 章平材料的旅游搜索 Agent 案例适合讲“传统监控盲区”：响应时间、错误率、工具激活成功率等技术指标可能正常，但用户参与度下降、无效反馈增加、工具选择准确性和响应有用性变差。缺乏系统化评估会让质量隐形降级持续数周。

- [SRC-005] 可化用的工程判断：Prompt 修改可能删除了必须使用的工具指令，导致 Agent 从专业计算转向泛化搜索；自动化评估能把发现和诊断时间从周级压缩到小时/天级。写作时如引用具体“98% 时间节省”等数字，应回查原页。

- [SRC-006] 可观测材料支持“给 Agent 做 CT”：大规模 Agent 的黑盒困境需要统一观测底座，深水区要做 AgentKit 深度观测，最终从可观测走向可迭代。可用于说明可观测不是 ops 附加项，而是 Agent 质量改进的证据链。

- [SRC-004] Coding Agent 飞轮材料将 Feedback Loop、Benchmark、Agent Engineers 放在同一主线。可用于讲：失败不是一次性事故，而是 eval case 的来源；Benchmark 不是论文指标，而是组织持续改进 Agent 行为的资产。

- [SRC-017] Harness Engineering 的 feedforward / feedback 与 computational / inferential 控制矩阵可用于梳理工具层：AGENTS.md、Skills 是前馈指导；测试、lint、类型检查是确定性反馈；AI review、LLM judge 是推理型反馈。演讲可强调“确定性的事交给确定性工具”。

- [SRC-001] CLI for AI Agents 提供工具层改造材料：Agent 体验与人类体验不同；Agent 需要 JSON 原生载荷、可动态查询的 schema、字段裁剪、输入防御、结构化 Skill 和单一信源多终端架构。可用于讲 CLI / MCP / 工具 API 不应只面向人类终端习惯。

- [SRC-001] “智能体并非受信任的操作员。绝不能盲目信任其输入。”可用于安全和权限章节。工具层应对路径、查询参数、ID、双重编码等做防御，把 CLI 作为错误输入的最后一道防线。

- [SRC-013] Agent 编排方式可按复杂度介绍：简单 LLM 调用、prompt chaining、routing、parallelization、orchestrator-workers、evaluator-optimizer、autonomous agents。每种都对应不同成本、延迟、可预测性和灵活性。不要把“更复杂”讲成“更先进”。

- [USER-008] 提速章节必须有评估标准。可结合 [SRC-002] 的“个人提效 ≠ 组织提效”、[SRC-008] 的协调税、[SRC-014] 的 eval、[SRC-017] 的质量左移讲：提速来自流程缩短、上下文传递损耗下降、反馈更快、测试更靠前、失败更快变成资产，而不是 token 生成速度。

- [SRC-008] 人月神话材料中传统固态组织的部门墙和 PRD 信息损耗，可用于解释 AI 为什么可能打破协调税：Agent 共享同一仓库状态，围绕统一工程资产工作，通过自动验证和状态回写减少重复解释。但必须避免写成“人越少越好”。

- [SRC-018] OpenAI 文章的“Humans steer. Agents execute.”可作为总结句：未来工程师的稀缺资源是时间和注意力，主要工作变成设计环境、定义意图、搭建反馈回路、让 Agent 可靠工作。
