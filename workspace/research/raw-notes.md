# Raw Notes

## 主线素材

- [USER-INPUT] 核心句：AI 编程不是推翻软件工程，而是把 SoC、抽象、文件结构、角色协作、测试验证这些老原则，放大成 AI-native 工作系统。
- [USER-INPUT] 核心定义：AI-native workflow = 模型推理 + 流程约束 + 状态反馈的动态系统。
- [USER-INPUT] 核心句：模型是动的流程，流程是动的模型。
- [USER-INPUT] 核心句：知识是 story diff，user journey 是知识。
- [USER-INPUT] 单仓库原则：仓库是 BA / DEV / QA / UI / Agent 共享的强状态空间。

## MindFlow / POMASA

- MindFlow 通过 Soul、Learning、Mind、Capability、Plan/Step、Task State 把认知、知识、任务执行和反省固化为文件化协议 [SRC-001][SRC-002]。
- MindFlow 的 lazy loading 说明上下文管理不是把所有知识塞给模型，而是在进入模块时按需加载权威规则 [SRC-002]。
- POMASA 的模式语言 + 生成器把 MAS 架构经验显式化，Required patterns 强制 Blueprint、参考数据、方法论、忠实调用和可追溯数据血缘 [SRC-005][SRC-006][SRC-007][SRC-008]。

## 本地 PDF

- CLI for AI Agents：面向人类的 CLI 追求发现性和容错性，面向 Agent 的 CLI 应追求可预测性、结构化、schema 自省、JSON 输入和上下文窗口控制 [SRC-020]。
- Coding Agent 飞轮：Agent 需要 Feedback Loop、Benchmark 和 Agent Engineers，把人放到 loop 里，而不是把人从系统里拿掉 [SRC-021]。
- JoyCode：企业级 AI Coding 的挑战来自业务场景复杂、用户画像丰富、复杂长任务、超大代码仓；“尽在上下文”可作为上下文管理章节的案例 [SRC-024]。
- DSL-Spec：AI 工程趋势从运行时、编译时继续左移到设计时；Spec 是人与 AI 共建手段，设计时有约束、有动机、最易维护 [SRC-023]。
- PRD 到上线闭环：AI 要运行在工程资产上，Doc 与 Code 联动，PRD 到上线形成闭环 [SRC-025]。

## Web / 公开资料

- Harness Engineering 是围绕 coding agents 构造上下文、指南、反馈传感器和验证环的工程工作 [SRC-050]。
- Anthropic 将 workflows 与 agents 区分：workflow 是 LLM 和工具沿预定义路径编排，agent 则有更高自主性；建议从能解决问题的最简单模式开始 [SRC-051]。
- Agent eval 术语：Task、Trial、Grader、Transcript/Trace、Outcome、Evaluation harness、Evaluation suite [SRC-052]。
- 长时间运行 agent 需要 harness、进度日志、checkpoint、handoff、测试和验证 [SRC-053][SRC-054]。

## 敏捷与单仓库协作重点

- Story / AC 是 Agent 理解业务目标、QA 生成测试、DEV 设计边界的共同输入 [USER-INPUT]。
- DoR 是 Agent 开始执行前的上下文完备性检查；DoD 是完成后的验收 checklist [USER-INPUT]。
- Sprint 是人和 Agent 协作的节奏控制器：计划、执行、checkpoint、review、retro [USER-INPUT]。
- Retro 是知识工程入口：失败、返工、遗漏应沉淀为 skill、测试、eval case [USER-INPUT]。
