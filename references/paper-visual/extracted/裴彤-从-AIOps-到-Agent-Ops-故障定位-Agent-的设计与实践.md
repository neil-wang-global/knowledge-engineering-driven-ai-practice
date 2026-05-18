# 裴彤-从-AIOps-到-Agent-Ops-故障定位-Agent-的设计与实践

- Source images: `references/paper-visual/images/裴彤-从-AIOps-到-Agent-Ops-故障定位-Agent-的设计与实践/`
- Processing mode: page-by-page visual information extraction (OCR-assisted; not a summary)
- Pages covered: 39

## Page 001

InfoQ 极客传媒

QCon

全球软件开发大会

从 AIOps 到 Agent Ops：

故障定位 Agent 的设计与实践

裴彤

快猫星云 AI 产品研发负责人

## Page 002

极客邦科技 2026年会议规划

促进软件开发及相关领域知识与创新的传播

◎6月？上海

2 1000人

0 8月9深圳

8 1000人

AiCon

•Al Infra 系統工程

AiCon

•Agentic AI

•多 Agent 协作与实践

•秷罼化与高效推理

全球人工智能开发与应用大会

*多榄态融合

*模型训练与推理创新

全球人工智能开发与应用大会

•多模态应用

•Al + IoT 场景实践

（会议时间：6月26-27日

•数据平台与祷征服务

会议时间：8月21-22日

•AI 工业化落地

010月9上海

R81200人

012月？北京

R81000人

Qcon

•Al Agent

•Vibe Coding

AiCon

•大模型架构创新

•智能可观測

*多模态 AI 产业融合

全球软件开发大会

•推理基珊

全球人工智能开发与应用大会

•具身智能

。模型攻防

•Al for Science

会议时间：10月22-24日

•Alx 创造力

会议时间：12月18-19日

•大模型安全

## Page 003

InfoQ 极客传媒

QCon

全球软件开发大会

01

从 AIOps 到 Agent Ops

02

设计思考与实现方案

目录

03

Flashcat Al Agent 的落地实践

04

可观测性智能化未来效果展望

## Page 004

从 AIOps 到 Agent Ops

Qcon

InfoQ 极客传媒

全球软件开发大会

## Page 005

M AIOps 到 AgentOps

Observable

Intelligent

Copilot

Agent

数据建设智能化

传统监控，可观

AIOps 时代

引入大模型的阶

以 Agent 为核

数据应用智能化

测性的起点

段

心的运维系统

Dashboard、告警、

异常检测、告警降

Copilot、AI 问答、

Agent、 Tool/Skill、

人工分析

噪、根因维度分析

Workflow 自动化

ReAct、Planning

系统交互智能化

Data for Human

Al assists Human

Human +AI 协同

Al takes actions

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 006

• Agent 如何与业务系统进行交互

数据接入与集成

Al 能查询数据是前提

•

Metric

Log

•

Trace

•

Event

• 基础设施

面向 Agent 的数据抽象

•

数据接进来+AI能有效利用

•

建设结构化知识图谱

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 007

Agent 如何理解业务系统

全局信息量太大，一个服务异常时，不知

缺少推理依据

道该分析哪些指标、日志，上下文爆炸

Agent

发现一个异常点，就认为是根因，甚至基于

放大幻觉问题

面临的问题

某些异常点过度归因，错误推断因果关系

证据不足时，无法明确给出结论，或给出一些

结论存在误导

“正确的废话”，结论似是而非，缺乏指导性

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 008

• Agent 如何理解业务系统

为什么需要知识图谱

仅有 Metrics / Logs / Traces 时

• 缺乏结构（不知道谁依赖谁）

Logs

Payment

Service

Metrics

Calls

• 缺乏语义（不知道服务是干什么的）

Order

Service

Depends

On

• 缺乏因果（不知道异常如何传播）

Propagates

Error

Calls

Traces

User

Depends On

Service

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 009

Agent 如何理解业务系统

知识图谱

属性

指标

Trace 元信息

日志元信息

事件

容量

SLO

（Attribute）

关系

（Relation）

调用关系（A B）

部署关系（pod node）

依赖关系（service 一 db）

实体

service

instance

pod

database

ma

job

（Entity）

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 010

Agent 如何理解业务系统

全局查看系统状态

快速收敛故障范围

“可观测”的

知识图谱

全面完成

快速下钻

巡检和隐患排查

分析故障根因

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 011

• Agent 智能化的目标效果

智能化目标效果

• 数据建设智能化：一句话创建知识图谱、监控视图

• 数据应用智能化：模型日常巡检、智能故障定位

create Monitoring

• 系统交互智能化：自然语言交互操作可观测系统

熱細

Analyze Problems

Daily Inspection/Patrol

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 012

Agent Ops 的数据闭环

数据生产：数据采集、接入

知识图谱：人机共建，Agent 驱动

3

2

数据应用：基于知识图谱进行故障定位

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 013

设计思考与实现方案

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 014

知识图谱的自动建设

知识图谱如何生成

数据治理没有捷径...

Garbage in garbage out

邑—

• 数据和知识将成为最重要的资产

四—

但可以利用 AI加速

接入 Metric 数据源->自动发现关键指标、实

体

• 接入日志源->自动关联实体和日志

• 接入事件源->自动关联实体和事件

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 015

知识图谱的自动建设

用规则约束数据

模型直接生成知识图谱

• 数据持续更新，Token 成本高

• 幻觉错误累加，数据逐渐不可用

• 可解释性差，治理难度高

Wasting

Amplifying

Introducing

Tokens

Uncertainty

Errors

Knowledge Graph

模型生成规则，规则生成数据

• 不描述具体的数据，而是描述数据的生成方式

Rules

Knowledge Graph

Periodic

Structured

• 实体规则：描述知识图谱的节点和属性

Rules/Schema

Execution

Data Output

• 下钻规则：描述知识图谱的依赖关系

• 模型发现规则，规则定期执行，更新知识图谱数据

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 016

• 知识图谱的自动建设

规则名称

• 数据源类型

生效位置

Linux Host With Meta Info

Prometheus

基础设施 -> Linux Host -> $busigroup

口编辑规则 （Linux Host With Meta Info）

Prometheus

中间件-> KAFKA

希选称签：Sbusgroup Sden

Prometheus

中间件-> MySQL-Cluster-> $cluster

v 够选条件

Prometheus

中间件->Redis-cluster ->$cluster

卡片信虫\包括路经信思，名称信息等）将从筛选指标的标签中获服，相应的信息可以逢过“介选标签”指定，并在其已地方通过变量形式引用该标签的值，

信边指标：wp

Kubernetes

微服务-> deployment（$DataSourceName）-> Snamespace

节选杯签：ramespace,deployment, inskanice

则

卡片名称可命名为：Sinstance

Flashcat APM

微服务->服务概况

卡片添加位置可为：k8s-> Snamespace -> Sdeplayment->#netence

箍造指标

cpuusnge_idle *onCident） group_Left（busigrowp,os） n9e_metadata_sys_info

沛送杨签

busigroup

②住 取>

预览 〇

渖选标签

ident

v 下钻路径 ④

+ 笊选行签

可将卡片标签作为变量，填写到下钻路径，如：URL仪表盘地址、Trace Service/apan、日志查询过滤条件等处，以实现精准下钻。

样例：卡片标盗包含：servce，下钻url地址：http:/asncat.com/dashboarde/7pera-$servce

+埼强标笠

可用标签（变量）：Sbusigroup Sident

V卡片标略0④

$bisigroup

对象类型

仪表盘

模板中心

Linux

机器常用指标（如果只想看当前业务組内的机器修改大.Y

Socal_urVcomponents/tastboard/detail？_wuid__=

ient

$ident

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 017

• 知识图谱如何帮助 Agent 推理

知识图谱如何帮助 Agent 推理

从现象到根因

Question

Instruction

••

LLM

Answer

• 某服务异常 下钻日志、trace

• 沿调用链向上游/下游传播分析

Encoder

Tool Selection

Context

• 有效约束思考范围

Search

Search+

Pattern Match

Query

Lexical Graph

Domain Graph

Graph Database

Documents

Data

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 018

• 知识图谱如何帮助 Agent 推理

几种不同的使用策略

结构化增强模型理解，实现简单

用于具体的细节分析，例如从日志

中提取异常原因，给模型提供充足

X浪费上下文空间，多跳推理强依赖模型能力

的上下文

Graph as Context

V 可解释性强，graph 查询路径就是推理路径

用于下钻分析和关联关系的探索，

Graph as Tool

给模型足够的自由度

X多轮 tool call，复杂场景下推理时间长，消耗大

Graph as Planner

V 避免无效探索，分析路径可控

用于约束整体流程和搜索空间，避

免分析过程跑偏

太强的约束可能限制模型的探索，错过真正根因

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 019

• 知识图谱如何帮助 Agent 推理

假设-验证

A 服务异常，怀疑根因

是B服务

Graph As Validator

在知识图谱中找到根因

对象 B

B的确实有问题

B 指标完全正常

找不到或无法验证

结论中明确“不确定”，

得到明确结论

继续分析其他根因

避免误导

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 020

Harness 实践

上下文信息的选择和过滤

Metric： ［timestamp,value］，大部分时

间戳和数据值是不重要的，真正有用的是整

趋势分析、异常点检测

体趋势和异常点

传统算法前置处理

大模型分析

最终结论

Log：故障时刻，经常会瞬间产生大量重复

的错误日志

日志聚类去重、关键词提取

直接分析效率低下、浪费

通过工程和算法手段，

Token

提升确定性，减少耗时和 Token

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 021

•

Harness 实践

可观测场景下 Single-Agent 的瓶颈

分析日志

Single-Agent

上下文超限

Lost in the middle

再分析 trace

再分析事件

总结生成结论

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 022

Harness 实践

SubAgent 共享上下文

SubAgent： 日志分析

MainAgent

共享上下文信息

MainAgent

SubAgent: Trace 分析

生成共享上下文

总结生成结论

故障背景

当前异常指标

故障对象元信息

业务知识库

SubAgent： 事件分析

只提供必要的信息

SubAgent： 指标分析

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 023

• Workflow vs Agent

Workflow 仍有存在的意义

Workflow：解决“确定的问题”

Agent：解决“不确定的问题”

• 提供非结构化决策

• 提供结构化能力

• 长尾问题交给 Agent自主规划解决

• 确定性的场景从 Workflow 出发，约束流程不走偏

• Workflow as Skill

• 不是用 Agent 替代 Workflow，而是让 Agent

学会在合适的时候使用Workflow

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 024

•

Skill / Tool 的设计思考

Skill 和Tool 的设计和优化

Skill：面向任务，包含流程、经验和最佳实践

Tool：通用、单一职责、可组合

• 描述步骤和经验

• Agent-Friendly：语义清晰、参数复杂度低

• 确定性的逻辑，使用脚本实现，稳定性远好于直接用自

然语言描述

• 非必要不加载，減少模型选择难度

• 安全边界：Ops Agent *通用 Agent，在灵

• X“先调用 A，再根据A返回的×字段调用B，.”

活性和安全中进行取舍

•

“使用 python 执行 a.py”

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 025

•

Agent 的记忆系统

Agent + Memory

短期记忆

结构化记忆

长期记忆

支持单次推理

提供系统认知

跨事件复用，自我学习

历史 case：过去是否发生过类似故障？当

故障现场、指标、日志、事件

知识图谱：下钻关系、拓扑关系

时的现场、上下文、对话内容

SubAgent 结论

业务知识库、Skil：最佳实践、排障经验

时间衰减、淘汰维护机制

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 026

Flashcat Al Agent 的落地实践

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 027

•

，Flashcat Al Agent 的落地实践

基于开源夜莺 （Nightingale）实现的统一可观测性产品，包括完整的指标、日志、链路、事

◎

件等维度的观测能力。

Flashcat

面向稳定性保障场景进行了增强，帮助用户快速发现故障，定位故障，是企业保障服务稳定

运行的支撑平台。

Flashcat 具备增强AI分析能力，加速故障的智能分析定位，已取得了实质进展，未来将在智

能化方向继续大力投入。

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 028

Flashcat Al Agent 的落地实践

数据生产、交互、应用 智能化闭环

Agent Core

Memory

Runtime

ReAct

Context/Session

Tool Sandbox

Workflow

Embedding/Graph

Cron Scheduler

Flashcat

Plan

File System

Observability

Al

灭火图：可视化的知识图谱

Agent

指标信息

下钻信息

拓扑关系

业务知识库

Metric

Log

LLM

数据集成

AI 集成

Trace

Event

Skill

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 029

Flashcat Al Agent 的落地实践

接入数据

指标数据源

数招栠成

日志数据源

河所于同开分所、台篮菁烈。似观品

ORACLE

MySGL

Elasticsearch

ClickHcuse

捞汛 CLS

2mbbx

Poc:greSCL

Clickloiea

SQLSarvar

VDORIS

河朱元SLS

OponScarch

Doris

mongoDB

效躥缘成

事件数据源

链路数据源

Skywalking

白定义事件

Zipkn

Jaogs

Skgwalkig

EAEEI

Elsetic APM

河凰云 CponTciematry

胸讯到APM

白定义事件

Prometheus

iasreta nwtry

PINPOINT

Ars Trace

Tempo

OpenTeleneiry

Pinpain

Opon-Faicon

肪讯云图控 CM

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 030

Flashcat Al Agent 的落地实践

创建知识图谱-“灭火图”

在这个空间下，分析 Flashcat_Prom 数源中的数，井创建灭火图卡片规则

⑦向

+ GEX

数据源 （ID:10174）进行分析和创建卡片规则。

数据源分析

*獲盖的观测对象需要补充。

Flashcat Prom （ID: 10174） 中识别到以下观滑对象：

观测时象

识别标签

实例示例

Linux主机

agent_hostname

dev-flasheye-02

MySQL 实例

address

10.99.1.106:3306

Redis实例

address

10.99.1.107:6379、10.99.1.235:6379

Qdrant 向量数据库

instance

http://10.99.1.108:0333/metrics

已创建的卡片规则总览

分层

规则名称

数抵恣

观测时象

关键指标

中间件

MySQL_Remote _Collec_Categraf

Flashcat_Prom

MySQL 实例

实例状态、慢查询、连接池使用率、连接致

中间件

Redis_Rerrote_Collect_Categraf

Flashcat_Prom

Redis 实例

实例状态。拒绝连接数、CPU/内存使用量

中间件

Redis_Local_Collect_Categrat

匹記数掘源

Redis 实例（本地〉

实例状态、拒绝连接数、CPU/内存使用量

中间件

Qdrant Remote Collect 0

Flashcat Prom

Qdrant 实例

实例存活状态

基础设施

Linux Host By Categraf

匹配效据滋

Linux 主扒

CPU、内存、磁盘、I0、网络

基础设施

Linux Hest With Meta Info

匹就敌据源

Linux 主机（含元信息〉

CPU、内存、醋盘、10

基础设施

Linux机器模板/机器模板

匹配数据滚

Linux 主机

CPU、负载、内存、磁盘

基础设施

uoc nelesNuDeroA

匹配数据源

K8s KubeProxy

存活状态、規则同步耗时

基础设施

拨測（HTTP/ICMPYTCP/UDP）

匹配数据滋

拔剥任务

採測结果、耗时、丟包率

微服务

K8s Deployment/ DaemonSet

匹配致据源

KBs 工作负

存活率、CPU/内存/磁盘使用率

应用

procstat

匹配数据源

进程

进程效量、CPU/内存使用

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 031

Flashcat Al Agent 的落地实践

知识图谱-“灭火图”

灭火圈

容母腥务

Fathew-acpa

MSCL焦荐

Ross 集苷

Rads-bywe

My/scL-cy-nke

十片5：%%2

十方48期2

卡左 -9級2

1/0/4

o/t/a

01113

Kuternexe

411:303

！基碳没期：4*

内商质蘿

外-凤 量

2N

Qcon

InfoQ 极客传媒

全球软件开发大会

## Page 032

Flashcat Al Agent 的落地实践

知识图谱-“灭火图”

灰火图固郡认空间

三 订单提交 首页/ 功能授口/电商/订单子系統

×

斑丝

』功能接口：57~

指标趋势

特征分析

• 觸值线 v

同 比vC ontv

念 卡片配置

V 电商 23

流量（req/min）

descvX

成功率（％）① 响应码统计（min/④

descv：！

廷时50分位

延时平均佶

descvK

> 品台 支付子系统 13

一当一碗一天的一周

一当前

前一天一前一周

-当前一醇一天一一周

v品含 订单子系統10

100-

676

会贯计价

4.69

取消吥单

品类冽表

12:0

陨存戒询

燹敢优蒽鉛

下钻路径0

A A分析

2。下站配置

訂总动瓶+

特征分析

Tracing

告鳘事件

事件墦

天火團

仪表盘

日志检索

知识库

汀槃动馥㕰

订草功能：

时间区间

2025-07-03 14:28

2025-07-03 14:32

结架敛

100

回 主题瓷球

汀单功山

url.path

Jkv

汀单媞交

② htp.response.status._code

［鹽入筛浩条件

》 网約车 20

夕关注維度

团神征分析

昀应码分布 ②

Qcon

InfoQ 极客传媒

全球软件开发大会

## Page 033

Flashcat Al Agent 的落地实践

基于知识图谱的故障定位

口 电前

EAltkd 請話/untan/地前系沈

這 FlashA

分折 服务报口 异常原思，分析完后真规列出餐因

分组：2

蒂础斑源

API

稻盘项

1009

50分

天火圈

发现异案：

成功串（96） 45.90

任好纯店 50x

1/110

牺征分折

正常 元异第特征：日志中末发现异富翼集维度

任务元社148

甘市粉業

夏段旱米

检剥對凉日惠

木年心

炭现舜常

检彩對骨凉Tac0

任务完購45#

/apiluseritetal

N。

/api/interfacn

仪表盘

吸现异第

检澎到跧常指樼

任点 868

事件分析

任务見麻：0A。

！水耳兴情

根因分析结论

/artuber baial urh./aoiuseubetal

1. Redis服务不可用

碳功率1961切

• 直接表现：日志中大量 Connection refused 和 dial tcp 皆误，表明Resdis（6380诺口）威务容机或配

駕锚溪，

•佐证：Trace中 Redi's SET 操作耗时异常（>12秒|，运超正常值人<Ims），说明Reslis完全无崎应或严重阻

2. 周务器留过費（加MRedis何期）

al-cens9ak-

③

Qcon

InfoQ 极客传媒

全球软件开发大会

## Page 034

•

Flashcat Al Agent 的落地实践

×

基于自然语言的智能巡检

请巡检当前空间的灭火图，分析系统的隐患和问题，生成巡检报告，以邮件形式发送到一。ad.com

N

no-reply-cat@notice.flashcat.cloud

no-reply-cat@notice.flashcat.cloud

收件人：

nuaming@tiasheat.com

四、AI 智能根因分析

灭火图巡检报告

空间：spece-d | 巡检泡團：2026-04-0917:13~1725（CST）| 卡片总效：135

核心根因：Kafka消费组 n9e.self-monitor-group 存在严重消發堆积

通过对异常卡片 KAFKA/demo-01-docker 触发Al分析（使用 DeepSeek-v3模型），得出以下结论：

4.1 KAFKA / demo-01-docker（组件层〉

一、巡检概览

• n9e-self-monitor-group 消费組：预估消费时长級升至 21,403ms，存在严重消费堆积，是触发异常的直接原因。

• fcoself-monitor-group 消费组：消费时长在332~2,018ms 之间波动，存在不稳定现象。

spece-d 空间共监控135张详情卡片，覆盖4个分层：微服务（10张）、組件（7张）、中间件（12张）、茶

• fe-self-monitor 主题：生产速率在 123.87~186.33 之问波动较大，可能影响；费稳定性。

础设施（106张）。

巡检期间共检测到2段异常波段：第一段持续4分钟（17:20~17:23），短暂 复1分钟后再次出现异常

五、发现的隐惠与问题

（17.25）异常高峰时有1张卡片飘红，异常集中在组件层的KAFKA.

1 Kafea 消费組严重堆积：nBe-seli-monltorgroup 消费组预估消费时长达11,403ms（约11秒），近超正常

二、异常时间分布

水平，消费者可能存在进程异常、性能瓶颈或分区分配不均的问题。

2. 异常间歌性反复：异常在短質恢复后再次出现（17:23恢复 27:25再次异常），说明根本原因末解决，

以下为检测到异常的时间点：

消费堆积可能持续忍化。

河间 （CST

异錦卡片數

卡片总數

严璽程度

04-09 17:20

135

3. fc-self-monltor-group 消费组波动：虽未触发异常条件，但消费时长波动花医较大（332~2.018ms），存

在劣化风险，

鬻持续关注。

04:09 17:22

13S

4. 生产速率不稳定：fself monitor 主题的生产速率波动可能源于上游业务负载不均，若波动加剧可網进一

135

步加重消费堆积。

。

六.治理建议

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 035

可观测性智能化未来效果展望

Qcon

InfoQ 极客传媒

全球软件开发大会

## Page 036

• 可观测性智能化的未来

Vibe Coding时代，可观测性越来越重要

• 开发范式变化：从“可控代码”到“概率系统”

• 面向可观测性的代码开发

• M review code 到 review observability data

可观测性系统的进化

• 基于反馈闭环持续优化

• 从“规则驱动”转向“经验沉淀+自我学习”

• 从“工具平台”到“智能中枢”

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 037

• 持续进化、自主学习的 Agent 基座

主动发现故障

自主学习、持续进化

从人工触发故障定位，到主动发现可疑故障，降

通过长期记忆，达到自主学习、自我进化的效

低告警遗漏风险

果，通过丰富的“经验”进一步提升故障发现和定

位准确性

反馈闭环

记忆、知识沉淀

数据自我完善

基于观察和人类反馈，逐渐积累历史 case 经验，

从故障 case 中进一步补全关联关系、记忆异常模

形成长期记忆和知识

式，完善知识图谱数据

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 038

InfoQ极客传媒

QCon

全球软件开发大会

THANKS

大模型正在重新定义软件

Large Language Model Is Redefining The Software

## Page 039

上

探索 AI 应用边界

AiCon

海

Explore the limits of Al applications

站

全球人工智能开发与应用大会

2026年6月26-27日/上海张江科学会堂

专题：世界模型与多模态智能突破

专题：Agent 系统架构与工程化实践

专题出品人：未政

专题出品人：鲁洁楠

极佳视界/ 联合创始人& 首席科学家

OPPO/大模型算法员责人

专题：AI 原生数据工程

专题：Agent 安全、评测与可信治理

专题出品人：王彦辉

专题出品人：马传雷（岳立）

火山引擎/数智平合产品总脂

支付宝/业务风险技术部员责人

专题：Agent 数据、记忆与运行时

专题：企业级研发体系的重构

基础设施

专题出品人：沈浪

专题出品人：邓亚峰

快手/研发效能员责人

EverMind / CEO
