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

### 整体叙事框架

本演讲应改为更适合现场讲述的结构。不要写成泛泛研究报告，也不要概括式带过。内容要丰富、周全、有工程判断，但语言保持干净、简单、简练。

标题确定为：**《知识工程驱动的 AI 实践》**。

新的主线从“为什么还要工程化与 SDD”开场，先回答听众最容易产生的疑问：模型越来越强，为什么还需要流程、结构、规则和工程资产。讲清这个问题后，再回到软件工程基本功，逐步推到 MindFlow、MAS、Skill / 工程文件、Rules、Knowledge、团队角色、自动化编排和无人值守。整体叙事要自然推进：先说明工程化的必要性，再讲为什么这些老概念在 AI 文件工程里仍然成立，最后讲如何把它们组合成可运行、可协作、可演进的 AI 工作系统。

#### 0. 为什么还要工程化与 SDD

开场先讲为什么强模型时代仍然需要工程化与 SDD。这里引入新增文章《当顶尖 Agent 模型越来越会自己干活，Prompt Engineering、SDD、MAS 还剩什么价值》。这篇文章的核心思想是：强模型会把一部分 planning、tool use、agentic orchestration 吃进模型内部，但这不代表工程方法失效，而是它们的价值从“能力补丁”迁移到“治理工具”。

这一章要直接回应现实问题：很多团队已经不是觉得 AI 不会写代码，而是觉得 AI 太快开始写代码。需求还没澄清，边界还没想清，验证还没设计好，模型就已经开始实现。中低端模型更容易过早收束，不容易充分考虑边界条件，也更容易用流畅输出掩盖需求没澄清、边界没想清、验证没设计好的问题。因此我们需要通过工程化设计控制 AI 做事：把意图说清楚，把约束钉住，把“想清楚”和“开始干”分开，把中间产物、检查点、验收标准和固定动作显化。

SDD 的价值不是神秘地增强模型智力，而是把“先想清楚”制度化。Prompt Engineering 越来越像任务接口设计，MAS 越来越像上下文、权限、并行和审计的系统架构，Hooks / Rules 提供 deterministic control。方法论不是过时，而是必要性开始分层：模型能力、预算、任务开放度、容错要求、治理需求共同决定工程强度。

这部分要短而有力，作为整场演讲的入口。它先建立判断：AI 编程不是让模型更快地产生更多代码，而是通过工程结构提高推理质量、协作质量和交付可控性。然后自然转入第一章：既然工程结构仍然重要，就要回到 SoC、抽象、目录结构这些软件工程基本功。

#### 1. 回归软件基本功（略写）

先讲 SoC、抽象/面向对象、文件目录结构。这些都是初级概念，不需要长篇定义，但要讲清楚它们应该复刻到 AI 的文件工程体系上。代码工程和 AI 文件工程的逻辑是通用的：边界清楚、对象清楚、位置清楚，系统才容易维护。

这里重点讲三件事。

第一，每个文档只负责特定范围，做到小而精，避免冗余。Story、ADR、Spec、Plan、State、Review、Eval 都应有自己的职责。

第二，文档之间如果有依赖，应通过 ID、链接、引用关系来维护，而不是复制出重复文档。重复文档会制造事实分叉，Agent 会不知道哪个版本是权威。

第三，目录结构不是收纳方式，而是知识对象的地址空间。正确文件、准确位置、稳定引用关系，会直接影响 Agent 是否能找到、理解、验证上下文。

这部分要略写，但态度要明确：这些基础能力非常重要，值得被重新重视。

#### 2. MindFlow 的设计思想

MindFlow 重点讲设计思想，不讲项目说明书。它的核心价值在于：通过规约、方向、状态和能力模块，让系统具备自我演进的基础。

MindFlow 体现的是模块化与解耦。Soul、Learning、Capability、Plan、Task State、Reflection 等概念被单独抽离，各自承担职责，不靠重复材料维持上下文。长期原则、学习资料、能力单元、执行状态和复盘结果分开存放，系统中断后可以恢复，角色切换后可以交接，经验积累后可以沉淀。

这里不能只把 MindFlow 讲成“文件作为 input 进来，最终 output 为输出”的流程。更重要的是讲它背后的高维知识运用：文件只是知识的载体，目录、引用、状态、能力和复盘共同构成一个可被 Agent 操作的知识空间。Agent 每次执行任务，不只是读取材料并生成文本，而是在这个知识空间里选择、组合、验证和更新知识。

从这里自然引出知识工程。MindFlow 不只是文件夹设计，它把“AI 应该如何管理知识、加载知识、更新知识”这个问题摆到了台面上。要进一步讲清楚：软件系统的本质就是知识，一个智能 AI Agent 系统也是知识。代码、文档、测试、规则、任务状态和运行反馈，都是知识在不同阶段的表达形式。

这里要加入一个重要判断：AI 实际上是一种未来的新软件。它最大的价值之一，是打破了“软件只能由开发人员制作”的知识垄断。过去，软件的用户和开发者往往不是同一批人，懂业务的人要通过需求文档、会议和排期，把知识转交给开发人员，再由开发人员把知识固化成系统。AI 推动了数字民主化，让更多人可以直接把自己的业务知识、工作流程和判断标准变成可运行的系统。这一点要讲得有力量，它是知识工程为什么重要的根本背景。

#### 3. 结合 MAS 与 MindFlow：强状态系统

接着讲 MAS，多智能体系统不能理解成多个 Agent 聊天。它本质上是一个编排系统，而且是强状态过程。

AI 系统的编排不是简单分工，而是围绕状态推进：谁读取什么、谁产出什么、产物放在哪里、谁验收、失败如何回流、下一步由谁接手，都必须可追踪。MindFlow 讲的是认知结构和自我演进，POMASA / MAS 讲的是多角色、多产物、多阶段的组织方式。两者结合，可以说明 AI-native 系统为什么需要强状态。

这里要把实践讲成成熟、高效、值得分享的工程方案：Blueprint、references、workspace、orchestrator、state、eval 和 handoff 共同构成 MAS 的运行环境。

#### 4. 状态控制的三种方式

在讲 Skill、工程文件和 Rules 前，先讲状态控制。AI 工作系统的控制方式大体可以分成三类。

第一类是强约束、固定调度。比如 Rules、Hooks、固定检查点、必须执行的测试、必须读取的工程文件。这类方式可靠性最高，灵活性最低。它适合承载安全边界、权限、验收、格式、提交前检查等必须发生的动作。

第二类是有建议的 AI 自主判断。比如 Skill、推荐流程、可选 checklist、Agent 根据任务判断是否加载某个能力。这类方式介于中间，保留一定灵活性，也提供一定约束，但会有漏触发、误触发和触发时机不稳定的问题。

第三类是完全由 AI 控制。模型自己决定读什么、怎么拆、什么时候停、是否验证。这类方式灵活性最高，但可靠性最低，适合探索、低风险实验和一次性任务。

这三种方式的灵活性和可靠性是反向关系。越固定，越可靠，但越不自由；越自由，越灵活，但越不稳定。工程设计的关键不是选一种，而是组合使用：强约束兜底，建议式调度提供能力，AI 自主控制负责开放探索。

#### 5. 抽象单元：Skill、工程文件与 Rules

这一章讲 Skill 和工程文件的本质联系。往大里讲叫 Skill，往小里讲就是工程文件。两者本质上都是可执行知识：把人的经验、判断标准、流程约束和输出格式变成 Agent 可读取、可执行、可检查的上下文资产。

但它们的调度方式不同。Skill 往往是随机调度的，带有不确定性，可能在任何端点被触发，也可能没有被触发。工程文件则是整体精心构建的自动化流程的一部分，调度机制更紧密、更确定，通常由流程规定何时读取、读取什么、如何产出。

因此不要执着于 Skill 这种扁平平铺的形式。真正重要的是结构化、模块化的设计。把知识按职责、状态、边界、引用关系组织起来，本质上就是软件架构里的面向对象设计。

这里还必须引入 Rules。Rules 就是规则，接近每次执行都会触发的 Hook。它是一种固定的、强约束的调度方式。优点是每次调用都稳定，调度起来省心，让人放心。缺点是太固定，不自由，每次都要走这条 hook。由于目前很多项目没有完整的项目级 Hook，Rules 需要被统一处理。

Skill、工程文件、Rules 要组合使用。Skill 提供可复用能力，工程文件提供结构化上下文和流程位置，Rules 提供确定性约束。三者组合好，项目协同才会更稳定。

这一章还要专门讲 Skill / Rule 被定义后如何验收。无法验收的 Skill 就像一个形状不固定的盒子，看起来装了经验，实际无法稳定复用。Skill 的规范可以类比函数：要有清晰的触发条件、输入、前置假设、步骤、输出、错误处理边界、权限边界和验收方式。写作时要参考 PPT 资料中关于 Skill 规范、Capability、Agent 文档和函数式接口的内容，讲清楚一个 Skill 不只是“提示词片段”，而是可执行、可检查、可交接的知识单元。

验收时要问：什么时候应该触发？输入是否足够明确？执行步骤是否能被不同 Agent 稳定复现？输出是否能被下游消费？是否内置验证动作？是否能减少重复解释？是否能防止同类错误复发？权限和副作用是否被限制？如果这些问题回答不清楚，这个 Skill / Rule 就还没有达到工程资产的标准。

#### 6. 知识工程中的“知识”定义

在软件编码语境下，知识与 Story 存在转化关系：Knowledge 是静态 Story，Story 是流动的 Knowledge。代码工程的本质也是知识工程，因为每一次需求、设计、实现、测试和验收，都是知识被发现、修改、固化的过程。

这里要展开 Skill 如何验收，以及 Story 如何验收。Skill 要看触发是否清晰、输入是否明确、步骤是否可执行、输出是否可消费、验证是否内置、权限边界是否清楚、能否减少重复解释、能否防止同类错误复发。Story 要看业务意图是否清楚、验收标准是否可测、依赖是否明确、边界是否可实现、完成后是否能沉淀到 Knowledge。

可以用 Flyway 类比 Story 和 Knowledge 的关系。每一个 Story 都像一个 Flyway Migration。Knowledge 则像所有 Migration 执行完后的最终数据库状态。Story 有时效性，维护困难；但每一次 Story 对 Knowledge 的增量，在 Knowledge 更新后，都应该实时反映代码库当前状态。

这一章要依赖应用材料展开，优先使用 `references/paper-visual/extracted/` 中关于工程资产、知识沉淀、Doc 与 Code 联动、Feedback Loop、Benchmark、Agent Eval 的资料。

#### 7. 角色而非人：软件团队的协作流程

在介绍 Skill、工程文件和 Knowledge 后，自然进入软件团队角色。核心原则是不按人划分职能，而是按角色划分能力。

团队中的每个角色都像一顶“思考帽”。同一个成员可以戴不同的帽子，一个 Agent 也可以承担某些帽子的动作。关键是所有角色都聚焦同一个项目仓库进行协作，使用同一个强状态空间。

先讲统一流程。这个流程贯穿从输入到输出的全过程：需求进来，经过 Tasking、澄清、设计、计划、实现、Review、测试和验收，最后代码出去，并且验收测试通过。它不是一个松散 checklist，而是一条资产生产线：每一步都有输入、输出、状态、负责人角色、检查点和回写位置。

这里要把 Tasking 放进去讲。Tasking 本质上是需求分析与拆解，和 SDD 很接近：先把业务意图、用户路径、验收标准、边界条件、依赖关系和风险拆出来，再决定进入实现。Tasking 不是简单列 TODO，而是把模糊需求转成可执行、可验证、可分派的任务结构。它是团队协作的前置知识整理，也是 Agent 能否稳定接手任务的关键。

这个统一流程里必须写入 Skill 的同步更新和维护。需求、实现、Review、测试和验收过程中发现的新规则、新判断、新失败模式、新业务知识，不能只留在对话里或某个人脑子里，而要回写到 Skill、工程文件、Knowledge 或类似 `SOUL.md` 的维护文件中。`SOUL.md` 这类文件用于承载长期原则、流程约束、知识更新规则和 Skill 维护机制，保证流程执行后资产会增长，而不是只产出一次代码。

这个流程里必须有交叉验证。编码完成后，QA 可以通过模拟浏览器等方式验证业务路径，也可以通过测试和 Code Review 验证实现质量。BA 检查业务意图是否被实现，DEV 检查需求和设计是否可实现，QA 检查验收是否可测，UI 检查用户路径是否完整，Reviewer 检查工程风险。

再讲多线程流程。多线程流程比单线程多一步：从 Epic 到 User Story。系统不仅拆解用户故事，还要自动解析用户故事之间的依赖，然后通过 Worktree 等手段并行完成。这样才能实现自动化智能编排，并行推进功能增量。

#### 8. 自动化与无人值守提前讲

自动化与无人值守要从后面单独提到这里讲。因为在角色流程、强状态、工程文件和 Knowledge 都讲完后，就可以自然说明一个项目如何实现长时间、低人工干预的功能编码开发。

这里要强调：这不是完全无人值守，而是长时间运行、低人工介入的开发模式。系统依靠明确任务边界、强状态、Worktree 隔离、自动测试、交叉验证、人工 gate、可观测和失败回流来运行。

这一章要说明从单线程到多线程，从手动协作到自动编排，从 Agent 执行到 Agent Teams 的演进路径。

#### 9. 后续章节参考文献展开

后续关于 Agent 设计、提速、测试评估、AI 编排、工具层改造、长时间运行和展望等内容，要更多参考已有文献和逐页摘取资料来展开，但重点不是堆案例，而是服务于统一流程：怎么构建这个流程，怎么构建一个高质量的流程。第九章之后的内容属于非常具体的实践，不能只写概念，要展开讲：Agent 如何设计，如何定义权限、输入、输出和验收；提速如何来自上下文管理、并行、自动验证和反馈闭环；编排如何在 sub-agent、plan、state、worktree、handoff 之间选择；工具层如何为 Agent 提供稳定运行环境；展望如何自然引到 Agent Teams 和组织形态变化。

讲为什么 AI 能大幅提速时，要采纳《人月神话》和“打破人月神话”相关材料里的沟通成本、协调税、部门墙、PRD 信息损耗等内容。传统软件团队扩大规模后会遇到沟通、同步和协调成本上升，AI 的价值之一是把一部分沟通成本、上下文传递成本和重复解释成本压低：Agent 可以共享仓库状态、读取同一套工程资产、沿着统一任务结构工作，并通过自动化验证和状态回写减少人工协调。但这里不能写成“人越少越好”，重点是 AI 改变了协作结构和知识传递成本。

素材取舍要明确：采纳“AI 工具个人提效不等于组织提效”和“SOP 就是资产生产线”；“Spec 不是文档，是需求契约”待定，可以先放上去试写；不采用现成的 Skill 生命周期方案、HopSpec 主线、Agent 评估案例、可观测闭环案例、GUI Agent 三层架构、OpenSandbox Runtime 主线作为核心结构，但这些材料中的表达和工程判断可以化用。采纳 Harness Engineering 中的 progressive disclosure、context firewall，以及长时间 Agent 的 feature list、progress file、clean state、单 feature 增量推进等做法，用来支撑统一流程和无人值守章节。

重点参考：`references/paper-visual/extracted/CLI-for-AI-Agents.md`、JoyCode、PRD 到上线闭环、Coding Agent 飞轮、DSL-Spec、Agent 可观测、Agent Eval、Harness Engineering、OpenSandbox、AIOps / RCA Agent、自动化 UI / GUI Agent、超级团队，以及 `references/web/24-mp-weixin-qq-com-s-b4Fh-3SQyWiB1HypUxk9wA.md`。写作时如果发现引用材料中有更合适的表达、案例、图示或判断，可以灵活换用过来，不要死守当前框架里的概括语；但最终组织必须回到统一流程构建，而不是材料堆砌。

叙事风格要求：

- 语言干净、简单、简练。
- 不要大量 bullet points，主稿应以自然讲述为主。
- 少用“不是……而是……”句式。
- 不要过度自由发挥，要优先阅读并化用已有资料、PDF 逐页摘取 Markdown、网页归档和用户提供的观点。
- Demo 结构要能强烈表达嵌套知识对象、文件位置、ID/link/reference 关系，不要使用过弱的平铺示例。
- MindFlow 和 POMASA 略讲项目细节，重点讲设计思想；同时强调 AI-native 系统应该是强状态、可编排、可演进的。
- 提速章节必须重写为有价值的工程判断：提速来自健全流程、工程资产、测试环境、评估体系和反馈闭环。

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
- https://mp.weixin.qq.com/s/b4Fh-3SQyWiB1HypUxk9wA — 《当顶尖 Agent 模型越来越会自己干活，Prompt Engineering、SDD、MAS 还剩什么价值》（重要，已归档到 `references/web/24-mp-weixin-qq-com-s-b4Fh-3SQyWiB1HypUxk9wA.md`）

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

最终只输出两份文件，面向技术团队内部成员和客户技术听众，适合 60-90 分钟演讲使用：

1. **HTML 演示文件**：用于现场演示，形式类似 PPT，一屏一屏往下翻。文件体积要小，内容尺寸要适合投屏演示，页面信息密度适中，不做臃肿网页，不依赖复杂外部资源。
2. **演讲稿文件**：完整中文讲稿，可直接照着讲，语言自然、有节奏，不要写成论文。演讲稿中保留必要引用、章节结构和备选 Q&A/附录内容，但不再单独输出 slide 提纲、DOCX 或 PDF。

**Report Structure**:

建议结构应调整为以下演讲主线。第 0 章先讲工程化与 SDD 的必要性，随后前三章固定，后续按自然语义推进：

0. 为什么还要工程化与 SDD：开场结合新增微信文章，说明强模型内化了一部分规划和编排能力，但中低端模型容易过早收束、遗漏边界，需要工程结构控制 AI 做事
1. 略写软件基本功：SoC、抽象/面向对象、文件目录结构如何复刻到 AI 文件工程体系
2. MindFlow 的自我演进：规约、方向、模块化、解耦、状态、能力、Reflection 如何让系统演进，并引出知识工程、软件即知识、AI 作为未来新软件与数字民主化
3. 通过 ProMaster / POMASA 介绍 MAS 的强状态：多智能体系统为什么是编排的强状态过程
4. 状态控制三分法：强约束固定、有建议的 AI 自主判断、完全 AI 控制，以及灵活性与可靠性的反向关系
5. Skill、工程文件与 Rules：三类状态控制如何落到可执行知识、工程文件和 Hook 式规则上，并讲清 Skill / Rule 像函数一样需要可验收规范
6. Knowledge 与 Story：Knowledge 是静态 Story，Story 是流动 Knowledge；代码工程本质是知识工程
7. Story 到 Knowledge 的 Flyway 类比：Story 是 Migration，Knowledge 是所有 Migration 执行后的最终状态
8. Skill 与 Story 的验收：触发、输入、步骤、输出、验证、权限、业务意图、AC、依赖、可测试性
9. 角色而非人：BA / DEV / QA / UI / Agent 是思考帽，围绕同一仓库和强状态协作
10. 统一流程与单线程协作：需求进入、Tasking、澄清、设计、实现、浏览器模拟验证、测试、Code Review、验收通过、代码输出，并同步维护 Skill 与 `SOUL.md` 类文件
11. 多线程协作流程：Epic 到 User Story，自动解析用户故事依赖，通过 Worktree 并行推进功能增量
12. 自动化与无人值守：长时间、低人工干预的功能编码开发，不是完全无人值守
13. Agent 设计、提速、测试评估、AI 编排、工具层改造、展望：参考文献和逐页摘取资料展开具体实践；提速可结合《人月神话》的沟通成本问题展开
14. 附录/Q&A

演讲稿不要写成层层 bullet 的报告，应以自然讲述段落为主。HTML 演示文件可以使用简洁 bullet、短句、图示化结构和一屏一主题的方式呈现。

**Deliverable File Formats**:

- [x] HTML 演示文件（必须生成，用于现场演示）
- [x] Markdown 演讲稿（必须生成，用于照稿讲）

不需要生成 DOCX 或 PDF。

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
3. **输出定位**：最终产物只包括 HTML 演示文件和 Markdown 演讲稿，不是公众号文章，也不需要额外输出 slide 提纲、DOCX 或 PDF。演讲稿应包含口语化但有结构的讲稿段落，不要堆大量 bullet points；HTML 演示文件用于现场展示，类似 PPT，一屏一屏往下翻，一屏一主题，内容尺寸适合投屏演示。
4. **叙事要求**：标题为《知识工程驱动的 AI 实践》。开场第 0 章先讲“为什么还要工程化与 SDD”，直接吸收新增微信文章思想：强模型内化了一部分规划和编排能力，但中低端模型容易过早收束、遗漏边界，所以需要工程结构控制 AI 做事。随后前三章固定：略写软件基本功；讲 MindFlow 的自我演进；通过 ProMaster / POMASA 介绍 MAS 的强状态。软件基本功部分要直接讲 SoC、抽象/面向对象、文件目录结构，不要长铺垫；这部分略写，但要讲清 AI 文件工程同样需要小而精、低冗余、靠引用维护依赖。MindFlow 要讲规约、方向、模块化、解耦和自我演进，并由此引出知识工程；这里要讲清软件系统的本质就是知识，智能 AI Agent 系统也是知识，AI 是未来新软件，并正在打破“软件只能由开发人员制作”的知识垄断，推动数字民主化。MAS 与 POMASA 要强调强状态和系统编排。随后讲状态控制三分法：强约束固定、有建议的 AI 自主判断、完全 AI 控制；说明灵活性和可靠性是反向关系。Skill / 工程文件章节必须讲清两者本质都是可执行知识，但 Skill 调度随机，工程文件调度更确定；还必须引入 Rules，把它解释成 Hook 式强约束，并讲清 Skill / Rule 定义后的验收标准。Knowledge / Story 章节必须讲 Knowledge 是静态 Story、Story 是流动 Knowledge，并使用 Flyway Migration 类比。角色章节必须讲 BA / DEV / QA / UI / Agent 是思考帽，围绕同仓库协作；这里要重点讲统一流程：需求进来，经过 Tasking、澄清、设计、计划、实现、Review、测试和验收，最后代码出去，并且验收测试通过。流程中必须写入 Skill 的同步更新和维护，通过类似 `SOUL.md` 的文件实施长期原则、流程约束、知识更新规则和 Skill 维护机制。后面再讲 Epic 到 User Story 的多线程并行流程。自动化与无人值守要提前到角色流程后讲，强调它是长时间、低人工干预，不是完全无人值守。后续 Agent 设计、提速、测试评估、AI 编排、工具层改造等必须参考文献和逐页摘取资料展开，但重点必须回到如何构建统一流程、如何构建高质量流程。
5. **重点保留用户原创观点**：
   - 模型负责推理，流程负责约束，状态负责让推理结果可以被恢复、检查和交接。
   - Story 是动态知识，Knowledge 是静态 Story；user journey 是团队发现、验证、固化知识的过程。
   - AI-native workflow = 模型推理 + 流程约束 + 状态反馈的动态系统。
   - 单仓库原则：仓库是 BA / DEV / QA / UI / Agent 共享的强状态空间。
   - AI 编程不是推翻软件工程，而是放大软件工程基本功。
   - 软件系统的本质就是知识，智能 AI Agent 系统也是知识。
   - AI 是未来新软件，它打破了“软件只能由开发人员制作”的知识垄断，推动数字民主化。
   - Tasking 本质上是需求分析与拆解，是把模糊需求变成可执行、可验证、可分派任务结构的过程。
   - 本次分享的重中之重是构建统一流程，以及构建一个高质量的统一流程。
   - 统一流程贯穿输入到输出：需求进来，代码出去，最后验收测试通过。
   - Skill 必须在流程中被同步更新和维护，并通过类似 `SOUL.md` 的文件承载长期原则、流程约束、知识更新规则和 Skill 维护机制。
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
   - 必须存在完整 Markdown 演讲稿。
   - 必须存在 HTML 演示文件，形式类似 PPT，可一屏一屏往下翻，文件体积小，内容尺寸适合现场投屏演示。
   - 最终只输出 Markdown 演讲稿和 HTML 演示文件两份文档，不需要 DOCX、PDF 或单独 slide 提纲。
   - Markdown 演讲稿必须包含必要引用列表，并可包含附录/Q&A 备选材料。
   - 必须报告这两份最终产物的完整路径。
   - 主稿标题必须是《知识工程驱动的 AI 实践》。
   - 开场第 0 章必须先讲为什么还要工程化与 SDD。
   - 第 0 章后必须进入 SoC、抽象/面向对象、文件目录结构。
   - 主稿应以自然讲述段落为主，不得大量堆 bullet points。
   - 不得频繁使用“不是……而是……”句式。
   - 第 1 至第 3 章顺序必须固定：略写软件基本功；MindFlow 的自我演进；通过 ProMaster / POMASA 介绍 MAS 的强状态。
   - 必须体现状态控制三分法：强约束固定、有建议的 AI 自主判断、完全 AI 控制，并说明灵活性与可靠性的反向关系。
   - 必须体现 Skill 随机调度、工程文件确定编排、Rules Hook 式强约束三者的差异与组合方式。
   - 必须讲清 Skill / Rule 定义后的验收标准：触发、输入、步骤、输出、验证、权限、副作用和下游可消费性。
   - 必须在第 0 章吸收新增微信文章思想，讲清为什么中低端模型容易过早收束、遗漏边界，所以需要工程化与 SDD 控制 AI 做事。
   - 必须体现 BA / DEV / QA / UI / Agent 作为“思考帽”的单线程流程、多线程流程、统一流水线和交叉检查。
   - 必须把“如何构建统一流程、如何构建高质量流程”作为本次分享的重中之重。
   - 必须讲清统一流程贯穿输入到输出：需求进来，经过 Tasking、澄清、设计、计划、实现、Review、测试和验收，最后代码出去，并且验收测试通过。
   - 必须把 Tasking 作为需求分析与拆解写入软件团队协作流程，并说明它与 SDD 的关系。
   - 必须说明流程中 Skill 的同步更新和维护机制，并说明类似 `SOUL.md` 的文件如何承载长期原则、流程约束、知识更新规则和 Skill 维护机制。
   - 必须展开 Agent 文档验收，参考 `references/papers/CLI_for_AI_Agents.pdf` 和 Skill 合法性验证思路。
   - 必须讲清 Knowledge / Story 的转化关系和 Flyway Migration 类比。
   - 必须在 MindFlow / 知识工程部分讲清软件即知识、Agent 系统即知识、AI 作为未来新软件和数字民主化。
   - 自动化与无人值守必须提前到角色流程后讲，强调长时间、低人工干预。
   - 提速章节必须有评估标准，不能只写“让模型多写代码”，并可结合《人月神话》的沟通成本问题展开。
   - 必须优先化用 `references/paper-visual/extracted/`、`references/web/` 和用户提供观点。
