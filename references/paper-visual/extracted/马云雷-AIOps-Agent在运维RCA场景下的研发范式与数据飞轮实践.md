# 马云雷-AIOps-Agent在运维RCA场景下的研发范式与数据飞轮实践

> Page-by-page visual information extraction from rendered page images. Text below preserves the visible text recognized on each page; pages with diagrams include every OCR-readable label captured from the image.

## Page 001

InfoO 极客传媒

QCon

全球软件开发大会

AlOps Agent在运维RCA场景的研发范式与

数据飞轮实践

马云雷

阿里云-云原生可观测-高级技术专家

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

01

AlOps 业务场景介绍

02

UModel：构建数字孪生的世界模型

03

Benchmark：建立进化的基线

目录

04

AgentLoop： 从运行时数据到 Agent 可靠性飞轮

## Page 004

AIOps业务场景介绍

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 005

• AlOps 发展历史和现状

AIOps核心需求

可观测

异常检测

故障诊断

自动修复

AIOps 1.0- 算法驱动时代（2018-

AIOps 2.0 - Agentic 系统化时代

2023）

（2023-

算法驱动时代：

• 核心方案：基于统计/ML算法/CNN模

Agentic 时代：

型

核心方案：Agentic 方式驱动探索与推理

• 典型能力：时序预测/异常检测/根因分

典型能力：异构数据自主理解、按需读取上下

析

文

• 致命痛点：泛化能力差（单点能力，换场

核心进化：从单点算法走向全局系统化工程

景即失效）

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 006

AIOps 能力表和进化路径

能力说明

场景标签

健康巡检

根因定位

L4辅助

具备规划和推理能力，能排查复杂问题，给出决策建议

决策

容量评估

变更分析

支持对多种可观测数据的解读和分析，从海量数

数据解读

趋势预测

L3深度洞察

据中提炼关键信息

模式分类

异常检测

噪声抑制

资源盘点

买体筛查

基于拓扑感知实体关系，支持根据实体检

L2拓扑感知

索关联的可观测数据集

依赖梳理

关联分析

支持使用自然语言对日志/时序库的

習能取数

数据审计

溯源取证

L1 基础查询

SQL/PromQL 生成及原始数据查询

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 007

自研 Agentic Al：多智能体协同与知识融合推理

基于大模型智能体协同与知识数据融合推理的智能运维

数字员工 & 多端支持

工具编排

多智能体与人机协作

AgentLoop持续迭代

权限& 配额

观测/评估/数据集/调优

Planning & Reasoning•任务规划

上下文

短期记忆

长期记忆

企业自建工具集

Memory•记忆

Tools，工具

故障预警

企业自建知识库

故障定位

故障诊断

工具集

工具集

工具集

LLM

数据

通用算子

可观测算子

云原生知识库

工具集

工具集

工具集

运维大模型

模型压缩

模型增强

UModel统一数据模型

日志

指标

链路

事件

剖析

拓抄

acon

InfoQ极客传媒

全球软件开发大会

## Page 008

AI-Native 研发范式下的三类挑战与解法

挑战 1：上下文不完整 -> UModel

让 Agent 读到异构上下文：Log / Trace / Metric / 配

研发

测试

CI/CD.

发布

观测

置/拓扑/知识；

把碎片化数据统一为可检索、可推理的世界模型。

传统研发范式

路径确定

挑战 2：质量不可度量-> Benchmark

测试覆盖率可以做到足够高

建立可测、可复现、可对比的任务与指标；

线上SLA相对有保障

用离线评测和在线观测持续衡量真实质量。

研发

离线评测

CI/CD

发布

观测

挑战 3：迭代不可持续 -> AgentLoop

让线上Case、Trace、反馈持续回流；

数据集＋

在线评测

沉淀高质量数据集，驱动上下文、模型与 Agent持续优

Al-Native研发范式

上下文获取的不确定性：

模型结果的不确定性：

• 异构数据的理解难度

• 输出非确定、难以穷尽验证

• 需要按需读取

• 需要持续评测与回归

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 009

UModel：构建数字孪生的世界模型

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 010

UModel：解决上下文问题

走向 Production 的第一步，不是追更大的模型，而是把复杂的云原生世界描述清楚。

真实痛点：数据孤岛与语义缺失

拓扑盲区：日志、指标、链路彼此割袭，Agent难以理解实体关系。

分析

决策

语义缺失：格式和系统常识不统一，模型容易在复杂诊断中“脑

补”。

采集

行动

破局之道：构建世界模型（UModel）

把日志、指标、链路、拓扑、变更、配置统一到同一套语义与格式。

从“看单点数据”变成“懂统一世界”，支撑诊断、影响分析、容量

评估。

核心价值：可复用的 Agent / Benchmark 底

壓系定义：实体拓扑给模型“导航仪”

UModel

语义丰富：标准化指标和日志语义，降低 Agent 理解门槛。

数据

知识

火 行动

UModel 是AlOps 的“底座中的底座”：数据、知识、行动进入同一套模

指标

事件

排查手册

FAQ

降级 加黑 回滚

日志

链路 CMDB

型，Agent 和 Benchmark 才有复用基础。

模版 模型

告警规则

开发 故障注入扩容

Profiling

交易 审计

黄金指标 Dashboard

执行命令 缩容

攻击 访问 消息

帮助文档 检测脚本

发布 预案执行 调度

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 011

可观测世界模型UModel 应用示例

查看关联指标

查看关联事件

操作日志

调用链

Deploy指标

变更事件

LogStore

问题根因

LogStore

Pod指标

MetricStore

EventStore

MetricStore

查看详细调用链

发布人

K8s

CI/CD

K8s

Deploy

集群

JOD

服务

K8s

实例

Pod

CI/CD 技能

服务

K8s

Code Repo

APM 技能

kubectl 工具

Node

Jira 工具集

K8s 技能

集

数据库

MySQL指标

MetricStore

ECS

ENI

MySQL

怀疑&论证

DB错误

业务

LogStore

分析报错

对象

Redis

ECS指标

ENI指标

MetricStore

MetricStore

Redis指标

业务日志

业务指标

MetricStore

LogStore

MetricStore

主机事件

DBA 技能

ECS 技能

查看关联日志

EventStore

Kubectl 工具

K8s 技能

Redis访问日志

集

DBA 工具集

L0gStore

InfoQ

云助手 工具集

全球软件开发大会

## Page 012

Benchmark： 建立进化的基线

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 013

为什么做 Benchmark:Agent 质量没有基线，就没有工程化迭代

RCA 场景不是单题问答，而是多步诊断链路；没有可复现基线，每次优化都很难判断真实收益。

传统优化的问题

Benchmark 带来的基线

反馈慢

真实任务

上线后依赖客户反馈或人工排查，问题发现慢，噪声也大。

把复杂拓扑、脏数据、多类故障、多层 Ground Truth，沉淀成可

复现 Case。

归因难

统一指标

改 Prompt、工具、策略之后，不知道影响范围，也不知道是哪一

围绕检测、定位、证据、行动、验证建立统一度量，而不只看最终

步起作用。

答案。

回归缺失

持续回归

修好一个 Bad Case，可能退化另一类Case；没有稳定回归集，很

每次改动都能可对比、可复现、可追责，把优化从感觉变成数据。

难规模化迭代。

Benchmark的本质不是“打分”，而是把不可控的线上 RCA 经验转成可复现、可对比、可回归的研发反馈。

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 014

怎么做 Benchmark：从 Case 到评估闭环

把线上失败、仿真故障和专家经验统一成任务，再用自动执行、智能评分和研发闭环持续驱动迭代。

EVIDENGE

J

统一任务

這 一眼看僅的涂双

25许佔演理（敗提京旧其結果

Case 题库 / 故障注入/Ground Truth

BE-Rise /比鲁斯

UModel 对齐实体、关系与数据语义

可观测 Vibeops评测

仁 產以T体雞限 （A TicS JORN）

生MB片

2

自动执行

受控上下文与工具集

你可以这利用.3期；

•E26日点：在「我据售深估，密用别。自武产出 1racai 与评体结果

自动运行 Agent，捕获 Trace / Trajectory

•着板成湯：在「奢板」技兴目，性能、Tokcn、工員燒必观襄整体效果与追化风险。

一城业坦板：糯论、关组食盐能畫、＆选过验激站。准难复。三月10、详出福地*丝。

3

智能评分

规则评估根因、证据、动作是否命中

& 或据期汗估（E2E）

Q 高线评估（工作台）

LLM-as-a-Judge评估推理质量

選入数照銀评結

核注婚出。

从 TO0k全凤經會

4

研发闭环

李批量评估

着板

接入CI/CD、发布门禁、失败建单

志入批橄躁值

打开看板

回流数据集，进入 AgentLoop

e 数据果管理

品 环境管現

雙得用泉与数额緒，指次 EXE 伊此每沒妇的號入，

益 以行F 与的A起際《期于 2E幾行募说擇与选貝参粉）。

做 Benchmark 不是建一个静态榜单，而是让每次线上失败都能变成下一轮可验证的改进。

Con

InfoQ 极客传媒

全球软件开发大会

## Page 015

）A

AgentLoop： 在线持续迭代调优

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 016

AgentLoop基于运行时数据的全链路数据飞轮

在线数据飞轮：

全栈可观测 语义可观测

数据流水线

RL 训练

在线/协同进化

Benchmark 的瓶颈：

•

数据是静态的

•，

无法覆盖线上的所有

观测

case

人工打标/加入数据集

运行时调优的三个方向：

去重

清洗

分析

DataSet

RL

•T

训模型

Trace

人工打标/加入数据集

调试Agent

采集

•

上下文自动调优

Agent

Metric

评估

LogStore

Log

具体任务：

• 观测实际运行的Case

收集 Good/Bad Case

回测

•

积累数据集

评估

• 反馈调优

部署

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 017

•

构建 Agentic 观测底座：从全栈数据采集到高维语义洞察

全栈可观测

采集

观测

纵向打通：覆盖“算力-模型-

高质量接入：全面拥抱开源与

视角跃迁：从系统监控到 AI开

应用”的全栈感知

低开销上报

发者 Debug 工作台

•laaS & CaaS： 深度覆盖 GPU、

•统一标准：深度融合高质量接入：

• 兼容传统：完整保留传统的微服务

全面拥抱开源与低开销上报

调用关系与基础资源视图。

RDMA 网络、CPFS 存储等核

OpenTelemetry协议，

统一Log

•面向 AI应用的全新语义视图：

心算力指标与容器状态

/ Trace / Metric 数据语义。

•Session：

完整还原用户与

•PaaS & MaaS：纳管大模型

• 无侵入探针：面向大模型量身定

Agent 的多轮对话历史。

推理/训练日志，及各核心 AI 组

制，无缝覆盖主流 Agent 框架，

•Topic：按主题区分会话。

件运行状态。

实现业务零代码修改接入。

• Semantic Trace： 追踪长周期

•极致传输：开源LoongCollector

、异步复杂任务的执行状态。

• APP：深入 Agent 业务逻辑，

高性能边缘采集，支持断点续传，

•Context： 深度解构大模型

实现应用侧多轮交互与工具调用

保障海量高并发日志的稳定上报。

Prompt & Response 及消耗细节。

的全链路追踪。

精准还原 RAG 检索结果与 Tool Use

的实时上下文。

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 018

基于向量的语义分析能力：从指标观测到语义观测

LLM 应用的关键信息在 Prompt / Response / Trajectory 中；语义分析要同时解决“看得懂”和“大规模成本可控”。

为什么：观测对象变了

怎么做：向量化分析链路

工程挑战：成本和吞吐

Chunkn （tokenz

batch「Embeddi

Embedding 是语义可观测的核心成本，

从指标到语义

n9

规模上来后，瓶颈会从算法变成吞吐和单

传统指标能看到数量和耗时，LLM 日志

的核心信息在长文本语义里。

向量索引/混合检索

GPU 批处理：打满负载

从单点到主题

同类问题需要语义搜索和聚类，才能发现

車复主题与共性失败。

面向两个核心任务

成本

规模

语义搜索

向量聚类

0.01/M

日均1万亿

从排查到闭环

TopK / 阈值

主题 / 相似 Case

token

token

语义标签、王题簇和相似 Case，会进入

云续数据集与 Benchmark。

语义可观测的难点不是“能不能向量化”，而是在生产规模下把成本打下来。

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 019

语义可观测：开发者视角的Trace

react step（Span数：72）

大烤型

调用树

链路图

时序线

请求时间：2026-03-25 19:19：.

耗时：8m50s

状态：

• Success

570593

田

Span名

调用次数1

◎

INTERNAL

72

Trcact20p

• react step 100%6

全部

大模型

reactSep

753

python

rcact stop

201

swe-agent

python

2

$.83

702:27 ma

2-

react step

10.27

：swe-agent

python

e rcac:sep

2-

12.95

Python

微服务视角

Agent 视角

重复 step 折叠

传统 Trace：

LLM 应用的数据特征：

会话视图：关注用户角度的交互记录

• 关注微服务视角

•

主要信息在模型的输入输出中

主题视图：关注同一主题的交互记录

•

关注组件调用关系

长文本富含语义信息

链路图：关注Agent的运行step和调用链路

。

关注延时等结构化信息

。

关注Agent的执行轨迹

上下文视图：关注模型输入输出的拆解和映射

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 020

• 从Trace到Trajectory：

以标准化信息获得洞见

Step 1

State： 已接到任务，但尚未验证标准输入。

Action读取 /app/data 并搜索 /app/data/t.jison®

Observation: /app/data 为空，且没有现成输入文件。

Transition：从*默认输入存在"转到*标淮输入缺失”

传统 Trace：

2.

Step 2

• 关注调用关系

State： 标准输入缺失。

Action：读取/app根目录。

• 有LLM调用、工具调用、截图等

Observation：发现需要改从环境目录找信息。

Transition：从”数据缺失”转到*开始全局探测环境鉴

Trajectory：

3. Step 3

State： 需要确定环境目录内容。

• 对 Agent 每一轮的信息进行标准化

Action：读取 /app/environment。

标准化 MDP （State,CoT,Action,Observe）

Observation：确认存在 environment/data

Transition：从”探测根目录"转到“聚焦环境数据区”。

• 关注轮次内的信息流动

4.Step 4

• 关注轮次间的状态变化

State：知道环境目录存在，但不知道数据文件。

Action： 搜系/app/environment/**/*.json。

• 标准化信息辅助 debug/后训练

Observation： 找到 AFM模板相关json文件。

Transition 从”未知输入替代源”转到*有可解析模板源"。

5.

Step 5

State：已定位环境数据目录，

Action：陕取/app/envi.ronment/data。

RL

Observation目录中有模板、参数文件、架构图。

Transition：从”找到路径”转到”确认素材集合”。

Trace

MDP

6.

SStep 6

State：需要从环境数据中提取网络结构。

Debug

Action：读取 metadata.json、azuredeploy.json。

azuredeploy.parametens.Json。

Observation：得到双 hub多VNET、hub ASN 65515、区域、地址空间等信息。

Transition： 从*知道有模板“转到 知道足以构造一个抽象 BGP 问题实例”。

QCon

无论for Human，还是for Agent，标准化都有利于降低熵

InfoQ 极客传媒

全球软件开发大会

## Page 021

构建高质量数据集：把运行时数据变成可训练资产

数据集不是日志归档，而是 AgentLoop 中用于回测、训练和上下文优化的核心资产。

从运行时数据到数据资产

Al Agent 数据清洗

多样性采样

生成质量评估

自动标注分类

凶躍任炎

1

标准化输入

戤据增强合成

鐒到蝪全波稆

OT-AI Span-LLM 数掘组装

OT-AI Trace 级别数据组装

Trace / Trajectory / Metric/ Log

Good/Bad Case / 人工反馈

S肆任多

清洗与标注

OT-AI Session 级别数据組装

OT-AI LLM 调用质量分析

OT-AI Trace 数話治理

OT-AI Session 深度洞察

2

投 wisian id 縣合多轮 Trate；F出與製会请赏授样

去重、过滤、质量评估

计，確盛 Prompt寵皮多维康分析

+墩建，溪别海数据泡增全诞路

减子文双舰计，確丝鸡会话数据给理与指强

自动标注＋人工复核

创建任务

模饭详惯

创建任务

SWE-Bench A： 轨迹数据组装

肉烟徽扶

SWE-Bench B: SFT 训练数据生

SWE-Bench C：執速质量評估

SWE-Bench D：工具使用模式挖

3

沉淀高质量样本

搖atep 极顾给日忠清洗，袁腫，烟裝游或实Q完整的

成靓质團评分和任妥分典标法，生威深估数据黨用于R

機竅 Agent 工馬我洞错路那使用报三，按摄式请义察

评估*高清面發叔路济，生成 SFT 請以数部第

类，生成工具膜路板注数部集用于 Tool Jse 专碳武虾

RL 数据集 / Benchmark 回归集

瑍粄洋犢

凶退际多

凶褪纭多

鵛建任务

上下文召回样本/黄金轨迹

数据集质量决定后续 RL、回测评估和上下文召回的上限。

运行时数据

标准化轨迹

高质量样本

回测/RL/召回优化

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 022

流水线核心挑战和方案：漏斗式降低大模型调用量

核心原则：低成本算子前置，只把高价值和高不确定样本送入昂贵模型与人工环节。

落地系统

从全量运行时数据到高质量数据集

酒入 Logstore 项目

原始运行数据

Trace / Log / Metric / Feedback

输入日志库

全量

精确去重/模板去重

先过滤重复样本和稳定模板

CPU

宇段投影

数琚转换

宇段投能：选择或乘命名宇段

采样 /近似去重

控制进入后续链路的数据规模

CPU

精确去重

数紹清洗

精确去重：基于指定宇段精路匹..

小模型预筛/ 规则评估 低成本判断质量、主题和风险

小模型

prompt 不館为空

大模型评估/

高价值/高不确定样本

大模型

Agentic 标注

LLM调用

AI 处理

LLM 週用：按 Prompt 模板演

人工复核 关键样本专家确认

人工

請箱入教据集名称

59 输出数据集

输出：高质量数据集/ Benchmark 回归集 /RL 样本

降本来自顺序：先去重和采样，再小模型筛选，最后才进入大模型与人工。

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 023

个返回

A一站式 RL 训练（dataset.salL.dagnosle.

RL训练解决方案

以数据集至RL训续的完整数据通路：数据加选 一预览验证 训练配置 FC部署 一領启动

日 数据筛选

数据预览

° 训练配置

（日）FC部

二代码生成

RL 设计：

寧 基础配置

區 调探参数

模聖参数

PPO配置

交互配置

1. 一键对接数据集

PPO算法说明

2. Rollout,Train 无状态API化，

Proximal Policy Optimization是一种稳定的策略梯度算法，通过限制策略更新福度来保证训练稳定性

采用池化GPU

算法类型

Agent Loop

优势估计器 ③；

GRPO

Rollout采样数 ◎：

3. Reward沙箱化运行

4. 客户端负责整合训练流程

PpO微批次大小 ②：

动态批次大小⑥：

GPU最大Token长皮

1：

8192

Client Side（本地/FC/ECS）

执行流程

Training Client （驱动训练循环：Sample Reward + Update • Weight Sync）

◎ sample（）

池化RL设计的优势：

Cliant Rollout

生成 responses

1.sample0

2.compute_reward0|

3.update（）

1. 多租户分时利用GPU，降低成本

② compute_reward0

2.GPU无状态，GPU/CPU任务解耦

阿里云FC

Client +Reward

数取 rewards

Rollout Server （：8780）

Reward Server （：8089）

Training Server （：8781）

• sample（）：

• 接收（prompt/response）

•update（）：

◎ update（）

生成模型喲应（只读权重）

•compute_reward（）：

汁算橯度井更新权重

Client + Training

返回数倘奖勋

更新崇系权服

L20/L4 X N

最存密縈熙

摆自定义

H20/A100 x N.

计源密集型

@ woight_synco|

权豐间步（発步｝

Training + Rollout

异步问抄权東

Trining-Rollout

QCon

C 循环

全球软件开发大会

## Page 024

•在线实时调优：Agent的在线进化

训模型

离线调优

两个趋势：

1. 模型能力越来越强

改代码

2. Agent架构标准化

数据集

仍存在的问题：

1. Agent在企业内场景

研发

运行

日志

仍面临工具和知识的

短板，需要探索和试

Skill

错

在线调优

2.企业内的数字员工缺

乏信息共享

用户提问

— 包含 图？

L YES -图片识别（1/N..N/N）•判断主题-进入对应主题路径

一 判断主题

步紧 状态

工具

參数

说明

F LogtaiL/采集 •read_file（logtail/overview.yamL）-...

— 告誉

- read_file（alert/overview.yamL） - read_aliyun_docx1-3

• 成功

read_file

logtail/overview.yaml

读取 Logtail 总览，合理

一 权限/RAM

- read_filelquery_analysis/overview-yaml + core.yamL）

× 文件不存在 read_file

Logtail/parameters-yaml

猪测路径，不存在

F K8s/密器

- read_file（query_analys1s + alert + sgl overview）

x 文件不存在 read_file

Logtail/performance-tuning.yaml

继续猜测，又不存在

F SPL

-read_file（spl/overview-yamL）- preview_Spl验证

• 成功

read file

core.yaml

退回读通用知识

— SQL查询

- read_file（query_analysis +sql overview）-sls_execute_5ql

× 404

read_aliyun_doc

•../sLs/togtail-performance-tuning-guide

开始猫 URL

其他

+ read_file（core yamL）-按需扩展

× 404

read_aliyun_doc

.•./sls/logtail-configuration-parameters

换个 Slug 继续猜

x 404

read_aliyun_doc

.../sls/adjust-logtail-parameters-for...

更长的 slug，还是猜

是香需要运维操作（查看配置/执行查询/诊断）？

成功

read_file

logtail/install-on-Linux.yamL

回到知识库找安装文档

L YES-load_tool- get_project/get_logstore/get_logtail_pipeline_config

× 404

read_aliyun_doc

.../sls/adjust-logtail-parameters-for-...（v2）

微调 URL 重试

•generate_S9LSLS_execute_59L

× 404

read_aliyun_doc

•../sls/Logtail-advanced-configuration

再换一个 slug

11

× 404

read_aliyun_doc

•••/sls/modify-logtail-configuration-file

冉换一个 slug

知识库信息是否充足？

12

× 404

read_aliyun_doc

•../sLs/logtail-configuration-file-reference

再换一个slug

YES-直接回答

13

× 404

read_aliyun_doc

.../sts/logtail-performance-optimization

再换一个 slug

L NO - read_aliyun_doCx1-3（≤3 次！）-回答

14

× 404

read_aliyun_doc

•../sls/troubleshoot-Logtail-collection-issues 最后一搏

15

• 成功

readfite

logtail/overview.yaml

重复读取（第1步已读过）

遇到 404/File-not-found？

16

成功

read_aliyun_doc

•./sls/select-a-network-type

终于找到一篇含参数的文档

一第1次-岩试1 次备选路径

|第2次-停止猜测，基于已有信息回答

［路，次婆不麻该到法这用

## Page 025

企业级数字员工的协同进化

AgentLoo

数字员工协同进化

p

Skill分发

数字员工的协同进化：

1. 黄金轨迹

2. 工具调用经验

数据采集

数据采集

数据采集

3. 数字员工 Agent共享信息

4. 权限管控

Agent

Agent

Agent

源码

pob

step

结果分析

tasks/citation-check

原始task统汁

原Stask

原始iob

14

全郃通过

token 下降 88.6%， step 下

降71.4%，成功率保持

优化后task统计

优化task

优化job

53427

全部通过

100%

lasks/dapt-intrusion-

原始task统汁

豆浴job

15 failed,22 passsed

成功率提升 29.7个百分点，

detection

沈化后task统计

优化task

优化job

4 tailed, 33 passed

tcken 仅上开3.9%

60%

原始task统计

原始task

晾始iob

19 failed, 29 passed

第一次优化 token 下降

34.9%，但成功率下降8.3个

优化后task统计

优化task

优化ipob

274920

23 falled,25 passed

百分点；第二次优化成动率提

升10.4个百分点.但 tokcn

+25.0pt

+23.0pt

优化局task统计

借鉴前两

借鉴的两次

518058

14 falled,34 passed

上升22.7%。

20%

+17.0pt

次执行优化 执行优化job

+10.0pt

task

3.0pt

0%

tasks-no-skills/data-to-d3

原始task统计

原始task

疏始iob

54280

2 failed, 6 passed, 7 errors

成功率提升46.7个百分点，

3.3%

errors 清 ，但token上升

成功率

2 falled, 13 passed

186.2%。

-20%

优化后task统计

优化task

优化ib

-20.0%

-29.2%

28.0%

推理步数

tasks-no skills/earthquake-

原始task统汁

原烩task

原始ob

232044

8 errors

token 下降4.1%，但成功率

-40%-

34 41.3%

olale-va cuiauon

8 errors

无提升，errors 无改善。

-41.7%

-43 8%

优化后task统计

优化task

优化job

222548

Token消耗

-60%

kasks-no-skills/software-

原始task统计

浣始task

晾始job

137575

7 Taled

成功率 升85.7个百分点。

dependency-audit

优化后task统计

优化task

优化job

77317

1mallec,6passed

token 下降 43.8%。

-80%

tasks/dialogue-parser（采用

原淤task统汁

原始tsk

源姶jb

2 failed,33 passed

成功率仅提升 2.9个百分点，

tasks/dapt-intrusion-

但 token上升 182.4%6，step

detection生成的prompt，测！

优化后task统计 优化task

优化iob

11allco.34 passed

上升 116.7%.

代码生成

数学淮理

文本总结

濏辑分析

雞莲任务

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 026

总结

UModel

Benchmark

AgentLoop

解决语义和上下文问题

建立质量基线

形成运行时数据轮

马赛克

统一日志、指标、链路、事

真实环境＋任务＋指标

Trace -> Trajectory->高

浙江 杭州

件、拓扒

可对比、可复现、可闭环

质量数据集

让 Agent 从“看数据” 到

从凭感觉优化到可量化迭代

漏斗式流水线降低模型调用

“懂世界"

成本

为 Benchmark 和 Agent

RL、在线进化、协同进化持

复用上下文

续优化

扫一扫上面的二维码图案，加我为朋友。

从统一世界模型，到可度量基线，再到可持续优化的 AIOps Agent 工程闭坏。

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 027

InfoQ 极客传媒

QCon

全球软件开发大会

THANKS

## Page 028

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
