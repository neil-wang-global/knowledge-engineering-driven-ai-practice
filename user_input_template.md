# User Input

---

## Language Settings

**Agent Blueprint Language**:

Chinese

**Report Output Language**:

Chinese

---

## Research Project Basic Information

**Project Identifier**:

ai-work-system-speech-20260518

**Research Topic and Core Questions**:

为技术团队成员及部分客户技术听众准备一份 60-90 分钟的中文演讲稿/讲稿大纲，主题暂定为：

**《从 AI Coding 到 AI 工作系统：软件工程基本功、知识工程与 Harness Engineering 实践》**

核心问题：

1. 为什么 AI 编程实践不应从“提示词技巧”或“工具使用”讲起，而应回到软件工程基本功：SoC（Separation of Concerns）、抽象/面向对象、文件目录结构、接口契约、测试验证？
2. 如何从这些基本功出发，解释 MindFlow、POMASA、Skill、MAS、多角色协作、强状态、分层 Plan、Agent 编排、自动化无人值守等实践？
3. 如何把“知识工程”讲清楚：Story 是动态知识，Knowledge 是静态 Story；user journey 中持续产生的变化应沉淀为 AC、ADR、工程文档、Skill、Capability、测试、eval case、workflow pattern？
4. 如何向技术团队说明 AI-native workflow 的本质：**模型推理 + 流程约束 + 状态反馈的动态系统**？
5. 如何说明提速不是盲目让模型多写代码，而是通过上下文管理、分层计划、角色协议、测试验证、评估闭环和工具层改造来控制代码产出水平？
6. 如何组织 BA / DEV / QA / UI / Agent 在单仓库中的协作实践：角色而非人、共享强状态、交叉检查、可追踪交付？
7. 如何设计 Agent：从角色协议出发定义上下文、权限、输入、输出、契约、验收，而不是造一个万能助手？
8. 如何解释 AI 编排常见办法：Vibe Coding、轻量 SDD、Sub-agent 委派、分层 Plan、强状态编排，以及它们的局限和适用范围？
9. 如何合理引入安全、可观测、Agent eval、CLI for Agents、长时间自主运行和无人值守实践？

---

## Initial Ideas and Insights

### 后续修订要求：整体叙事框架

本演讲应改为更适合现场讲述的结构。不要写成泛泛研究报告，也不要概括式带过。内容要丰富、周全、有工程判断，但语言保持干净、简单、简练。

标题确定为：**《知识工程驱动的 AI 实践》**。

开场不要铺垫太多，直接从三个基础概念讲起：SoC、抽象/面向对象、文件目录结构。这三个都是初级概念，讲清价值后快速带过。重点不是复述概念定义，而是说明它们在 AI 时代被放大的价值：边界、对象、位置、引用关系、上下文组织和可验证协作。

整体主线应按以下顺序组织：

1. 回到软件工程基本功：SoC、抽象/面向对象、文件目录结构。
2. MindFlow：讲设计思想，说明文件化认知结构、状态、能力和按需加载如何帮助 AI 理解任务。
3. 知识工程理论：结合熊节“不是提示词工程，是知识工程”的问题导向、价值框架、信息储备、理论方法、表现形式，并引出核心定义：**AI-native workflow = 模型推理 + 流程约束 + 状态反馈的动态系统**。
4. POMASA / MAS 工程：讲多 Agent 系统为什么需要 Blueprint、references、workspace、orchestrator 和强状态，并引出后面 AI 编排。
5. Skill / 工程文档：讲其本质是可执行知识。需要讲清智能体工程里的严格 Load：按流程确定性读取指定内容，本质上和 Skill 一样都是知识注入；区别是 Skill 调度不确定，严格 Load 是确定的。
6. Story / Knowledge / user journey：讲 Story 是动态知识，Knowledge 是静态下来的 Story；user journey 是团队持续发现、验证、固化知识的路径。这个观点放在角色、敏捷与单仓库协作处展开。
7. 角色而非人：讲软件团队中的 BA / DEV / QA / UI / Agent 都是能力单元，聚焦同一个仓库工作。要分别讲各角色能力、流程流水线，以及这些流水线如何统一、如何交叉检查。
8. Agent 设计：从角色协议、上下文、权限、输入、输出、契约、验收出发。重点讲 Agent 文档本身必须通过验收，验收思路参考 `references/papers/CLI_for_AI_Agents.pdf` 和 Skill 合法性验证。
9. 提速：不要写成“让模型多写代码”。提速来自前面流程足够健全、上下文足够清楚、验证足够稳定，并且需要评估标准。
10. 检测与测试：讲如何控制代码产出水平，测试为什么重要，失败如何回流为 eval case、规则、Skill 和工程文档。
11. AI 编排：讲 Vibe Coding、轻量 SDD、Sub-agent、分层 Plan、强状态编排的适用范围和局限。可参考第二篇 AI 编程文章的思路。
12. 自动化与无人值守：说明通过强状态、权限、验证、评估和编排，如何逐步走向高度自治系统。

叙事风格要求：

- 语言干净、简单、简练。
- 不要大量 bullet points，主稿应以自然讲述为主。
- 少用“不是……而是……”句式。
- 不要过度自由发挥，要优先阅读并化用已有资料、PDF 逐页摘取 Markdown、网页归档和用户提供的观点。
- Demo 结构要更能强烈表达嵌套知识对象、文件位置、ID/link/reference 关系，不要使用过弱的平铺示例。
- MindFlow 和 POMASA 略讲项目细节，重点讲设计思想；同时强调 AI-native 系统应该走向高度自治。
- 提速章节必须重写为有价值的工程判断：提速来自健全流程、工程资产、测试环境、评估体系和反馈闭环。

### 原始核心思路

本演讲应以“回归软件工程基本功”作为入口，而不是直接讲 AI Coding 工具。核心论点：

> AI 编程不是推翻软件工程，而是把 SoC、抽象、文件结构、角色协作、测试验证这些老原则，放大成 AI-native 工作系统。

建议主线：

1. **软件工程基本功：SoC、抽象、目录结构**
   - SoC 的价值：降低上下文污染、明确责任边界、支持 agent 分工、支持分层 plan、支持独立验证。
   - 抽象/面向对象的价值：封装变化、命名职责、形成接口契约、让 AI 在边界内推理。
   - 文件目录结构的价值：不是项目收纳，而是一种数据结构；正确文件、正确位置、稳定 ID/link/reference 关系共同构成 Agent 可遍历的事实空间。
   - 关键句：结构越清晰，AI 越可靠；结构越混乱，AI 只是更快地制造混乱。

2. **上下文管理：AI 辅助编程的核心变量**
   - AI 辅助编程的核心变量是上下文管理。
   - 所有工程手段本质都在回答：什么信息应该出现、什么时候出现、出现给哪个角色、以什么格式出现、如何验证它被正确消费。
   - SoC 减少不相关上下文；抽象压缩上下文；文件结构索引上下文；Skill 按需加载上下文；Agent 隔离上下文；Script 把无需推理的内容移出上下文；Test/Eval 对上下文消费结果打分。

3. **MindFlow：从软件结构到认知结构**
   - 如果代码系统需要 SoC、抽象和目录结构，AI 工作系统同样需要认知层面的 SoC、抽象和目录结构。
   - MindFlow 略讲思维即可：把目标约束、学习材料、能力单元、计划步骤、任务状态落到文件里。
   - MindFlow 不是重点介绍对象，而是说明工程结构如何加快 AI 理解任务、恢复状态和沉淀能力。

4. **知识工程理论**
   - 使用熊节“不是提示词工程，是知识工程”的五支柱：问题导向、价值/意识形态框架、信息储备、理论方法、表现形式。
   - 与 MindFlow 对齐：问题导向≈任务识别；价值框架≈Soul；信息储备≈Learning/Knowledge Base；理论方法≈Capability；表现形式≈Output Template。
   - 核心定义：**AI-native workflow = 模型推理 + 流程约束 + 状态反馈的动态系统**。
   - 模型负责推理，流程负责约束，状态负责让推理结果可以被恢复、检查和交接。

5. **POMASA：MAS 工程与 AI 编排样本**
   - POMASA 略讲思维即可：多智能体系统不能只靠多个 agent 聊天，而要依赖 Blueprint、references、methodology、workspace、_output 和 orchestrator。
   - 说明 MAS 工程加速的是理解和协作：每个 Agent 能快速找到角色定义、输入来源、方法论约束、工作区和交付位置。

6. **Skill / 工程文档：本质是可执行知识**
   - Skill 和工程文档的本质不是说明书，而是把人的经验、判断标准和流程约束，变成模型可调用的上下文资产。
   - 传统工程文档与 AI Skill 的共同价值：压缩经验、固化判断、降低沟通成本、提供执行约束、形成团队共同语言。
   - 渐进加载：知识不是一次性投喂，而是按需出现。知识工程不是把知识全部塞进去，而是设计知识何时、以何种粒度、被谁读取。
   - Story 是动态的知识，Knowledge 是静态下来的 Story：BA 澄清、DEV 发现边界、QA 发现缺陷、客户调整验收标准，都应沉淀为 AC、ADR、Skill、文档、测试、eval case。该观点放到角色、敏捷与单仓库协作中展开。
   - Skill 验收/评分：触发清晰、输入明确、步骤可执行、输出可消费、验证内置、权限边界清楚、能减少重复解释、能防止同类错误再次发生。

7. **角色而非人：敏捷与单仓库协作编码实践**
   - AI 工作流里讨论的不是“人被替代”，而是“角色被重新定义”。BA、DEV、QA、UI 都是角色，不一定对应固定人员；Agent 也可承担部分角色，但必须有边界。
   - 将 AI 工作流与敏捷结合：敏捷里的 Story、Backlog、Sprint、DoR、DoD、Review、Retro，本质上都是团队围绕 user journey 持续发现、验证、固化知识的机制。AI 不应绕过敏捷，而应把敏捷工件变成可执行、可检查、可回流的强状态。
   - BA 的 Story / Acceptance Criteria 不只是需求文本，而是 Agent 理解业务目标、QA 生成测试、DEV 设计实现边界的共同输入；DoR 可作为 Agent 开始执行前的上下文完备性检查；DoD 可作为 Agent 完成后的验收 checklist。
   - Sprint 不只是时间盒，而是人和 Agent 协作的节奏控制器：计划阶段明确任务边界和依赖，执行阶段通过 task state / checkpoint 管理进展，Review 阶段检查 outcome，Retro 阶段把失败、返工、遗漏沉淀为 skill、测试和 eval case。
   - 单仓库原则：仓库不是代码集中管理，而是 BA / DEV / QA / UI / Agent 共享同一个强状态空间。
   - 仓库中应包含 PRD/user story、UX/UI spec、domain model、plan、task state、implementation、test cases、review notes、eval cases、release notes、knowledge updates。
   - 讲清 BA、DEV、QA、UI 各自流程，以及交叉检查：BA 检查 DEV 是否实现业务意图；DEV 检查 BA 需求是否可实现；QA 检查 BA 验收是否可测试；QA 检查 DEV outcome；UI 检查 BA 用户路径；DEV 检查 UI 技术约束。
   - 强调敏捷实践在 AI 时代的变化：站会可以转化为状态同步和 blocker 暴露；看板可以转化为 Agent 可读的任务状态；Retro 可以转化为知识工程入口；Backlog refinement 可以转化为上下文补全和风险识别；验收标准可以转化为自动测试和 Agent eval。

8. **Agent 设计：从角色协议开始**
   - Agent 不是 prompt 名字，而是角色、权限、上下文、输入输出和验收标准的组合。
   - Agent 至少定义：角色、输入、输出、权限、状态、验收、交接。
   - 可引入 Thinker Agent、Worker Agent、Reviewer Agent、Orchestrator。
   - 契约驱动的跨层一致性：上游导出契约“我提供什么”，下游依赖契约“我需要什么、为什么需要、如何消费”。分层不是把东西切开，而是通过契约让切开的部分还能一致协作。
   - 下游依赖必须是上游导出的子集；契约最好能被 script 校验，而不是靠模型看一眼。

9. **提速：控制代码产出水平，而不是盲目加速**
   - AI 编程提速不是让模型更快输出，而是让系统能承接更大规模、更少返工、更可验证的产出。
   - 控制任务粒度、上下文、边界、输出、验证。
   - AI 不是降低设计重要性，而是提高设计杠杆；AI 越会写代码，错误设计越会被放大成大量错误实现。

10. **测试、评估与检测：让提速可持续**
    - 没有测试的提速，是把风险从开发阶段推迟到验收阶段。
    - 测试不是为了证明人写对了，而是为了让 AI 有稳定的反馈环境。
    - 确定性的事交给确定性的工具：状态管理、契约校验、进度查询、lint、test、文件结构检查、frontmatter 校验、输出格式校验等不要交给模型创造性解释。
    - 反思循环必须带证据：“已检查，没问题”不算验证。反思需引用目标、章节、契约、文件、测试、输出。
    - 失败是 eval case 的来源：客户反馈、QA bug、review 问题、Agent 跑偏、上下文缺失都应回流为测试、checklist、skill rule、eval case。
    - Agent Eval 可简讲 Task、Trial、Grader、Transcript、Outcome、Evaluation Harness、Evaluation Suite。
    - Outcome 优先，不要死盯路径；能力评估 vs 回归评估；pass@k vs pass^k 可轻讲。
    - 模型“偷懒”不只是态度问题，而是目标、上下文、反馈和验收不足。

11. **AI 编排常见办法：Vibe Coding、SDD、Sub-agent、分层 Plan、强状态**
    - 纯 Vibe Coding：小任务快速，但上下文不可控、结果难复用、缺少文件化 plan。
    - 轻量 SDD：brainstorming、plan、task、impl；适合千行级任务，有 plan with file 和断点续跑，但集中 plan 在企业级会爆上下文。
    - Sub-agent 委派：隔离执行上下文、降低主会话污染、提高并行度，但存在上下文不完备、并行冲突、交接协议不足等风险。
    - 分层 Plan：解决集中 plan 的上下文爆炸，按架构边界拆分规划，每层只关心自己职责，上下游通过契约交接。
    - 强状态编排：plan、state、contract、review、test result、output 都落盘。

12. **工具层改造：面向 Agent 的 CLI / MCP / Skill 注入**
    - 人类 CLI 不等于 Agent CLI。
    - 人类体验优化发现性和容错性；智能体体验优化可预测性和纵深防御。
    - Agent 是不受信任的操作员：能力强，但会幻觉、误读、被注入攻击影响。
    - CLI for Agents 法则：JSON 载荷、schema 自省、field mask / pagination / NDJSON、输入防御、--dry-run、--sanitize、SKILL.md / CONTEXT.md 注入硬规则、单一信源多终端架构。

13. **自动化与无人值守：长时间运行的条件和边界**
    - 无人值守不是减少人类责任，而是把人类责任前置到 workflow、权限、状态、测试和评审设计里。
    - 自动化成熟度：L1 对话辅助、L2 任务执行、L3 Workflow 执行、L4 多 Agent 编排、L5 长时间自主运行。
    - 长时间运行需要强状态、权限边界、checkpoint、自动测试、独立 review、人类关键决策点、可观测、回滚机制。
    - 风险：漂移、错误累积、虚假完成、成本失控、安全越界、上下文污染。

14. **展望**
    - Agent Teams：从编排到协作。当前 MAS 多是主从式编排；下一步可能是协作式 agent team：Worker 可向 Thinker 开卡，Reviewer 触发返工，QA 阻塞发布，角色之间通过强状态和契约双向协作。
    - 架构形态会被 AI 重新塑造：现有微服务、领域划分、服务拆分很大程度为人的认知上限设计；未来架构决策可能从“人能理解多少”变成“AI 在什么粒度上生成和维护代码最高效”。但性能、安全、部署、组织边界仍然重要。
    - 框架是为了消灭自己而存在：当前分层 plan、契约校验、渐进加载、权限分级都是模型能力不足时的工程补丁；但搭建这些补丁的过程会迫使团队想清楚哪些事需要推理、哪些事需要规则、哪些信息何时出现。框架会过时，工程判断不会过时。

附录/Q&A 可覆盖：Promptfoo / Braintrust / LangSmith / Langfuse，SWE-bench / Terminal-Bench，上下文压缩技术细节（summary、tool output pruning、sliding window、pinning），具体平台实现差异。

---

## Data Collection

**Data Sources**:

1. 用户提供并归档到仓库的 PDF 原件：`references/papers/`。
2. PDF 逐页视觉信息摘取资料：`references/paper-visual/extracted/`，这是后续写作优先使用的本地素材源。
3. PDF 页面图片归档：`references/paper-visual/images/`，用于回看原始页面视觉证据。
4. PDF 视觉处理索引：`references/paper-visual/INDEX.md` 与 `references/paper-visual/manifest.json`。
5. 已归档网页全文、HTML 与截图：`references/web/`。
6. 用户提供的微信文章链接及其本地网页归档。
7. POMASA / MindFlow GitHub 项目资料。
8. 公开 Harness Engineering、Agent Eval、AI Coding、Agent Runtime、Agent Observability、Agent QA、企业知识沉淀相关资料。
9. 必要时补充公开网页、技术博客、论文、产品文档等，但必须保持引用可追溯。

**Existing Reference Materials**:

本地引用素材源：

- `references/papers/` — 用户提供的 PDF 原件，可用于引用文件名与核对原始资料。
- `references/paper-visual/extracted/` — PDF 逐页视觉信息摘取 Markdown，后续写作应优先从这里取材。
- `references/paper-visual/images/` — PDF 页面图片，用于核对 slide 视觉内容、图示、表格和页面上下文。
- `references/paper-visual/INDEX.md` — PDF 原件、页面图片、逐页摘取 Markdown 的总索引。
- `references/paper-visual/manifest.json` — 机器可读索引，记录每份 PDF 页数、图片目录、摘取文件和处理状态。
- `references/web/` — 已抓取网页的 Markdown、HTML、截图和 README 索引。

重要微信文章：

- https://mp.weixin.qq.com/s/MGnWz2b2H63lC8tK7UbrDA — 《不是提示词工程，是知识工程》（重要）
- https://mp.weixin.qq.com/s/9Dh-e7Z139QoOqrWOqkKJA — 《我希望用一篇文章帮你叩响AI辅助编程的大门》
- https://mp.weixin.qq.com/s/pwhg5Kmh3wMlxqIlbVqGMw — 《Anthropic 万字长文：AI Agent 评估体系全解析》

GitHub 项目资料：

- https://github.com/neil-wang-global/MindFlow/blob/main/README-CN.md
- https://github.com/neil-wang-global/MindFlow/blob/main/SYSTEM.md
- https://github.com/neil-wang-global/MindFlow/blob/main/tasks/README.md
- https://github.com/neil-wang-global/MindFlow/blob/main/capabilities/README.md
- https://github.com/eXtremeProgramming-cn/pomasa/blob/main/README.md
- https://github.com/eXtremeProgramming-cn/pomasa/blob/main/README.zh-cn.md
- https://github.com/eXtremeProgramming-cn/pomasa/blob/main/skills/pomasa/SKILL.md

本地 PDF 资料：

- references/papers/CLI_for_AI_Agents.pdf
- references/papers/牛万鹏-构建 Coding Agent 的飞轮：Feedback Loop、Benchmark、Agent Engineers.pdf
- references/papers/彭佩乔-让每个员工都有一个 Coding Agent：蚂蚁 Vibe Coding 平台落地半年后的实践经验 .pdf
- references/papers/曹偲-DSL-Spec：TocoAI 的后端 Harness Engineering 实践.pdf
- references/papers/徐翔-尽在上下文&mdash;&mdash;JoyCode 的企业级 AI Coding 实践.pdf
- references/papers/李文鹏-让 AI 运行在工程资产上：从 PRD 到上线的交付闭环、Hybrid 执行、 Doc 与 Code 联动.pdf
- references/papers/钱世俊-给 Agent 做&ldquo;CT&rdquo;：大规模 Agent 的可观测与质量保障体系.pdf
- references/papers/章平-从盲目调优到数据驱动-大规模 Agent 的评估工程实践.pdf
- references/papers/赵文成-从个人经验到组织资产：小米运维知识沉淀的闭环实践.pdf
- references/papers/黄闻欣-超级团队进行时：从用 AI 到 AI 自己找活干.pdf
- references/papers/陶宇田-OpenSandbox：重新思考 Agent 时代的 Runtime.pdf
- references/papers/蔡明哲-从单点辅助到 Agent 闭环.pdf

Harness Engineering 参考资料（如可访问则引用）：

- https://martinfowler.com/articles/exploring-gen-ai/harness-engineering.html — Harness engineering for coding agent users
- https://www.humanlayer.dev/blog/skill-issue-harness-engineering-for-coding-agents — Skill Issue: Harness Engineering for Coding Agents
- https://martinfowler.com/articles/exploring-gen-ai/harness-engineering-memo.html — Harness Engineering - first thoughts
- https://openai.com/index/harness-engineering/ — Harness engineering: leveraging Codex in an agent-first world
- https://mitchellh.com/writing/my-ai-adoption-journey — My AI Adoption Journey
- https://www.anthropic.com/engineering/harness-design-long-running-apps — Harness design for long-running application development
- https://blog.langchain.com/the-anatomy-of-an-agent-harness/ — The Anatomy of an Agent Harness
- https://www.inngest.com/blog/your-agent-needs-a-harness-not-a-framework — Your Agent Needs a Harness, Not a Framework
- https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents — Effective harnesses for long-running agents
- https://www.anthropic.com/engineering/building-effective-agents — Building Effective AI Agents
- https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents — Demystifying evals for AI agents

---

## Analysis Methods

1. **概念谱系分析**：从软件工程基本功（SoC、抽象、目录结构、契约、测试）推导到 AI-native 工作流、MindFlow、POMASA、Skill、MAS、Agent 编排。
2. **案例归纳**：从 MindFlow、POMASA、归档 AI Coding / Agent 工程 PDF、微信文章中提取可讲述案例与思想片段。
3. **工程模式抽象**：总结上下文管理、渐进加载、强状态、契约驱动、Agent/Skill/Script 分工、分层 Plan、Eval、CLI for Agents 等通用模式。
4. **演讲叙事设计**：避免资料堆砌，按“软件工程基本功 → 认知/知识工程 → MAS/Skill/角色协作 → 提速/测试/编排 → 工具/自动化/展望”组织。
5. **引用与可追溯性**：所有外部观点或资料中的具体事实、术语、案例，需在正文中添加引用。引用可采用脚注或括号形式，但最终稿必须让读者知道观点来源。

---

## Output Format

**Report Format**:

最终输出为一份面向技术团队内部成员和客户技术听众的中文演讲稿/讲稿大纲，适合 60-90 分钟演讲。需要同时包含：

1. 完整讲稿正文（可直接照着讲，语言自然、有节奏，不要写成论文）。
2. 演讲结构大纲（章节、时间分配、每章核心观点）。
3. 关键 slide 提纲（每页标题、核心 bullet、可视化建议）。
4. 引用资料列表（按章节或脚注整理）。
5. 附录/Q&A 备选材料。

**Report Structure**:

建议结构应调整为更直接的演讲主线：

1. 开场：直接讲 SoC、抽象/面向对象、文件目录结构为什么在 AI 时代更重要
2. 软件工程基本功：SoC 解决上下文污染，抽象形成对象边界，目录结构提供对象位置和引用关系
3. MindFlow：从软件结构到认知结构，讲文件化状态、能力、计划和按需加载
4. 知识工程理论：问题导向、价值框架、信息储备、理论方法、表现形式；引出 AI-native workflow
5. POMASA / MAS 工程：多 Agent 系统需要 Blueprint、references、workspace、orchestrator 和强状态
6. Skill / 工程文档：可执行知识、Skill 不确定调度、严格 Load 确定调度、Skill 合法性验收
7. Story / Knowledge / user journey：Story 是动态知识，Knowledge 是静态 Story，user journey 是知识固化路径
8. 角色而非人：BA / DEV / QA / UI / Agent 的能力单元、统一流水线、单仓库强状态、交叉检查
9. Agent 设计：角色协议、上下文、权限、输入输出、契约、停止条件、验收和可观测
10. 提速：通过健全流程、工程资产、任务边界、验证环境和评估标准控制代码产出水平
11. 测试、评估与检测：测试、eval、benchmark、feedback loop、失败回流
12. AI 编排常见办法：Vibe Coding、轻量 SDD、Sub-agent、分层 Plan、强状态编排
13. 自动化与无人值守：状态、权限、checkpoint、review、回放、回滚和高度自治
14. 展望：Agent Teams、AI 重塑架构形态、框架为了消灭自己而存在
15. 附录/Q&A

主稿不要写成层层 bullet 的报告，应以自然讲述段落为主；提纲和 slide 部分可以使用 bullet。

**Deliverable File Formats**:

- [x] Markdown (always generated)
- [x] DOCX (recommended, for editing)
- [x] PDF (recommended, for distribution)

如果 DOCX/PDF 导出环境不可用，至少必须生成 Markdown，并说明导出失败原因。

---

## Pattern Selection

**Quality Assurance Level**:

- [ ] Simple: Only adopt required patterns, no additional quality checks
- [ ] Standard (default): Adopt QUA-01 Embedded Quality Standards + BHV-05 Grounded Web Research
- [x] Strict: Adopt QUA-01 + QUA-02 Multi-Layer Quality Assurance + BHV-05 Grounded Web Research

**Other Patterns to Enable or Disable**:

启用或强调以下要求：

- 必须严格引用用户提供的材料；用户已授权“所有材料可随意引用，但引用时添加引用”。
- 对引用材料中的事实、案例、术语、观点，需要添加引用来源。
- 不要写成泛泛 AI 评论文章；必须围绕用户指定的主线和 thought。
- 不要过度营销化；面向技术团队，语言要有工程感、判断力和可落地性。
- 最终稿要能作为演讲稿使用，不能只是研究报告。

---

## Other Requirements

1. **语言风格**：中文，专业但不晦涩，有判断力；适合技术团队和客户技术听众；避免八股、空话、焦虑式表达。语言必须干净、简单、简练，少用“不是……而是……”句式。
2. **引用要求**：用户提供的所有资料均可引用。引用时必须添加引用，形式可以是脚注、括号引用或章节后引用列表。对本地 PDF 可引用文件名；对微信文章和网页可引用标题及 URL。后续写作应优先使用 `references/paper-visual/extracted/` 中的逐页摘取资料、`references/web/` 中的网页归档，以及用户提供的核心观点，不要凭空自由发挥。需要核对原始材料时，回到 `references/papers/` 和 `references/paper-visual/images/`。
3. **输出定位**：这是“演讲稿/讲稿大纲”，不是公众号文章。应包含口语化但有结构的讲稿段落。主稿不要堆大量 bullet points；bullet 主要用于结构大纲、slide 提纲和附录。
4. **叙事要求**：标题为《知识工程驱动的 AI 实践》。开场直接讲 SoC、抽象/面向对象、文件目录结构，不要长铺垫。MindFlow 和 POMASA 讲设计思想即可，并强调 AI-native 系统应走向高度自治。Skill / 工程文档章节必须讲清 Skill 不确定调度与严格 Load 确定调度的区别。角色章节必须讲 BA / DEV / QA / UI / Agent 的能力、统一流水线和交叉检查。Agent 设计章节必须展开“Agent 文档本身如何通过验收”。提速章节必须围绕健全流程、工程资产、验证环境和评估标准重写。
5. **重点保留用户原创观点**：
   - 模型负责推理，流程负责约束，状态负责让推理结果可以被恢复、检查和交接。
   - Story 是动态知识，Knowledge 是静态 Story；user journey 是团队发现、验证、固化知识的过程。
   - AI-native workflow = 模型推理 + 流程约束 + 状态反馈的动态系统。
   - 单仓库原则：仓库是 BA / DEV / QA / UI / Agent 共享的强状态空间。
   - AI 编程不是推翻软件工程，而是放大软件工程基本功。
5. **必须纳入的 thought**：
   - AI 辅助编程的核心变量是上下文管理。
   - 渐进加载。
   - 契约驱动的跨层一致性。
   - 确定性的事交给确定性的工具。
   - 反思循环必须带证据。
   - 失败是 eval case 的来源。
   - Agent 是不受信任的操作员。
   - 框架是为了消灭自己而存在。
   - 人类体验 vs 智能体体验。
   - 架构形态会被 AI 重新塑造。
   - AI 不是降低设计重要性，而是提高设计杠杆。
   - 模型“偷懒”不是态度问题，而是反馈不足。
   - pass@k vs pass^k 可轻讲。
   - Agent Teams 放在展望猜想。
6. **附录材料**：Promptfoo / Braintrust / LangSmith / Langfuse，SWE-bench / Terminal-Bench，上下文压缩技术细节，具体平台差异等放在附录或 Q&A，不进入主干长讲。
7. **最终产物验收标准**：
   - 必须存在完整 Markdown 讲稿。
   - 必须包含引用列表。
   - 必须包含 slide 提纲。
   - 必须包含附录/Q&A。
   - 必须报告最终产物完整路径。
   - 主稿标题必须是《知识工程驱动的 AI 实践》。
   - 开场必须直接进入 SoC、抽象/面向对象、文件目录结构。
   - 主稿应以自然讲述段落为主，不得大量堆 bullet points。
   - 不得频繁使用“不是……而是……”句式。
   - 必须体现 Skill 不确定调度与严格 Load 确定调度的差异。
   - 必须体现 BA / DEV / QA / UI / Agent 的统一流水线和交叉检查。
   - 必须展开 Agent 文档验收，参考 `references/papers/CLI_for_AI_Agents.pdf` 和 Skill 合法性验证思路。
   - 提速章节必须有评估标准，不能只写“让模型多写代码”。
   - 必须优先化用 `references/paper-visual/extracted/`、`references/web/` 和用户提供观点。
