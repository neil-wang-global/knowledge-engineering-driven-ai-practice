# 当顶尖 Agent 模型越来越会自己干活，Prompt Engineering、SDD、MAS 还剩什么价值


**📷 This page contains 2 significant image(s). Check screenshot.png for visual content.**

# 当顶尖 Agent 模型越来越会自己干活，Prompt Engineering、SDD、MAS 还剩什么价值

[卷书成船](javascript:void(0);)
# 引言

在很多团队的实际使用中，一个常见场景已经不是“AI 不会写代码”，而是另一种更微妙的体感。它像是在偷懒。需求还没澄清完，它就急着开始实现；边界条件没想清楚，它先自己补默认值；方案还只有一个模糊轮廓，它已经把执行往前推了。表面看很积极，实际上是在用流畅感掩盖过早收敛。

也正因为这样，过去几年才会不断长出一整套工程化方法。Prompt Engineering 用来把意图说清楚，把约束钉住；SDD 用来把“想清楚”与“开始干”分开；MAS 用来把复杂任务拆成角色、上下文和阶段，各自有边界，有检查点，有中间产物。它们在很长一段时间里都像是给模型装外骨骼。

但 2026 年再看这个问题，气氛已经变了。你把一个复杂需求丢给强模型，它常常不用 elaborate prompt，不用手写流程图，甚至不用你先把 plan 展开到很细，也能自己拆任务、自己调工具、自己把结果往前推。OpenAI 在 GPT-5 的官方介绍里，已经把这类能力写成模型本身的一部分：这是一个会根据问题复杂度决定何时快速响应、何时投入更多推理和工具调用的 unified system，同时在 instruction following 与 agentic tool use 上显著增强[5]。Anthropic 这边的表述也很接近。Claude 最新的 prompting 文档明确建议，对强 thinking 模型先给 general instructions，不必急着用人类写好的逐步脚本去框它；同一份文档还直接说，最新模型已经具备更强的原生 subagent orchestration 能力[6]。如果你最近频繁觉得“这些方法论好像没以前那么刚需了”，这不是错觉。

问题不在于这种体感对不对，而在于它到底意味着什么。

## 一、为什么很多人开始怀疑这些方法论没那么需要了

先承认一个事实：顶尖模型确实把一部分原本必须外置的能力，吃回了模型内部。OpenAI 的 reasoning best practices 现在写得很直接，面对 reasoning models，通常应该用更直接、更简洁的提示；显式要求模型“step by step”往往并不必要，甚至可能适得其反[1]。这句话的含义很重。它等于承认，在足够强的模型上，一部分旧式 Prompt Engineering 的边际收益已经下降了。

Anthropic 的文档把这个趋势说得更完整。它一方面建议对强模型多给 high-level instructions，少做过度规定；另一方面又提醒，Claude 4.6 这类模型变得更主动了，如果还沿用过去那种“不断提醒它别偷懒、别省略步骤”的老式提示方式，反而可能触发过度行动或错误拆分[6]。也就是说，模型不是单纯变聪明，而是连“自己决定怎么开始做”这件事都更强了。

这个变化在产品定位里同样可见。OpenAI 把 GPT-5.1 直接定位为 coding 和 agentic tasks 的旗舰模型，并且把 reasoning effort 做成可配置能力[2]。Anthropic 在 Claude Opus 4.6 的发布页里也强调，它会更仔细地规划，能更长时间维持 agentic tasks，在更大的代码库里更可靠，同时继续扩展 agent teams、adaptive thinking 和 context compaction 这类能力[9]。如果模型本身已经能在更长轨迹里维持状态、延迟决策、反思修正，那么过去很多“替模型搭手脚架”的外部方法，当然会显得不那么必需。

所以，怀疑 Prompt Engineering、SDD、MAS 的必要性，本质上不是对方法论的厌倦，而是对模型代际变化的正常反应。很多方法之所以曾经显得重要，是因为模型本来不够稳、不够会想、不够会拆。今天最强的一档模型已经把其中一部分工作接过去了。

## 二、但这种变化不是“方法论失效”，而是“必要性开始分层”

如果把结论直接写成“顶尖模型时代，这些方法论已经不需要了”，那还是太快了。更准确的说法是：这些方法不再是所有模型、所有任务、所有团队都必须默认启用的通用前提，它们的必要性开始分层。

为什么要强调“分层”两个字？因为模型能力只是一个变量，另外还有两个同样关键的变量，一是成本预算，二是任务的开放度与容错要求。OpenAI 对 GPT-5 系列的官方定位本身，就在说明这件事。GPT-5 mini 被描述为更快、更省成本，更适合 well-defined tasks 和 precise prompts[3]；GPT-5 nano 则进一步下探到 summarization、classification 这类边界更清楚、收敛更快的工作[4]。官方并没有直接写“这类模型更容易过早收敛”，但它给出的任务定位已经足以导出一个工程含义：当任务开始变得开放、歧义高、边界复杂、错误代价更高时，你更可能需要额外结构来托底。

这也是为什么很多团队会在真实工作里得到一种看似矛盾的体验。一方面，最强模型的确越来越能“一把梭”；另一方面，只要预算稍微压下来、任务稍微散一点、流程稍微长一点，问题就又回来了。你会重新开始关心需求是否真的被说清楚，检查点是不是足够明确，中间产物能不能被审计，某些动作是不是必须强制发生。模型越往下沉到更高性价比的一档，这些问题往往越早浮出来。Anthropic 在 Sonnet 4.6 的发布中也呈现了类似趋势：能力确实在从最顶级配置向更高性价比型号下沉，但同一页面也明确提醒，模型在 computer use 等场景里依然没有达到最熟练人类的水平[10]。能力下沉是真的，边界仍然存在也是真的。

所以，“要不要方法论”不是一个抽象立场问题，而是一个条件判断问题。你用什么模型，花多少钱，做什么类型的任务，容错率多高，决定了你到底需要多强的外部结构。

## 三、Prompt Engineering、SDD、MAS 今天分别还在解决什么问题

先说 Prompt Engineering。它最早被很多人理解成一套“教模型怎么想”的技巧学。但从 OpenAI 和 Anthropic 当前的文档看，强模型时代更稳的做法恰恰不是拼命给它写思维脚本，而是把目标、边界、成功标准、输入范围和禁止事项说清楚[1] [6]。这意味着 Prompt Engineering 的重心在移动。它没有消失，但它越来越不像“逼模型进入正确思路”的魔法，而更像一种接口设计工作。你不是替模型推理，而是在定义任务边界、上下文组织方式和输出约束。它从 cognitive crutch 变成 contract surface。

再说 SDD。如果把 SDD 理解成一种以 specification 为核心、强调 multi-step refinement、让团队先把 what 和 guardrails 显化再进入 how 的 structured process，那么它今天最现实的价值，并不是神秘地增强模型智力，而是把“先想清楚”这件事制度化[11]。这点其实和强模型并不冲突。模型越强，越容易让人误以为“边想边做就够了”；但在需求含糊、边界多、多人协作、结果需要复用或追责的时候，问题恰恰不是模型会不会写，而是团队有没有把约束讲清楚。SDD 真正对抗的对象，不是模型愚笨，而是项目里的模糊、短视和过早执行。这个作用在预算受限、模型不够强、需求歧义高的时候尤其明显，但即使放到强模型场景，它也依然承担着显化意图和验收标准的作用。

MAS 则更容易被误读。很多人一说多智能体，第一反应是“多叫几个模型一起想，效果会不会更强”。从研究上看，这种设想不是完全站不住脚。More Agents Is All You Need 这篇论文指出，在其设定下，随着 instantiated agents 数量增加，性能会提升，而且这种收益与任务难度相关[12]。但如果只看到这一半，就会把 MAS 写歪。Anthropic 的 subagents 文档其实给了一个更工程化也更现实的解释：subagents 的关键收益在于独立上下文、工具限制、权限边界、成本控制，以及让主对话保持聚焦[7]。同一份文档还明确写了哪些时候不该拆 subagents：频繁来回迭代、共享大量上下文、对延迟敏感、只需要快速定点修改的时候，主对话反而更好[7]。这说明 MAS 在强模型时代的核心价值，已经不适合被概括为“让模型更会想”，而更接近“让系统更好管”。

```
More Agents Is All You Need
```

这个迁移，在 hooks 这种机制里更明显。Anthropic 对 hooks 的定义很直白，它要提供的是 deterministic control，确保某些动作总会发生，而不是把这件事交给模型临场决定[8]。这几乎就是工程治理的标准语汇。模型可以越来越聪明，但工程系统仍然会继续需要硬边界、固定检查点、权限控制和可重复规则。因为系统要保证的不只是“最后大致做出来”，而是“每次都在可接受边界内做出来”。

## 四、真正变化的，是这些方法的价值从能力补丁迁移到治理工具

把前面的线索放在一起，能看到一个比较清晰的迁移路径。

在模型还不够强的时候，Prompt Engineering、SDD、MAS 很大程度上扮演的是能力补丁。你需要它们，是因为模型自己不会拆、不会想、不够稳、记不住、容易乱来。那时这些方法像是外接大脑、外接骨架、外接记忆。

但当顶尖 Agent 模型逐步把规划、任务拆解、长链推理、工具调用、自我修正吸收进模型能力之后，工程方法的角色开始变化。Prompt Engineering 变成任务接口设计；SDD 变成需求澄清与护栏前置；MAS 变成上下文、权限、并行和审计的系统架构；hooks 这类机制则直接承担合规和 deterministic control[1] [6] [7] [8]。它们没有简单消失，只是不再以“替模型补智力”的面貌出现。

这也是为什么今天讨论这些方法，不能再停留在“有没有用”的层面。更应该问的是：它们在替谁解决什么问题？如果问题是“模型自己能不能把一个复杂任务想清楚”，那么在最强模型上，外部方法的边际收益的确下降了。如果问题是“系统能不能稳定、可控、可复查地交付”，那么这些方法不但没退出，反而更像底层设施。

这一点甚至可以反过来解释一个经常被忽略的事实：模型越强，团队未必越会减少工程控制。恰恰相反，Anthropic 在强调 Claude Opus 4.6 规划和持续执行能力增强的同时，也继续强化 agent teams、context compaction、effort controls 这类系统能力[9]。这说明前沿厂商自己也并不把“模型更强”理解成“外部结构不再重要”。他们做的事情更像是两条线并进：一条线把模型推得更强，另一条线把系统控制面做得更细。

## 五、给开发者的一个简单判断框架

如果一定要把结论压缩成一句话，那不是“这些方法过时了”，也不是“这些方法永远重要”，而是：它们正在从通用前提，变成情境化工具。

一个简单的判断方法，可以只看四个变量。

第一，模型够不够强。如果你用的是当前一代顶尖 Agent / reasoning 模型，很多过去必须外接的 planning scaffold，今天确实可以少一点。第二，预算紧不紧。只要你往更快、更便宜、更高性价比的模型档位移动，对任务定义清晰度和结构化输入的要求通常就会上升[3] [4]。第三，任务是否开放且高风险。需求含糊、边界复杂、容错低的任务，比简单明确任务更需要前置澄清和中间检查点。第四，系统是否需要治理。只要你开始在意权限、审计、复用、并行和固定动作保证，MAS、hooks、SDD 这些结构就会重新变得有价值[7] [8]。

换句话说，今天比较稳的策略不是“永远先上方法论”，也不是“相信强模型自己会搞定一切”，而是根据任务条件动态决定工程强度。一次性的个人探索，强模型加直接交互，往往已经足够。多人协作、预算受限、流程要复用、结果要追责的工作，结构化方法依然是低成本的保险。

## 六、结语：不是站队，而是重新划边界

顶尖 Agent 模型确实改写了很多工程经验。它们让一部分 Prompt Engineering 失去了旧时代那种“像咒语一样调教模型”的神秘感，也让某些原本必须外置的 planning 和 orchestration 开始内化为模型能力[1] [5] [6] [9]。如果你因此觉得一些方法论没那么需要了，这个感觉并不荒谬。

但另一半同样重要。模型变强，并没有把工程问题抹掉。它只是让问题从“如何让模型会做”转向“如何让系统做得稳、做得对、做得可控”。Prompt Engineering、SDD、MAS 还在，只是它们越来越像边界控制、流程显化和治理设计，而不再只是能力补丁。

真正成熟的结论，不是宣布一种方法论胜利或死亡，而是承认边界发生了变化。对最强模型，少一点手把手，多一点清晰约束；对预算受限和复杂高风险任务，保留足够的结构；对需要协作、审计和复用的系统，继续把治理层建好。到这一步，方法论才不再像信仰，而开始真正像工程。

## 参考文献

[1] OpenAI. Reasoning Best Practices[EB/OL]. [2026-03-07]. https://developers.openai.com/api/docs/guides/reasoning-best-practices.

[2] OpenAI. GPT-5.1[EB/OL]. [2026-03-07]. https://developers.openai.com/api/docs/models/gpt-5.1.

[3] OpenAI. GPT-5 mini[EB/OL]. [2026-03-07]. https://developers.openai.com/api/docs/models/gpt-5-mini.

[4] OpenAI. GPT-5 nano[EB/OL]. [2026-03-07]. https://developers.openai.com/api/docs/models/gpt-5-nano.

[5] OpenAI. Introducing GPT-5[EB/OL]. 2025-08-07 [2026-03-07]. https://openai.com/index/introducing-gpt-5/.

[6] Anthropic. Claude Prompting Best Practices[EB/OL]. [2026-03-07]. https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/claude-prompting-best-practices.

[7] Anthropic. Subagents[EB/OL]. [2026-03-07]. https://docs.anthropic.com/en/docs/claude-code/sub-agents.

[8] Anthropic. Hooks Guide[EB/OL]. [2026-03-07]. https://docs.anthropic.com/en/docs/claude-code/hooks-guide.

[9] Anthropic. Introducing Claude Opus 4.6[EB/OL]. 2026-02-05 [2026-03-07]. https://www.anthropic.com/news/claude-opus-4-6.

[10] Anthropic. Introducing Claude Sonnet 4.6[EB/OL]. 2026-02-17 [2026-03-07]. https://www.anthropic.com/news/claude-sonnet-4-6.

[11] GitHub. Spec Kit[EB/OL]. [2026-03-07]. https://github.github.io/spec-kit/.

[12] Wang W, Yuan W, Lin R, et al. More Agents Is All You Need[EB/OL]. 2024-10-11 [2026-03-07]. https://doi.org/10.48550/arXiv.2402.05120.

微信扫一扫赞赏作者喜欢作者


![Image: "赞赏二维码" - 110x110]()

[喜欢作者](javascript:;)
[0人付费](javascript:;)
[其它金额](javascript:;)
搜索「」网络结果

[搜索「」网络结果]()
暂无留言

[发消息](javascript:;)
微信扫一扫关注该公众号

当前内容可能存在未经审核的第三方商业营销信息，请确认是否继续访问。

[继续访问](javascript:)
[取消](javascript:)
[微信公众平台广告规范指引](javacript:;)
[知道了](javascript:;)
[取消](javascript:void(0);)
[允许](javascript:void(0);)
[取消](javascript:void(0);)
[允许](javascript:void(0);)
[取消](javascript:void(0);)
[允许](javascript:void(0);)
微信扫一扫可打开此内容，使用完整服务


![Image: "划线引导图" - 252x214](https://res.wx.qq.com/op_res/opqv3ix6k9E4e64ZzO7uIqE3ZblwIojfmt7u70m59yS1ylFK-hTu6Ra8V_LaWQJ1P4OlUJPdXLfVBtrm3TwRrw)

[我知道了]()
暂无留言

[发消息](javascript:;)
## 确认提交投诉

你可以补充投诉原因（选填）

确定

[确定]()