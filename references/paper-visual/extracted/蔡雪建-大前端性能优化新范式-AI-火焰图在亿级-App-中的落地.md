# 蔡雪建-大前端性能优化新范式-AI-火焰图在亿级-App-中的落地

- Source images: `references/paper-visual/images/蔡雪建-大前端性能优化新范式-AI-火焰图在亿级-App-中的落地/`
- Processing mode: page-by-page visual information extraction (OCR-assisted; not a summary)
- Pages covered: 35

## Page 001

InfoQ 极客传媒

QCon

全球软件开发大会

大前端性能优化新范式

— AI火焰图在亿级App中的落地

蔡雪建

快手/大前端性能负责人

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

01

为什么需要AI分析火焰图？

02

FlameEye的AI技术实现

目录

03

FlameEye的Al评测体系

04

总结和展望

## Page 004

背景

为什么需要AI分析火焰图？

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 005

• 背景：快手性能发展历程

2026

2025

智能化（Agentic）

AI Native x 性能

2022

为AI而生，重构研发体系，释放

智能化（Agent）

糸统价值

2020

Al First x 性能

体系化

以AI为先，优化现有流程，提升

局部效率

指标体系：全页面、全指标覆盖

基础化

评价体系：优平比—健康度

基础可观测、可归因

归因体系：指标归因 成因归因

聚焦全局视角

优化体系：全方位专项治理

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 006

• 背景：大前端火焰图的“巴别塔”问题

前端火焰图

自研火焰图

Android火焰图

iOS火焰图

鸿蒙火焰图

QCon

InfoQ极客传媒

全球软件开发大会

## Page 007

背景：大前端火焰图分析的挑战

分析门槛

分析效率

分析覆盖

分析孤岛

火焰图分析高度依赖专家经

海量Trace 需人工逐层分

人工分析容易遗漏问题，导

火焰图分析专家有限，难以

验，新人难以快速上手

析，过程耗时耗力

致优化不彻底

规模化支撑业务需求

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 008

背景：FlameEye介绍

公一场入，

①

Agent一站式分析火焰图

IS社交更面启动：iPhicne12Prc-2.5区

HyperAl Search or type ' for commands or " for SaL mode

支持大前端的全部性能分析维度（启动、

刈话分斫

m役

卡顿、功耗..），并打通各平台，实现发

xxY &Default workspace

现、分析、解决全环节的AI自主化建设

1. 丰纳理产面安石，而非计算密第

，例少糖袖：正姨理如站在顿結菜个后台线理的任学

2

Agent对话分析火焰图

球，裕源x些，宗以。

？依堂物：砾在以测皑销卖物。导致里缨但故理网光您

。 阿步0O：在王续煌执行了而西然攻件这跟或戏热你且

可选择火焰图的局部片段进行对话分析，

•影糖：这是學封悉食汤染珍段絕时过核的造相原团，万可

或基于一键分析结果进行更深入的分析

，佳务缩依毅：而在阶个升行的任务落：炎此灌取凉和网络

的效果。

•形感 科盛引中前择河最授决定丁耍那校刻内容何时服

户 越为了必镇路径上能感發，在网生状况布住号，双险

3

Agent批量火焰图分析

支持批量火焰图分析，找出共性问题或版

芹洪主綫檬严重規書向圈

生产认ZQ的你上。以雅通尽重的测肇-

本间劣化问题

w TmeineSn：

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 009

FlameEye的AI技术实现

从专家经验到工程科学

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 010

•

FlameEye：设计理念

过去 Human In The Loop

国区*

87

»>

抓取火焰图

专家分析

产出分析报告

业务解決

现在 Human On The Loop

监督者

上传

产出

自动抓取

自动分析

自动解决

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 011

• FlameEye：拆解思路

沙盒式问题解决

基于沙盒进行性能优化、性能验证、并在优化

解决问题

完成后自主创建Merge Request

专家级问题分析

分析问题

、多平台、多维度路由分析-指标级、成因级、源

码级协调分析

无死角问题发现

发现问题

全面打通线上监控平台、线下拦截工具，并赋

能开发者一键智能抓取

性能优化全流程

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 012

FlameEye：发现问题-有哪些场景？

开发调试

测试准入

线上运维

大盘告警

开发调试

测试准入

线上运维

发现方式：主动分析火烙图

发现方式：测试反馈+流水线

发现方式：大盘告警

特点：开发者主动行为

特点：自动化触发测试准入

特点：被动感知

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 013

FlameEye：发现问题-全面打通

全面打通线上平台

◎全面覆盖线下工具

线上

线下

Keep

Hyper

Radar

DevTools

AppLab

发现问题

• OpenClaw智能抓取

优化

抓取Trace*

返回Trace

—发出指令—

一智能分析一

adb-skills

kuaishou-uri-skills

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 014

FlameEye：分析问题-整体思路

编排者

Agent群

合成者

路由1~N

火焰图

LLM

调用

专家策略.

汇总

数据库

合成

多份场景

结果

LLM

LLM

LLM

专家策略

返回

返回

口记忆系统

2 Skill

SMCP

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 015

FlameEye：分析问题-编排者

火焰图输入

识别场景

归一化处理

平台多

文件格式处理

规则设定

大模型识别

Androld

T0S

Harmony

Wep

格式多

traceprocessor/streamer

，trace

转换沩数据库

Jjson.pertetto-tracetrace

.html.cpuprofile

自

信息多

用户选择火焰图类

自动识别用户意图

DB

型、分析场景

cpu信息

.线程信息 帧信息 电流信息 网络信息

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 016

FlameEye：分析问题-Agent群

有火焰图数据库、分析场景，AI能否自主完成分析？

火焰图数据库

正确分析结果？

数据流

分析场景

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 017

• FlameEye：分析问题-Agent群

以页面启动为例

• 分析起点、结束点是哪里？

•分析的关键链路是什么？

• 涉及的巨量上下文怎么处理？

AAAAAAAAAAAAAAAA AAAAAAAA AA RNSTY

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 018

FlameEye：分析问题-Agent群

规则引擎

大模型引擎

Use

界定问题＜>性能监控

Prompt

Skills

系统提示词

Perfetto

Result

火焰图

用户输入

L09

Use

§组织上下文

Perf一domain

过滤界外无效信息

识别界内关键信息

分割界内关键信息

Kesult

场景

（压缩上下文

口 Memory

门 KRAG

相同Slice聚合

分析记录、历史会话

专家经验、历史案例

分析结论

“双引擎”驱动：规则引擎致力于领域划分、聚焦上下文，大模型引擎致力于垂直领域经验

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 019

FlameEye： 分析问题-最后一公里

传统

Al-Native

技术专家分析火焰图后，给到业务

AI要全流程串起来，通过火焰图发现问

团队优化建议

题，还要继续结合业务代码明确根因，

从而打通解决问题。

演进

已优化/

解决

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 020

FlameEye：分析问题-最后一公里

性能现象

代码定位

代码理解

根因分析

基于火焰图识别性能问题

基于火焰图Slice映射代码位置

结合函数和调用链，理解代码

结合代码逻辑判断根因和可

》

语义

〉》做功空间

••

serviceC（）

Root Cause

Step1

Step2

Step3

Step4

深度结合业务领域知识，从现象到本质的“跃迁”

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 021

FlameEye：分析问题-最后一公里

火焰图抓取

源码服务

Web端：源码天然可回溯

预

标准化接口：封装代码读取

源码可见

能力

回@

MCP

口川

全链路朔源：支持多源仓库

分析Agent

路由

移动端：精准插装、Slice对齐

代码定位

主仓库：核心业务

@ 代码理解

搜索引擎

comka#func

② 根因分析

comkbajkfec#func

子仓库：依赖模块

插装

可朔源

依赖解析

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 022

FlameEye：分析问题-合成者

合成者

火焰图1

聚合分析

• S2

找到共性的核心问题

火焰图 2

AI 初步分析

最终结论

劣化、

问题根源与优化建议

初步分析结果

对比分析

火焰图 3

找到版本间的劣化问题

aCon

InfoQ 极客传媒

全球软件开发大会

## Page 023

•分析问题：反馈沉淀与能力进化

FlameEye分析

火焰图

分析结果

持续学习

用户反馈

自我进化

评测系统

©- 优秀案例

Prompt优化

国 反馈数据

调度策略优化

28 分析经验

分析路径优化

知识沉淀/ RAG知识库

Agent策略优化

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 024

FlameEye：解决问题

沙盒环境

修复大模型

仓库管理

git、 Ifs、gitlab

分析结论

File —

CentOS

一 Shell

思考

观察

100p

提示词

创建MR

拉分支

修复

验证

提代码

编码管理

Code CLl

大前端研发范式

“沙盒”修复：构建可靠、定制的沙盒环境，赋予AI自由探索和解决问题的能力

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 025

FlameEye： 案例

Klaw.帮我抓一下快手精选页的火焰

图，并用FlameEye分析下卡顿问题，

Trace文件

并直接优化下

好的！正在自动抓取火焰图

Step1：火焰图抓取

Step2: AI分析问题

火焰图抓取成功，开始使用FlameEye

解決问题Pormpt

Skil进行火焰图分析

分析结论

火焰图分析完成，共发现了如下5个性

能问题：***********

自动触发解决问题Skill，已完成代码

修改与MR提交，以下是Review链接；

RMKESIE

幵始妥婪碎燶

文***文*****

Step3：自主代码性能优化

Step4：人工Review

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 026

FlameEye：成果

分析次数

采纳率

业务收益

30% v

5000次

80%

多页面启动耗时

火焰图分析

反馈记录

40% v

多页面发热率

1 用户数150+

持续优化

①

10+业务场景

aCon

InfoQ 极客传媒

全球软件开发大会

## Page 027

FlameEye的Al评测体系

工具能力评价与持续优化

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 028

FlameEye：评测体系-整体思路

评测样本

评测执行

评测结果

人工输

规则评估器

评测指标

equals/ regex加权计分

通过率/ SLA /Token消耗

Prompt调

样本集

脚本评估器

评测记录

整

输入/GroundTruth

JS沙箱/自定义逻辑

分析报告/ 对抗验证/裁判评估

上下文优化

•..

自动生

LLM 评估器

评测复盘

成

万擎，自定义语义评估

失败样本/失败原因

猎手（对抗（裁判

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 029

FlameEye：评测体系-落地方案

评测执行环境

评测结果反哺

人工评估

猎手Agent调用

对抗Agent验证

裁判Agent评估

人工Review

人工审核分析结果后调整分析系统

问题全面分析，找超

问题对抗分析，找子

LLM综合判定，置信

确认有效问题•沉淀

一个

评估结果反哺

超集

子集

结论

通过评估结论迭代预处理步骤。Prompt

BadCase沉淀

异常分析结果沉淀到RAG经验数据库

评测指标

评测结果

Token

指标变

猎手记

通过率

SLA

对抗结

裁判评

性能&成本优化

消耗

化

果

佶

通过指标变化合理调整

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 030

FlameEye：评测体系-案例

05

AIRCVE

Fenicofng

对抗评测

園

比搜高麻事务便突R到70.0Qms- ©AiTinso ticn.：.coman

ancotn.

人工Review

裁判评测

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 031

04

总结和展望

Al时代的工程新范式

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 032

FlameEye：

总结

拆解

发现问题Agent

分析问题Agent

解决问题Agent

逻辑

无死角

问题本质

安全可靠

数据库

规则引擎

仓库管理

多平台。

线上

线下

做功

全方位

多格式编排者

双引擎

合成者

沙盒

覆盖

路径

多场景

优化

场景

大模型引擎

编码管理

评测

它 猎手Agent

× 对抗Agent

◎ 裁判Agent

体系

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 033

FlameEye：未来展望- AI Native时代

90%工作有AI完成

人仅少量介入

—

人与AI深度协同

AI自主闭环（Agentic）

人主导

A辅助

AI自主完成部分环节

AI端到端自主交付

L1:AI辅助

12:AI协作

13:AI主导

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 034

InfoQ 极客传媒

QCon

全球软件开发大会

THANKS

大模型正在重新定义软件

Large Language Model Is Redefining The

Software

## Page 035

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
