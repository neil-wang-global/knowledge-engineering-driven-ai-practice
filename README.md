# 知识工程驱动的 AI 实践

这个仓库保存《知识工程驱动的 AI 实践》演讲的完整生产过程：从原始任务、参考资料、研究笔记、多智能体协作提示词，到最终演讲稿和 HTML 演示稿。

它不是一个普通的 PPT 仓库。它展示的是一套更重要的东西：如何把一次复杂演讲，做成一条可追溯、可复用、可验证、可继续演进的知识生产线。

如果你正在学习 AI Coding、Agent 工作流、SDD、MAS、知识工程、企业级 AI 研发流程，这个仓库可以作为一个完整案例来读。

## 这个项目想回答什么问题？

今天很多人已经会用 AI 写代码、写文档、做总结。但真正困难的问题不是“AI 能不能生成内容”，而是：

- 如何让 AI 在复杂任务中不乱跑？
- 如何把模糊输入变成可执行、可验证的流程？
- 如何让 Agent 之间围绕同一套状态协作？
- 如何把一次任务里的经验沉淀成下一次可复用的知识？
- 如何让个人提效变成组织级提效？

这场演讲的主线就是：

> 如何构建统一流程，以及如何构建一个高质量的统一流程。

仓库里的每个目录都服务于这条主线。

## 你可以从哪里开始？

### 1. 先看最终产物

- [`_output/final-speech.md`](_output/final-speech.md)：完整中文演讲稿。
- [`_output/presentation.html`](_output/presentation.html)：最终 HTML 演示稿。

如果你只想快速了解观点，先读演讲稿。如果你想看视觉表达和 slide 结构，打开 HTML 演示稿。

### 2. 再看任务是怎么被定义的

- [`user_input_template.md`](user_input_template.md)：原始任务输入、主题要求、素材清单和写作约束。

这里能看到演讲不是凭空生成的，而是先把目标、边界、素材、重点和禁区说清楚。

### 3. 然后看 Agent 如何分工

- [`agents/`](agents/)：多智能体协作提示词。

当前包含：

- `00.orchestrator.md`：总编排智能体。
- `01.source_collector.md`：资料收集智能体。
- `02.synthesis_analyst.md`：综合分析智能体。
- `03.citation_verifier.md`：引用核验智能体。
- `04.speech_writer.md`：演讲稿写作智能体。

这些文件展示了一个重要思路：Agent 不是“一个万能助手”，而是一组有角色、有输入、有输出、有检查点的工作节点。

### 4. 最后看证据链和中间过程

- [`workspace/research/`](workspace/research/)：研究过程中的中间产物。
- [`references/`](references/)：参考资料和方法论材料。
- [`references/papers/`](references/papers/)：本地归档的 PDF 参考资料。
- [`references/web/`](references/web/)：网页资料归档。
- [`references/paper-visual/`](references/paper-visual/)：从 PDF 中抽取的可读文本和视觉材料。
- [`references/methodology/`](references/methodology/)：研究流程、输出模板和方法论说明。

这些内容让最终稿可追溯。你可以看到观点来自哪里，材料如何被筛选，哪些判断被保留，哪些内容被降级。

## 仓库结构

```text
.
├── _output/
│   ├── final-speech.md          # 最终演讲稿
│   └── presentation.html        # 最终 HTML 演示稿
│
├── agents/
│   ├── 00.orchestrator.md       # 总编排
│   ├── 01.source_collector.md   # 资料收集
│   ├── 02.synthesis_analyst.md  # 综合分析
│   ├── 03.citation_verifier.md  # 引用核验
│   └── 04.speech_writer.md      # 演讲写作
│
├── references/
│   ├── methodology/             # 方法论与模板
│   ├── papers/                  # PDF 参考资料
│   ├── paper-visual/            # PDF 抽取与视觉材料
│   └── web/                     # 网页资料归档
│
├── workspace/
│   └── research/                # source inventory、raw notes、synthesis、citation verification
│
├── user_input_template.md       # 原始任务输入
├── CLAUDE.md                    # Claude Code 项目说明
└── README.md
```

## 这个仓库适合怎么学习？

### 学 AI 工作流设计

重点看：

- `user_input_template.md`
- `agents/00.orchestrator.md`
- `workspace/research/synthesis.md`
- `_output/final-speech.md`

你会看到一个复杂主题如何被拆成阶段、角色、输入、输出和验收标准。

### 学多智能体协作

重点看：

- `agents/`
- `workspace/research/source-inventory.md`
- `workspace/research/citation-verification.md`

这里的 MAS 不是为了炫技，而是为了控制复杂度：收集、综合、核验、写作各司其职。

### 学知识工程

重点看：

- `references/`
- `workspace/research/raw-notes.md`
- `workspace/research/synthesis.md`
- `_output/presentation.html` 中关于 Knowledge、Story、Skill、Rules、SOUL.md、统一流程的章节。

核心思想是：知识不能只停留在聊天记录里。它应该有位置、有结构、有引用、有回写机制。

### 学演讲稿生产

重点看：

- `_output/final-speech.md`
- `_output/presentation.html`
- `references/methodology/output-template.md`

你可以对比最终稿和中间研究材料，理解如何从材料堆叠走向一条清晰主线。

## 核心观点速览

这场演讲围绕以下判断展开：

1. AI Coding 的关键问题已经从“会不会生成”转向“能不能稳定交付”。
2. 方法论没有消失，而是从能力补丁变成治理工具。
3. SDD、MAS、Rules、Hooks、Skill、Knowledge 都是在控制流程质量。
4. Story 是流动的 Knowledge，Knowledge 是静态的 Story。
5. 统一流程不是 checklist，而是资产生产线。
6. 仓库不是代码文件夹，而是 Agent 可导航的知识地址空间。
7. 组织级提效来自共享状态、明确角色、可验证输出和持续回写。

## 如何重新运行这套流程？

可以从总编排智能体开始：

1. 阅读 [`user_input_template.md`](user_input_template.md)，确认任务目标和素材边界。
2. 阅读 [`agents/00.orchestrator.md`](agents/00.orchestrator.md)，理解整体流程。
3. 按阶段调用资料收集、综合分析、引用核验和演讲写作智能体。
4. 把中间结果写入 `workspace/research/`。
5. 把最终结果写入 `_output/`。
6. 保留 `references/` 下的证据链，避免最终稿失去来源。

## 受保护的证据链

以下目录保存引用证据和原始材料，重新运行流程时应尽量保留：

- `references/papers/`
- `references/paper-visual/`
- `references/web/`
- `workspace/research/`

这些目录让项目具备可审计性。没有证据链，AI 生成内容就很容易变成不可追溯的“看起来合理”。

## 适合谁阅读？

这个仓库适合：

- 想把 AI Coding 做成稳定工程流程的开发者。
- 想理解 SDD、MAS、Agent Workflow 的技术负责人。
- 想把团队经验沉淀成组织知识的工程管理者。
- 想学习如何用 AI 完成复杂研究、写作和演讲生产的人。
- 想研究 Pomasa、MindFlow、Claude Code、Agent Harness 等实践的人。

## 外部参考项目

演讲中提到的两个重要参考项目：

- MindFlow: <https://github.com/neil-wang-global/MindFlow>
- Pomasa: <https://github.com/eXtremeProgramming-cn/pomasa>

## 许可证

本项目中的原创内容采用 [Creative Commons Attribution 4.0 International License](LICENSE)（CC BY 4.0）授权。

你可以复制、分享、改编和二次创作，也可以用于商业场景，但必须保留作者署名、注明来源链接，并说明是否做过修改。

推荐署名方式：

```text
《知识工程驱动的 AI 实践》
作者：Neil Wang
项目地址：https://github.com/neil-wang-global/knowledge-engineering-driven-ai-practice
许可证：CC BY 4.0
```

注意：`references/` 下归档的第三方资料可能有各自的版权或使用条款。CC BY 4.0 仅适用于本仓库中的原创内容和整理成果，不改变第三方资料的原始授权。

## 一句话总结

这个仓库不是在展示“AI 帮我写了一篇演讲稿”。

它展示的是：

> 如何把 AI 放进一条高质量流程里，让输入、角色、状态、验证、输出和知识回写形成闭环。

如果你想学习 AI 时代的软件工程和知识工程，可以从这里开始。
