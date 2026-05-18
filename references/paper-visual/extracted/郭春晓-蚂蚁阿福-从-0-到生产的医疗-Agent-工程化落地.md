# 郭春晓-蚂蚁阿福-从-0-到生产的医疗-Agent-工程化落地

> Page-by-page visual information extraction from rendered page images. Text below preserves the visible text recognized on each page; pages with diagrams include every OCR-readable label captured from the image.

## Page 001

InfoO 极客传媒

QCon

全球软件开发大会

蚂蚁阿福 Agent：

医疗研

发范式与实践

郭晓

蚂蚁集团 医疗工程引擎

## Page 002

极客邦科技 2026 年会议规划

aCor

促进软件开发及相关领域知识与创新的传播

06月9上海

281000人

08月 9深圳

88 1000人

AiCon

•Al Infra 系统工程

AiCon

•Agentic Al

•多 Agent 协作与实践

•轻量化与高效推理

全球人工智能开发与应用大会

多模态融合

•多模态应用

全球人工智能开发与应用大会

•模型训练与推理创新

•Al + IoT 场景实践

会议时间：6月26-27日

数据平台与特征服务

会议时间：8月21-22日）

•Al工业化落地

010月9上海

283 1200人

◎12月？北京

2 1000人

：AlAgent

Qcon

•Vibe Coding

AiCon

•大模型架构创新

智能可观测

•多模态 AI 产业融合

全球软件开发大会

推理基建

全球人工智能开发与应用大会

•具身智能

模型攻防

Al for Science

会议时间：10月22-24日

•Al x 创造力

会议时间：12月18-19日

•大模型安全

## Page 003

InfoQ 极客传媒

QCon

全球软件开发大会

蚂蚁阿福 Agent 的痛点、挑

01

战

02

Agent 研发范式的北极星指标与技术体系

目录

Agent上下文的挑战

04

从 RAG 到Agentic RAG 的实战

05

医疗记忆

06

训推优化

## Page 004

蚂蚁阿福Agent的痛点与挑战

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 005

• 医疗 Agent 的核心挑战

专业性要求极高

非确定性挑战

医疗领域错误容忍度极低，一个错误回答可能影响患者健康

大模型复读机、数值计算错误、异常处理

决策

需要严格遵循循证医学原则

长期记忆缺失

风控合规

每位患者的健康状况、病史、用药记录各不相同

患者隐私保护、数据安全合规要求严格

需要精准的个性化健康档案支撑

防蒸馏攻击、风险防控不可或缺

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 006

• Agent 研发范式与传统研发范式的区别

传统业务研发

搜推研发范式

Agent 研发范式

迭代频率，双周

迭代频率，周1~2次

迭代频率：天级别

•需求一设计一开发一测试一上线

•数据驱动，A/B Test 验证

•评测驱动 （EBDD），Benchmark

牵引

• 代码驱动，人工 QA 验证

•特征工程+模型训练

• Prompt+RAG +模型+工具协

•变更周期长，迭代速度受限

，线上指标牵引优化方向

同迭代

• 适合确定性需求场景

•适合效果可量化的场景

• Badcase 驱动的快速闭环

• harness Al 人均提效30%~10x

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 007

Agent 研发范式北极星指标

与技术体系

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 008

整体技术架构

客户端

H5、native hybrid

GRPC、RTC

应用层

智篇体编排

用户增长

机构接入

运营后合

Agent层（Intelligent Agent Layer）

Agent-RAG

Agent-Mem

Agent-迭代范式

智能体协作

Index

短期记忆

rubric

多智能体会诊

迭代效率

医学桖豖

长期记忆

badcase

多智能苓研究

风险防控

MAS

场釁压编

debug平台

Al infra & 模型

模型

Agent RL

LLM

LVM

Agentic model

Agent env

ToolEnv

数据

权威库

标准库

post-train数据

指阐

书籍

网页

病症药术险

医生、医院

复杂搜素问級

多轮问诊数掘

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 009

• 评测体系的建设 EBDD

Evaluation And Badcase Driven Development

以评测为核心驱动力的研发范式，通过系统化的 Benchmark建设和 Badcase 分析，

实现从「代码驱动」到「评测驱动」的范式转变，建立可量化、可追踪、可闭环的研发流程。

E - Evaluation

B- Badcase

D- Driven

D - Development

Benchmark

体验优化

流水线

生产化

评测体系

•基于 Rubric 的评测方式

• 多种反馈渠道

•评测一定位一修复一验证

•评测能力线上化

闭环

• 多正确答案场景覆盖

• 动态分拣

•A/B 实验与灰度验证

•快速迭代，自动发现天级

•自动化评测 ＋人工终审

* 核对与巡检

别交付

•监控告警与持续优化

：70% 场景覆盖，X万评

测集

•评测耗时从1-2 天降至小

时级

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 010

• 评测和 Badcase 驱动的研发范式

Benchmark + Badcase 双循环驱动

Benchmark

Badcase

根因

方案

效果

评测

发现

分析

优化

验证

。 持续循环选代，不断提升模型与系统能力

小时级

评测耗时

（原1-2天）

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 011

•评测可靠性

可靠评测=稳定数据集＋足够样本量＋可信评审者

数据集是否稳定

样本量够不够

裁判靠不靠谱

评测集二义性，以及是否

先定义最小有效提升，再

多次打分不一致，是有效

有区分度

谈样本量。

提升，还是裁判波动。

判断

判断

想看更小提升，成本会陡

判断

区间越宽，数据越不稳。

增。

多次一致性（变异系数）

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 012

12

Agent上下文挑战

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 013

• 医疗上下文的挑战

上下文工程

信息密度高

医疗对话涉及症状描述、检查结果，用药记录，既往病史等多维信息，

单次会话信息量还超一般对诘场景

多轮对话依赖

医疗问诊天然是多轮交互过程，需要精确追踪上下文中的关键实体（药品、

症状、指标）并保持语义一致性

上下文窗口有限

复杂病例可能涉及数十轮对话和大量参考资料，超出模型上下文窗口限制，

需要高效的压缩与检索策略

O

跨 Agent 共享

4

主子 Agent 架构下，上下文在不同 Agent 间传递时容易出现信息损失或污染，

需要设计合理的共享与隔离机制

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 014

• 长上下文的处理

上下文工程

关键信息抽取

•有限抽取策略：识别并保留诊断关键信息（主诉、症状、检查结果）

．人工确认机制：关键医疗信息需患者确认，避免误抽取

•结构化存储：将非结构化对话转为结构化健康档案

上下文压缩

•语义压缩：保留核心语义，去除冗余信息

•选择性传递：根据当前任务动态选择相关上下文片段

•渐进式摘要：长对话自动生成分段摘要

分层记忆机制

：短期记忆：当前会话内的即时上下文管理

•长期记忆：跨会话的患者健康档案与历史记录

．记忆融合：短期与长期记忆的动态检索与融合

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 015

• 主子 Agent 的上下文共享

上下文工程

问题与技术挑战

• 上下文有限：单 Agent 无法承载复杂医疗推理的全部上下文

• 上下文污染：不同子任务的上下文混合导致推理质量下降

• 长上下文指令遵循：超长上下文下模型对指令的遵循度下降

技术方案：单 Agent -多 Agent 架构升级

• 主 Agent负责任务分解与上下文调度

•子 Agent 专注特定领域（检索、诊断、用药推荐等）

•上下文路田：根据子任务类型选择性传递相关上下文

• 结果聚合：子 Agent 结果经主 Agent 融合后生成最终回答

业务成果：深度检索准确率 提升19%

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 016

04

从 RAG 到，

Agentic RAG 的实战

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 017

M RAG 到 Agent RAG 的实战

检索增强生成

27.5

25.5

25.0

技术挑战

19.0

• 医疗检索效果要求极高：药品类问题强依赖检索

14.0

• 医保类问题强依赖检索，且政策具有区域性和时效性

• 多跳 Query 处理：如「肝功能不好+发烧一能吃什么药一

怎么吃」

rcher-R1-328

03.search

技术方案

gemline.5pro.seaich

•Index 策略＋混合检索：结合稠密检索与稀疏检索

•融合医学专业性的 Agentic 检索框架

•问题合成：选稀有实体、模糊化、模型生成合成思路

AQ 问答准确率

•高质量轨迹合成：强模型生成轨迹。思维链重写

业界对抗第一

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 018

Agentic RAG 的架构与医疗询证检索

Agent 框架+循证医学检索

循证医学（Evidence-Based Medicine）思想融入 Agent 检索框架，

通过多阶段检索策略实现高精度医疗问答。

Stage l: Query 理解

Stage 2： 循证检索

Stage 3：证据融合

•意图识别与实体抽取

： 权威指南文献检索

• 多源证据排序与去重

• 多跳问题分解

• 药品说明书精确匹配

•证据等级评估

• 检索策略路由

• 医保政策区域化检索

• 结合推理生成回答

检索 Benchmark BRIGHT 取得 SOTA | 框架已开源| 发表论文一篇

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 019

05

记忆

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 020

• 医疗记忆的挑战与难点

从数据、记忆、决策到治理，医疗个性化的难点贯穿全链路

（用户数据管理复杂

乙〕数椐融合与理解难度高

• 长期信息与短期状态混杂

• 数据来源多且格式不统一

• 健康状态持续变化，信息容易过期

• 数据质量参差不齐

• 多轮对话中上下文容易漂移

信息沖突难以消解

3〕个性化决策与安全控制难平衡

4

效果评估与合规治理门槛高

• 何时调用个性化不易判断

• 效果难评估

• 高风险信息不能漏也不能乱用

• 结果需要可解释、可追溯

• 个性化越强，错误代价越高

• 隐私与合规要求高

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 021

记忆架构方案

Layer 1

输入与身份识别层

难点：多县份

用户输入

身份识别引擎

患者本人

家属/代理人

对话/问诊/报告

滋图＋角色＋权限

不同身份一独京记忆空间＋差异化权限边界＋隐私隔离

Layer 2

记忆处理层

记忆提取（LLM）

冲突裣測

置信度評估

高置信度一 入库

结构化医疗事实抽取

新汨记忆矛盾识别

医疗票实可信度打分

低置信度一确认

人工礴认

关键小实乳核

Layer3

记忆存储层

难点：长期记忆

难点：记忆退忘

会话记忆（Session）

扇例级记忆 （Case）

长期记忆 （Pronle）

遗忘策略引憼

TTL 衰减

记录当前会话的症状、意图

记录诊断结论、治疗方案

记录慢性病史、过敏史

短期记忆按时间自动过期

与临时推理中间状态

用药与检查检验结果

家族病史与用药偏好

合規洲除

用户撤回/GDPR/医疗法规

反馈回路

记忆更新

置信度淘汰

会浩结束后停动清筋

荷例关闭后安档

强化！修止

持久花，主动營理

低置傐度记忆定期清理

向董数据库

图效凞率

结构化存储

含井去爾＆ 丰动修正

矛盾记忆合井，错误记忆纠正

Layer 4

检索与应用层

语义裣繁

身份权限过滤

时效性排序

上下文組装

Agent 响应生成

向量相似度匹配

按身份载剪可见范国

近期优先＋衣減加积

动态 Context Packing

Grounded +个姓化

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 022

训推优化

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 023

• 推理优化

推理加速

TTFT （Time To First Token）

TPOT （Time Per Output Token）

Prompt 缓存：复用高频 Prompt的KV Cache

Continuous Batching：动态批处理请求

• Prefill 优化：分离 Prefill 与 Decode 阶段

Speculative Decoding：小模型预测+大模型验证

•模型量化：FP8/INT8 降低计算开销

• Speculative Decoding：长短分离

• 业务隔离：长短分离

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 024

Agent RL 性能优化方案

推理加速

Agent RL 训练架构挑战

Agent RL system

• Agent运行环境与训练耦合严重，工具 Env与训练环境不分离

hgontErgno

Mocel Trerer

•训练耗时长：1T 模型，单 step 43分钟

（sime. AReal voill

agsn:am

FsoP

• Rollout 1200s | Reward 600s | Reshard 800s

• 模型 Reward 达不到要求，需要升级 Reward 架构

2momd

优化方案

升级 Agent 训练架构

解耦运行环境与训练环境

model as reward

FP8 量化加速

Rollout 阶段从 1200s 降至1080s

半异步化训练

进一步降至 960s，减少等待开销

全球首个支持开源FP8训推方案

Reward Service 升级

Reward 计算从 600s 降至120s

全球首个支持开源QAT训练方案

社区代码优化

Reshard 从 800s 降至48s

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 025

InfoQ极客传媒

QCon

全球软件开发大会

THANKS

Al Agent 正在重新定义医疗

健康

Al Agent Is Redefining Healthcare

## Page 026

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

OPPO/大模型算法员责人

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
