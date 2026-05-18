# 钱世俊-给-Agent-做-ldquo-CT-rdquo-大规模-Agent-的可观测与质量保障体系

> Page-by-page visual information extraction from rendered page images. Text below preserves the visible text recognized on each page; pages with diagrams include every OCR-readable label captured from the image.

## Page 001

InfoQ 极客传媒

QCon

全球软件开发大会

构建大规模 Agent 的 CT 系统：

火山引擎 Agent 可观测实践

钱世俊

火山引擎 应用观测技术负责人

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

背景与挑战 -Agent时代 的黑盒困境

02

破局之道 - 构建统一观测底座

03

深水区探索：AgentKit 深度观测

目录

04

工程化闭环 - 从可观测到可迭代

05

落地为王-OpenClaw 观测实践

06

总结与展望

## Page 004

背景与挑战

Agent的“黑盒”困境

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 005

• 构建大规模 Agent 的 “CT 系统”

Agent 正在重塑我们与软件、乃至与数字世界的交互

# Agent Thought Chain

neuron + ACTIVATED

path: INPUT - PARSE - REASON + OUTUT

犯错、变慢、甚至“发疯”？问题出现在哪里？

Layer ［2］ - Layer （61

confidence: 0.97

亟需“CT系统”来看请它每一步的决策

可见

可解释

可行动

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 006

背景：大模型 Agent 时代的黑盒困境

复杂性剧增

1

Agent 的能力源于其包含规划（Planner）、

Var itr

工具调用 （Tool）和记忆（Memory）的复杂

1

复杂性剧增

工作流，而非单一的LLM 调用

1

1

U

黑盒状态

黑盒状态

2

内部决策过程不透明，导致问题排查困难

W&teErr BM！

waieishuatiy

成本失控

LwJar

成本失控

3

复杂的调用链使得 Token消耗的归因变得极其

困难

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 007

•

挑战：横跨基础设施到应用层的监控断层

业务应用

DAU

用户反馈

E2E延迟

业务转化率

链路断：TracelD 丢失 /业务上下文断裂

Agent框架

Planner延迟

Tool Error Rate

RAG 检索耗时

Memory负载

语义断：跨供应商链路孤岛/语义对齐失效

大模型服务

TTFT

TPOT

Token成本

模型幻觉率

API稳定性

因果断：硬件指标与推理逻辑脱节

云基础设施

GPU显存利用率

网络RDMA延迟

K8s Pod 重启次数

节点 OOM 驱逐次数

acon

InfoQ 极客传媒

全球软件开发大会

## Page 008

破局之道

构建统一观测基座

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 009

•破局之道：构建统一观测基座

统一观测

Metrics

Logs

Traces

Al Telemetry

门户

加工

看板

告警

集成

破局的关键在于构建一个统一观测基座，通过融合多维

数据和协同五大支柱，拉通端到端的监控链路

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 010

全栈观测门户：一站式工作台

统一观测门户

Al 观测

稳定性驾驶舱

多云观测

统一接入门户

依托于统一观澜产品入口统一数据

面向Al场累，提供零侵入动态理点

全景覆盖业务、应用、 产品、

接入、覆蓝 多公有云厂商的

通过提供统一的接入中心、一链把

接入、可视化配置、告營生命周期

注入，提供一站式观测 可视化、

资源等路层的多种观调数据来自助

可观涮效

应用制和云上环境接入到全機可观

台理、观调底座托管 等一系列操作

链路分析能力，目前完成端到端

完成故障止损操作及很因分析，及

測平台

体验

快速定位排障

底层依蔱等細节

端侧监控

自定义看板

应用观測

可观测数据源

目

客户端观測

应用监控

日志查询

云拨测

应用性能监控

链路追踪

TLS 日志服务

云原生监控

应用诊断

告警/事件 中心

统一观测

云监控

目

Agent探测

Prometheus

基础设施监控

配置、管理中心

客户端监控

Agent任务管理

ClickHouse

节点管理

云服务监控

接入中心

Prometheus

托管服务

诊断分析

数据接入

数据处理

事件中心

监控中心

告警中心

错误分析

QCon

InfoO

极客传媒

全球软件开发大会

## Page 011

•统一集成中心：海量异构数据一键接入

3

广泛兼容

Java

Python

支持市面上主流的技术栈、云服务、中间件以及国内外知名的大模型 API

OpenTelemetry

Native

Nd

OpenAI

Node.Js

拥抱标准

原生兼容 OpenTelemetry（OTel）开放标准，保证了平台未来的扩展性和

AWS

互操作性

Docker

便捷接入

GihHub

K8s

零代码无感接入+轻量配置管理+统一采集器 OneAgent

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 012

统一集成中心的核心：OneAgent

OneAgent控制面

业务1

字节Metrics

2.0SDK

管控模块

wusher 1

APMPlus

心跳及配置拉取

业务2

攒块

澄水綫监听加载

自监控模埃

Checkpoint

OpenTeleme

try SDK

VMP

业务3

InfluxDB

悠改指坛名箱

SDK

Tag名，

螭除或补充

Input

对齐规范

部分Tag

pace Tag系合

flusher_3

云监控

OneAgent

过滤&

flusher_4

TLS

OneAgent

业务4

Prometheus

SDK

业务5

日志文件

OneAgent 是字节可观测团队提供的新一代可观测性

数据［M.T.L.E］采集和处理管道（DataPipeline）

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 013

统一集成中心的核心：

OneAgent 性能优化实践

将计算与1/0分离，在数据发送阶段

指标的标签原先使用 map结构存

• 预分配大块内存：用于连续的

采用基于 RTT 的自适应调节算法。

储，由于许多后端要求标签有序，这

string 创建，以減少小块内存分配。

该算法能根据每个请求的 RTT动态

导致每次处理数据时都需要对 map

调整数据发送的并发度。

的 key 进行动态排序。

• 尽可能使用栈内存：通过分析减少

由此带来的连锁效应：

对象逃逸到堆上。

•后端状态好、RTT 低时：自动调高

• 遍历、插入、合并效率大幅提升：

并发度阈值，充分利用带宽，提高吞

切片的顺序访问对 CPU Cache 更友

• 使用对象池和引用计数：复用高频

吐量，防止数据积压。

好。

创建和回收的临时对象。

•编码器性能提升30%以上：如

•后端异常、RTT 升高时：主动降低

flusher_prometheus 等编码器不再

•优化日志打印：通过判断日志级别

并发度阈值，利用本地队列缓冲数

需要内部排序。

和延迟求值 （lazy-evaluation），避免

据，避免对后端造成过大压力。

• 高频核心方法性能提升一个数量

在低级别日志下不必要的字符串拼接

级：GetSize（、CloneO、SortTo0

和函数调用开销。

等方法的性能得到大幅改善。

预排序：从 map 到

发送并发度自适应调整

SortedSlice 的改进

其他代码细节优化

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 014

• 统一集成中心的核心：

OneAgent 性能优化实践

PneAgent CPU Usage （200k dps）

OTELCOL CpuUsage （200k dps）

HTTP Logs 转 OTLP,HTTP上报

110.55%

270.05%

HTTP Metrics 转 OTLP,HTTP上报

96.80%

269.75%

HTTP Traces 转 OTLP,HTTP上报

83.17%

165.15%

1. 重载场景下OneAgent数据吞吐可以比 OtelCollector高一倍

cpu usage percentage （Daemonset）

800%

600%

0%

18:00.

18:30

19:00

19:30

20:00

20:30

21:00

21:30.

22:00

22:30

23:00

23:30

min max、

avG

container_cpu_usage_seconds_total;sum ｛instance：

24.6%

613% 205%

2. OneAgent 负载整体降低了50%以上，部分重载节点性能提升了3倍

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 015

统一数据加工：流转间的“提纯与瘦身"

数据脱敏：实时抹除日志或 Trace中的 PIl（如电

话、Token 密钥）防泄露。

Raw Data

黑白名单过滤：委弃几余的探针心跳、压测流量或

Debug 级别的无用效据。

清洗与过滤

清洗

元数据补齐：自动每一条数据打上统一的上下文标

签（如集群名、地域、业务租户等）。

富化

数据富化

动态映射：如IP 自动转 Geo地域，错误码映射为明

确的业务语义。

转换

日志/链路转指标（Log/Trace-to-Metrics）：从海量大模

分流

降维与转换

型对话日志与链路中实时提取重点字段，生成时序指标。

指标转指标（Metrics-to-Metrics）：利用降采样，将高基

数、高密度的原始指标预聚合为宏观报表指标。

Processed Data

动态分流

冷热分离：

冷热分离：高频告警与近期业务数据入“热存”保障

热存储

冷存储

极速查询；海量全量流水入“冷存”降低开销。

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 016

•统一看板：全局视角的交互式洞察

P

跨类型数据联动

多数据源混绘

同一个仅表盘内展示指标曲线、日志流与

支持在一个看板内，同时使用

Prometheus/APM/日志 等多个底层异构数

链路拓扑，实现所见即所得的下钻排障

据源进行绘制对比

A

统一看板

D

Grafana 平滑迁移

预置行业模板

完全兼容 Grafana 的JSON 模型定义，支

沉淀 Agent 与大模型领域的行业最

持海量存量 Grafana 看板的一键平滑导入与

4出

佳实践模板，支持一键克隆与按需组

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 017

统一告警：智能降噪与精准触达

智能告警降噪

基于规则的收敛、去重及依赖链路抑制，将

海量子产品异常输入

海量报警风暴收敛为一条核心根因告警，避

免“狼来了”效应。

子产品A异常

子产品B异常

［更多异常.］

子产品C异常

子产品D异常

统一告警配置管理

◎

全局配置面板

分发

飞书通知

①1

降噪漏斗

全局配置：

• 告警优先级：高

分发

打通所有底层观测产品，通知策略与接收人（如

① 过滤重复异常

电话通知

飞书群、Webhook）只需全局配置一次，告别

• 分发规则：启用

在指标、日志、链路系统里重复配置的噩梦。

② 排除误报噪音

• 通知设置：完成

分发

邮件通知 箱

③ 筛选高优告警

开箱即用的预置规则

输出：高优告警（已降噪）

内置 Agent与大模型场景的最佳实践告警模

版（如 TTFT 突增、Token 成本暴涨、工具

调用大面积失败等），一键启用。

aCon

InfoQ 极客传媒

全球软件开发大会

## Page 018

•统一观测基座，是 Agent 深度观测的前置条件

统一接入（OTel + OneAgent）

白盒化链路

1

全栈数据采上来、不断链

Planner Tool RAG Memory-> LLM

统一加工（清洗/脱敏/派生）

可存、可算、可控成本

可解释归因

2

慢在哪/错在哪/钱花在哪

统一呈现（门户/看板）

支撑

跨指标/日志/链路一体联动

统一告警（降噪/触达）

闭环进化

3

回流样本 评测 优化 线上验证

昇常能被及时发现与路由

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 019

Q

深水区探索

AI与Agentkit深度观测

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 020

AI与大模型观测：从底层到调用的全透视

AI 语义规范

应用层

Prompt

Kesponse

在 OpenTelemetry 标准基础上，扩展了针

（Application Layer）

用户输入：“帮我生成春日旅行攻略”

模型回复：“推荐大理行程：Day1逛洱海..”

对大模型的专属语义字段

模型层

数据归一化

Tokens: 256

Latency: 180ms

Temp:0.8

（Model Layer）

通过标准化的适配层，将不同框架、不同模型供应商

OpenAI

火山方舟

Anthropic

统一纳入到观测体系中，有完全一致的观测体验

GPU 利用率

设施层

88%

显存占用

GPU 温度

91%

74°C

100

890

（Intrastructure Layer）

150

$80

160：

端到端全栈关联

100

229

230

将上层的 Prompt/Response 内容分析，与底层 GPU

的利用率、显存消耗等基础设施指标完全关联，实现真正

的全栈透视

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 021

核心能力：大模型推理性能观测

时延拆解

AI服务监控看板

精确监控 “首字返回时间 （TTFT）”和“每Token生成

时间（TPOT）”，帮助判断是模型

*思考”慢还是

“吐

M

时延分解

Token消耗占比

会话追溯（脱敏）

字”慢

【轮次1】

网络传输|120ms

Prompt：用户［U***123］：请查询我的*“物流状态

4 Response:C

助手：您的*物流当前【运输中】

其他

业务A

预计*日到达

排队等待|280ms

成本监控

40%

』性能：耗时240ms| Tokens:180

【轮次2】

业务C

实时统计 Prompt 和 Completion 的 Token开销，并

业务B

20%

Prompt：用户［U***123］：能否修改“*收货地址？

按业务，用户，模型等多维度进行分析，揪出成本热点

TTFTS|450ms

30%

Response：

助手：可通过【我的*】>

【订单管理】修改地址

总耗时：1070ms

Top3消耗排行

性能：耗时190ms Tokens:210

【轮次3】

TPOT

220ms

Agent_001:12,450 Tokens

Prompt：用户［U****123］：谢谢

会话与内容追溯

台 Agent_002: 9,870 Tokens

Response:03

助手：不客气©

留 Agent_003: 7,620 Tokens

性能：耗时110ms Tokens:45

完整记录多轮对话的上下文、Prompt/Response

内容，用于问题排查、效果评估和安全审计

QCon

InfoQ极客传媒

全球软件开发大会

## Page 022

• AgentKit 深度应用监控：什么是AgentKit

AgentKit是为AI Agent构建、部署、运行提供支持的开发工具平台，为Agent提供模型之外的安全、内置工

具、记忆、知识、监控、评测等基础设施

App

Agent

Any Agent

VeADK+ Other Framevork

Deploy

Identity

User

Gateway

Runtime

Guardrails

Built-in tools & Sandbox

MaaS

Memory

Models

Observability

Prompt Pllot

Agent RL

Guardrails

Evaluation

AgentKit

深度埋点和集成

开箱即用的观测能力

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 023

AgentKit 深度应用监控：全局运行时洞察

~ Agentk！总览

＜工貝分析

Agenst 调用故

Ageniat 调用数的势器

工及调用次数

工再调用 tcken

工真调用耗附

1036

112

04w 018mg2

wvock_trocng

—工月調用汉效

-工具黃用 Vkin

Agennt 会话戬越势团

Aaensit 调用平均發时

Agentt调用错设率

工具调用次数。分工具

工具選用 tckcen-分工具

工具调用耗时。分工具

320

MIN

204120012441600121420021205002022215 0400

Soairego Tondreyo vzndwoop epndmo Tadpap

-povide..

-J且啡，

-丁具液

-PA-..

- P9.w..

AgentKit 调用和会话数据总览，可视化展示数据分布和趋势

针对 AgentKit 中所有工具提供的工具分析看板，可视化展示工具调用相关数据和趋势

x Agent 执行分析

执行步数

xcken 分布

耗时分布

80-90.

80-90.

- 50-20..

-80-90.

Agent 的执行数据分析，并通过饼图形式可视化展示分布数据

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 024

Agent 链路剖析：白盒化的调用链分析

会话详惰

单链路详情

我话巾

退用链饮日 27

Trace洋情

Tace完發日志

开始甜间：202601-29 15:54:10

做耗时：337245

紅用数：1

Sp数：62

状烈码：0

拓邦凶

火焰凶

1.045

第1淡受用岱

2025-06-09 15:0053

2025-06 08 1591:66

大侠型組件振旅（5）

1001 5

worktlow1

朔*条谟用盟

Somn.C

337.248

起皆时從

0 开始时间：2025-06-09 15.0056

• e frurusse POST /runsst

387 24：

2026-01-2915:54:10

详细倍忍

• imocation woksom 8 2226/230

337,248

20250120 1554:10

2 Input

黑性

請用一分还鞋释：

• alLimnIm 85332/41105723）

27478

2026-01-29 15:54:12

input》

FCRMAT

JSON：

1.38

Outout

v ceoue tcol imoge geerate 1ool

12.043

2026-01-29 1554:28

Ouspu

•◎moge-geneyate

30.848

"intent_onalysis"："n. sntont: genera !in2, Roguired tonLs: Horein3. Hesponse tyne: Textuol exn Lanatianlnn

•③ calLlm_tsk. 316984（Z16984）

6.525

2026-01-29 1554:28

model

s0lut1on_plan%：“1。常君使用的工鸟：无Xn2，执行卡素；真强果第店期了3

1n3。預需植果市站：一句请的文本能降：的”

C POSI

6.628

2026-01-29 15：$4:28

双&终成品

"50l result： "No tool mitchisd".

•不是鸡面“N0 5001 natahed”、小

© POST

5.733

2026-01-2915:54:28

6.825

© POST

6.818

2026:01201554:28

瑞邦丽鱼：

Takan 双： 721

•② clLlIm_tark S-16384（16386）

10.845

202601-2915:54:28

• PST

链路还原

边界定界

以火焰图或时序图的形式，清晰地还原从 Planner 的

通过对比 Trace 中不同 Span 的耗时，可以一键判断间

规划，到中间每一步工具（Tool）的调用，再到与

题是出在模型生成慢，还是某个外部 API接口卡顿，或

LLM 的交互的全过程

是在效据处理上

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 025

隐形瓶颈透视：记忆与知识库观测

Agentkit 超用观测

运行时监控

知识库分析

会活分析③

Trace分析

日志分析

Memary分析

单铤路详情

刽建事件

记亿召回

ce.80

拓扑圈

12

0.38

25.00%

3

0.81。

0.00

坦件奶盗伪

ywrn.kncwetoe 2

0请等入省你

名称

AP 芝週用汶丝

42.01

© GET

0.478

200

监控硗情

7810mk

224:8m

wArg_Lccakesw：

详坦信息

Agentkit 忠用观瀏

•◎ niwtedlsw.snoth kesmbttge1

2169:8

20--12-12 19862

② POST

会话分析 0

ET san htp sind

Inputv

TEXTJSON

◎ aitnhtpsnd

225-12-12158621

知识库分析

• @ hwtidnLsintLenbtyebi

13212e 204-12-12 158833

知识榕紧

② PosT

1G7.28ms

2085-12-12 158658

Prorethst-asete 加好的F

• cETkn htp sand

0040④ 2025-12-12 150558

巫购链⑤

© oeToun htp sns

Qnare 202：-12-18 158550

TEXT

（ISON

7

0.19

0.00

"rmwrite.euy:mutl.

• 语捨入名稼

AP！总该用汉数

平圪死迟

总貓漠乎

0.195

平均菇迟

总银溪穻

0.188

性能观测：监控对话历史（Memory）的加载耗时，以及在 RAG 流程中，对向

质量评估：在 Trace 链路中直接透出 RAG的Top-K 召回结果、相关性得分、使用

量数据库的检索性能和 Embedding 过程的耗时

的 Chunk内容，帮助开发者快速评估知识库的召回效果。

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 026

04

工程化闭环

从可观测到可迭代

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 027

•

•工程化闭环：观测一回流一评测一优化

观测数据回流

优化闭环

将线上真实 Trace 的高价值样本（如典型失败案

将评测结果沉淀为优化动作清单（Prompt 调

例、高频调用场景）自动回流到评测系统，构建

整、检索策略优化、模型/路由策略切换），形成

覆盖主流场景的高质量评测集

观测一回流一评测一优化的持续迭代闭环

工程化闭环

离线评测

在线评测

在每次版本发布前，用回流数据对新旧版本进行

在生产环境持续监控 Agent 的效果和异常模式，

离线对比和回归测试，用指标（如成功率、轨迹

一旦质量退化（如误答率上升、Token消耗异

相似度）说话，确保“上线不翻车”

常），能第一时间发现并定位到具体场景

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 028

•

数据回流：连通观测与优化的桥梁

离线回流机制

自动化标注与对齐

支持将落盘的高价值Trace，按规则进行清洗提取，

在回流过程中支持根据埋点元数据进行自动化初步

定期回流至评测数据集，满足大规模离线分析与批

标注，将零散的观测点位对齐结构化的评测数据

量评测需求

集

自动标注

在线流式回流

在线回流

实现高价值反馈（如点踩、异常熔断链路）的实时

回流，支撑分钟级的数据大屏与动态告警拦截

离线回流

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 029

• 评测体系：为 Agent划定能力基准线

从结果到过程的质量保障

1

2

3

4

5

？

回流数据评测化

结构化评测集管理

多维度评测指标

自动与人工协同

反哺模型与Prompt

无缝对接数据回流池，

支持多源数据导入与灵

不仅评测答案的准确性

支持 LLM-as-a-Judge

基于评测结果，指导

将提纯后的线上真实

活构建，提供版本化控

与相关性，还内置对

的大规模低成本自动化

Prompt 结构优化、工

User Query 与长上下

制与切片抽样策略，确

Token 效率、API调用

预评测，同时提供白盒

具接口设计调整，或为

文转化为评测基准题库

保评测样本的科学性与

合理性、拒答率等

化的人工复核界面，对

模型微调提供高价值训

场景覆盖度

Agent 专有指标的深度

关键高风险回流数据进

练样本，让 Agent 的

评估

行人工标注对齐

“思考方式”不断进化

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 030

评测体系：为 Agent 划定能力基准线

液奶对比委鞋

比实验详情 #27922

•汇总得分

指关位 0g2

4W

ounuiticins

多实验对比分析

人工校准得分

提供指标统计和数据明细，帮助开发者从「宏观」角

人工核对评测集输入与实际输出，识别评估器评

度对比多个实验的整体优劣，从「微观」视角比较每

条评测数据在不同实验中的表现

估不准确的异常案例

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 031

15

落地为王

OpenClaw 观测实践

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 032

落地为王：OpenClaw 的监控实战

接入前

接入后

ERROR

ERROR

ERROR

MTTR+80%

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 033

SLI 度量先行，数据驱动的全链路可观测

传统系统

OpenClaw

请求

）

请求

多步推理（LLM）

多次tool 调用

返回

）

状态更新

最终响应

传统单一维度 SLI（success / latency）

多层＋可归因＋面向任务的SLI体系

QCon

InfoO 极客传媒

全球软件开发大会

## Page 034

SLI 度量先行，数据驱动的全链路可观测

网关健康度

1. Channel /接入层

Socket 建连成功率

端到端请求成功率、耗时-北极星指标

Session 初始化成功率

2. Message/ Session 层

Session卡顿率、恢复成功率

935

消息出入队成功率

3.Queue/调度层

消息排队时延

OpenClaw 全链路SLI体系

Agent 执行成功率

4.Agent执行层（核心）

Agent 执行耗时

LLM响应成功率、TTFT

5. LLM /Tool/Memory层（Al层）

- Tool执行成功率

一 Cache命中率

任务创建成功率

6. 定时任务

任务执行成功率-北极星指标

aCon

InfoQ 极客传媒

全球软件开发大会

## Page 035

• 深入运行时的采集

OpenClaw Agent Runtime

-gateway_Start/stop

- before_tool_call/after_tool_call

- session_start/end

- agent_start/end

-message_received/sent

- subagent_spawning/spawned/ended

-|Im_input/output

自研 apmplus-openclaw-plugin

Plugin Hook Events

APMPlus OpenClaw Observability Plugin

TraceContext Manager

Span Operations

Metrics Recorder

（context.ts）

（span.ts）

（metrics/）

我们不满足于表面的日志抓取，而是

Hook Handler Layer （index.ts）

深入 Agent 的运行时，通过 Hook

- 26+ hook handlers for full lifecycle coverage

机制在会话开始、模型推理、工具调

Log Module

Native Diagnostics

ID Matching

（og/

Service（service.ts）

（idMatch.ts）

用、任务分派等关键生命周期节点进

行精准的信号采集。

OpenTelemetry SDK & Exporters

TracerProvider+

MeterProvider +

LoggerProvider +

BatchSpanProcessor

PeriodicMetricReader

BatchLogRecordProcessor

这保证了数据的完整性与实时性，从

X OTLP Proto Exporters（HTTP）

源头抓住了最真实的执行现场。

•yv1/traces

fv1/metrics

/v1/logs

APMPlus Backend Observability Platform

Gm@

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 036

•

核心优势：APMPlus OpenClaw 插件

观测维度

多 Agent 场景

工具调用

采集原理

信息丰富度

归因与分析

跨端与扩展

接入复杂度

最终价值

官方观测插件

不支持。

不支持。

有限的运行时采集。不足。

基本无法归因。

不支持。

简单。

仅提供基础的“指

无法关联多个 Agent

完全无法追踪工具

通过运行时 Hook

信息非常稀疏，仅

由于 Trace 链路

仅覆盖 Agent

仅需启动并配

标监控”

，让你

之间的调用关系，每

调用的过程与细节。采集少量关键事件，包含 Token 指标

断裂且信息缺失，

自身，不具备跨

置即可使用

“知道”有

个 Agent 的追踪信

但覆盖范围和深度

和会话状态等基础

几乎无法对复杂问

端能力和扩展性。

Agent 在运行，

息都是孤立的，难以

不足。

数据，不支持请求

题进行有效的根因

但无法深入了解其

形成完整的协作视图。

详情、生命周期等

分析。

内部工作细节和问

深度信息。

题根源。

基础日志采集方案

有限支持。

有限支持。

解析

相对完整。

信息零散

不支持。

复杂。

更适合用作基础的

基于单会话日志采集，通过解析日志能够

session.jsonl日

部分关键信息（如

信息更偏点状、零

通常更聚焦在

需要手动安装

“日志查看”

一旦派生新会话，

分析出工具调用，

志文件，进行事后

Prompt）不会落

散，要做多维度关

：Agent 本身，

采集插件，并

在复杂多 Agent

Trace 容易“断裂”，但调用细节（如入

拼凑和还原，信息

盘，因此难以从日

联和下钻分析需要

对多 Channel

依赖服务端日

场景下，分析效率

还原多 Agent 协作

参、耗时）丢失严

存在滞后，且容易

志中还原，对复杂

投入较多人工梳理。信息和底层指标

志解析功能。

受到一定限制。

链路的成本高，需大重。

遗漏部分运行时细

问题的分析颗粒度

的覆盖相对有限。

量人工拼凑。

节。

有限。

APMPlus 插件

原生支持。

支持。

深入 OpenClaw

完整。

端到端全链路关联。支持。

相对简单。

真正实现

：“可归因

能够串联主、子

为工具调用提供独

运行时，基于真实

可采集完整的模型 可从业务指标下钻

可采集多

提供一键安装

可迭代”的可观测

Agent的协作链路，

立的Span，并能

生命周期节点采集，输入（含系统提示

到 Trace，再到

Channel信息，

并配置脚本，

性，帮助团队“看

方便做清晰的归因分

与主 Agent 的

信息完整、实时、

词）、工具调用细

Log，实现精准根

并支持灵活扩展

只需要一行命

懂”问题、量化成

析。

Trace 丝滑串联。

精准。

节等运行时内存中

因定位。

Metrics，与底

令即可完成。

本、指导优化。

在失败时，可下钻

的关键信息。

层系统指标打通。

定位到具体的入参

与异常信息，精准

复盘。

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 037

Data Collection & Processing

OpenClaw 全链路 SLI体系构建

apmplus-openclaw-plugin

多维度数据采集

系统定时任

务….

退行时Hook

OpenClaw Host

实时诊断日志

• apmplus-openclaw-plugin:MTL数据通过OTEL格式上报

Agent Runtime

ECS系统日志

•文件日志采集（结构化诊断日志为主）：典型是

/tmp/openclaw/**/*.log，通过 input file 并做多层

ECS实例监控

OneAgent

Openclaw诊断日志，审计

日志，cronjob 状态..

JSON 解码后上报。

流水线处理

•宿主机指标采集（主动采集）：将 CPU,Mem,Load, 10

Traces & Metrics

& Logs

等ECS 带内监控上报，让用户更好地了解ECS状态

•定时任务主动采集（主动采集）：将系统定时任务以及

Openclaw 定时任务数量和运行状态周期性采集上报

APMPlus Platform

SLI/Metrics

（服务稳定性度量）

提炼&清洗

LoeS

Traces

（原始日志关联）

（全链路追踪）

SLI 指标清洗与派生

脓发

• 原生采集的指标

Trace 根因诊断

• 日志转指标：字段提取＋聚合计算＋指标上报

指导

n SLI 稳定性大盘

QCon

Observability & Governance

全球软件开发大会

## Page 038

OpenClaw 全链路SLI体系构建

建立用户视角的"黄金指标”

开箱即用的SLI观测能力

SLI 指标

业务价值

回答的关键问题

wMF-wc/niatmnL

对话成功率

衡量用户请求是否被成功完整地处

“我的用户请求是否得到了有效回

理，是服务可用性的核心体现。

应？”

对话响应P95 延迟

反映绝大多数用户感知的端到端响

“我的用户是否在可接受的时间内

应速度，比平均值更能代表真实体

得到了答复？”

验。

Agent 执行成功率

度量核心业务逻辑（Agent执行）

“是 Agent内部出错了，还是其

的稳定性，是定位内部问题的关键。他环节的问题？

首次可见回复成功率

关注用户是否快速收到了系统的初

“系统是否让用户感觉“活”着，

（近似）

步反馈，衡量系统的即时响应能力。而不是在‘假死’？”

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 039

• 案例一：秒级定位下游 API 超时故障

问题现象

用户反馈 OpenClaw 某个 Agent 响应非常缓慢

观测路径

通过用户 ID 找到对应的 Trace，查看火焰图

在火焰图中，发现一个名为 get_weather_api 的 Span耗时占了总时长的90%，并最终

证据发现

以 network timeout 错误结束

根因是该天气查询AP！ 的供应商网络抖动。临时修复措施是增加了超时时间和重试机制，

根因与修复

并对该工具进行了降级处理

aCon

InfoQ 极客传媒

全球软件开发大会

## Page 040

•

案例二：Token 成本风暴溯源

财务发出预警，某个 Agent应用的 Token 消耗在特定时间段内出现指数级暴增，P99

问题现象

Token/请求指标远超正常水平

观测路径

从成本看板的异常高点出发，下钻到消耗最高的 Agent 和时间段，筛选出该时间段内的

异常 Trace

在异常 Trace 的火焰图中，发现同一个 generate_summary 工具被连续调用了数十次。

证据发现

查看每个 Span 的 Prompt，发现 Agent 在不断地对已经很长的摘要进行再摘要，形成

“摘要的摘要的摘要⋯⋯”

，导致上下文（Context Window）滚雪球式地放大

根因是 Prompt设计存在歧义，未能明确指示 Agent 在生成摘要后应停止。

修复措施包括：

根因与修复

重构 Prompt：增加明确的终止指令。

设置 Guardrail：在 Agent层面增加 max_iterations 限制，强制跳出循环。

增加预算与早停：为单次任务设置 Token 消耗预算，超支则提前终止。

建立回归评测：将此失败案例加入回归测试集，防止未来再次出现。

aCon

InfoQ 极客传媒

全球软件开发大会

## Page 041

，案例三：模型幻觉与记忆截断排查

用户反馈在一个长对话中，Agent开始“胡说八道”，忘记了之前提供的关键信息，表现

问题现象

出严重的“模型幻觉”。但该模型本身在标准评测集上表现正常

观测路径

检查该会话的 Trace，重点关注 RAG 相关的 Span和对话历史（Memory）加载环节

•在RAG 检索的 Span 中，发现对于用户后期的提问，向量数据库返回的 Top-K结果的相似度

证据发现

得分极低（<0.2），且召回的文档片段与问题无关。

• 查看 Trace 的初始部分，发现load_memory 这个 Span耗时很长，并且其输出的上下文在

某一轮后被截断，丢失了用户早期输入的关键信息（如产品名称）。

1） 用户的后期提问方式比较口语化，导致与知识库中标准术语的向量相似度过低，RAG召回失效。

长对话导致上下文总长度超出 Token上限，系统自动截断了早期的、包含关键定义的会话历史。模型在没有关键

上下文的情况下，只能开始

“自由发挥

根因与修复

修复：

优化 RAG：引入查询重写 （Query Rewriting）来处理口语化输入；调整 Chunk 策略和 Embedding 模型。

优化记忆管理：引入

“长期记忆摘要化”机制，将早期对话压缩成摘要；对会话中的关键事实（如实体、术语）进行

Pinning， 确保不被截断。

建立轨迹评测：建立评测标准，确保在长对话场景下，关键信息的召回率不低于某个阈值。

aCon

InfoQ 极客传媒

全球软件开发大会

## Page 042

总结与展望

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 043

•

总结：构建全栈 Agent 可观测基座

全栈统一观测基座

Agent 专有深度洞察

2

3

打破数据孤岛，融合集成、加工、看板与告警，

深入生命周期，提供大模型推理耗时

消除多产品割裂带来的认知与维护成本

（TTFT/TPOT）、精准 Token 成本核算及知

识库诊断

1

4

白盒化全链路溯源

工程化持续迭代闭环

端到端 Trace 重建，清晰还原 Planner、

打通“观测-回流-评测-优化”的数据链路，支

Tool与LLM之间的复杂编排，精准定位性

撑大规模 Agent从被动排障向数据驱动的持

能瓶颈

续演进

全栈 Agent 可观测基

座

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 044

• CT 系统能力矩阵：可见/可解释/可行动

• 端到端 Trace

可见

• 统一语义

•统一入口（门户/看板联动）

• 白盒化过程 （Planner / Tool / RAG/

Memory）

可解释

• 因果与边界（阶段拆解＋依赖定界）

• 成本归因（Token/费用按链路归因）

• 告警联动（自动路由到 Owner）

可行动

• 回流评测（失败样本 >黄金评测集）

• 优化闭环（评测对比 策略上线 验证）

把 Agent 从黑盒变白盒：先可见，再可解释，最终可行动

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 045

•展望：从“全面体检” 迈向“自动驾驶”

更开放的生态

从“被动可见“到“主动治愈"

提供标准化的 Agent

观测API，与第三方工

具和平台无缝集成

更智能的排障

推进观测系统与业务编排框架联动，

实现外部 API 的动态降级、

Token 暴涨拦截及智能路由切换

基于可观测数据，实现自动化

的根因分析与诊断结论推送

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 046

Q&A

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 047

InfoQ 极客传媒

QCon

全球软件开发大会

THANKS

大模型正在重新定义软件

Large Language Model Is Redefining The

Software

## Page 048

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
