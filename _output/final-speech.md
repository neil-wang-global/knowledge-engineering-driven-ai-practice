# 从 AI Coding 到 AI 工作系统：软件工程基本功、知识工程与 Harness Engineering 实践

> 60-90 分钟中文演讲稿：现场讲述版

---

## 0. 这版怎么讲

这场分享的叙事顺序要回到更原始、更基础的东西。

不要一上来讲 AI Coding 工具，也不要一上来讲 Agent 框架。先回到软件工程的基本功：SoC、抽象、面向对象、文件目录结构、接口契约、测试验证。因为 AI 编程不是推翻这些基本功，而是把它们的价值放大了。

这版的主线是：

1. 先讲为什么 AI 时代更需要 SoC、抽象、面向对象和文件目录结构。
2. 再讲 MindFlow：它不是重点介绍对象，而是一个把认知过程、任务状态、能力沉淀工程化的例子。
3. 再讲知识工程理论：不是提示词工程，而是问题、价值、信息、方法、表现形式的组织；引出 **AI-native workflow = 模型推理 + 流程约束 + 状态反馈的动态系统**。
4. 再讲 POMASA 和 MAS 工程：多 Agent 不是群聊，而是 Blueprint、references、workspace、orchestrator 和强状态。
5. 再讲 Skill / 工程文档：它们的本质是可执行知识，然后讲 Story、user journey、敏捷工件如何沉淀成组织知识。
6. 再讲角色而非人：BA / DEV / QA / UI / Agent 如何在单仓库里协作、交叉检查，并自然引出 Agent 设计。
7. 再讲提速：提速不是让模型多写代码，而是控制代码产出水平，并用测试、eval、review、工具链检测输出质量。
8. 最后讲 AI 编排：Vibe Coding、轻量 SDD、Sub-agent、分层 Plan、强状态编排，以及如何走向自动化和无人值守。

全场核心句：

> AI 编程不是推翻软件工程，而是把 SoC、抽象、目录结构、角色协作、测试验证这些老原则，放大成 AI-native 工作系统。

另一个核心定义：

> AI-native workflow = 模型推理 + 流程约束 + 状态反馈的动态系统。

模型负责推理，流程负责约束，状态负责让推理结果可以被恢复、检查和交接。

---

## 1. 演讲结构与时间分配

| 章节 | 时间 | 现场要讲清楚什么 |
|---|---:|---|
| 1. 开场：为什么 AI Coding 要回到软件工程基本功 | 6 分钟 | AI 让代码产出变快，也让混乱被更快放大；因此更要回到 SoC、抽象、目录、契约、测试。 |
| 2. SoC、抽象与文件目录结构：AI 时代的基本功 | 14 分钟 | SoC 降低上下文污染；抽象压缩变化；目录结构是 Agent 可遍历的事实空间。 |
| 3. MindFlow：从软件结构到认知结构 | 8 分钟 | MindFlow 把目标、学习、能力、计划、状态文件化，帮助 AI 更快理解、恢复和沉淀任务。 |
| 4. 知识工程：不是提示词工程 | 10 分钟 | 用熊节的知识工程五支柱解释：AI-native workflow 是模型推理、流程约束、状态反馈的动态系统。 |
| 5. POMASA 与 MAS 工程：多 Agent 不是群聊 | 8 分钟 | POMASA 展示 Blueprint、references、methodology、workspace、_output、orchestrator 如何支撑 MAS。 |
| 6. Skill / 工程文档：本质是可执行知识 | 10 分钟 | Skill 和工程文档不是说明书，而是触发、输入、步骤、输出、验收、评分和权限边界。 |
| 7. 角色而非人：单仓库里的 BA / DEV / QA / UI / Agent 协作 | 14 分钟 | Story 是动态知识，Knowledge 是静态 Story；单仓库是共享强状态空间；角色之间要交叉检查。 |
| 8. Agent 设计：从角色协议开始 | 8 分钟 | Agent 是角色、权限、上下文、输入输出、状态、验收和交接的组合，不是 prompt 名字。 |
| 9. 提速：控制代码产出水平，而不是代码喷射 | 8 分钟 | 提速来自任务粒度、上下文、边界、输出、验证的控制，设计错误会被 AI 放大。 |
| 10. 测试、评估与检测：让提速可持续 | 8 分钟 | 测试是 AI 的反馈环境；确定性的事交给确定性工具；失败要进入 eval case。 |
| 11. AI 编排与自动化：从 Vibe 到无人值守 | 10 分钟 | 比较 Vibe Coding、轻量 SDD、Sub-agent、分层 Plan、强状态编排，并说明无人值守边界。 |
| 12. 结尾：框架会过时，工程判断不会过时 | 4 分钟 | Agent Teams、AI 重塑架构形态、Harness 成熟后框架会变化，但工程判断仍然重要。 |

---

## 2. 完整讲稿正文

### 1. 开场：为什么 AI Coding 要回到软件工程基本功

大家好，今天这个题目叫《从 AI Coding 到 AI 工作系统》。

我想先说一个可能有点反直觉的判断：AI Coding 做得越深入，越不能从提示词技巧讲起，也不能从某一个工具讲起，而要回到软件工程基本功。

为什么？

因为 AI 让代码产出变快了，但它不会自动让工程变清楚。相反，如果一个团队原来需求边界不清、目录结构混乱、接口契约模糊、测试不足、文档没人维护，那么 AI 只会更快地把这些问题放大。

以前一个设计错误，可能需要几天时间才扩散到几百行代码。现在一个错误设计，Agent 可能十分钟就生成几千行实现、测试、配置和文档。速度变快以后，真正的问题不是“模型会不会写”，而是“系统能不能承接模型的产出”。

所以今天我不想把 AI Coding 讲成工具使用课。我更想讲一个工程问题：

> AI 编程不是推翻软件工程，而是把 SoC、抽象、目录结构、角色协作、测试验证这些老原则，放大成 AI-native 工作系统。

过去我们讲 SoC，是为了让人更容易理解系统；今天我们讲 SoC，是为了让人和 Agent 都能在清晰边界里工作。

过去我们讲抽象和面向对象，是为了封装变化；今天我们讲抽象，是为了压缩上下文，让模型在稳定接口内推理。

过去我们讲文件目录结构，是为了让项目可维护；今天我们讲目录结构，是为了给 Agent 提供一个可遍历、可引用、可验证的事实空间。

过去我们讲测试，是为了证明代码没有明显问题；今天我们讲测试，是为了给 AI 一个稳定的反馈环境。

这就是这场分享的主线：从软件工程基本功出发，往上推导到 MindFlow、知识工程、POMASA、Skill、角色协作、Agent 设计、测试评估、AI 编排和无人值守。

最终我们要回答的问题不是“怎么让模型更会写代码”，而是：

> 怎么让一个团队把业务知识、工程判断、流程约束和反馈机制，组织成 AI 可以稳定消费、执行、检查和演化的工作系统。

---

### 2. SoC、抽象与文件目录结构：AI 时代的基本功

我们先回到最原始的三个基本功：SoC、抽象、文件目录结构。

#### 2.1 SoC：关注点分离，不是概念装饰

SoC 就是 Separation of Concerns，关注点分离。

这个词大家都熟，但在 AI Coding 里它的价值会变得更直接。

因为模型的工作方式非常依赖上下文。你给它什么，它就围绕什么推理。你把业务目标、历史讨论、接口约束、临时想法、测试失败、评审意见全部混在一段长 prompt 里，它看似读到了全部，实际上很难区分哪些是权威事实、哪些是推理过程、哪些是草稿、哪些已经废弃。

人类工程师有时候可以靠经验判断：“这段话只是背景，那段才是正式约束。”但 Agent 不一定能稳定判断。上下文混杂以后，它很容易把背景当约束，把草稿当结论，把过期信息当最新状态。

所以 AI 时代的 SoC，不只是代码模块的关注点分离，也包括知识和上下文的关注点分离：

- 业务意图放在哪里；
- 决策理由放在哪里；
- 接口契约放在哪里；
- 执行计划放在哪里；
- 当前状态放在哪里；
- 测试结果放在哪里；
- 评审意见放在哪里；
- 经验沉淀放在哪里。

比如同样是“企业用户注册”，不要把所有东西写成一个万能大文档。更好的方式是把关注点拆开：

- `docs/stories/STORY-ENT-001-enterprise-registration.md`：只放业务目标、角色、验收标准、out of scope；
- `docs/decisions/ADR-012-enterprise-registration-boundary.md`：只放边界决策、替代方案和取舍理由；
- `docs/specs/API-ENT-001-enterprise-registration.md`：只放接口契约、错误码、兼容性；
- `workspace/plans/STORY-ENT-001-plan.md`：只放执行计划、步骤拆分和依赖；
- `workspace/states/STORY-ENT-001-state.md`：只放当前状态、阻塞点、下一步消费者；
- `workspace/reviews/STORY-ENT-001-review.md`：只放评审发现、证据和处理结论；
- `workspace/eval/STORY-ENT-001-regression.yaml`：只放可重复验证的回归场景。

这首先不是代码分层，而是知识和 Markdown 工程分层。代码只是这个系统的一个消费者和产物。

SoC 的价值是减少上下文污染。它告诉 Agent：你现在处理的是业务问题、设计问题、实现问题、测试问题，还是评审问题；你应该读哪个文件，在哪个章节写入结果，可以引用哪些材料，不能越权修改哪些内容。

没有 SoC，AI 会更快地制造混乱。有了 SoC，AI 才有可能在边界内工作。

#### 2.2 抽象与面向对象：压缩上下文，封装变化

第二个基本功是抽象，尤其是面向对象背后的思维。

这里不是要争论 Java、函数式、DDD 哪个更好。我想借用的是面向对象背后的工程直觉：把一组稳定的职责、状态、行为和边界，组织成一个可以命名、引用、协作、演进的对象。

在 AI 工作系统里，不只是代码对象需要这样设计，Markdown 文件也需要对象感。

一个 story 文件不是“需求文字”，它是一个 Story 对象。
一个 ADR 文件不是“架构说明”，它是一个 Decision 对象。
一个 plan 文件不是“待办列表”，它是一个 Execution Plan 对象。
一个 state 文件不是“进度随手记”，它是一个 Workflow State 对象。
一个 review 文件不是“意见汇总”，它是一个 Review Result 对象。
一个 eval 文件不是“测试补充”，它是一个 Regression Evidence 对象。

如果文件没有对象感，AI 读到的是散文；如果文件有对象感，AI 读到的是结构。

比如一个 Story 对象可以这样写：

```markdown
---
id: STORY-ENT-001
type: user_story
status: ready
owner_role: BA
consumers: [DEV, QA, UI, Reviewer, Agent]
links:
  decisions: [ADR-012]
  specs: [API-ENT-001]
labels: [enterprise, registration, onboarding]
---

# 企业用户注册

## Goal
让企业管理员可以创建企业账号，并邀请成员加入。

## Actors
- 企业管理员
- 普通成员
- 系统管理员

## Preconditions
- 管理员已完成手机号验证
- 企业名称未被占用

## Acceptance Criteria
- AC-001: 企业名称重复时，系统返回明确错误
- AC-002: 手机号未验证时，不允许创建企业
- AC-003: 创建成功后生成默认团队空间

## Out of Scope
- 企业认证审核
- 付费套餐绑定

## Verification
- tests/acceptance/STORY-ENT-001.test.ts
- workspace/eval/STORY-ENT-001-regression.yaml
```

这份 Markdown 的关键不是“格式好看”。关键是它已经具备对象属性：

- `id` 是对象标识；
- `type` 说明对象类型；
- `status` 说明生命周期；
- `owner_role` 说明谁维护它；
- `consumers` 说明谁会消费它；
- `links` 说明它和其他对象的关系；
- `labels` 说明它如何被检索和聚合；
- `Acceptance Criteria` 是可验证字段；
- `Verification` 把需求对象连接到测试和 eval。

这就是 Markdown 的面向对象设计。

抽象的价值在这里也很清楚：它压缩上下文。

如果没有抽象，Agent 每次都要读完整讨论、完整历史、完整代码，才能理解一个任务。如果有稳定对象、稳定字段、稳定 ID、稳定接口，它只需要读取当前角色需要的对象，就能在边界内推理。

抽象不是为了显得高级，而是为了让变化有容器，让上下文可压缩，让协作有契约。

#### 2.3 文件目录结构：不是收纳，是事实空间

第三个基本功是文件目录结构。

我们过去常把目录结构当成项目收纳：`src` 放代码，`tests` 放测试，`docs` 放文档。

但在 AI 工作系统里，目录结构首先是一种结构建模。它和面向对象是一致的：对象需要命名空间，对象需要位置，对象之间需要关系。

如果说一个 Markdown 文件是对象，那么目录就是对象所在的包，文件路径就是对象地址，标题层级就是字段位置，frontmatter 是对象元数据，ID、link、label 是对象之间的引用关系。

对 Agent 来说，“信息存在”还不够，它必须知道信息在正确文件的正确位置。

继续看企业注册：

```text
docs/
  stories/STORY-ENT-001-enterprise-registration.md
  decisions/ADR-012-enterprise-registration-boundary.md
  specs/API-ENT-001-enterprise-registration.md
src/
  domain/enterprise/
  application/enterprise/
  infrastructure/enterprise/
tests/
  acceptance/STORY-ENT-001.test.ts
workspace/
  plans/STORY-ENT-001-plan.md
  states/STORY-ENT-001-state.md
  reviews/STORY-ENT-001-review.md
  eval/STORY-ENT-001-regression.yaml
```

这棵目录树真正起作用的地方，不是文件夹名字，而是引用关系稳定：

- story 通过 `ADR-012` 链到决策；
- ADR 通过 `API-ENT-001` 链到接口契约；
- plan 通过 `STORY-ENT-001` 链回业务目标；
- test 名称包含 `STORY-ENT-001`；
- review 文件引用同一个 story ID 和 PR；
- eval case 使用同一个 label，比如 `enterprise-registration`；
- state 文件记录当前 checkpoint 和下一步消费者。

这样 Agent 不需要靠“全文搜索 + 猜测”理解项目，而是可以沿着对象关系遍历工程空间。

所以目录结构要回答的不只是“放在哪里”，而是四个工程问题：

1. 正确文件：这类信息的权威来源是哪一个文件？
2. 准确位置：应该写进哪个 heading、哪个字段、哪个列表？
3. 引用关系：它要链接哪些 ID、anchor、label、test、eval？
4. 消费路径：哪个角色或 Agent 会按什么路径读取它？

这就是强状态。

弱状态是聊天上下文、口头约定、临时 prompt、模型说“我记住了”。
强状态是文件路径、对象 ID、章节位置、链接关系、状态字段、测试结果、评审结论、eval case。

弱状态适合探索，强状态适合交付。

这三个基本功放在一起，就能解释后面所有内容：MindFlow 是认知层面的结构化，知识工程是知识层面的结构化，POMASA 是多 Agent 协作层面的结构化，Skill 是经验和流程的结构化，测试和 eval 是反馈的结构化。

---

### 3. MindFlow：从软件结构到认知结构

讲完 SoC、抽象、目录结构，我们再看 MindFlow，就不会把它理解成一个普通工具或模板集合。

MindFlow 的关键，不是“多几个文件夹”，而是把认知过程工程化。

如果代码系统需要 SoC、抽象和目录结构，那么 AI 工作系统也需要认知层面的 SoC、抽象和目录结构。

一个人做复杂任务时，脑子里其实有很多层东西：

- 我是谁，我的长期原则是什么；
- 我现在要解决什么问题；
- 我已经学过哪些资料；
- 我掌握了哪些可复用能力；
- 我当前计划是什么；
- 我执行到哪一步；
- 我遇到了什么阻塞；
- 我完成后要把经验沉淀到哪里。

如果这些都只在聊天上下文里，任务一长就会丢。上下文压缩一次，细节丢一点；换一个 Agent，又丢一点；中途打断，再恢复，又丢一点。

MindFlow 的设计价值在于：它把这些认知状态拆成文件化对象。

可以把它简化理解为几类对象：

- Soul：长期原则、价值判断、角色风格；
- Learning / Knowledge Base：学习材料、参考资料、事实储备；
- Capability：可复用能力和方法；
- Plan / Step：当前任务计划和步骤；
- Task State：执行状态、阻塞点、检查点；
- Reflection：复盘和经验沉淀。

这背后就是前面讲的 SoC。长期原则不要和当前任务状态混在一起；学习材料不要和执行计划混在一起；能力单元不要和一次性输出混在一起。

MindFlow 也体现了渐进加载。不是把所有知识一次性塞给模型，而是在需要的时候加载对应对象：做任务时读 Plan，遇到方法问题时读 Capability，需要背景时读 Learning，恢复现场时读 Task State。

它加速的不是“模型多写几行字”，而是三件事：

第一，减少重复解释。很多背景不用每次重新讲，因为已经落到了文件里。

第二，让长任务可以恢复和交接。任务中断后，不是靠模型“记得”，而是靠 state、plan、checkpoint 恢复。

第三，让经验可以沉淀成能力。一次任务里的成功路径、失败路径、检查清单，可以被整理成 Capability 或 Skill，下一次再调用。

所以 MindFlow 可以作为一个样本：AI 工作系统要从聊天式交互，走向文件化、状态化、能力化。

这里不需要把 MindFlow 讲成主角。它的启发是：

> 如果软件系统需要结构，AI 的认知过程同样需要结构。

有了这个基础，我们就可以进入更大的概念：知识工程。

---

### 4. 知识工程：不是提示词工程

这里可以接上熊节那篇《不是提示词工程，是知识工程》。

这篇文章有一个很重要的提醒：我们不应该只盯着“怎么问 AI”，而要往前看，问“AI 要处理的知识是怎么组织出来的”。

文章里提到知识工程的五个支柱：问题导向、价值框架、信息储备、理论方法、表现形式。

放到 AI Coding 里，这五个支柱非常具体。

第一，问题导向。不是“帮我写个功能”，而是这个功能解决谁的什么问题，用户路径是什么，业务目标是什么，不解决什么。

第二，价值框架。什么叫好？什么叫不能接受？是安全优先、性能优先、上线速度优先，还是长期可维护性优先？没有价值框架，模型只能按最常见答案生成。

第三，信息储备。有哪些业务术语、历史 ADR、客户反馈、接口文档、失败案例、代码约定是权威来源？信息储备不足，模型就会补；补出来的内容有时候很像真的，但不一定正确。

第四，理论方法。你用什么方法分析问题？是领域建模、事件风暴、DDD、测试金字塔、风险驱动测试、还是分层计划？方法不明确，模型就会把任务当普通文本生成。

第五，表现形式。最后交付给谁？是演讲稿、PRD、ADR、代码、测试、review 报告、eval case、还是 release note？表现形式不清，输出就很容易“看着像完成，实际上不可消费”。

所以提示词只是最后一层。真正重要的是前面的知识组织。

这也能解释 AI-native workflow 的本质：

> AI-native workflow = 模型推理 + 流程约束 + 状态反馈的动态系统。

模型负责推理。它处理开放问题，做关联、补全、设计、解释、生成。

流程负责约束。它规定什么时候读什么，哪个角色做什么，输入输出是什么，什么情况必须停下来。

状态负责恢复、检查和交接。它告诉我们任务进行到哪一步，哪些假设成立，哪些测试失败，哪些问题未解决，下一步消费者是谁。

如果只有模型推理，没有流程约束，AI 工作流会变成自由发挥。

如果只有流程约束，没有模型推理，它只是传统自动化脚本。

如果没有状态反馈，任务无法恢复，错误无法累积成经验，协作无法交接。

所以 AI-native workflow 不是“模型更强所以流程可以少一点”。恰恰相反，模型越强，流程和状态越重要。因为产出规模变大以后，缺少约束的错误也会更快放大。

知识工程要解决的不是“知识库里有没有资料”，而是：资料如何变成对象，如何被角色消费，如何被流程触发，如何被状态记录，如何被测试和 eval 验证，如何在失败后回流。

这就自然引出多 Agent 系统。因为当工作变成多个角色、多个对象、多个阶段，单个万能 Agent 很快会遇到上下文污染和职责混乱。

---

### 5. POMASA 与 MAS 工程：多 Agent 不是群聊

接下来讲 POMASA 和 MAS 工程。

这里也不要把 POMASA 讲成项目说明书。把它当成一个样本就够了：它展示了多 Agent 系统如果要工程化，不能只是多个 Agent 聊天，而要有 Blueprint、references、methodology、workspace、_output 和 orchestrator。

很多人第一次理解多 Agent，会想象成：我开几个模型，一个当产品经理，一个当开发，一个当测试，让它们互相讨论。

这个方式做 demo 可以，做真实交付就会遇到问题。

第一，角色边界不清。每个 Agent 都觉得自己可以补充需求、修改设计、顺手实现、顺手评审，最后责任混在一起。

第二，知识来源不清。一个 Agent 把资料转述给另一个 Agent，另一个 Agent 再转述给第三个 Agent。每转述一次，约束就丢一点。

第三，状态不清。谁完成了什么，谁阻塞在哪里，哪个输出是最终版，哪个只是草稿，很容易散落在对话里。

第四，验收不清。Agent 互相说“看起来不错”，但没有独立证据，没有引用文件，没有测试结果，没有 review checklist。

POMASA 的价值在于，它把 MAS 做成工程结构。

- Blueprint 定义角色和职责，不靠口头任命；
- references 定义权威资料来源，不靠聊天转述；
- methodology 定义分析方法和流程约束；
- workspace 存放中间产物和状态；
- `_output` 存放最终交付；
- orchestrator 推进任务、分配角色、检查交付。

这里有一个特别关键的原则：调用子 Agent 时，不要由上游转述它的完整职责，而是让子 Agent 自己读取完整 Blueprint。

这听起来像细节，其实非常重要。因为长链路里最容易出问题的是指令失真。上游转述一次，丢一点；再转述一次，又丢一点。最后子 Agent 执行的已经不是原始任务，而是被压缩、改写、误解后的任务。

所以 MAS 工程的底层原则是：

> 关键约束必须有权威来源，不能靠口口相传。

POMASA 还引出了后面要讲的强状态编排。

强状态不是说“多写文档”，而是让角色、输入、输出、状态、验证都能落到可追踪的对象里。多 Agent 系统如果没有强状态，本质上只是多个上下文窗口在漂移。

这时我们先把这个概念埋下来：后面讲 AI 编排时，会再展开 Vibe Coding、轻量 SDD、Sub-agent、分层 Plan 和强状态编排各自的适用范围。

现在先进入另一个关键问题：这些流程、判断和经验，如何变成 Agent 可以执行的知识？这就是 Skill 和工程文档。

---

### 6. Skill / 工程文档：本质是可执行知识

以前工程文档经常有一个尴尬处境：写的时候很认真，用的时候没人看。新人可能会看，但不知道哪些是必须遵守，哪些只是背景说明；老同事可能知道，但不会每次都翻。

AI 加入以后，工程文档的价值发生了变化。

文档不再只是“给人看的说明”，它可以变成 Agent 执行时读取的规则、模板、检查清单和验收标准。

但前提是：文档必须写成可执行知识。

可执行知识和普通说明文档的区别在于，它不只是解释“是什么”，还要说明：

- 什么时候触发；
- 输入是什么；
- 依赖哪些权威来源；
- 执行步骤是什么；
- 输出到哪里；
- 什么情况算完成；
- 什么情况必须停止；
- 如何验证；
- 权限边界在哪里。

这就是 Skill 的价值。

一个差的 Skill 可能写成：“你是资深工程师，请认真实现企业注册功能。”

一个好的 Skill 会更像这样：

- 触发条件：当 story 状态为 `ready`，且需要实现企业注册功能时触发；
- 输入对象：`docs/stories/STORY-ENT-001-enterprise-registration.md`、`ADR-012`、`API-ENT-001`；
- 允许读取：相关 domain、application、interface、test 目录；
- 允许修改：只允许修改与 enterprise registration 相关的文件；
- 必须步骤：读取 story → 检查 AC → 检查 ADR → 生成 plan → 实现 → 补测试 → 运行验证 → 回填 state；
- 输出对象：code diff、test result、state update、review note；
- 停止条件：AC 不可测试、ADR 缺失、接口契约冲突、权限越界；
- 验收方式：每条 AC 有测试覆盖，PR 引用 story 和 ADR，state 有证据。

这样 Skill 就不再是提示词，而是工作协议。

工程文档也是一样。

API 文档不应该只是列接口，而要说明调用方、前置条件、状态变化、错误路径、兼容性和验收方式。

测试规范不应该只是说“要写测试”，而要说明什么场景必须测，谁负责测，失败如何回流。

代码评审规范不应该只是说“注意可维护性”，而要说明哪些问题阻塞合并，哪些问题是建议，review 结论写在哪里，如何引用证据。

所以 Skill 和工程文档的共同本质是：

> 把人的经验、判断标准和流程约束，变成模型可调用、可执行、可检查的上下文资产。

这里可以简单讲 Skill 的验收或评分。

一个 Skill 好不好，不看写得长不长，而看它能不能减少重复解释、减少同类错误、稳定产出可消费结果。

可以用几个维度评分：

1. 触发是否清晰：什么时候应该用它，什么时候不该用它？
2. 输入是否明确：需要哪些文件、对象、参数？
3. 步骤是否可执行：Agent 能不能按步骤走，而不是靠猜？
4. 输出是否可消费：输出给谁，放在哪里，格式是什么？
5. 验证是否内置：如何证明执行结果符合要求？
6. 权限是否清楚：能读什么、能写什么、不能碰什么？
7. 是否减少重复解释：下次遇到同类任务，是否不用从头讲？
8. 是否防止同类错误：过去失败是否变成了规则、测试或 eval？

这里就回到知识的重要性。

知识不是静态存储出来的，而是在 user journey 中不断被发现、验证、固化出来的。

我更愿意这样说：

> Story 是动态知识，Knowledge 是静态下来的 Story。

Story 是动态知识，因为它会随着 BA 澄清、DEV 设计、QA 测试、UI 走查、客户验收不断变化。客户临时补充一个异常路径，QA 发现一个边界条件，DEV 发现一个领域约束，Reviewer 发现一个安全风险，这些都是 story 在动态地产生知识。

Knowledge 是静态 Story，因为一旦这些变化被确认，就不应该继续漂在聊天记录里。它应该沉淀为 AC、ADR、工程文档、Skill、Capability、测试、eval case、workflow pattern。

所以 user journey 不是一条画在白板上的流程线，而是团队持续发现知识、验证知识、固化知识的过程。

这就自然进入团队协作：谁发现知识，谁验证知识，谁固化知识，谁消费知识？

---

### 7. 角色而非人：单仓库里的 BA / DEV / QA / UI / Agent 协作

AI 工作流里，不要一上来讨论“AI 会不会替代某个人”。更准确的讨论方式是：角色会怎么变化。

BA 是角色，DEV 是角色，QA 是角色，UI 是角色，Reviewer 是角色，Agent 也可以承担某些角色活动。一个人可以承担多个角色，一个 Agent 也可以承担部分角色，但角色边界不能消失。

为什么要讲角色？因为 AI 工作系统不是“一个人加一个助手”，而是一组角色围绕同一个事实空间协作。

这个事实空间，我建议放在单仓库里理解。

单仓库不是说所有团队必须用一个巨大 monorepo。这里说的是：关键交付状态要处在一个可追溯、可读取、可检查的共享空间里。

这个空间里不应该只有 `src` 和 `tests`，还应该有：

- PRD / user story；
- UX / UI spec；
- domain model；
- ADR / API spec；
- plan；
- task state；
- test cases；
- review notes；
- eval cases；
- release notes；
- knowledge updates。

这样 BA、DEV、QA、UI、Reviewer 和 Agent 才能围绕同一个事实空间协作。

我们用一个 story 的流转看一下。

#### 7.1 BA 流程：把业务意图变成可验证对象

BA 的工作不是写一段“需求描述”就结束。

在 AI 工作系统里，BA 要把业务意图变成 Agent、DEV、QA、UI 都能消费的对象。

BA 至少要输出：

- Goal：这个功能解决什么问题；
- Actors：有哪些用户角色；
- User Journey：用户怎么走；
- Acceptance Criteria：什么情况算满足；
- Out of Scope：哪些不做；
- Business Rules：业务规则和边界；
- Open Questions：尚未澄清的问题；
- Links：关联 ADR、UI spec、API spec、历史反馈。

BA 还要接受检查。

DEV 可以检查 BA 的需求是否可实现、边界是否清楚、是否有技术冲突。
QA 可以检查 AC 是否可测试、异常路径是否覆盖。
UI 可以检查 user journey 是否完整、状态流转是否自然。
Agent 可以检查 story 是否缺字段、链接是否断裂、状态是否 ready。

这就是交叉检查。

#### 7.2 DEV 流程：把业务对象转成设计、实现和契约

DEV 的工作也不只是“写代码”。

DEV 要把 Story、AC、ADR、API Spec 转成实现边界和工程契约。

DEV 至少要做：

- 读取 Story 和 AC，确认要实现的业务目标；
- 读取 ADR，确认已经存在的架构决策；
- 识别领域对象、应用服务、接口边界、数据持久化边界；
- 输出 plan，说明修改哪些文件、为什么这样改、风险在哪里；
- 实现代码时只在允许边界内修改；
- 为关键路径补测试；
- 回填 state，说明完成了什么、验证了什么、还剩什么。

DEV 也要被检查。

BA 检查实现是否偏离业务意图。
QA 检查测试是否覆盖 AC 和异常路径。
Reviewer 检查代码是否符合 ADR、接口契约和安全边界。
Agent 可以检查 PR 描述是否引用了 Story、ADR、Tests，是否有越权修改。

#### 7.3 QA 流程：把验收标准转成反馈环境

QA 在 AI 工作系统里的价值会更高，不是更低。

因为模型需要反馈环境。没有测试，Agent 只能根据文本判断“看起来对”。有测试、有 eval、有失败记录，Agent 才能在环境里得到明确反馈。

QA 至少要做：

- 把 AC 转成测试场景；
- 把异常路径转成边界测试；
- 把历史 bug 转成 regression case；
- 把客户反馈转成验收补充；
- 把 Agent 跑偏案例转成 eval case；
- 把不可测试的 AC 反馈给 BA。

QA 不只是最后验收，而是把业务正确性变成可检测信号。

#### 7.4 UI 流程：把用户路径转成可交互约束

UI 也不只是画图。

UI 要把 user journey、状态变化、交互边界、错误提示、空状态、加载状态、权限状态写成可消费对象。

UI 输出的不只是视觉稿，还应该包括：

- 页面状态；
- 用户路径；
- 交互规则；
- 错误提示；
- 空状态和异常状态；
- 与 API / Story / AC 的链接。

DEV 可以检查 UI 是否有技术约束冲突。
QA 可以检查 UI 状态是否可测试。
BA 可以检查 UI 是否符合业务路径。
Agent 可以依据 UI spec 生成测试或检查实现差异。

#### 7.5 单仓库链路：让角色围绕同一事实空间协作

一个 story 在单仓库里应该有一条可追踪链路：

`STORY-ENT-001` → `ADR-012` → `API-ENT-001` → `UI-ENT-001` → `workspace/plans/STORY-ENT-001-plan.md` → `src/application/enterprise/registerEnterprise.ts` → `tests/acceptance/STORY-ENT-001.test.ts` → `workspace/reviews/STORY-ENT-001-review.md` → `workspace/eval/STORY-ENT-001-regression.yaml`。

这条链路越稳定，协作越不依赖口头同步。

BA 检查 DEV 是否实现业务意图。
DEV 检查 BA 需求是否可实现。
QA 检查 BA 验收是否可测试。
QA 检查 DEV outcome 是否可信。
UI 检查 BA 用户路径是否完整。
DEV 检查 UI 技术约束是否可落地。
Reviewer 检查代码是否符合设计和安全要求。
Agent 在边界内执行、检查、回填。

这不是让流程变重，而是让协作变得可执行。

这也自然引出 Agent 设计：如果角色边界清楚，Agent 才能被设计成某个角色的执行者，而不是万能助手。

---

### 8. Agent 设计：从角色协议开始

Agent 不是 prompt 名字。

不是写一句“你是资深工程师”，它就变成了可靠工程师。

Agent 是角色、权限、上下文、输入、输出、状态、验收和交接的组合。

更准确地说：Agent 是工作系统里的角色实例。它应该沿着对象网络工作，而不是自由发挥。

设计 Agent 不要从“它聪不聪明”开始，而要从“它承担哪个角色、消费哪些对象、输出什么证据”开始。

一个 Agent 至少要定义七件事：

1. 角色：它是 BA Agent、DEV Agent、QA Agent、Reviewer Agent，还是 Orchestrator？
2. 输入：它读取哪些对象？Story、ADR、Spec、Plan、Diff、Test Result？
3. 输出：它产出什么对象？Plan、Patch、Review、Test、Eval、State Update？
4. 权限：它能读什么、能写什么、不能碰什么？
5. 状态：它如何记录进度、阻塞和下一步？
6. 验收：谁验收它，依据什么证据？
7. 交接：它的输出给下游哪个角色消费？

比如 DEV Agent 不能只定义成“实现功能”。它应该定义成：

- 输入：ready 状态的 Story、相关 ADR、API Spec、允许修改目录、测试命令；
- 权限：只能修改 story 关联范围内的源代码和测试；
- 输出：code diff、test result、state update；
- 停止条件：AC 不可测试、ADR 缺失、接口冲突、测试环境不可用；
- 验收：Reviewer Agent 和 QA Agent 分别检查代码与测试证据。

Reviewer Agent 也不能只说“帮我看看代码”。它应该有独立上下文，重点检查：

- 是否实现 Story 的业务意图；
- 是否遵守 ADR 和接口契约；
- 是否越权修改；
- 测试是否覆盖 AC；
- 是否有安全、性能、可维护性风险；
- 输出是否引用证据，而不是一句“看起来没问题”。

这里可以区分几类 Agent：

- Thinker Agent：只做分析和设计，不改代码；
- Worker Agent：按计划实现，不随便改设计；
- Reviewer Agent：独立检查，不共享实现者的自我解释；
- QA Agent：把 AC、异常路径、历史缺陷转成测试和 eval；
- Orchestrator：编排流程、维护 state，不混入具体实现细节。

这种拆分不是形式主义，而是为了避免上下文污染。

同一个 Agent 如果又设计、又实现、又评审、又修复，它会越来越容易自我合理化。它刚刚做了一个设计，又要评审自己的实现，天然容易解释为“这是合理的”。

所以 Agent 设计的第一原则是角色协议，而不是 prompt 风格。

---

### 9. 提速：控制代码产出水平，而不是代码喷射

接下来讲提速。

很多人一听 AI Coding 提速，就会想到：让模型写更多代码，让它一次性完成更多任务，让它少问问题。

但真实工程里，这种提速很危险。

真正的提速不是代码喷射，而是控制代码产出水平。

什么叫控制代码产出水平？就是控制五件事：

1. 任务粒度：一次让 Agent 做多大的事情；
2. 上下文范围：它应该看到哪些信息，不应该看到哪些噪声；
3. 修改边界：它可以改哪些文件，不能改哪些文件；
4. 输出形态：它应该输出 patch、plan、test、review，还是 state update；
5. 验证方式：怎么证明它做对了。

如果这五件事不控制，模型越强，风险越大。

比如你让 Agent “实现企业注册系统”，它可能会一次性改 domain、application、controller、database、UI、测试、文档。看起来产出很多，但 review 成本巨大，错误定位困难，失败后也不知道从哪里恢复。

更好的方式是把任务拆成可验证步骤：

1. 补全 Story 的 AC 和 Out of Scope；
2. 确认是否需要 ADR；
3. 设计 API Spec；
4. 实现 domain invariant；
5. 实现 application use case；
6. 实现接口层；
7. 补 acceptance test；
8. 跑测试；
9. 回填 state；
10. 触发 review。

每一步都有输入、输出、边界和验收信号。

速度来自哪里？不是来自一次生成更多代码，而是来自返工减少、定位更快、交接更清楚、失败可恢复。

这里要强调一句：

> AI 不是降低设计重要性，而是提高设计杠杆。

以前设计不清，开发慢一点，还可能在写代码过程中慢慢发现问题。现在 AI 太快了，设计不清会被迅速展开成大量错误实现。

所以提速的核心不是让模型少思考，而是让系统更早暴露错误、更快反馈、更容易恢复。

可以把提速分成几层：

- L1：个人辅助，补代码、解释代码、写测试；
- L2：任务执行，有 plan、有边界、有验证；
- L3：Workflow 执行，多个角色和状态串起来；
- L4：多 Agent 编排，Thinker、Worker、Reviewer、QA 协作；
- L5：长时间自主运行，有 checkpoint、observability、rollback、人类 gate。

越往上，越不能靠“模型更努力”。越往上，越需要强状态、角色协议、测试和工具层约束。

---

### 10. 测试、评估与检测：让提速可持续

没有测试的提速，是把风险从开发阶段推迟到验收阶段。

在 AI 时代，测试不只是质量保障。测试是 AI 的反馈环境。

模型看不见“业务上对不对”，除非我们把对错变成可检测信号。它也看不见“流程上走没走完”，除非 state、checkpoint、review、eval 都有明确记录。

所以确定性的事要交给确定性的工具。

状态管理、契约校验、进度查询、lint、test、文件结构检查、frontmatter 校验、输出格式校验，这些都不要交给模型创造性解释。

有一句原则很好用：

> Skill 编排流程，Agent 处理不确定性，Script 处理确定性。

模型适合处理开放问题，脚本适合处理确定规则。不要让模型去判断一个 failed 状态是不是“基本完成”。

反思也一样。

“我检查过了，没问题”不算反思。

真正的反思必须带证据：引用哪个目标、哪个章节、哪个契约、哪个文件、哪个测试、哪个输出。

比如 Reviewer Agent 不能只说“实现符合需求”。它至少要能指出：检查了 `STORY-ENT-001` 的哪几条 AC；对应测试在哪里；ADR 的哪个 decision 被实现遵守；哪个失败路径进入 eval；哪些文件没有越权修改。

失败也不能只当事故。失败是 eval case 的来源。

客户反馈、QA bug、review 问题、Agent 跑偏、上下文缺失，都应该回流成测试、checklist、skill rule 或 eval case。

Agent eval 可以简单讲几个概念：

- Task：要评估的任务；
- Trial：一次执行尝试；
- Grader：评分器，可以是规则、脚本、人或模型；
- Transcript / Trace：执行过程和工具调用轨迹；
- Outcome：环境最终状态；
- Evaluation Harness：执行、记录和评分的评估环境；
- Evaluation Suite：一组可重复运行的任务集。

这里重点不是术语，而是思路：

> 不要只评估 Agent 说了什么，要评估环境最后变成了什么。

如果 Agent 最后说“完成了”，但测试没跑、state 没更新、review 没证据、eval 没新增，那 outcome 就不是完成。

企业交付关心的不是偶尔成功，而是稳定不坏。pass@k 可以说明“多试几次能不能成功”，pass^k 更关心“连续多次是否都成功”。真实生产更接近后者。

这也解释了为什么很多团队觉得模型“偷懒”。很多时候不是模型态度问题，而是目标不清、上下文不完整、反馈不及时、验收不可验证。系统没有给它足够清晰的约束，它就会选择看起来最顺的路径。

所以测试、评估和检测不是 AI 工作系统的尾巴，而是让提速可持续的基础设施。

---

### 11. AI 编排与自动化：从 Vibe 到无人值守

最后讲 AI 编排的常见办法。

第一种是纯 Vibe Coding。

它适合小任务、探索性任务、个人快速试错。优点是快，反馈直接，心理负担低。缺点也明显：上下文不可控，结果难复用，缺少文件化 plan，失败后不容易恢复。

第二种是轻量 SDD。

这里可以理解成从 brainstorming 到 plan，再到 task，再到 implementation。它比纯 Vibe 更工程化，因为有计划、有文件、有阶段，有时候还能断点续跑。它适合千行级任务，或者边界相对清楚的功能。

很多 AI 编程入门文章都会强调这一点：不要只靠一句 prompt 让模型开写，而是先让它理解仓库、提出方案、列出计划、拆成任务，再逐步执行。这个思路非常有价值，因为它把“即时生成”变成了“有计划的生成”。

但轻量 SDD 也有局限。它通常把太多东西塞进一个集中 plan：架构、框架、接口、领域边界、测试策略、风险都在一个文件里。任务小的时候没问题，任务大了以后，plan 会变成长上下文黑洞。

所以轻量 SDD 适合从 Vibe Coding 迈向工程化，但它不是企业级复杂任务的终点。它解决了“不要无计划地写”，但还没有完全解决“计划本身如何分层、如何被多个角色消费、如何验证上下游契约一致”。

第三种是 Sub-agent 委派。

Sub-agent 的价值是隔离上下文、提高并行度、减少主会话污染。比如让一个 Agent 专门看测试失败，让另一个 Agent 专门做文档核对，让第三个 Agent 做安全 review。

但 Sub-agent 也有风险：上下文不完备、并行冲突、交接协议不足。如果子 Agent 不知道权威输入在哪里，不知道输出写到哪里，不知道谁验收，它只是另一个会跑偏的上下文窗口。

第四种是分层 Plan。

分层 Plan 解决的是集中 plan 的上下文爆炸。比如按 OHS、Application、Domain、Infrastructure 分层，每层只关心自己的职责。

上游导出契约，下游依赖契约。下游依赖必须是上游导出的子集。

这就是契约驱动的跨层一致性。

分层不是把东西切开以后各干各的，而是通过契约让切开的部分还能一致协作。最好这些契约能被 script 校验，而不是靠模型看一眼。

第五种是强状态编排。

强状态编排不是只靠一个 plan，而是把 plan、state、contract、review、test result、eval、output 都落盘。

Orchestrator 不只是“分配任务”，而是维护状态：谁在做什么，当前 checkpoint 是什么，阻塞在哪里，下游消费者是谁，哪些证据已经满足，哪些还缺。

这时 AI 编排才有可能从单次任务执行，走向自动化和长时间运行。

但自动化和无人值守不是放飞 AI。

无人值守不是减少人类责任，而是把人类责任前置到 workflow、权限、状态、测试和评审设计里。

要进入长时间运行，至少需要：

- 强状态：任务进展、假设、阻塞和证据都可恢复；
- 权限边界：Agent 能读什么、写什么、执行什么要清楚；
- checkpoint：关键节点可以暂停、检查、接管；
- 自动测试：确定性反馈必须自动运行；
- 独立 review：不能只相信执行 Agent 自己说完成；
- 人类关键决策点：高风险变更、产品取舍、安全边界要有人类 gate；
- 可观测：成本、耗时、失败类型、工具调用、上下文来源要能追踪；
- 回滚机制：出错时能停止、恢复、重跑或降级。

工具层也要跟着改。

人类 CLI 不等于 Agent CLI。人类体验追求好探索、好容错；智能体体验追求可预测、可约束、可防御。

从工具安全角度看，Agent 应该被当作能力很强但不可完全信任的操作员。它会幻觉，会误读，也可能被提示注入影响。

所以面向 Agent 的 CLI 应该支持：

- JSON payload，而不是只给人看的自然语言输出；
- schema 自省，让 Agent 知道参数、类型和约束；
- field mask 和 pagination，避免一次返回撑爆上下文；
- NDJSON，支持长任务流式输出；
- `--dry-run`，让高风险操作先预演；
- `--sanitize`，降低提示注入和脏数据污染；
- 结构化错误，让 Agent 能判断可重试、需澄清，还是必须停止；
- 明确权限边界，避免“顺手改了不该改的东西”。

所以从 Vibe 到无人值守，中间不是靠信仰跨过去的，而是靠上下文管理、分层计划、角色协议、测试验证、评估闭环和工具层改造一步步跨过去的。

---

### 12. 结尾：框架会过时，工程判断不会过时

最后收束到三个判断。

第一，Agent Teams 会出现。

现在很多多 Agent 系统还是主从式编排：主 Agent 拆任务，子 Agent 执行。未来可能会走向协作式 Agent Team。Worker 发现设计有问题，可以向 Thinker 开卡；Reviewer 可以触发返工；QA 可以阻塞发布；BA 可以要求补充 AC。角色之间通过强状态和契约双向协作。

第二，架构形态会被 AI 重新塑造。

今天很多微服务、领域划分、服务拆分，是为人的认知上限设计的。未来架构决策可能会从“人能理解多少”，变成“AI 在什么粒度上生成和维护代码最高效”。当然，性能、安全、部署、组织边界仍然重要，但认知约束会变化。

第三，框架是为了消灭自己而存在。

分层 Plan、契约校验、渐进加载、权限分级、强状态编排，都是当前模型能力不足时的工程补丁。未来模型更强，这些框架形态会变化。

但搭建这些框架的过程不会白费。它会迫使团队想清楚：哪些事需要推理，哪些事需要规则，哪些信息应该何时出现，哪些结果必须被验证。

框架会过时，工程判断不会过时。

所以回到开头：AI Coding 的终局，不是人人都会写 prompt，也不是模型替我们写完所有代码。

真正的终局是：团队拥有一个可演化的 AI 工作系统。业务知识、工程决策、上下文规则、角色协议、测试反馈、失败经验，都能被对象化、引用化、验证化，然后持续转化为 AI 可以执行的能力。

AI 编程不是推翻软件工程，而是把软件工程基本功放大到知识、上下文和工作系统层面。

谢谢大家。

---

## 3. Slide 提纲

1. 标题页：从 AI Coding 到 AI 工作系统
2. 开场问题：为什么个人体感提效，组织交付没有等比例提效？
3. 核心论点：AI 编程不是推翻软件工程，而是放大基本功
4. 为什么先讲 SoC、抽象、目录结构，而不是提示词技巧
5. SoC：Separation of Concerns / 关注点分离
6. AI 时代的 SoC：业务、决策、契约、计划、状态、验证分离
7. 示例：企业注册 story 如何拆成 Story / ADR / API Spec / Plan / State / Review / Eval
8. 抽象与面向对象：职责、状态、行为、边界
9. Markdown Object：Story、ADR、Plan、State、Review、Eval 都是对象
10. Story 对象示例：id、type、status、owner、links、AC、Verification
11. 文件目录结构：不是收纳，是事实空间
12. 正确文件、准确位置、稳定 ID、link、label
13. 弱状态 vs 强状态：聊天上下文不能支撑组织交付
14. MindFlow：从软件结构到认知结构
15. MindFlow 的对象：Soul、Learning、Capability、Plan、Task State、Reflection
16. 知识工程五支柱：问题、价值、信息、方法、表现形式
17. AI-native workflow：模型推理 + 流程约束 + 状态反馈
18. POMASA：多 Agent 不是群聊
19. MAS 工程：Blueprint、references、methodology、workspace、_output、orchestrator
20. Skill / 工程文档：可执行知识
21. Skill 评分：触发、输入、步骤、输出、验证、权限、复用、防错
22. Story 是动态知识，Knowledge 是静态 Story
23. 角色而非人：BA / DEV / QA / UI / Reviewer / Agent
24. BA 流程：业务意图 → 可验证对象
25. DEV 流程：业务对象 → 设计、实现和契约
26. QA 流程：验收标准 → 反馈环境
27. UI 流程：用户路径 → 可交互约束
28. 单仓库协作：共享强状态空间
29. 交叉检查：BA 查业务意图，QA 查可测试性，Reviewer 查工程风险
30. Agent 设计：角色、权限、上下文、输入输出、状态、验收、交接
31. Thinker / Worker / Reviewer / QA / Orchestrator
32. 提速：控制代码产出水平，而不是代码喷射
33. 任务粒度、上下文范围、修改边界、输出形态、验证方式
34. 测试是 AI 的反馈环境
35. 确定性的事交给确定性的工具
36. 失败是 eval case 的来源
37. Agent Eval：Task / Trial / Trace / Outcome / Grader
38. AI 编排演进：Vibe Coding → 轻量 SDD → Sub-agent → 分层 Plan → 强状态
39. 契约驱动的跨层一致性
40. Agent CLI：人类体验 vs 智能体体验
41. 无人值守条件：强状态、checkpoint、权限、review、observability、rollback
42. 展望：Agent Teams 与架构形态变化
43. 结束页：框架会过时，工程判断不会过时

---

## 4. 引用列表

- 熊节，《不是提示词工程，是知识工程》，https://mp.weixin.qq.com/s/MGnWz2b2H63lC8tK7UbrDA
- 《我希望用一篇文章帮你叩响AI辅助编程的大门》，https://mp.weixin.qq.com/s/9Dh-e7Z139QoOqrWOqkKJA
- 《Anthropic 万字长文：AI Agent 评估体系全解析》，https://mp.weixin.qq.com/s/pwhg5Kmh3wMlxqIlbVqGMw
- 徐翔，《尽在上下文——JoyCode 的企业级 AI Coding 实践》，`references/papers/徐翔-尽在上下文&mdash;&mdash;JoyCode 的企业级 AI Coding 实践.pdf`
- 李文鹏，《让 AI 运行在工程资产上：从 PRD 到上线的交付闭环、Hybrid 执行、Doc 与 Code 联动》，`references/papers/李文鹏-让 AI 运行在工程资产上：从 PRD 到上线的交付闭环、Hybrid 执行、 Doc 与 Code 联动.pdf`
- 牛万鹏，《构建 Coding Agent 的飞轮：Feedback Loop、Benchmark、Agent Engineers》，`references/papers/牛万鹏-构建 Coding Agent 的飞轮：Feedback Loop、Benchmark、Agent Engineers.pdf`
- 曹偲，《DSL-Spec：TocoAI 的后端 Harness Engineering 实践》，`references/papers/曹偲-DSL-Spec：TocoAI 的后端 Harness Engineering 实践.pdf`
- 钱世俊，《给 Agent 做 CT：大规模 Agent 的可观测与质量保障体系》，`references/papers/钱世俊-给 Agent 做&ldquo;CT&rdquo;：大规模 Agent 的可观测与质量保障体系.pdf`
- 章平，《从盲目调优到数据驱动：大规模 Agent 的评估工程实践》，`references/papers/章平-从盲目调优到数据驱动-大规模 Agent 的评估工程实践.pdf`
- `CLI_for_AI_Agents.pdf`，`references/papers/CLI_for_AI_Agents.pdf`
- MindFlow README-CN，`https://github.com/neil-wang-global/MindFlow/blob/main/README-CN.md`
- MindFlow SYSTEM，`https://github.com/neil-wang-global/MindFlow/blob/main/SYSTEM.md`
- MindFlow tasks README，`https://github.com/neil-wang-global/MindFlow/blob/main/tasks/README.md`
- MindFlow capabilities README，`https://github.com/neil-wang-global/MindFlow/blob/main/capabilities/README.md`
- POMASA README 中文，`https://github.com/eXtremeProgramming-cn/pomasa/blob/main/README.zh-cn.md`
- POMASA Generator Skill，`https://github.com/eXtremeProgramming-cn/pomasa/blob/main/skills/pomasa/SKILL.md`
- POMASA Pattern Catalog，`https://github.com/eXtremeProgramming-cn/pomasa/blob/main/skills/pomasa/pattern-catalog/README.md`
- POMASA BHV-02 Faithful Agent Instantiation，`https://github.com/eXtremeProgramming-cn/pomasa/blob/main/skills/pomasa/pattern-catalog/BHV-02-faithful-agent-instantiation.md`
- Anthropic, “Building effective agents”, https://www.anthropic.com/engineering/building-effective-agents
- Anthropic, “Demystifying evals for AI agents”, https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents
- Anthropic, “Effective harnesses for long-running agents”, https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents
- Martin Fowler, “Harness engineering for coding agent users”, https://martinfowler.com/articles/exploring-gen-ai/harness-engineering.html

---

## 5. 附录 / Q&A 备选材料

### Q1：为什么不在正文里放很多 [SRC-xxx]？

现场演讲不适合把引用编号塞进正文，会打断听众理解。正文中保留来源归属，完整引用放在最后。正式发布版可以再加脚注。

### Q2：Promptfoo、Braintrust、LangSmith、Langfuse 怎么定位？

它们属于 eval / observability / trace / experiment management 层。主讲不展开产品比较，只强调评估系统要记录 Task、Trial、Trace、Outcome，并能重复运行。

### Q3：SWE-bench、Terminal-Bench 该怎么讲？

它们可以作为 benchmark 例子，但不要把 benchmark 等同于生产可用性。Benchmark 证明“能做”，生产系统还要证明“稳定做、可回滚、可观测、可验收”。

### Q4：上下文压缩有哪些技术？

可以讲 summary、tool output pruning、sliding window、pinning、field mask、分页、NDJSON。重点不是技巧，而是区分哪些信息必须完整保留，哪些可以压缩，哪些应该由工具确定性查询。

### Q5：什么时候用 Sub-agent？

当任务边界清晰、输入输出可文件化、执行结果可独立验收时适合用 Sub-agent。边界不清时，先做 plan 和 contract，不要急着并行。

### Q6：AI 会不会替代 BA / DEV / QA / UI？

更准确的说法是角色会被重组。Agent 可以承担部分角色活动，但角色边界、验收责任和业务判断不会消失。

### Q7：无人值守什么时候安全？

当任务边界明确、权限可控、状态可恢复、测试可自动运行、关键决策有人类 gate、失败可回滚时，可以逐步增加无人值守程度。
