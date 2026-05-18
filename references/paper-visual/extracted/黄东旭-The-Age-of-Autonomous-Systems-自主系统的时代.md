# 黄东旭-The-Age-of-Autonomous-Systems-自主系统的时代

> Page-by-page visual information extraction from rendered page images. Text below preserves the visible text recognized on each page; pages with diagrams include every OCR-readable label captured from the image.

## Page 001

InfoQ 极客传媒

QCon

全球软件开发大会

The Age of Autonomous

Systems

自主系统的时代

黄东旭

PingCAP TIDB 联合创始人兼 CTO

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

• 关于我

黄东旭

•TiDB联合创始人CTO，软件工程师/创业者

• Agentic Engineering 推动者和实践者

• Token 日消耗量>100M，峰值>1B

•分布式数据库 TiDB，及其云服务 TiDB Cloud

•新一代 Agent Native Infra 产品线：db9.ai /

mem9.ai / drive9.ai

我世界的源代码

微信扫一扫二维码，关注我的公众号

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 004

• 今天聊点啥？

Coding is （almost） solved

Software is not

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 005

软件的构建

软件的形态

软件的未来

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 006

软件的构建

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 007

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 008

• 计算机发展史：关于抽象的历史

执行载体

思考载体

aCon

InfoQ 极客传媒

全球软件开发大会

## Page 009

• 计算机发展史：关于抽象的历史

计算机诞生之初：

硬件即是执行载体也是思考载体

编程语言诞生后：

硬件：执行载体

代码：表达意图的媒介（工具），思考载体

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 010

•为什么这次不一样？

这次是载体级别的变革。

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 011

• 为什么这次不一样？

代码第一次

从思考载体变成了执行载体

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 012

• 为什么这次不一样？

那个我们所围绕的、作为核心思考载体的“代码时代”

已经结束了。

软件的生产实现民主化。

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 013

•为什么这次不一样？

上一次类似转变对社会产生的产生的影响：

诞生了整个软件行业

这次呢？

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 014

从一个新闻说起

Engineering at Anthropic

Building a C compiler with a

team of parallel Claudes

Published Feb 05, 2026

We tasked Opus 4.6 using agent teams to build a C Compiler, and then

（mostly） walked away. Here's what it taught us about the future of

autonomous software development.

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 015

大概从去年11月份开始：

- GPT 5.2/Opus 4.5

- Codex / Claude Code

Agent 已经能够独立完成长程复杂软件任务

仔细想想，复杂的软件永远可以通过拆解模块以降低局部的复杂

性，所以这意味着什么？

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 016

纯黑盒开发变成可能，我的实践是：已经是现实

3个月/100万行代码 / 基础软件项目/ 已经上线/100% 无人工

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 017

今天的思考媒介是什么？

？

aCon

InfoQ 极客传媒

全球软件开发大会

## Page 018

•今天的思考媒介是什么？

Goal + Context + Constraints

（目标工程）

（上下文工程）

（环境管理）

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 019

• 今天的思考媒介是什么？

Goal: Skills （Superpower, Gstack ...） •.

Context: Harness Engineering / Ralph Loop / RAG / Memory

Constraints: Sandboxes / Environment Engineering / 自动化测

试/CICD/ Lint…

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 020

人与 Agent 的协同模型

Agent（低 entropy / 高频执行）

•实现代码（implementation）

•生成测试（tests）

Human（高 entropy /低频决策）

•运行实验（exploration）

•定义目标（what & why）

•做局部优化（local optimization）

•约束系统

s（constraints / invariants）

•需要设计成持续运行系统

•做最终决策（approval / tradeoff）

•设计架构（system boundary）

•PRD / Spec / success criteria

•环境工程

Agent

Agent

（低 entropy /高频执行）

（低 entropy /高频执行）

Agent之间需要交流，任何工作都需要多 Agent的多轮次迭代

Agent 之间不能共享各自 Context，

但是需要共享项目上下文

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 021

Claude Code

＋

个

claude.aiicooe

个 Add trigger

New routine

Name

Runs asjared@spacetowerdev.com

ZZZ

pr-triage-bot

PR opened

PR merged

Release published

Issue opened

When a pull request is opened against main, fetch the diff and the linked Linear is

files （anything under /payments or /auth）， check for missing tests, and post a thre

hold the review and ping the author.

or choose event

Fires only on Pullrequest:opened

个 Add trigger

Filter （optional）

Trigger this routine from external systems by

｛｝ Active

sending a POST request to the URL below with

code/jared/space-tower

×

+ Add a filter condition

your token.

Without afilten the routine fires on every matching event.

URL

Selecta trigger

https://hooks.routines.dev/r/pr-triage-b..

G

Schedule

Runs on a recurring cron schedule

Token

82

GitHub event

rt_live_8f2CWPMdFrA

Regenerate

日

Runs when a GitHub webhook event fires

Regenerating invalidatesthe previlous token immediately.

Delete the token to disable APl triggering for this routine

｛｝ APL

Trigger from your own code via the /fire endpoint

> Example curl

Connectors

4

Connectors

Done

All connected integrations are included by default. Remove any you don't need for this routine.

Behaviour

GitHub X

Linear ×

Permissions

## Page 022

从1时代的废墟中，有哪些会留下？

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 023

Harness Engineering is still good engineering

朴素的软件工程

复杂性管理

需求分析

项目管理

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 024

软件的形态

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 025

软件使用逻辑变了

过去：

软件的形态是静态的。

程序员设计成什么样，用户就只能

用什么样。

•UI 是固定的

•功能是固定的

•用户路径是设计好的

这意味着什么？

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 026

软件使用逻辑变了

现在：

软件开始没有固定形态了。

UI / 交互不再是核心接口

"意图”才是接口

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 027

• 一个思考题

为什么古老的 UNIX 哲学（CLI）

在当下 Agent 时代又开始复兴？

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 028

• 一个思考题

UNIX从来并不是一个静态的操作系统

而是一套通过组合动态生成软件的体系

< Hide Controls 69 results found

+ DATE

HOST

SERVICE

CONTENT

Dac 14 19-46:24 853| 11-98f3hc6a14fssfca

xisablo/company-profsleffro-

• Mocern bundies are detacted. Modern node （aervar） 13 cnob-

Dec 14 19:46:24.656 1-076738186766918cd wissble/cotpany.profsle/fro-

• Listening on: http://172.17.8.3日：3098/

I Dec 14 18:46:24.5531-8767a8186766318cd

visabln/conpary-prof:1o/fro-

1 Bodorn bundkes ara detectod. Xodern node （snrvor） 15 cnab-

I Dec 14 18:46:23.855 1-00f3be6c15f65fc92

vizsble/company-profsle/fro-

> Sentry regorting i8 onsbled fclient cide: enabled, server.

I Dac 14 18:46:23.437 1-8767a8186366918cd

visoble/compary-profile/fra-

• Sentry roporting 25 onab2ad （cliant sidw: mnabled, servar=

08€④1880.2201 2-0½ 308∞8 0021s4

v1s8b1e/cowpany-protsle/1ro-

s nuxt start

Dcc 14 18:46:21.901 1-00f3bc6c16f65fcsz

wisablc/company.profsle/fro-

yarn run v1.22.5

cat 1og | grep ‘error’I wC -1

VS

09¢ ④ 19 46:2①∞②99

1-a767a8186766019cd

visable/company-profsle/fro-

S nuxt stars

Dec 14 18:46:21.237 1-87673818676691ecd| wissble/company_profsleifro-

yarnrun w1.22.5

1-80f3b86c1ff65fcsz

yts0ble/company-prots1eftro-

1-876798186766918cd wissb1e/compary-profsle/fro-

Ciuster:wv-1-Fanily:w2w-1.-vis80le..company-profile-f-

Dec

78:46:14.669

1-89863835903b13183

visible/compary_profs1effro-

at moxt （node_nodules/connect/1ndex.-15:183:5）

34 10.46:14 669

i-0$3680359e361a186

visable/compary-profile/fro_

at c8l1 （node..nodulesfconnectfindex.j3:239-7）

19:46:14.669

1-89968838903b1a186

| wisable/company_profile/fro-

at nuxtVidclcwara （rado_nadulas/anuxt/sorvor/diat/acrver.js-

a.sewer.tenerkouce tnode.now2e8/enuxe/seendolss/aenve.

visablc/company-profilc/fro-

at YucRendcrer.rendcrRoute （node_madules/Onuxt/vuc-renderer-

09∞ ④ 1④84621④ 63⑨ ①∞④9④63835＄9301135

visable/company-prof:1e/fro-

at norma112eLRL｛nnco_nodu2ea/snuxt/wue-randerer/d1s5/wue-r-

1 Dec 14 10:46:14.669 1-899688859e3b1a186 wisable/cotpany_profile/fro-

at parseURL （node_ncdules/snuxt/vue-renderer/dist/wue-rende-

D9c 14 19:46:14.659

1-89963835903b1a185

04c 14 18:46:14 659 | 1-0996908500351:186

visable/company.profsle/fro_

aCon

InfoQ 极客传媒

全球软件开发大会

## Page 029

• 两个软件的主战场

人类（GUI/行业需求/娱乐/...）：价值驱动

你的行业/工作在这根轴的哪个位置？

机器（数据库/操作系统/云/编译/..）：效率驱动

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 030

• 软件市场从纺锤形向两极聚集，中间的软件市场被挤压

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 031

• 靠近人的一端，正在发生的变革

从 Claude Code 到 OpenClaw 到 Slock

过程舒适（给人的情绪价值）+结果扎实

（传播）

（留存）

下一次革命是人类交互体验的革命：键盘->鼠标->触控平板->？

交互改进的核心：人类的输入（交互）是否能让 Agent 交付更好的结果？

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 032

• 靠近机器的一端，正在发生的变革

Scaling Managed Agents: Decoupling

the brain from the hands

基础软件的逻辑：

Harnesses encode assumptions that go stale as modelsimprove. Managed Agents

-our hosted service for iong-horizon agent work—is built around interfaces that

从给人用->给 Agent用

stay stable as harnesses change.

例子：

•Resou:ces/MCP

从 TiDB Cloud 到 TiDB Cloud Zero

Session

Harness

Sandbox

问题：

为Agent 设计的云服务会是什么样？

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 033

TiDB CLoud Zero

Journeys CLI API

Demo

FAQ

-- VECTOR SEARCH ENABLED --

FOR HUMAN

FOR AGENT

COPY

Database Built

# For Agent

for Agents.

Read https://zero.tidbcloud.com/SKILL.md

and follow the

instructions to create a database using TiDB Cloud Zero.

Lero

sign-up, zero config.

Provision a disposable MysOL-compatible database for AI agents，

MCP servers, and RAG prototypes with vector and full-text

search

in milliseconds.

Source: /SKILL.nd

Task: Create database instance

TRY IN BROWSER

CLI QUICKSTART

Mode: Follow instructions exactly

Expected: Instance ready

aCon

InfoQ 极客传媒

全球软件开发大会

## Page 034

• 以Agent 为中心的软件体验设计

Agent Experience：

• 最小化 Tool Use 摩擦

• 最大化信息密度

•相信模型能力，减少人为设计

例子：

Agent Onboarding

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 035

软件的未来

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 036

• 为什么这次不一样？

上一次类似转变对社会产生的产生的影响：

诞生了整个软件行业

这次呢？

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 037

以 Gstack 为例子，谈谈未来的软件形态

GStack

garrytan/gstack

Use Garry Tan's exact Claude Code setup: 23

opinionated tools that serve as CEO,Designer, Eng

Manager, Release Manager, Doc..

Claude Code

Garry Tan

-〇

• gstack

（Y Combinator CEO）

Claude Code Skills

第一个受到广泛关注的

FROM A SINGLE ASSISTANT

TO A VIRTUAL TEAM

Agent-Native‘软件’

Q）

⑧⑦②0

Gstack 在把 Claude Code 作为操

CEO

EM

Designer

Reviewer

OA

Release

（Rethink Produet） （Lock Architecture）

（AI Slop）

（Find Bugs）

（Real Brovser）

（PRs）

作系统使用

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 038

• Skill的未来

Skill 的问题：

• 结构化程度不足（无法开发复杂 Skill）

• 缺乏可观测/调试性

也许会出现更好的抽象，但是满足以下条件：

• 更复杂更完整

• 自然语言描述，人和机器协同生成

•有一定的结构化，可以 Debug

• 会伴随着环境分发和运行

• 蒸馏人类专家知识

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 039

• 软件的“寒武纪大爆发”

后生动物门类在前寒武纪至

寒武纪大爆发

在不到地球历史

寒武纪过渡时期首次大量出

1% 的时间诞生了

现的重大生命演化事件

绝大多数动物门类

？

？

软件的开发门槛变低/ 灵活性提升

大量长尾需求可以被满足

46亿年

38亿年

5.6亿年

4千万年

5.2亿年

<1%

现在

46亿年

aCon

InfoQ 极客传媒

全球软件开发大会

## Page 040

为什么我们还在讨论编程？

今天以编程作的核心能

力的 Agent 形态是被设

计出来的

7You're

Absolutely

A 社的战略方向：

编程是表达世界和影响世界

Right！

的最通用手段，也是通往

AGI 的道路

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 041

InfoQ 极客传媒

QCon

全球软件开发大会

THANKS

大模型正在重新定义软件

Large Language Model Is Redefining The

Software

## Page 042

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
