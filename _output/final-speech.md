# 知识工程驱动的 AI 实践

> 60-90 分钟中文演讲稿：现场讲述版

---

## 0. 这版怎么讲

这版直接从三个老概念开始：SoC、抽象、目录结构。它们都是初级概念，但在 AI 时代更重要。模型能写代码以后，工程质量的瓶颈转向知识组织、流程约束和反馈系统。

主线很简单：软件工程基本功 → MindFlow → 知识工程 → POMASA / MAS → Skill 与工程文档 → 角色流水线 → Agent 设计与验收 → 提速与评估 → 编排和无人值守。

核心定义：

> AI-native workflow = 模型推理 + 流程约束 + 状态反馈的动态系统。

模型负责推理。流程负责约束。状态负责恢复、检查和交接。

---

## 1. 演讲结构与时间分配

| 章节 | 时间 | 要讲清楚什么 |
|---|---:|---|
| 1. SoC、抽象、目录结构 | 10 分钟 | 这三个基础能力决定 AI 能否在清晰边界内工作。 |
| 2. MindFlow | 8 分钟 | 把认知过程文件化、状态化、能力化。 |
| 3. 知识工程 | 8 分钟 | 用问题、价值、信息、方法、形式组织 AI 可消费的知识。 |
| 4. POMASA / MAS 工程 | 8 分钟 | 多 Agent 系统靠 Blueprint、references、workspace 和强状态运行。 |
| 5. Skill / 工程文档 | 10 分钟 | Skill、工程文档、严格 Load 本质都是可执行知识。 |
| 6. 角色流水线 | 14 分钟 | BA、DEV、QA、UI、Agent 是能力单元，流水线必须统一且交叉检查。 |
| 7. Agent 设计与验收 | 12 分钟 | Agent 文档必须可验收，像 Agent CLI 一样有 schema、权限、验证和可观测性。 |
| 8. 提速与评估 | 10 分钟 | 提速来自健全流程、工程资产和评估标准。 |
| 9. 编排与无人值守 | 10 分钟 | 从 Vibe、SDD、Sub-agent、分层 Plan 走向强状态自治系统。 |
| 10. 结尾 | 4 分钟 | 框架会变，工程判断不会变。 |

---

## 2. 完整讲稿正文

### 1. SoC、抽象、目录结构

先讲三个基础概念：SoC、抽象、目录结构。

SoC 是 Separation of Concerns，关注点分离。放到 AI 实践里，它解决的核心问题是上下文污染。业务意图、架构决策、接口契约、执行计划、运行状态、测试结果、评审意见，如果混在一份大文档或一段长 prompt 里，模型会读到很多信息，却很难判断哪一段是权威约束，哪一段只是讨论过程。

所以 SoC 在这里很朴素：一个文件只承担一个清楚职责。Story 管业务目标和验收标准。ADR 管决策和代价。Spec 管契约。Plan 管执行。State 管状态。Review 管检查结论。Eval 管回归证据。

抽象和面向对象也一样。这里借用一个工程直觉：把稳定职责、状态、边界和关系组织成对象。AI 读 Markdown 时也需要对象感。一个 story 文件要有 ID、状态、维护者、消费者、链接关系、验收字段和验证入口。这样模型拿到的是结构，不是散文。

目录结构是对象空间。文件路径是对象地址。标题是字段位置。ID、link、label 是引用关系。Agent 能不能稳定工作，很大程度取决于它能否在这个空间里找到正确文件、正确位置和正确关系。

一个更合适的结构可以长这样：

```text
knowledge/
  product/
    stories/
      STORY-ENT-001.md
    journeys/
      JOURNEY-ENT-REGISTER.md
  architecture/
    decisions/
      ADR-012-enterprise-boundary.md
    contracts/
      API-ENT-001-registration.yaml
  delivery/
    plans/
      PLAN-STORY-ENT-001.md
    states/
      STATE-STORY-ENT-001.md
    reviews/
      REVIEW-STORY-ENT-001.md
  quality/
    acceptance/
      AC-STORY-ENT-001.md
    evals/
      EVAL-STORY-ENT-001.yaml
src/
  enterprise/
    domain/
    application/
    interface/
tests/
  acceptance/
    STORY-ENT-001.test.ts
```

这棵树表达得更强烈：知识、交付、质量、代码分层放置；每层有自己的对象；对象之间靠 ID 连接。`STORY-ENT-001` 可以连到 journey、ADR、API contract、plan、state、review、eval 和 acceptance test。Agent 不需要靠猜，它沿着关系走。

这三个概念讲到这里就够了。SoC 给边界，抽象给对象，目录给位置。后面所有内容都从这里长出来。

---

### 2. MindFlow：把认知过程工程化

MindFlow 的价值不在形式，而在设计思想。

一个 AI 系统要长期工作，不能只靠聊天上下文。它需要知道长期原则、学习材料、当前任务、可复用能力、执行状态和复盘结果分别放在哪里。MindFlow 把这些内容拆成文件化结构：Soul、Learning、Capability、Plan、Step、Task State、Reflection。

这就是认知层面的 SoC。长期原则不要混进一次任务。学习材料不要混进执行状态。能力单元不要混进临时输出。任务被中断时，靠 state 恢复；换 Agent 时，靠 plan 和 task state 交接；完成任务后，靠 reflection 和 capability 沉淀。

MindFlow 还体现了一个关键点：知识要按需加载。AI 不需要一开始读完整世界。进入任务时读目标和状态；需要方法时读 capability；需要背景时读 learning；需要恢复时读 state。

这和后面要讲的高度自治有关。自治需要结构、状态和加载规则。模型在结构里推理，流程在边界里推进，状态让任务可恢复。

---

### 3. 知识工程：从提示词到工作系统

熊节那篇《不是提示词工程，是知识工程》给了一个很好的框架：问题导向、价值框架、信息储备、理论方法、表现形式。

放到 AI 实践里，这五件事比 prompt 更靠前。

问题导向决定任务到底解决什么。价值框架决定什么叫好，什么叫不接受。信息储备决定模型能依据哪些事实。理论方法决定怎么分析和推进。表现形式决定最终产物给谁消费。

缺任何一层，模型都会补。它补出来的内容可能很顺，但不一定正确。

所以 AI-native workflow 可以定义为：

> 模型推理 + 流程约束 + 状态反馈。

模型处理开放问题。流程规定输入、输出、角色和停止条件。状态记录进度、证据、阻塞和交接。

这个定义也说明了 AI-native 系统应该高度自治。高度自治不等于无人看管。它意味着系统能自己读取状态，自己选择下一步，自己调用工具，自己留下证据，自己触发检查，并在不确定时停下来请求决策。

这类系统的核心资产是工程知识：对象、契约、状态、检查、评估和回流机制。

---

### 4. POMASA / MAS 工程：多 Agent 需要工程结构

POMASA 也不用讲成项目说明书。它的价值是给 MAS 工程一个清楚样本。

多 Agent 系统最容易做成群聊：一个 Agent 当产品，一个当开发，一个当测试，大家互相转述。这个方式很快会失真。角色边界会混。权威信息会丢。状态会散在对话里。验收会变成“看起来可以”。

POMASA 的思路更工程化。角色来自 Blueprint。资料来自 references。方法来自 methodology。中间产物进入 workspace。最终交付进入 `_output`。Orchestrator 负责推进和检查。

这里有一个非常重要的原则：子 Agent 要读取自己的完整 Blueprint，调用方只传参数。不要由上游 Agent 转述子 Agent 的职责。长链路里，转述就是损耗。

这也解释了强状态。MAS 要可靠，必须有强状态。谁在做什么，读了什么，产出了什么，谁来验收，失败如何回流，都要落到可追踪对象里。

高度自治的 AI-native 系统，本质上就是强状态驱动的 MAS。Agent 在 Blueprint、references、workspace、state、eval 的结构中运行。

---

### 5. Skill / 工程文档：本质是可执行知识

Skill 和工程文档的本质是一样的：把经验、判断标准和流程约束，变成模型可读取、可执行、可检查的知识。

一个 Skill 要说明触发条件、输入、读取内容、执行步骤、输出位置、停止条件、权限边界和验证方式。工程文档如果想给 Agent 用，也要具备这些要素。

这里要区分两种加载方式。

第一种是 Skill 调度。它通常带有不确定性。Agent 需要判断当前任务是否匹配某个 Skill，是否要加载，什么时候加载。调度本身有模型判断参与。

第二种是严格 Load。它是确定性的。流程规定某个阶段必须加载某个概念、某个文档、某个契约。比如进入实现阶段前，必须加载 Story、ADR、API Contract 和修改边界。进入 Review 阶段前，必须加载 diff、AC、测试结果和 review checklist。

两者本质相同，都是把知识作为运行时上下文资产。区别在于：Skill 调度是智能选择，严格 Load 是流程保证。前者灵活，后者稳定。工程上两者要配合。

一个好的工程文档可以这样验收：触发清楚，输入明确，步骤可执行，输出可消费，验证内置，权限清楚，能减少重复解释，能防止同类错误复发。

这也解释了 Story 和 Knowledge 的关系。

Story 是动态知识。BA 澄清、DEV 发现边界、QA 发现缺陷、UI 发现路径问题、客户改变验收标准，都会让 Story 变化。

Knowledge 是静态下来的 Story。确认后的变化要沉淀成 AC、ADR、工程文档、Skill、Capability、测试、eval case 和 workflow pattern。

User journey 是团队发现、验证、固化知识的路径。

---

### 6. 角色而非人：单仓库里的统一流水线

AI 工作流里，重点是角色能力怎么重组。

BA、DEV、QA、UI、Reviewer、Agent 都是能力单元。一个人可以承担多个角色，一个 Agent 也可以承担部分角色。关键是流水线统一，状态统一，检查统一。

BA 的能力是把业务意图变成可验证对象。它产出 Story、User Journey、AC、Out of Scope、Open Questions。BA 的输出要被 DEV 检查可实现性，被 QA 检查可测试性，被 UI 检查路径完整性。

DEV 的能力是把业务对象转成设计、契约和实现。它读取 Story、ADR、Spec，产出 Plan、Code、Test、State Update。DEV 的输出要被 BA 检查业务意图，被 QA 检查结果可测，被 Reviewer 检查工程风险。

QA 的能力是把验收标准转成反馈环境。它把 AC、异常路径、历史 bug、客户反馈转成 test 和 eval。QA 也要反向检查 BA 的 AC 是否可测试，检查 DEV 的 outcome 是否有证据。

UI 的能力是把 user journey 转成交互约束。它产出页面状态、错误提示、空状态、权限状态和交互规则。UI 要被 BA 检查业务路径，被 DEV 检查技术约束，被 QA 检查可测试性。

Agent 的能力是执行、检查和回填。它可以承担 BA、DEV、QA、Reviewer 的部分动作，但必须运行在明确边界内。

这些流水线必须统一。统一的意思是：所有角色围绕同一个强状态空间工作。这个空间可以是单仓库：Story、ADR、Spec、Plan、State、Code、Test、Review、Eval 都在同一个可追踪结构里。

检查必须是交叉的。BA 不验收自己的 Story，DEV 不只相信自己的实现，QA 不只在最后兜底，Reviewer 不只读 diff，Agent 不验收自己的完成声明。

一条健康流水线应该像这样流动：Story 进入 Spec，Spec 进入 Design，Design 进入 Work Item，Work Item 进入 Implement，Implement 进入 Review，Review 进入 Test/Eval，Release 后回写 Knowledge Base。

这和“让 AI 运行在工程资产上”的实践是一致的。SOP 是资产生产线。Spec 不是普通文档，它是需求契约。没有清晰交接包，就无法判断任务该交给人还是交给 Agent。

---

### 7. Agent 设计与验收：文档要先过关

Agent 设计的重点是角色协议和验收。

一个 Agent 文档本身必须通过验收。没通过验收的 Agent 文档，会把混乱传给模型。

可以借用 Agent CLI 的思想来验收 Agent 文档。面向人的说明可以模糊，面向 Agent 的接口要可预测。CLI for Agents 强调 JSON payload、schema 自省、field mask、pagination、NDJSON、dry-run、sanitize、结构化错误和明确权限边界。Agent 文档也应该有同样精神。

它至少要通过七类检查。

第一，接口检查。输入对象是什么，字段是什么，是否有 schema。不能只写“读取相关资料”。要写清楚读哪些文件、哪些 section、哪些 ID。

第二，权限检查。能读什么，能写什么，不能碰什么。高风险动作是否要求 dry-run 或人工 gate。

第三，加载检查。哪些知识由 Skill 选择加载，哪些知识由流程严格 Load。严格 Load 的内容不能靠 Agent 自己想起来。

第四，输出检查。输出放在哪里，格式是什么，谁消费。Review 输出要有问题等级、证据、文件位置和处理建议。State 输出要有完成项、阻塞项、下一步和验证结果。

第五，停止条件检查。遇到 AC 不可测、ADR 缺失、契约冲突、权限越界、测试环境不可用时，Agent 必须停，不许编。

第六，验证检查。每个关键输出都要有验证信号。代码要有测试。文档要有链接。Review 要有证据。Eval 要能复跑。

第七，可观测检查。要记录任务、工具调用、失败原因、成本、耗时、人工介入点。没有可观测，无法改进 Agent。

这套验收也适用于 Skill。Skill 合法性不看名字好不好听，看它是否能被稳定触发、稳定加载、稳定输出、稳定验证。

所以 Agent 设计可以总结成一句话：

> Agent 是可验收的角色协议。

---

### 8. 提速与评估：流程稳，才跑得快

提速这件事，不能写成“让模型多写代码”。这个说法没有价值。

真正的提速来自健全流程。流程越稳，Agent 越敢自动化。资产越完整，准备成本越低。验证越自动，返工风险越低。

可以用一个简单公式看 Agent 成本：

> Agent 总成本 = 准备成本 + 验证成本 + 返工风险。

准备成本来自上下文不清、交接包不完整、契约缺失。验证成本来自测试不全、review 没标准、输出不可观测。返工风险来自任务边界过大、权限过宽、失败不能恢复。

所以提速的方向很清楚：降低准备成本，降低验证成本，降低返工风险。

这靠前面的流水线完成。Story 清楚，Spec 稳定，Work Item 小，权限明确，测试可跑，Review 有标准，Eval 能回归，State 能恢复。这样 Agent 才能跑得快。

提速还需要评估标准。只看“写了多少代码”会误导团队。更好的评估要同时看 Outcome 和 Execution。

Outcome 看结果质量：功能是否达成，测试是否通过，业务 AC 是否覆盖，安全和可维护性是否达标。

Execution 看执行过程：上下文是否准确，工具调用是否有效，是否有无效探索，是否按计划推进，是否及时停止，是否留下证据。

这和一些 Coding Agent 实践里的四象限分析很接近：高 Outcome、高 Execution 是理想状态；高 Outcome、低 Execution 说明结果不错但过程浪费；低 Outcome、高 Execution 说明执行顺但方向错；低 Outcome、低 Execution 就是系统性问题。

Benchmark 的重点也不只是分数。更重要的是发现异常值。异常值能暴露模型偏好、工具无效调用、上下文压缩问题、临时文件滥用、错误恢复策略等问题。

Feedback Loop 也很关键。线上 Agent 要能观测失败率、调用次数、工具使用、无效调用、人工接管点。没有这些数据，团队只能凭感觉调 prompt。

所以提速来自飞轮：流程资产让 Agent 更稳，评估发现异常，异常回流成规则、Skill、测试和 eval，下一轮 Agent 更快。

---

### 9. 编排与无人值守：从工具使用到自治系统

最后讲 AI 编排。

Vibe Coding 适合探索。轻，快，反馈直接。边界一复杂，就会失控。

轻量 SDD 适合把探索变成计划。先理解，再计划，再拆任务，再实现。它比 Vibe 稳。问题是大任务会把所有内容塞进一个大 plan，最后 plan 自己变成上下文黑洞。

Sub-agent 适合隔离上下文。一个 Agent 查资料，一个写方案，一个做 review，一个看测试。它的前提是输入输出清楚，否则只是并行制造混乱。

分层 Plan 适合复杂工程。产品层、应用层、领域层、基础设施层各自计划，通过契约连接。下游依赖必须是上游导出的子集。契约最好能脚本校验。

强状态编排是更高一级。Orchestrator 不只分任务，还维护 state、checkpoint、contract、review、test result、eval 和 handoff。系统能知道自己到哪一步，缺什么证据，下一步该交给谁。

这才接近高度自治。

高度自治系统至少要具备这些条件：状态可恢复，权限可控制，检查可自动，关键节点可暂停，输出可验收，失败可回放，风险可回滚。

无人值守要求前面所有东西更严格：流程更清楚，权限更窄，状态更强，测试更多，review 更独立，观测更完整。

Agent 是能力很强但不完全可信的操作员。它需要好工具、硬边界、结构化错误、dry-run、sanitize、日志和回滚。

走到这里，AI Coding 就升级成 AI-native 工作系统。

---

### 10. 结尾：框架会变，工程判断不会变

最后收束。

未来会出现更强的 Agent Teams。Worker 可以向 Thinker 开卡，Reviewer 可以触发返工，QA 可以阻塞发布，BA 可以要求补 AC。角色会更像自治单元。

架构形态也会变化。过去很多边界是为人的认知上限设计的。未来一部分边界会围绕 AI 最适合生成、维护、验证的粒度重新调整。

框架也会变。今天的分层 Plan、Skill、强状态、权限分级，很多都是当前模型能力下的工程补丁。模型变强后，形式会变化。

但工程判断不会过时。

SoC、抽象、目录结构、契约、测试、评估、状态、反馈，这些东西会继续存在。AI 越强，它们越重要。

知识工程驱动的 AI 实践，核心是把知识组织成系统：可加载、可执行、可检查、可演化。

谢谢大家。

---

## 3. Slide 提纲

1. 标题页：知识工程驱动的 AI 实践
2. 先讲三个老概念：SoC、抽象、目录结构
3. SoC：减少上下文污染
4. 抽象：让 Markdown 和代码都有对象感
5. 目录结构：对象空间
6. 嵌套结构示例：knowledge / delivery / quality / src / tests
7. MindFlow：认知过程工程化
8. MindFlow：Soul、Learning、Capability、Plan、State、Reflection
9. AI-native workflow：模型推理 + 流程约束 + 状态反馈
10. 知识工程五支柱：问题、价值、信息、方法、形式
11. POMASA：MAS 需要工程结构
12. Blueprint、references、workspace、_output、orchestrator
13. 强状态驱动高度自治
14. Skill / 工程文档：可执行知识
15. Skill 调度 vs 严格 Load
16. Story 是动态知识，Knowledge 是静态 Story
17. 角色能力：BA、DEV、QA、UI、Reviewer、Agent
18. BA：业务意图到可验证对象
19. DEV：业务对象到设计、契约、实现
20. QA：验收标准到反馈环境
21. UI：用户路径到交互约束
22. 统一流水线与交叉检查
23. Agent 设计：可验收的角色协议
24. Agent 文档验收：接口、权限、加载、输出、停止、验证、观测
25. Agent CLI 思路：schema、JSON、dry-run、sanitize、structured error
26. 提速公式：准备成本 + 验证成本 + 返工风险
27. Outcome / Execution 双维评估
28. Benchmark 用来发现异常值
29. Feedback Loop：观测失败率、工具调用、人工接管点
30. 编排方式：Vibe、SDD、Sub-agent、分层 Plan、强状态
31. 无人值守条件：状态、权限、检查、回放、回滚
32. 结束：框架会变，工程判断不会变

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
- HumanLayer, “Skill Issue: Harness Engineering for Coding Agents”, https://www.humanlayer.dev/blog/skill-issue-harness-engineering-for-coding-agents

---

## 5. 附录 / Q&A 备选材料

### Q1：为什么讲稿里少放引用编号？

现场演讲不适合频繁打断。正文保留来源归属，完整来源放在文末。发布版可以补脚注。

### Q2：Promptfoo、Braintrust、LangSmith、Langfuse 怎么定位？

它们在 eval、trace、observability、experiment management 层。主线不做产品比较，只强调 Task、Trial、Trace、Outcome 必须能记录和复跑。

### Q3：SWE-bench、Terminal-Bench 怎么讲？

它们适合说明 benchmark，但不能直接代表生产可用。生产系统还要看权限、回滚、可观测、验收和长期稳定性。

### Q4：什么时候用 Sub-agent？

任务边界清楚、输入输出能文件化、结果能独立验收时适合用。边界不清时，先补 contract 和 state。

### Q5：无人值守什么时候安全？

状态可恢复、权限可控、测试可自动运行、关键节点有人类 gate、失败可回放和回滚时，可以逐步扩大无人值守范围。
