# 赵庆杰-从一次会话到亿级并发-构建可扩展-可隔离的-AI-Agent-运行环境

- Source images: `references/paper-visual/images/赵庆杰-从一次会话到亿级并发-构建可扩展-可隔离的-AI-Agent-运行环境/`
- Processing mode: page-by-page visual information extraction (OCR-assisted; not a summary)
- Pages covered: 34

## Page 001

InfoQ 极客传

QCon

全球软件开发大会

构建可扩展，可隔离的 AI Agent 运行环

境

阿里云 AgentRun 产品技术负责人：赵庆杰

InfoQ 2026 Al Agent Infra

## Page 002

极客邦科技 2026 年会议规划

促进软件开发及相关领域知识与创新的传播

06月°上海

28 1000人

08月？深圳

88 1000人

AiCon

•Al Infra 系统工程

AiCon

•Agentic Al

，多 Agent 协作与实践

•轻量化与高效推理

全球人工智能开发与应用大会

多模态融合

•模型训练与推理创新

全球人工智能开发与应用大会

•多模态应用

•Al + IoT 场景实践

会议时间：6月26-27日

数据平台与特征服务

会议时间：8月21-22日）

•Al工业化落地

010月9上海

283 1200人

◎12月？北京

881000人

Qcon

：AlAgent

•Vibe Coding

AiCon

•大模型架构创新

智能可观测

•多模态 AI 产业融合

全球软件开发大会

§推理基建

全球人工智能开发与应用大会

•具身智能

•模型攻防

*Al for Science

会议时间：10月22-24日

•Al x 创造力

会议时间：12月18-19日

•大模型安全

## Page 003

InfoQ 极客传媒

QCon

全球软件开发大会

Al Agent 时代的基础设施变革

阿里云 AgentRun 企业级 Agent 平台

关键技术能力深度解析

目录

客户实践与案例分享

Agent Infra 的核心挑战与设计原则

未来展望与总结

## Page 004

Al Agent 时代的

基础设施变革

从 Prompt Engineering 到 Harness

Engineering

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 005

•

企业级 Agent 开发面临的六大挑战

开发模式多样

高性能安全

模型和工具

1

2

3

难以持续演进

执行环境难构建

服务稳定性差

不同层次开发者需要无代码/低代码/

Agent 需安全隔离的执行环境运行代码

Agent依赖大模型和外部工具服务

高代码多种模式，期望持续演进

自建成本高、性能差、安全隔离困难

缺乏统一的容错和治理机制

效果评估和

企业数据安全

4

5

6

多Agent 协同

持续优化困难

和合规挑战

缺乏基础设施

Agent运行是黑盒，无法评估效果

涉及知识库、用户数据等敏感信息

Agent 间通信、状态管理，失败恢复

不知道如何优化，成本不透明

数据安全和合规是最大顾虑

分布式编排与调度复杂度高

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 006

AI 工程方法的三次演进

Prompt Engineering

Context Engineering

Harness Engineering

2022-2024

2025

2026

关注如何表达需求

关注怎么提供恰到好处的信息

关注如何构建系统

打磨单次对话里的指令

上下文裁剪、压缩、按需检索

运行环境＋工具调用＋记忆＋评估

研究怎么提问，给出示例

在有限 context window 下组织背景

Agent = LLM + Harness

资料

核心洞察：一旦模型能力过线，瓶颈就会外移。智力本身不再是瓶颈，瓶颈转移到了系统层。

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 007

Agent = LLM + Harness： 六大关键组件

Memory &

Tools &

Infra &

Orchestration

Evaluation

Observability

Context

Skills

Guardrails

记忆与上下文管理

工具与技能

编排与协调

基础设施与保障

评估与验证

追踪与观测

Agent 应该看到什么

扩展 Agent的行动能

任务拆分、推进与收

沙箱、权限、失败恢

验让闭环与自动修正

执行轨迹，日志，监

信息

力

敛

复

控

信息层（准备信息） 执行层（推动执行） 反馈层（复盘结果）

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 008

•

为什么 AI Agent 基础设施成为核心竞争力

训练即部署

Harness 被模型吸收

Agent 能力的上限由环境质量决定

模型公司把"模型+Harness"当整体优化

Cursor 用真实用户 coding 环境训练 Composer

tool search、programmatic tool use 等

Windsurt：环境质量对模型表现影响最大

能力已被模型内生化

Harness 即数据飞轮

Multi-Agent 协同时代

真正有价值的数据：Agent 跑出来的执行轨迹

从个人 Vibe Coding 到多 Agent 协同开发

Harness 不再只是脚手架

峰值日消耗 12亿 Token

而是模型能力生成的土壤

需要完善的 CI/CD 与 Harness 体系

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 009

2

阿里云 AgentRun

企业级 Agent 平台

以高代码为核心、生态开放、灵活组装的一站

式 Agentic AI 基础设施平台

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 010

函数计算 AgentRun 助力企业加速 AI 创新

7AgentRun是以高代码为核心、生态开放、灵活组装的一站式 Agentie AI 基础设施平自，为企业级Agent提供开发、调试、部署、运

维的全生命周期管理。助力企业和开发者专注于 AI 业务创新，无需自建和管理底层基础设施，让 Agentic AI 真正进入企业生产环境。

高代码

低代码

超级 Agent

灵活定制，稳定运行

开箱即用，快速验证

AS AgentScope

LangChian

ADK

CrewAI

Qoder 智能生成

Dify

AiStudio

Agent 市场

MCP&SDK

MCP

智能

Art

行政

客服

Agent

助手

AgentRun

可观测

凭证管理

Observability

Agent 评估

Evaluation

沙箱

Credential

Sandbox

运行时

模型接入

记忆/知识库

网关

Runtime

Model

Context Eng.

Al Gateway

工具/市场

Connector

Function

MCP

SKills

Call

Agent

浏览器

Code

AI⑧

酒行时

品沙箱，

：“百炼

"Modelstope

••OTS：

••ADB.。

CMS 2.0

angfuse

Hi

模型

ComfyUI

函数计算

'并源/微调模型

Promote

LoongSuite

on PAI&FC&ACS

Higress

市场

Flow

MemO

Ragflow

全球软件开发大会

## Page 011

函数计算 AgentRun：产品定位与架构

以高代码为核心、开放生态、灵活组装的一站式 Agentic AI 基础设施平台

为企业级 Agent 提供开发、调试、部署、运维的全生命周期管理

构建

运行时

部署

稳定

效果

安全

高低代码一键转换

开箱即用 Sandbox

全栈 Serverless

Al Gateway 治理

全链路可观测

VPC/IDC 互通

拥抱主流 AI开发框架

Agent/Code/Brows

极致弹性、按需付费

模型 Fallback

Agent/Rag/Tool评

数据不出域

AgentScope/LangC

er/AlO

免运维

熔断降级

估

凭证管理

hain/ADK

安全隔离、高性能

零到百万级并发

并发控制

数据飞轮

权限隔离

Qoder 智能生成

毫秒级弹性

持续优化

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 012

AgentRun 四大核心优势

• 自动应对0到百万级并发

• 高性能多语言 Sandbox

Serverless

• 毫秒级冷启动和弹性伸缩

企业级

•多维度隔离（会话亲和/请求隔离）

基础设施

•按量付费，不使用不计费

Runtime

•统一模型代理、熔断降级

与安全隔离

• 无需管理服务器/容器/K8s

• MCP 标准化治理

零运维、极致弹性、按量付费

高性能、高安全、开箱即用

• 兼容 AgentScope/LangChain 等5+框架

• 端到端全链路 Trace

开源开放

• 无代码一键转高代码

全链路

• 细粒度成本归因

无框架锁定

• 深度集成 RAGFlow/MemO

可观测与评估

• 实时性能监控、智能异常诊断

• 模块化使用，可散件集成

• Agent/Rag/Tool 多维度评估

数据不出域，灵活集成，平滑演进

看得清、管得住、优化快

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 013

AgentRun 赋能 Agent 研发全生命周期闭环

01

POC 验证

02

构建 Build

03

部署 Deploy

运行 Runtime

无代码 60 秒快速创建

低代码/高代码框架集成

Serverless 零运维弹性

企业级 Sandbox &

Gateway

数据驱动• 持续迭代 • 越跑越好

08

强化学习 RL

07

微调 Fine-tune

06

评估 Evaluate

05

观测 Observe

基于业务数据持续提升

Trace 生成数据集微调

Agent/RAG/Tool 多维评估

全链路 Trace 实时监控

QCon

InfoQ极客传媒

全球软件开发大会

## Page 014

）4

关键技术能力

深度解析

Runtime & Sandbox / 上下文工程/可观测与

评估

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 015

企业级 Runtime 与安全隔离：Agent & Sandbox 运行时

Agent Runtime

Code Sandbox

Browser Sandbox

AIO Sandbox

AgentScope / LangChain

多语言代码执行环境

浏览器自动化环境

全能沙箱环境

Llamalndex/ CrewAI/ADK

内置 Python/Node/Java

Web 爬取与信息提取

Computer Use 能力

轻量化函数

安全隔离，防数据泄露

表单填写与页面交互

复杂工作流编排

毫秒级弹性

支持 Skills 挂载

截图与内容分析

GPU 算力解耦

百万级

毫秒级

60%」

函数& 会话规模

冷启动加速

平均 TCO 降低

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 016

• 会话亲和与隔离/ Sandbox 实例动态挂载

会话亲和&会话隔离

Sandbox 实例动态挂载

会话亲和（MCP 场景强诉求）

传统架构的问题

同一用户请求始终路由至同一实例

多租户数据共享有安全风险

避免 SessionlD 丢失和工具调用失败

无法满足每个实例路径不同的需求

支持 MCP SSE/ Streamable HTTP/

挂载存储路径变化不确定

Header Field / Cookie 四种亲和类型

Serverless AI 解决方案

会话隔离（Sandbox 场景强诉求）

会话粒度存储粘性

一个 Session 独占一个函数实例

会话与特定租户存储子目录强绑定

避免不同请求间的数据残留和泄漏

层次化纵深防御体系

POSIX标准多租存储安全实践框架

mount /user-id/session-id 独占目录

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 017

，上下文工程：记忆系统丿知识库/MCP＆ Skills

Memory 系统

知识库/ RAG

MCP & Skills

•情景记忆/ 语义记忆丿技能记忆

• 插拔式支持企业知识库

• MCP + Function Call 双协议

• 全量会话记忆与会话缓存

• 拥抱开源 RAGFlow

• 海量工具一键集成

• 记忆可追溯、可定义、可优化

•上下文模式+工具模式

• AI 自动生成工具代码

• 采用开源 MemO，数据不出域

• 跨平台知识检索

• Skills 支持 Sandbox 和动态挂载

可插拔设计：生态开放、灵活组装——一键托管或绑定已有部署（VPC/IDC），企业数据不出域

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 018

• 全链路可观测与 Agent 评估

AI 全栈统一监控

端到端链路追踪

基于 Prometheus 构建AI 全栈监控大盘

基于 OpenTelemetry Trace 全链路追踪

模型性能分析

用户终端一网关一模型应用

Token 成本分析

一模型服务 一外部工具

GPU 资源异动分析

Agent 质量评估

数据飞轮持续提升

在线评估：运行时 Trace 自动评估

反馈评估 数据标注一测试集回放

离线评估：Trace 生成数据集对比实验

一模型微调->持续迭代

评估指标：LLM / Tool / Token/Score

清晰捕捉变更对质量的影响

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 019

•模型运行时与 AI Gateway 治理

Serverless 模型运行时

Al Gateway 治理能力

开箱即用的模型部署

统一模型代理

内置 VLLM /SGLang/ Ollama/LMDeploy

支持30+模型服务提供商直连

最快 30s 转化为 OpenAI 兼容 API

通义千问 / DeepSeek / OpenAI / Gemini

2万+热门模型一键托管到云上环境

企业级治理

弹性交付

多模型负载均衡与 Fallback

DevPod 二次开发

并发控制与限流

弹性交付 GPU，低峰缩 0

响应缓存与超时控制

CPU/GPU/MEM 算力解耦

统一凭证管理

1/N GPU 卡灵活切分

Token 用量统一管理

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 020

①5

AgentRun 企业级实战

FunClaw 一基于 AgentRun 打造企业级

Agentic Al助手方案

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 021

企业级 Agentic Al 整体方案架构

FunClaw 企业级 Agentic Al 助手平合

用户交互

超级 Agent

多渠道接入

全场景能力

智能中枢/任务编排

钉钉/书 /企微/Webul

对话 /编程/PPT / 自动化

FunAgent 企业级 Agent 组装工厂与运营中台

业务用户

生态广场

低码构建

知识中枢

双模管理

Agent / 模型 / 工具/

Agent 创建＋提示词工程

知识库/ 记忆/ 工具 / 技

管理员后台＋用户界面

Promnt

AgentRun Agentic AI硬核引擎与运行底座

AI

Intra

运行内核

资产中心

数据智能

可观测性

Agent Runtime + Sandbox

模板/ Prompt/工具

知识库/记忆/模型服务

全链路 Trace + 监控大盘

FunClaw 是 AgentRun 团队自研并实战验证的企业级方案

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 022

FunClaw 平台架构图

FunClaw Architecture Diagram

① Access Layer（接入层）

员工在企业 IM / WebUl发

钉钉

飞书

企微

自建客户端

消息，FunClaw 调动工具

（or WebUl）

做完事情。

② Core Platform Layer

（核心层）

2 员工端

V 管控端

FunClaw 核心平台

Sandbox 环境托管 OpenClaw

统一鉴权与权限管控

资源配额管理

成本与监控

基于企业 IAM 进行统一

对企业资源、Model、Token

提供整体的成本管理和资

调用

Agent

业务 Agent（多个）

企

鉴权及权限管控

及 Agent 进行配额管理

源消耗监控图

运行环境

处理特定业务流程

IAM对接

Agent 配额配置

Token使用趋势

控制

现有IAM

账号管理

Model通道配置

费用报告

角色授权

Token管理

操作记录/审计

超级 Agent（Super Agent）

作为全场景 Al Agent 核心入口

③ External Services Layer

（外部服务层）

模型网关

技能枢纽

记忆分级与管理

员工通模型通道，FunClaw 调其模型

管理对接 Skill Hub，为 FunClaw 配 Skill

为超级/业务 Agent 提供长期、短期记忆。

为FunClaw 提供必要的

外部能力对接

S

企业自建 Skill库

通义千问

DeepSeek

ChatGPT 其他大大模型

External Skill Hub

核心记忆/短期记忆 核心记忆/长期记忆

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 023

• 超级 Agent：智能中枢与能力生态

超级 Agent 作为统一智能中枢，以自然语言为入口完成任务理解、拆解、编排与执行。

智能分发与任务编排

能力生态整合管理

• 具备自然语言理解和意图识别能力

• 支持创建自定义 Agent，连接万种能力

• 将复杂需求智能分解力多个子任务

• 注册接入外部平台 Agent 和工具

• 自动选择最合适的 Agent或工具执行

• 构建个性化能力生态系统

•从对话到 PPT 制作，统一入口完成

• 可视化统一管理所有能力资源

•实现真正的一站式AI 服务体验

• 打破平台壁垒，让 Al能力形成协同效应

两种交互模式：简单任务直接响应；复杂任务进入多 Agent 协作，由 Manager 拆解、Worker 执行、系统汇总。

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 024

FunClaw 企业级部署与安全隔离

一键部署安全加固方案

FC Sandbox 自定义部署

• 开源一致体验，资源用量可预估

• MicroVM 级别运行环境隔离

。 Serverless 隔离运行环境，支持大规模弹性扩展

• 会话隔离：一会话一实例

• 中心化 AI 网关避免 API Key泄露

•动态挂载独立存储，结束自动清零

• 全链路日志审计，HTTPS 加密访问

• VPC 安全组＋网络 ACL 白名单

运行隔离

网络隔离

存储隔离

权限隔离

会话隔离

五重安全防线：每个会话独享函数实例，任务结束即销毁，零残留

企业级管理：SSO集成/ 组织权限/资产中心/灰度发布/全链路审计合规

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 025

•

FunClaw 一键部署架构与弹性计费

基于阿里云 Serverless 构建完整部署链路，可一键拉起云端 FunClaw 实例。

模型支持：智谱 GLM-5 / 千问 Qwen3.5-Max / DeepSeek 等主流基座模型

弹性计费模式

安全加固特性

NAS/OSS 文件系统

。活跃计费：CPU 利用率高时正常计费

• HTTPS 访问加密

• 静态角色描述文件（SOUL.md）

• 闲置计费：CPU 低负载时自动降本

• 黑白名单权限隔离

• 每日记忆文件+Skills 文件

•日间扩容/夜间缩容，自动伸缩

• SLB统一入口监听

• 记忆可编辑/抽取/复用

•资源用量可预估，统一出账

• 全链路SLS日志审计

• 快速上传导入多种 SKis

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 026

？

Agent Infra 的

核心挑战与设计原则

从开发者痛点到 Harness Engineering 最佳实

践

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 027

•Harness 设计原则：信息层 ——精准比求全更重要

Trick 1：渐进式披露

Trick 2: Tools 越少而精越好

把信息做成分层加载系统

Agent 的强大不在于工具箱里有多少把扳手

Level 1: CLAUDE.md 一元规则入口

Claude Code 约20 个工具，仍在审视是否需要

Level 2:SKILL.md —按需调用能力包

Vercel 精简工具后速度和可靠性显著提升

Level 3：参考文件/脚本一完成任务的细节

Trick 3: Context Window 甜蜜区间

Trick 4: Subagent 做 Context 隔离

上下文利用率超过阈值后性能开始下降

复杂任务分配给独立 subagent

Opus 4.6 长上下文维持七成检索命中率

每个 subagent 在更小更干净的 context中

顶级工程师保持 context 利用率在60%以下

主线程只做调度和收口 （Context Firewall）

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 028

Harness 设计原则：执行层与反馈层

执行层：给 Agent一套执行规划

反馈层：Agent 的复利飞轮

Research Plan Execute - Verify

"'Anytime you find an agent makes a mistake，

每个阶段单独 session，单独context

you take the time to engineer a solution such

that the agent never makes that mistake again."

"'Enter plan mode for ANY non-trivial task"

—— Mitchell Hashimoto

"lf something goes sideways, STOP and

re-plan immediately — don't keep pushing."

构建反馈闭环：

-— Claude Code 负责人 Boris Cherny

•有效验证手段使产出质量提升2-3倍

• 自动迭代模式：做一验一不过一继续

人最该介人的地方：事前规划而非事后审核

• 每次失败都让系统永久变好

一行糟糕的计划，长出几百行糟糕的代码

Autoresearch 闭环思路：

提出idea一实验一观察 保留/丟弃一循环

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 029

Multi-Agent 协同：从 Vibe Coding 到 Coordination Engineering

Agent 层级与

Harness Engineering

从L1 到L4

组织架构

基础设施需求

的演进

• 放弃"一台机器”上持续聊天模式

• Sandbox：安全隔离执行环境

• L1 Prompt Engineering

• 角色划分：Dev/ Architect/

• Team Memory：团队记忆系统

• L2 Context Engineering

Memory Keeper

• Agent Dropbox： 协作文件共享

• L3 Harness Engineering

• Ground Rules 注人所有 Agent

•Agent 邮箱：独立通信系统

• L4 Coordination Engineering

•CI/CD：完整回归测试环境

• 最终：Intention Engineering

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 030

未来展望

与总结

Al Agent Infra 的下一步

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 031

• AI Agent 基础设施的未来趋势

从 Harness 到 Coordination

Agent 原生存储与数据范式

L1 问答质量一L2认知边界 _3 执行闭环 _4组织协同

文件系统+SQL 的融合（Agent-Native Storage）

Multi-Agent Networks 成为下一代产品形态

Agent需要的不只是数据库，而是“理解一切”的存储平台

类似"Agent 协作版飞书”：监工看板＋协作IM 平台

支持百亿级 Agent 租户的存储云平台

模型与 Harness 深度耦合

企业级 Agent 基础设施平合

模型公司端到端做 Harness，应用公司也开始训模型

Serverless +安全隔离+开源开放＋全链路可观测

Continuous Learning：基于自己的 Harness 和业务数据做开源模型 RL

无代码到高代码平滑漢进，CI/CD 天然集成

"每行代码的保质期可能只有2个月"

阿里云 AgentRun：做企业级 Agent 的最佳运行底座

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 032

•

总结：Al Agent 基础设施的核心要点

行业趋势

• AI 工程方法持续演进：Prompt Context Harness Engineering

• 核心竞争力转向系统层：Harness=环境＋工具＋记忆＋评估

•Multi-Agent 协同从实验走向生产，需要完善基础设施

AgentRun 的答案

• Serverless 基础设施：零运维、极致弹性、0到百万级并发

•企业级 Runtime：高性能 Sandbox、会话亲和/隔离、动态存储挂载

• 开源开放：兼容主流框架、数据不出域、平滑演进

•全链路可观测：Agent 不再是黑盒，数据飞轮持续提升效果

一句话总结

大模型正在重新定义软件

AgentRun 让企业级 Agent 跑得更快、更稳、更安全。

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 033

InfoQ 极客传媒

QCon

全球软件开发大会

THANKS

大模型正在重新定义软件

Large Language Model Is Redefining The Software

## Page 034

上

探索 AI 应用边界

AiCon

Explore the limits of Al applications

全球人工智能开发与应用大会

2026年6月26-27日/上海张江科学会堂

专题：世界模型与多模态智能突破

专题：Agent 系统架构与工程化实践

专题出品人：朱政

专题出品人：鲁浩楠

极佳视界/联合创始人& 首席科学家

OPPO /大模型算法员责人

专题：AI 原生数据工程

专题：Agent 安全、评测与可信治理

专题出品人：王彦辉

专题出品人：马传雷（岳立）

火山引擎 /数智平台产品总监

支付宝 /业务风险技术部员责人

专题：Agent 数据、记忆与运行时

专题：企业级研发体系的重构

基础设施

专题出品人：沈浪

专题出品人：邓亚峰

快手 / 研发效能员责人

EverMind/ CEO
