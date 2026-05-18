# Knowledge Engineering Driven AI Practice

这个仓库保存《知识工程驱动的 AI 实践》演讲项目的输入、参考资料、Pomasa 多智能体工程和最终交付物。

## Workflow

- 输入：`user_input_template.md`
- 智能体蓝图：`agents/`
- 方法论文件：`references/methodology/`
- 运行工作区：`workspace/`
- 最终输出：`_output/final-speech.md`、`_output/presentation.html`

## Protected Evidence

以下目录是引用证据链，重新运行智能体工程时应保留：

- `references/papers/`
- `references/paper-visual/`
- `references/web/`

## Run the MAS

从总编排智能体开始：读取 `agents/00.orchestrator.md`，并按其中的阶段调用资料收集、综合分析、引用核验和演讲写作智能体。
