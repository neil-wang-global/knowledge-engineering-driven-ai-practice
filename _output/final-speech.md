# 知识工程驱动的 AI 实践

项目：ai-work-system-speech-20260518

> 这是一份 60-90 分钟中文演讲稿。主线只有一条：如何构建统一流程，以及如何构建一个高质量的统一流程。

## 开场

各位好，今天分享的题目是《知识工程驱动的 AI 实践》。这个题目听起来有点大，但我想讲的不是一个抽象概念，也不是一组工具清单。我想讨论一个很具体的问题：当 AI 已经能写代码、能读仓库、能调用工具、能做一部分规划时，我们怎样把它放进一个稳定、可协作、可演进的工作系统里。

很多团队第一次接触 AI Coding，会从提示词、模型选择、编辑器插件开始。这些当然有价值，但如果只停在这里，很快会遇到同一个问题：模型确实能产出代码，而且产出得很快；可团队不一定知道它为什么这么写，边界有没有覆盖，需求有没有被误解，测试有没有验证到关键路径，下一次换一个 Agent 或换一个人接手时，状态还能不能恢复。

所以今天我不会把重点放在“如何让模型多写一点代码”。我更关心的是：怎样让模型的推理结果可以被流程约束，被状态记录，被测试验证，被团队交接，并且最终沉淀成工程资产。用一句话概括，AI-native workflow 是一个动态系统：模型负责推理，流程负责约束，状态负责让推理结果可以被恢复、检查和交接。这个定义是本次分享的项目 framing，不是行业标准术语，但它会贯穿今天所有章节。

## 第 0 章：为什么还要工程化与 SDD

我们先回答一个最容易被问到的问题：模型越来越强，为什么还要工程化？为什么还要 SDD、流程、规则、状态、验收？

这个问题不能只从“模型会不会写代码”来回答。今天很多团队的真实体感，已经不是 AI 不会写，而是 AI 太快开始写。需求还没澄清完，它已经开始实现；边界条件还没想清楚，它先自己补默认值；方案只有一个模糊轮廓，它已经把执行往前推。表面看很积极，实际上是在用流畅感掩盖过早收束。

所谓过早收束，不是模型输出慢，也不是模型语气不自信。恰恰相反，它常常表现得很自信。它会很快选定一条路径，很快补齐缺失信息，很快生成代码，很快宣布完成。但它没有充分展开问题空间：异常路径有没有覆盖，权限边界有没有想清楚，状态一致性有没有保证，验收条件有没有被定义，测试有没有验证到真正的业务路径。这种问题在演示场景里不一定明显，在真实工程里会变成返工、线上风险和知识漂移。

顶尖模型确实在变化。它们越来越能自己拆任务、调工具、维持更长轨迹，也能把一部分 planning、tool use、orchestration 吃进模型内部。以前很多外置提示词、外置流程、外置角色，是在给模型补能力；现在最强的一档模型，已经把其中一部分能力内化了。所以我们不能把 Prompt Engineering、SDD、MAS 当成永远固定的一套仪式。

但这不等于方法论失效。更准确地说，方法论的必要性开始分层。你用什么模型，花多少钱，任务有多开放，错误代价有多高，是否需要协作、审计、复用和治理，决定了工程结构要多强。一次性的个人探索，强模型直接交互可能已经够用；多人协作、预算受限、需求含糊、边界复杂、结果要追责的任务，就必须把外部结构建起来。

尤其是中端或低端模型、上下文不足、反馈不足、预算受限的场景，过早收束会更早浮出来。它们更依赖清晰的任务边界，更依赖明确输入，更依赖检查点和验收标准。你不给结构，它就会自己补结构；你不给边界，它就会自己猜边界；你不给验证，它就会用“看起来合理”的输出来代替验证。这不是态度问题，是反馈不足和约束不足的问题。

这就是 SDD 的价值。SDD 不是神秘地提高模型智力，它是把“想清楚”和“开始干”分开。它要求我们先把 what、why、guardrails、验收标准和关键边界显化，再进入 how。它对抗的不是模型愚笨，而是项目里的模糊、短视和过早执行。

Prompt Engineering 的价值也在迁移。它越来越不像“教模型怎么想”的咒语，而更像任务接口设计：目标是什么，输入范围是什么，禁止事项是什么，成功标准是什么，输出结构是什么。提示词不是魔法，它是任务契约的一部分。

MAS 的价值也不能理解成“多叫几个模型一起想”。真正有工程价值的 MAS，是把复杂任务拆成角色、上下文、权限、阶段、产物和验收。它让系统知道谁负责澄清，谁负责实现，谁负责核验，谁能读什么，谁能改什么，中间产物放在哪里，失败如何回流。它解决的是上下文隔离、权限边界、并行推进和审计问题。

Rules 和 Hooks 则解决另一类问题：哪些动作不能交给模型临场决定。比如提交前必须跑检查，引用必须可追溯，敏感操作必须确认，测试失败不能宣称完成。这些动作要有 deterministic control。模型可以推理，但固定边界要由流程和工具兜住。

所以，AI 编程不是推翻软件工程，而是放大软件工程基本功。AI 越快，越需要流程控制它什么时候开始；AI 越能做，越需要状态记录它做到了哪里；AI 越像执行者，越需要权限边界和验收边界。

今天的主题因此不是“AI Coding 技巧”，而是如何构建统一流程，如何构建一个高质量的统一流程。统一流程从输入到输出：需求进来，经过 Tasking、澄清、设计、计划、实现、Review、测试和验收，最后代码出去，并且验收测试通过。所有后面的概念，SoC、MindFlow、POMASA、Skill、Rules、Knowledge、Story、Worktree、Eval、Harness，都会回到这条流程上。

## 第 1 章：软件基本功：SoC、抽象/面向对象、文件目录结构

既然工程结构仍然重要，我们就先回到几个很老的基本功：SoC、抽象/面向对象、文件目录结构。

这些概念不需要重新讲教科书定义。对 AI 文件工程来说，SoC 就是每个文档、每个文件、每个知识对象只承担清晰职责。Story 负责描述一次业务增量，ADR 负责记录架构决策，Spec 负责表达需求契约，Plan 负责拆解执行路径，State 负责记录当前进度，Review 负责记录审查意见，Eval 负责验证行为是否满足要求。它们应该小而精，边界清楚，尽量避免互相复制。

重复文档在 AI 系统里会制造事实分叉。一个 Agent 看到 A 文件，一个 Agent 看到 B 文件，两份材料都像权威，但内容不一致，系统就会开始漂移。正确做法是用 ID、链接和引用关系维护依赖，而不是把同一段事实复制到很多地方。这样，知识更新时有一个权威位置，引用者只引用它。

抽象和面向对象也可以迁移到 AI 文件工程。Skill、Rule、Capability、Agent Blueprint、工程约定、验收模板，本质上都是知识对象。一个好的知识对象要有边界：它解决什么问题，什么时候触发，输入是什么，输出是什么，副作用是什么，下游如何消费。没有边界的知识对象，就像没有接口的类，短期可用，长期不可维护。

目录结构也不是收纳方式。它是知识对象的地址空间。Agent 是否能找到正确文件，是否能理解文件之间的关系，是否能在任务中恢复状态，都受目录结构影响。OpenAI 的 Harness Engineering 文章里把仓库知识看作 system of record，并强调类似 AGENTS.md 的文件更像地图，不是百科全书；这个说法对我们很有启发。目录、入口文件、引用关系、测试命令、状态文件共同组成 Agent 可导航的工程地图。

所以，AI 辅助编程的核心变量是上下文管理。上下文管理不是把所有材料都塞进去，而是给模型低噪声、可处理、可验证的上下文。确定性的事交给确定性的工具，推理性的事交给模型或人。这个分工，是高质量流程的第一层地基。

## 第 2 章：MindFlow 的自我演进与知识工程

有了文件工程的基本功，我们就可以看 MindFlow。这里我不把 MindFlow 讲成项目说明书，而是把它看作一个知识工程系统。

MindFlow 的项目资料中有 Soul、Learning、Mind、Capability、Plan、Task State 等结构。它把长期原则、学习资料、能力单元、执行计划、任务状态和反思结果分开管理。MindFlow SYSTEM 里还强调 lazy loading 和 Artifact Data Flow：不是所有上下文一开始都加载，而是按阶段、按需要加载；任务执行中的产物和状态要被记录，便于恢复、交接和复盘。

这背后的思想很重要。一个智能系统不应该把所有知识都揉成一个巨大 prompt。它需要把知识分层：长期稳定的原则放一层，项目知识放一层，可复用能力放一层，当前任务状态放一层，执行后的反思再回写一层。这样，系统中断后可以恢复，角色切换后可以交接，失败发生后可以沉淀。

MindFlow 也让我们自然进入“知识工程”。我想提出一个项目观点：软件系统的本质就是知识，智能 AI Agent 系统也是知识。代码是知识，文档是知识，测试是知识，规则是知识，任务状态是知识，运行反馈也是知识。它们处在不同阶段，表达形式不同，但都是团队对业务、技术、约束和经验的固化。

从这个角度看，AI 是一种未来的新软件。这里我把它作为演讲者观点，而不是外部事实来引用。过去，业务人员和开发人员之间有一条很厚的知识转换链：业务知识经过会议、PRD、排期、开发、测试，最后变成系统。AI 降低了把知识变成可运行系统的门槛，让更多懂业务的人可以参与到系统构造中。这是一种数字民主化的方向。

但门槛降低不等于工程消失。恰恰因为更多人可以把知识转成系统，知识对象、流程约束、验收标准、状态回写就更重要。MindFlow 给我们的启发是：不要把 AI 系统看成一次对话，要把它看成一个可演进的知识空间。

## 第 3 章：POMASA 与 MAS 的强状态

接下来讲 POMASA 与 MAS。POMASA 在这里不是作为工具教程来讲，而是作为一个例子，说明多智能体系统如果要进入工程实践，必须从“聊天”走向“强状态编排”。

很多人听到 MAS，会想到多个 Agent 在一个群里聊天。这个理解太轻了。真正有工程价值的 MAS，不是多个 Agent 聊天，而是一个围绕状态推进的编排系统。关键问题不是“有几个 Agent”，而是：谁读取什么，谁产出什么，产物放在哪里，谁验收，失败如何回流，下一步由谁接手。

POMASA 的项目资料把它描述为构建声明式 MAS 的模式语言和生成工具包，强调定义层、执行层、数据层，强调文件系统作为数据总线。在它的 Skill 资料里，可以看到 Blueprint、Pattern、Prompt-Defined Agent、Orchestrated Pipeline、Filesystem Data Bus、Verifiable Data Lineage 这些概念。这些词背后其实是同一件事：多角色、多产物、多阶段协作必须有强状态。

MindFlow 讲的是认知结构和自我演进；POMASA / MAS 讲的是多角色、多产物、多阶段的组织方式。两者放在一起，就能解释 AI-native 工作系统为什么需要强状态。模型负责推理，流程负责约束，状态负责让推理结果可以被恢复、检查和交接。

强状态不是把所有东西都写下来。强状态是让关键产物有位置，关键转移有记录，关键判断有来源，关键验收有证据。没有强状态，Agent 之间的协作会变成聊天接力；有了强状态，协作才像工程流水线。

## 第 4 章：状态控制三分法

在讲 Skill、工程文件和 Rules 之前，我们先建立一个控制框架。我把 AI 工作系统的状态控制分成三类。这是本次分享的工程分类，不是外部标准。

第一类是强约束、固定调度。比如 Rules、Hooks、必须读取的工程文件、固定检查点、必须执行的测试、提交前检查、权限边界和安全规则。这类控制可靠性最高，灵活性最低。它适合承载必须发生的动作。

第二类是有建议的 AI 自主判断。比如 Skill、推荐流程、可选 checklist、按任务判断是否加载的能力模块。它保留一定灵活性，也提供一定约束，但会存在漏触发、误触发和触发时机不稳定的问题。

第三类是完全由 AI 控制。模型自己决定读什么、怎么拆、什么时候停、是否验证。这类方式灵活性最高，但可靠性最低，适合探索、低风险实验和一次性任务。

这里有一个经验判断：可靠性和灵活性通常存在张力。越固定，越可靠，但越不自由；越自由，越灵活，但越不稳定。高质量流程的关键不是选一种，而是组合使用：强约束兜底，建议式调度提供能力，AI 自主控制负责开放探索。Anthropic 在 Building Effective Agents 中区分 workflows 与 agents，也提醒我们从简单、可预测的模式开始，只有任务需要时才增加自主性。

## 第 5 章：Skill、工程文件与 Rules

有了三分法，我们就能更清楚地看 Skill、工程文件与 Rules。

Skill、工程文件和 Rules，本质上都是可执行知识。它们把人的经验、判断标准、流程约束和输出格式，组织成 Agent 可读取、可执行、可检查的上下文资产。

但它们的调度方式不同。Skill 往往更依赖触发条件和模型判断，调度有不确定性。它可能在合适的时候被调用，也可能被漏掉。工程文件通常处在流程规定的位置，比如需求模板、设计模板、任务状态、验收清单、项目原则文件，调度更确定。Rules / Hooks 则接近强约束，每次满足条件都执行，适合放安全边界、格式要求、提交检查和必须验证的动作。

所以不要执着于 Skill 这个名字。往大里讲它叫 Skill，往小里讲就是工程文件；更抽象地说，它们都是知识对象。真正重要的是结构化、模块化和可验收。

一个成熟 Skill 不应该只是提示词片段。它更像一个函数：有触发条件，有输入，有前置假设，有步骤，有输出，有错误处理，有权限边界，有副作用说明，有验证方式，下游能消费。CLI for AI Agents 的资料强调，人类体验和智能体体验不同，Agent 更需要结构化信息、JSON、schema、自省能力和输入防御。这个思想同样适用于 Skill：给人看的说明，不一定适合 Agent 稳定执行。

Rules 也要验收。一个 Rule 如果太宽，会频繁打断流程；如果太窄，会漏掉风险；如果没有退出条件，会让系统僵硬。Rules 像 Hook 式强约束，优点是稳定，缺点是自由度低。Skill、工程文件、Rules 要组合使用：Skill 提供可复用能力，工程文件提供结构化上下文和流程位置，Rules 提供确定性约束。

## 第 6 章：Knowledge 与 Story

接下来进入知识工程的核心。我想用两个词：Knowledge 和 Story。

本次分享采用一个项目观点：Story 是动态知识，Knowledge 是静态 Story。Story 是一次变化，是某个用户路径、某个业务意图、某个增量的表达。Knowledge 是这些变化被验证、被固化、被回写之后的当前状态。

User journey 本质上是团队发现、验证、固化知识的过程。需求澄清是在发现知识，设计是在组织知识，实现是在编码知识，测试是在验证知识，Review 是在校正知识，验收是在确认知识已经进入系统当前状态。

如果一个 Story 做完了，但知识只留在聊天记录里，或者只留在某个 Agent 的临时上下文里，它就没有真正沉淀。高质量流程要求被验证的增量回写到 AC、ADR、工程文档、Skill、Capability、测试、eval case 或 workflow pattern 中。李文鹏关于“让 AI 运行在工程资产上”的材料强调工程资产、SOP、Doc 与 Code 联动、交付闭环；Anthropic 的 Agent eval 文章也强调不能只看模型自述完成，而要看 task、trial、grader、transcript/trace 和 outcome。这些材料共同支撑一个方向：知识必须通过流程进入可验证资产。

## 第 7 章：Story 到 Knowledge 的 Flyway 类比

为了让这个关系更容易理解，可以用 Flyway Migration 类比。这个类比是项目观点，不是 Flyway 官方定义。

每个 Story 都像一个 migration。它有时间性，有变化意图，有增量内容。Knowledge 则像所有 migration 执行完后的当前数据库状态。我们不会让业务系统长期依赖一串零散 migration 来回答“现在数据库是什么样”；我们会关心当前 schema 和当前数据状态。同样，团队也不能长期依赖一串 Story 来回答“系统现在应该怎样工作”。

Story 有时效性。它描述的是“这次为什么改、改了什么、怎么验收”。但当它完成后，里面被验证的知识应该进入当前 Knowledge：代码要变，文档要变，测试要变，Skill 可能要变，规则可能要变，eval case 可能要增加。

这就是回写闭环的意义。没有回写，流程只产出一次代码；有回写，流程会让资产增长。统一流程的价值，不只是把需求送到代码，而是让每一次需求都成为知识系统的一次增量演进。

## 第 8 章：Skill 与 Story 的验收

现在我们把 Skill 和 Story 放到同一个质量框架下看。高质量流程的关键不是“定义了 Skill”或“写了 Story”，而是它们能不能被稳定验收。

Skill / Rule 的验收，可以像验收函数一样问：什么时候应该触发？输入是否明确？前置假设是否说清？步骤能否被不同 Agent 稳定复现？输出是否结构化？下游是否能消费？是否内置验证动作？权限和副作用是否被限制？失败时如何处理？是否能减少重复解释？是否能防止同类错误复发？如果这些问题回答不清楚，这个 Skill 还只是经验片段，不是稳定工程资产。

Story 的验收则要问：业务意图是否清楚？用户路径是否完整？验收标准是否可测？依赖是否明确？边界是否可实现？最终状态是否符合 Knowledge？完成后是否有应当回写的文档、测试、Skill、eval case？

这里要特别强调：不要只相信 Agent 说“我完成了”。Anthropic 的 eval 资料提醒我们，评估应该关注最终状态、trace/transcript、grader 和 outcome。Martin Fowler 的 Harness Engineering 文章也强调 feedforward / feedback controls，以及把质量检查前移。确定性的检查交给确定性的工具，推理判断交给模型或人；反思循环必须带证据，失败应该进入 eval case。

## 第 9 章：角色而非人

有了知识对象和验收，我们再看团队协作。这里的关键词是：角色而非人。

BA、DEV、QA、UI、Agent，不一定对应固定人头。它们更像几顶思考帽。一个人可以戴多顶帽子，一个 Agent 也可以承担某些帽子的动作。关键是每顶帽子有清晰责任：BA 关注业务意图和验收标准，DEV 关注设计与实现可行性，QA 关注可测性和质量风险，UI 关注用户路径和交互完整性，Agent 负责检索、执行、修改、验证、总结等具体动作。

这里要引入单仓库原则：仓库是 BA / DEV / QA / UI / Agent 共享的强状态空间。这也是项目 framing。仓库不只是代码存放处，而是需求、设计、计划、状态、测试、Review、规则、Skill、验收证据共同存在的地方。OpenAI 的 Harness Engineering 文章中提到 repository knowledge as system of record，这可以作为外部支撑。

传统软件团队常见的问题，是部门墙、协调税和 PRD 信息损耗。相关材料提到产运研协作中存在沟通、同步、协调成本。AI 的价值之一，是压低上下文传递成本和重复解释成本：Agent 可以读取同一套工程资产，沿着统一任务结构工作，通过自动测试和状态回写减少人工协调。但这不等于“人越少越好”。重点是协作结构变化，人的角色更多转向目标、边界、反馈和治理。

## 第 10 章：统一流程与单线程协作

这是全场最重要的一章。前面所有概念，最终都要落到统一流程。

统一流程从需求进入开始。第一步不是编码，而是 Tasking。Tasking 是需求分析与拆解：把模糊需求变成可执行、可验证、可分派的任务结构。它要澄清业务意图、用户路径、验收标准、边界条件、依赖关系和风险。Tasking 与 SDD 很接近，都是把“先想清楚”制度化。

Tasking 之后是澄清。澄清的目标不是把问题问完，而是把影响实现和验收的未知项暴露出来。哪些信息必须问用户，哪些可以假设，哪些必须写入风险，哪些可以延后验证，都要进入状态。

然后进入设计和计划。设计不是大文档，而是对关键决策、接口契约、状态变化、数据边界、错误处理和测试策略的说明。计划不是 TODO 列表，而是可执行路径：先做什么，后做什么，每一步的输入输出是什么，完成条件是什么，失败如何回流。

实现阶段，Agent 可以发挥速度优势，但必须沿着设计和计划推进。实现过程中如果发现需求误差、设计缺口、测试缺口或工程约束冲突，不能只在对话里说一下，要更新状态，必要时回到澄清或设计。

实现后进入 Review、测试和验收。Review 看工程风险，QA 看可测性和业务路径，UI 看用户体验路径，BA 看业务意图是否实现。测试不仅包括单元测试、集成测试，也可以包括浏览器模拟验证、关键路径回放、静态检查和 lint/type check。最后，代码出去，并且验收测试通过。

这条流程不是 checklist，而是资产生产线。每一步都有输入、输出、状态、负责人角色、检查点和回写位置。需求不是只流向代码，也流向 Knowledge。流程中发现的新规则、新失败模式、新业务判断、新测试场景，要同步更新 Skill、工程文件、Knowledge，或类似 `SOUL.md` 的长期原则文件。这里的 `SOUL.md` 是类比性说法；MindFlow 中的 Soul 有项目资料支撑，但其他项目可以用不同文件名承载长期原则、流程约束、知识更新规则和 Skill 维护机制。

如果这条单线程流程跑不通，不要急着并行，不要急着无人值守。先让一个需求能稳定地从输入到输出，能被验收，能回写资产。单线程闭环质量，是多线程和自动化的前提。

## 第 11 章：多线程协作流程

当单线程闭环稳定后，才谈多线程。

多线程流程通常从 Epic 到 User Story。Epic 先被拆成多个 Story，团队需要识别依赖关系：哪些 Story 可以独立做，哪些必须等待基础能力，哪些共享同一模块，哪些会争用同一接口或数据结构。自动解析 Story 依赖目前证据不足，所以这里把它作为设计方向，而不是成熟结论。

并行推进时，Worktree 是重要隔离机制。OpenAI 和 Anthropic 的 harness 材料都提到与 worktree、clean state、per-worktree app、长时间任务状态相关的实践。每个 worktree 可以承载一个独立功能增量，但它不是随意并发。每条并行线仍然要有状态、测试、Review、合并门禁和知识回写。

多线程不是跳过统一流程，而是把统一流程复制到多个隔离工作流中，再通过依赖、状态和验收汇合。并行带来的提速，来自减少等待和协调损耗；质量仍然来自强状态、测试、Review、验收和回写。

## 第 12 章：自动化与无人值守

角色流程、强状态、工程文件和 Knowledge 都讲完后，我们才能讲自动化与无人值守。

这里要非常克制。无人值守不是完全自主魔法，而是长时间、低人工干预、有边界、有测试、有人工 gate 的开发模式。系统依靠明确任务边界、强状态、Worktree 隔离、自动测试、浏览器验证、可观测、人工 gate 和失败回流来运行。

Anthropic 关于 long-running agents 的文章提到 feature list、progress file、git history、clean state、单 feature 增量推进、浏览器验证等做法。这些做法解决的是同一个问题：跨上下文窗口、跨 session、跨执行阶段时，Agent 如何知道现在做到哪里，下一步是什么，哪些已经验证，哪些还没验证。

长时间运行最怕几种失败模式：Agent 过早宣布完成；没有进度记录，下一轮无法恢复；猜测测试命令；遇到失败后绕过验证；把未完成事项标记为 done；把复杂任务一次性铺开，最后上下文崩掉。解决方式不是相信模型会更认真，而是把进度文件、feature list、验收检查、测试命令、人工 gate 和失败回流放进流程。

自动化的演进路径可以是：先有单线程统一流程，再有多线程 worktree 隔离，再有长时间低人工介入，再逐步探索 Agent Teams。Agent Teams 可以作为展望，但不应说成成熟的完全自治组织。

## 第 13 章：Agent 设计、提速、测试评估、AI 编排、工具层改造与展望

最后一章把具体实践放回统一流程。

先说 Agent 设计。Agent 不是万能助手。一个好的 Agent 应该从角色协议出发定义：它的上下文是什么，权限是什么，输入是什么，输出是什么，契约是什么，验收是什么，失败如何处理，副作用有哪些。Anthropic 的 Building Effective Agents 提醒我们，先从简单 workflow 开始，按任务需要选择 prompt chaining、routing、parallelization、orchestrator-workers、evaluator-optimizer 或 autonomous agents。复杂不等于先进，适合才重要。

再说提速。AI 的提速不只是 token 生成速度。真正有组织价值的提速，来自上下文传递损耗下降、等待减少、反馈更快、测试更靠前、失败更快变成资产。传统团队扩大规模后会遇到沟通成本、同步成本、协调税和部门墙。《人月神话》相关材料在本仓库中被用来讨论这些协作问题。AI 的价值之一，是让 Agent 共享仓库状态、读取同一套工程资产、沿着统一任务结构工作，并通过自动化验证和状态回写减少重复解释。

测试评估也要进入主线。Agent eval 不是只问“模型答得好不好”，而是设计 task、trial、grader、trace/transcript、outcome 和 evaluation suite。失败是 eval case 的来源。模型“偷懒”很多时候不是态度问题，而是反馈不足、状态不足、验收不足。把失败变成 eval case，系统才会越跑越稳。

可观测也是高质量流程的一部分。钱世俊关于 Agent 可观测的材料强调推理、工具调用、轨迹和质量问题需要可追踪、可诊断、可迭代。对 Agent 系统来说，只看最终输出不够，还要能看到中间轨迹、工具调用、错误回流和质量变化。

工具层也需要改造。人类体验和智能体体验不同。人喜欢页面、说明、宽松输入；Agent 更需要 JSON、schema、字段裁剪、稳定错误码、权限边界、可自省接口和输入防御。CLI for AI Agents 的资料强调 Agent 是不受信任的操作员，工具层要做纵深防御。确定性的事交给确定性的工具，工具输出要结构化，权限要最小化，副作用要可控。

最后是展望。框架是为了消灭自己而存在，这是一个工程判断：当某个模式稳定后，它应该沉淀为工具、模板、规则、测试、Skill 或 workflow，减少人和 Agent 的重复解释。架构形态也会被 AI 重新塑造。AI 不是降低设计重要性，而是提高设计杠杆。未来我们会看到更多面向 Agent 的工程资产、更多可验证流程、更多低人工介入的长时间任务，也会看到 Agent Teams 这类组织形态探索。但无论形态怎么变，核心仍然是统一流程和高质量流程。

## 结尾

今天我们从工程化与 SDD 讲起，回到 SoC、抽象和目录结构，再看 MindFlow 的知识分层、POMASA 的强状态 MAS，接着讲状态控制三分法、Skill / 工程文件 / Rules、Knowledge 与 Story、Flyway 类比、验收、角色流程、多线程、自动化和工具层改造。

如果只带走一句话，我希望是这一句：AI-native workflow 是模型推理、流程约束和状态反馈的动态系统。模型能力会继续增强，但工程系统仍然需要边界、状态、验收和回写。我们要做的，不是让 AI 更快地产生更多代码，而是让 AI 在一个高质量流程里持续产出可验证、可交接、可演进的工程资产。

## 附录 / Q&A 备选

### Q1：Prompt Engineering 还重要吗？

重要，但它越来越像任务接口设计。提示词不再只是“怎么问模型”，而是定义输入、输出、约束、角色、上下文和验收。对于高风险、长期运行、多人协作的任务，仅靠一次提示词不够，需要工程文件、Rules、测试和状态回写。

### Q2：什么时候用 workflow，什么时候用 agent？

如果路径固定、验收明确、风险较高，优先用 workflow。如果任务开放、路径不确定、需要探索，可以增加 agent 自主性。Anthropic 的建议是从简单模式开始，只有需求推动时才增加复杂度。

### Q3：如何开始建设统一流程？

先不要做大平台。选一个真实需求，跑通单线程闭环：Tasking、澄清、设计、计划、实现、Review、测试、验收、回写。把每一步的输入输出、状态文件、责任角色和检查点固定下来。等单线程稳定后，再谈 worktree 并行和长时间运行。

### Q4：Eval 工具怎么选？

Promptfoo、Braintrust、LangSmith、Langfuse 等工具可以进一步调研；SWE-bench、Terminal-Bench 等 benchmark 也可以作为背景材料。但本稿不做工具推荐或排名。更重要的是先定义自己的 task、grader、trace、outcome 和 evaluation suite。

### Q5：如何判断一个 Skill 是否值得沉淀？

看它是否反复出现，是否能减少重复解释，是否能防止同类错误，是否有稳定触发条件，是否有明确输入输出，是否能被不同 Agent 复现，是否能被下游消费，是否有内置验证。

## 引用与来源

- 用户输入与项目 framing：`user_input_template.md`。
- 综合分析与证据映射：`workspace/research/synthesis.md`。
- 引用核验与降级建议：`workspace/research/citation-verification.md`。
- 《当顶尖 Agent 模型越来越会自己干活，Prompt Engineering、SDD、MAS 还剩什么价值》：`references/web/24-mp-weixin-qq-com-s-b4Fh-3SQyWiB1HypUxk9wA.md`。
- 《不是提示词工程，是知识工程》：`references/web/01-mp-weixin-qq-com-s-MGnWz2b2H63lC8tK7UbrDA.md`。
- MindFlow README-CN：https://github.com/neil-wang-global/MindFlow/blob/main/README-CN.md。
- MindFlow SYSTEM：https://github.com/neil-wang-global/MindFlow/blob/main/SYSTEM.md。
- MindFlow tasks README：https://github.com/neil-wang-global/MindFlow/blob/main/tasks/README.md。
- MindFlow capabilities README：https://github.com/neil-wang-global/MindFlow/blob/main/capabilities/README.md。
- POMASA README.zh-CN：https://github.com/eXtremeProgramming-cn/pomasa/blob/main/README.zh-cn.md。
- POMASA SKILL：https://github.com/eXtremeProgramming-cn/pomasa/blob/main/skills/pomasa/SKILL.md。
- CLI for AI Agents：`references/paper-visual/extracted/CLI-for-AI-Agents.md`；原 PDF：`references/papers/CLI_for_AI_Agents.pdf`。
- 李文鹏，《让 AI 运行在工程资产上：从 PRD 到上线的交付闭环、Hybrid 执行、Doc 与 Code 联动》：`references/paper-visual/extracted/李文鹏-让-AI-运行在工程资产上-从-PRD-到上线的交付闭环-Hybrid-执行-Doc-与-Code-联动.md`。
- 牛万鹏，《构建 Coding Agent 的飞轮：Feedback Loop、Benchmark、Agent Engineers》：`references/paper-visual/extracted/牛万鹏-构建-Coding-Agent-的飞轮-Feedback-Loop-Benchmark-Agent-Engineers.md`。
- 钱世俊，《给 Agent 做“CT”：大规模 Agent 的可观测与质量保障体系》：`references/paper-visual/extracted/钱世俊-给-Agent-做-ldquo-CT-rdquo-大规模-Agent-的可观测与质量保障体系.md`。
- 章平，《从盲目调优到数据驱动：大规模 Agent 的评估工程实践》：`references/paper-visual/extracted/章平-从盲目调优到数据驱动-大规模-Agent-的评估工程实践.md`。
- 陶宇田，《OpenSandbox：重新思考 Agent 时代的 Runtime》：`references/paper-visual/extracted/陶宇田-OpenSandbox-重新思考-Agent-时代的-Runtime.md`。
- 王东旭，《打破“人月神话”：Agent 重塑风控场景产运研职能》：`references/paper-visual/extracted/打破-ldquo-人月神话-rdquo-Agent-重塑风控场景产运研职能-王东旭.md`。
- 黄闻欣，《超级团队进行时：从用 AI 到 AI 自己找活干》：`references/paper-visual/extracted/黄闻欣-超级团队进行时-从用-AI-到-AI-自己找活干.md`。
- Anthropic, Building Effective Agents：`references/web/13-www-anthropic-com-engineering-building-effective-agents.md`。
- Anthropic, Demystifying evals for AI agents：`references/web/14-www-anthropic-com-engineering-demystifying-evals-for-ai-agents.md`。
- Anthropic, Effective harnesses for long-running agents：`references/web/15-www-anthropic-com-engineering-effective-harnesses-for-long-running-agents.md`。
- Anthropic, Harness design for long-running application development：`references/web/16-www-anthropic-com-engineering-harness-design-long-running-apps.md`。
- Martin Fowler, Harness engineering for coding agent users：`references/web/17-martinfowler-com-articles-exploring-gen-ai-harness-engineering-html.md`。
- OpenAI, Harness engineering: leveraging Codex in an agent-first world：`references/web/19-openai-com-index-harness-engineering.md`。
- HumanLayer, Skill Issue: Harness Engineering for Coding Agents：`references/web/21-www-humanlayer-dev-blog-skill-issue-harness-engineering-for-coding-agents.md`。
- LangChain, The Anatomy of an Agent Harness：`references/web/22-blog-langchain-com-the-anatomy-of-an-agent-harness.md`。
- Inngest, Your Agent Needs a Harness, Not a Framework：`references/web/23-www-inngest-com-blog-your-agent-needs-a-harness-not-a-framework.md`。
