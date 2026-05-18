# 陈彪-ZillizTown-基于-Milvus-与-Claude-Code-打造企业版-OpenClaw

> Page-by-page visual information extraction from rendered page images. Text below preserves the visible text recognized on each page; pages with diagrams include every OCR-readable label captured from the image.

## Page 001

InfoQ极客传媒

QCon

全球软件开发大会

ZillizTown

基于 Milvus 与 Claude Code 打造企业版 OpenClaw

陈彪

Zilliz 工程总监

QCon 2026 北京•Agentic Engineering

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

入口在迁移，软件在改变

目录

02

ZillizTown 初见• 4个真实场景

03

技术选型与架构

04

拆解 ZillizTown 内部机制

## Page 004

O1

入口在迁移，软件在改变

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 005

流量入口正在迁移

2025-2026;12个月集中爆发

2025.03

AWS

CLI Agent 发布

30,000,000

2025.08

Sentry

MCP Server 发布

Sentry MCP 月请求量

2025.09

cloudflare

首个远程 MCP Server

以前

2025.10

Snowflake

MCP Server Preview

用户通过浏览器和 App使用软件

•

2025.10

Stripe

MCP + Agent Toolkit

现在

•

2025.11

Vercel

MCP + Agent Tools

用户通过 Agent 使用Skills

2025.12

Databricks

MCP 50+工具

2026.03

Google

Workspace CLI + MCP

aWS

ASENTKY

$motser

2026.03

飞书

Lark CLI 开源，200+命令

stripe

AVerce！

它们不是在做 Agent，而是在为 Agent做接口

不适配 Agent的软件，就像 2010年没做移动端

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 006

OpenClaw 多做了哪一步？

人与 Agent 之间的两段距离

Coding Agent 对比

效率距离

已解决、

Agent

效率距离

物理距离

Agent

电脑

Claude Code

X终端

Cursor

X IDE

Claude Code / Cursor / Windsurf / Copilot 都做到了

但一人还是被困在电脑前面

Windsurf

X IDE

物理距离

Copilot

突破点 大

X IDE/终端

OpenClaw

/IM 接入

被困

IM 接入

随时触达

ZilizTown

/飞书

坐在电脑前

书/Telegram

手 上指挥Agent

Agent 从“程序员专属”变成”所有人可用"

335K Stars

核心原因不是功能多

"×上有人给全家各配了一个 Agent—自己，妻子、儿子”

是触达方式变了

效率距离所有人都在做，物理距离才是 OpenClaw 爆火的原因

这也是我们把展示层建在飞书上的原因

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 007

Skills 是新的 App

传统软件 vs Skills

OReilly 研究数据

维度

传统软件

Skills

+13.2%

开发者

专业团队

一个人就能写

Skills 平均提于

开发周期

月~年

分钟～小时

4x

载体

代码+GUI

Markdown文本

紧凑＞全面

管理

部署/运维/升级

Git + PR Review

alku > oous

」模型+好Skills>大模型先Skills

核心逻辑

用代码固化流程

用文本打包知识

变更成本

高（改代码＋重新部署）

低（改一行就生效）

关键发现

人类领域知识是瓶颈

模型无法自己生成有效 Skills

模型= CPU

Agent = 0S

Skills = App

不需要自己造CPU 和 OS，只需要写好 App

你的领域经验= Skils的原料

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 008

入口在迁移，软件在改变，人的知识是缰绳

这些东西在企业里到底怎么落地？

我们在 Zilliz 内部做了一个真实样本

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 009

02

ZillizTown 初见

先看四个真实场景

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 010

• 场景 1：飞书里的日常对话

话题

话题

彩白：Zillia Town和院系《Bil Cheny的会话

① Avatar 住在飞书里

演讲标题

知S同苦

Agent 取代浏览器：从 OpenClaw 希软件流：入口的范式转移

不用打开终端、不用换 App一私聊或群里@

Ziliz Tovm：翻期 OpenClaw 主瑟

18:09

演讲简介

但好民劑额安分到

过去半年，一个有意思的现象正在发生：Snowtlake. Stripe. Sentry、Cloudflare. Google

都能用

Workspace 安至少8 家主流软件厂商，纷纷给自己的产品加上了CLI和MCP按口，

一不是给

回 Beg lswchens htps:/guubr15.8

人用的新界面，是给 Agent用的。软件的流量入口正在从浏览器悄悄迁移到 Agent。

Zlliz Town: Snowtlake 買最近1，

16:39

OpenClaw 的 310K Stars 不是個然，Cursor i Agent 进了IDE, Claude Code 让 Agent 进了

终端，但人还是得坐在电縮前。OpenClaw 通过 Teiegram 和7书打通了 P2A ｛Person-to-

2 主会话=main Session

Agent）—探作电脂从”坐在电脑前"变成了 发一条消息”，这是它在 Cursor 和 Claude Code

自陈兹（Bil Cher）：PR优码审查通..

昨天

之后还能燎火的关银。

跟 Avatar 单独私聊—持久的主会话，永不驱

本次演讲将从这个趋势出发，脚三件事：入口为什么在变、Skils怎么替优传统软件、以及我

昨天

们在 Zilliz内部是怎么从零搭建 Agent平台并把虾养起来的。会结合真实的工程经验和踩坑教

训，最后有现场 Demo。

R（Bil Chen）： Zendesk Ticket、 而

一、入口在迁移：Agent 是新的浏览器

陈彪 （Bill Chen）： Zendesk Ticket.... 5

•从GUI到对话式交互：不是回归CLI，是又一次抽象层跃汪

3 话题 =独立 Session

•8 家传统软件厂商为 Agent开接口的行业证据与时间线

•OpenClaw 为什么是这个趋势的典型代表：P2A via IM 打通了最后一环

陈彪（Bill Chen）：@陈彪 （Bill Che.. 响

二、软件形态在改变：Skills是新的App

群里每开一个话题=一个独立 Claude Code 进

•"软分叉”：Skills在运行时注入行为，不改底层模型，Markdown 替代组码

程，上下文不串

昨天

•一个真实故事：公司里 CTO、SRE、算法，两位老板各自独立造了自己的养虾软件—软件

开发门槛已经低到人人可造

• Hamness（缰绳）：大模型是概率游戏，CLAUDE.md/Skills /Memory 是你乳服機率的

麻彪（Bill Chen）：@自定义机器人..

三、ZillizTown： 我们怎么做的

• P2A 通道选择；为什么选飞书而不是 Web 或IDE 插件

④ 跨启停连续

•记忆系统：CLAUDE.md MEMORY.md •主题文件 Skills.的层次化架构。以及基于

MemSearch +Zilliz Cloud Mlvus 的长期语义记忆

关掉《书再打开，上下文都在—-resume 机制

Ziliz Tovm：写問报（重新开..

3月22日

• Cron /Heartbeat；传统 Cron 跑和本，Agent Cron 唤一个有判断力的脑子

回蜓话選

Zilliz Tovn： 研究 Zilliztown.

3月22日

同时发送到会话

Aa©

@

密 魚前政导分马］

Avatar 不是 App，是住在你飞书里的同事

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 011

• 场景 2:Agent 自己醒来巡检

① Agent 自己设闹钟

然 ZIllzTown

每介Zii是学的战字分与生后的地方

机器人

E 云文档

取文件

不是人写 crontab一 Avatar 自己调 Cron MCP 创建定时任务

小 口线上微服务异常巡检报告（2026-03-25）Notficsatips

巡检摘要

• P1 问題：2个

•P2问題：5个

•P3/噪音：多个（详见下方）

② 带着完整上下文醒来

P1问题

CLAUDE.md + Memory + 78个 Skills— Agent 醒来时就是一个完整

1. ［CN］ cloud-alert: NPE 导致告鳘订阅失效

的大脑

•现象：NetricAlertorchestrator 拋 NullPointerException，

ALertSubscribeConfig,getEnterpriseonLy（）返回 null

•頻率：02:01 UTC 集中爆发30+次

• LogQL：｛app="cloud-alert｝|~

"NutIPointerException.*getEnterpriseOnLy"

自主判断，不是固定模板

•根困：代码 Bug- BetEnterpriseOnly（） 宇段未设默认值，

Boolean 拆箱时 NPE

•影响：告警汀阅松查流程中断，可能导致用户收不到告警通知

2. ［Global+CN］ cloud-service: CLEAN_INS 用户清理动作持续积

每次巡检的输出不一样—对比昨天、发现异常、给出建议

压

•现象：UserActionServiceSConsumer处理 CLEAN_INS 任务持续失敗并重新入队

•频率：Clobal 积压到 2025-12的任多，CN 积到2025-09

•LogQL: tapp="cloud-servicell］ |- "Failed to process

UserActionDO.*CLEAN INS”

•根因：下游清環接口特续返回销误，任务反复重试无法完成

• 影响：欠费用户实例无法被自动清理，资源浪费

4 独立 Session，不阻塞

P2问题

Cron 任务在独立 Claude 进程跑，不影响主聊天

3.［Global］ cloud-data-service:CopyLoop 任务持续报错

•现象：ECopyLoopProcessor］ forEachExec catch exception +

1oopDealRunningJobs error, cmdId：%s

•热率：每2-3 秒一次，多个 pod

Cron 唤醒的是大脑，不是脚本

*每天99 点自动巡检线上告警

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 012

• 场景 3:Avatar 找 Avatar 帮忙

① Avatar 之间可以互相通信

经过 Hub 路由一Avatar 发现其他 Avatar、发消息、派任务

Zilliz Town 每个Zilliz同学的数字分导生活的地方 机器人

E+

參消思

口云文盛

國 面佩奇 维尼修斯（发出 DM）

Norficalion

•保奇：维尼修斯，这是 PR#4218的完堅信总：

2 按 Skills 找对的人

PR #4218:fix（activity）：use K8s APl direct query in

find_agents（skill="review"）—找到装有 review 技能的 Avatar

patchOperatorDeploymentLabels

• Target: master

• Branch:control_center_biue_green

• Files:2files， +55/-35

• Author: Thor-ChenBiao

问题背景

③ 发消息或派任务

直接换式迁移时，openManualNode依次调用：

1. stopReconcile +OK

send_message 同步对话，create_task 异步派活

2. ensureMilvus -通过 K8s API 创理 deployment OK

3. patchOperatorDeploymentLabels 使用 Informer 緩存 查找 operator

deployment 空列表 静跳斜过

由于 Informer 还没同步新 namespace的 deployment，导致 replica-index label 未被

patch，下游 rolling-standalone_deploy_config 步骤报错 "component deploy

count is not 2"-

4 对方自主判断

修复内容（MilvusDirectlyModeHelper.java， +15/-1）

对方 Avatar 根据自己的角色决定接受、拒绝、或提问

*我的 Avatar 调用同事的 Avatar 做 code review

每个人的能力脱水成 Skills，别人的 Skills 为我所用

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 013

• 场景 4：在飞书里训练 Avatar

① 训练就在飞书里完成

Zilliz Town 每个2i这同学的毁宇分身生活的地方

机路人

Q

巴云文档

文件

不用打开终端、不用碰CLAUDE.md 文件—手机就能训练

③）

我已经在部蛋了，你不用搞了，而且你部署的参数都是错的，你看看我的启动的流水线，学习一

下参数

佩奇 效字分克

2 跟 Avatar 对话就是训练

4个工具调用-47s

纠正它、告诉它用户偏好、分享踩坑经验—Avatar 自己记下来

学到了，关键差异记下来：

我之前的销误：

• GIT_REPO_URL 用了独立仓库 URL（如 cloud-ops.git、cloud-activity-

provider.git）

3 Avatar 自主决定记什么

• 没传 DEDICATED SERVICE NAME

正确参数：

•GIT_REPO_URL = https://github.com/zilliztech/zilliz-cloud.git（统一

不是灌数据—它判断什么重要，写进 MEMORY.md/ topic 文件

用 monorepo）

• DEDICATED SERVICE_ NANE = cloud-ops 或 cloud-activity-provider（通过

这个参数区分服务）

• DEPLOY_REGION = Both （Global + CN）

•SYNC_CN_IMAGE_MODE）= beta-ali-oss

你当前正在跑的两个构建；

④4 训练产物

• #5731- cloud-ops （master > UAT Both）—进行中

• #5732 - cloud-activity-provider （master - UAT Both） —进行中

记忆（MEMORY.md）＋技能（Skills）+工具（MCP 配置）

我把这个参数模式记到memory 里，下次不会再搞错。都记好了、下次部署我会用正确的参

效：monorepo URL + DEDICATED SERVICE_NAME + DEPLOY_REGION=Both +

SYNC CN_INAGE_ MODL=beta-aL1-0SS。

训练的主动权在 Avatar，不在训练者

al tokens in: 1,150,238| out: 1,831| $4.2480| 90.0s•ctx: 24% （240K/1000K）

*对话后 Avatar 自动总结经验，提示将记录到 MEMORY.md

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 014

03

技术选型与架构

我们是怎么选择、怎么设计的

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 015

• Agent 的六个核心技术要素

不管用什么框架，构造一个 Agent 都绕不开这六个要素。建立通用词汇表，后面拆解时对号入座。

上下文窗口

系统提示

技能

01

02

03

Context Window

System Prompt

Skiils

类比• 工作台大小

类比•宪法

类比

•App

单次推理的工作记忆上限，决定 Agent一

始终在上下文的指令，定义 Agent 的身

领域知识包，按需加载用完释放，不常驻上下

次能摊开多少信息

份、角色、行为规则

文

如：Claude 1M tokens,System Prompt 约占

Claude Code: CLAUDE.md（Framework 级+

Claude Code: SKILL.md,description 匹配触

0.6%

项目级＋用户级）

发

工具接口

长期记忆

子代理

04

05

06

MCP

Memory

Sub-agent

类比

• USB 接口

类比•硬盘

类比•子线程

连接外部系统的标准协议，让 Agent 能调

跨会话的持久化信息，会话结束之后 Agent

委派子任务给独立 Agent 执行，不阻塞主

用任何有接口的服务

还能记住的东西

会话

如：飞书 MCP / PagerDuty MCP / Milvus

Claude Code: MEMORY.md，+ 向量数据库（外

Claude Code: Task tool，+ A2A 协作

MCP

挂）

QCon

六个要素，共同决定 Agent 的能力边界。接下来，逐个看 ZillizTown 是怎么做的。

InfoQ 极客传媒

全球软件开发大会

## Page 016

•大模型是 CPU,Agent 是 OS,Skills 是 App

把大脑接上身体—让 Agent 在企业里活起来

传统栈

Agent 栈

我们的选择

3数件屬

App•应用

Skills + MCP

ZillizTown• 78 Skills + 4 MCP

传统栈

Agent 栈

我们的选择

2系締层

OS•操作系统

Agent Runtime

Claude Code•50万行代码

传统栈

Agent 栈

我们的选择

1 算力层

CPU• 算力

大模型

Anthropic Claude•Opus/Sonnet/Haiku

围绕 Claude Code,ZillizTown 补了一圈工具 —不碰OS，专心做 App

飞书触达

定时调度

IM

Cron

Hub + Connector + WebSocket

Cron MCP•Agent 自设闹钟

CC

跨会话记忆

（Mem

A2A

多 Agent 协作

PostgreSQL 持久化

A2A 路由＋任务系统

Claude Code

集体记忆

我们的 Agent OS•基座

Skils 工程化

Vec

Git

Miivus 向量数据库

推理•上下

GitHub 同步+配置即人格

文•Skills• Memory MCP• Sub-agent

QCon

水涨船高

Claude Code 每次升级，ZillizTown 自动受益

InfoQ 极客传媒

全球软件开发大会

## Page 017

• OpenClaw 适合单人，ZillizTown 为企业多人协作而设计

OpenClaw 聚焦单人效率，ZillizTown 聚焦企业协作

单人架构

企业级多人架构

OpenClaw

ZillizTown

335K Stars：最优秀的单入 Coding Agent

既支持单人工作，，又支持多人协作

架构机制

架构机制

• 一条 EventStream

• Hub 中心路由

所有消息、事件、工具调用串成一条线

avatarld - connectorld - WebSocket.精确送达

•层级委派

• Room 共享空间

父 Agent 派子 Agent，子 Agent 不能横向沟通

多个 Avatar 看得见彼此的消息、接力讨论

• 手动 Session

• A2A 对等通信

用户自己点 "New Conversation” 切会话

Avatar 主动找 Avatar，不需要父子关系

• Slack Webhook

• 自动 Session

-个 bot 一个实例.bot 之间互不感知

消息到达系统自动创建，一人可多会话并行

结果

结果

把2个 bot 拉进同一个 Slack群

互相看不见对方的消

10个 Avatar 一个群——自主判断、话题收敛、A2A 接力

息

QCon

做企业的 Agent，多人协作是底层基础设施

InfoQ 极客传媒

全球软件开发大会

## Page 018

ZillizTown 架构：两种视角，同一个系统

左：；逻辑层级，看”哪个是核心"

右：物理流向，看"数据怎么流"

逻辑层级•系统结构视角

物理视角•数据流向

L4

接入层

Access

外部通信入口

Access

飞书 Bot

A2A API

REST Admin

飞书•A2A•REST

WebSocket 长连接

/api/a2a/send•tasks

/apply-contig

WebSocket / REST

L3

个性化层

Personalization

纯配置•定义 Avatar 是溢

Hub

CLAUDE.md

MEMORY.md

Skills

路由中枢•审计

人格指令

前 200行自动加载

-/.claude/skills/

•Websocket

MCP配置

Cron DB

claude.json

cron.db SQLite

Connector

taoPersonalization

每 Avatar 独立进程

配置资源池

L2

运行时层

Connector

每 Avatar 独立过湿，添换 Claude Code

staln stream-json

HubConnector

ClaudeExecutor

SessionManager

WS 客户端＋重连

stream-json: resume

LRU•main 永驻

Claude Code

ProcessSupervisor

CronScheduler

MCP Server

Runtime （0S）

健康检查＋重启

本地 tiCk

Cron•Feishu•Hub•Task

API湯用

中枢层

Hub

准一路血中心，系統基到

Anthropic API

ConnectorManager

ThreadOrchestrator

AvatarRouter

Opus/Sonnet/Haiku

WS连接注册表

Judge 路由决策

requestld 关联

一条消息从外部到推理结果的路径

SkillSyncService

CronService

AvatarManager

GitHub 同步

60s tick 调度

生命周期管理

代外层表象、系统基石

QCon

Hub 是单中心但无状态，Connector 可横向扩展

支撑 100+ Avatar 并发不阻塞

InfoQ 极客传媒

全球软件开发大会

## Page 019

Hub + Connector = A2A 协作网络

N个 Avatar 不是N个工具—是一张 N ×（N-1）条路径的协作网络

注册拓扑•Hub作为能力索引

100个 Avatar 的协作路径对比

SRE

oncall•debug

OpenClaw•层级委派

Doc

Dev

wiki•spec

code,review

N-1

99

树形结构•父一子单向

条协作路径

Data

Hub

QA

sql，分析

注册中心＋能力索引

ZillizTown。 Hub+Connector

Intra

PM

N×（N-1）

deploy、k8s

roadmap

网络结构•任意对等

Design

9,900

UI•UX

条协作路径

每个 Avatar 只连 Hub

OIN 连接，HUD 知道在线•谁有什么Skills

01

A2A 协作

02

集体记忆

治理内生

03

Avatar 主动找 Avatar

组织智慧自动沉淀

Hub 天然的审计/限流/灰度点

• find_agents（skill="review"）

•所有 Avatar 的经验 Milvus

• 权限：谁能调谁（角色/部门）

• send_message（toAvatarld, msg）

• 任何 Avatar 可语义搜索

•审计：所有请求经过Hub

• create_task（toAvatarld, task）

•100人×200对话/天=2万条/天

• 灰度：新 Skill 先推10% Connector

对方自主判断接受或拒绝•human-in-the-loop

从个人记忆到组织智慧•Big Cluster Serving

中心化治理•没有 Hub 企业用不了

QCon

网络价值＞节点价值之和—

-100个 Avatar 不是加法，是乘法

InfoQ 极客传媒

全球软件开发大会

## Page 020

04

拆解 ZillizTown

Agent 的内部工程细节

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 021

让 Claude Code 的 Session 被业务接管、进程被 Hub 托管、行为被Hook 扩

•

展

协议层主动驱动•业务层 Session 管理•进程层长活自愈•扩展层 Hook 注入

业务语义层：Session 管理

通信协议＋业务语义层

01

主动驱动 + Session管理

原生 Claude Code:session 找不回

，UUID忘了，接不回昨天的对话

协议层：主动驱动

，换 cwd.claude -C 找不到之前会话

Headless 模式（-p）

CLI 可编程调用•必须 --allowed Tools 否则静默挂起

ZillizTown:Room + Avatar 自动映射 session_id

stream-json 双向协议

-input/output-format stream-json•NDJSON 事件流•进程长活

•话题（Room） = 持续对话空间，用户只管话题

--resume + JSONL 存储

-/.claude/projects/.../｛session_id｝jsonl•append-only• 崩溃不丟

进程生命周期•24×7可用

侧路护展•AOP 切面

02

03

进程管理：长活• 唤醒• 自愈

Hook注入：memorysearch

Claude Code 原生 Hooks

长活

input-format stream-json 下进程不退出•stdin 持续接消息

SessionStart/End•PreToolUsePostTo olUse•Notification•Stop

唤醒

飞书消息•Cron 到期（独立进程）•A2A 请求 stdin写入

memorysearch：挂在 PreToolUse

自愈

ProcessSupervisor 30s 健康检查•指数退避重启（1s/5s/15S）

① Claude 准备调工具 触发 PreToolUse

② Hook 查询Milvus（语义相似的历史经验）

重试

静默退出（exit 0无输出）一清 session_id 不用--resume 重启

③ top-K 经验注入 context -Claude 带着经验决策

QCon

主动驱动+Session 管理• 进程保活•Hook 挂载

把CLI 升级成企业 Runtime

InfoQ 极客传媒

全球软件开发大会

## Page 022

多 Session 机制：一个 Session 一张 1M 工作台

左：看单 Session 内部装了什么•右：看 Avatar 怎么用多 Session 绕过1M 上限

单 Session 的内部

多 Session 机制

1M token 的物理分配

一个 Avatar •N 张独立工作台

/context

最佳使用方式

Context Usage

claude-opus-4-6［1m］• 649k/1000k

小 Session 解决小问题-

-不让一个 Session 被用完

okens（65%）

Estimated usage by category

a System prompt: 6.1k tokens （0.6%）

Avatar-123 同时运行的工作台

System tools: 4.1k tokens（0.4%）

白容恩

e Custom agents: 813 tokens（0.1%）

session-main-•••

跟 user 持续对话

参 总色

总 Memory files: 78 tokens （0.0%）

主聊天

永驻

1M

Skills: 5.8k tokens （0.6%）

也得已安是部是是定努安是密安影影常思代起

电 Messages: 633.3k tokens （63.3%）

session-thread-abc

"排 线上告警"

B Free space: 317k （31.78）

1M

话题讨论

LRU候选

区 Autocompact buffer: 33k tokens

（3.3%）

MCP tools /mcp （Loaded on-demand）

session-cron:daily

每天9点独立执行

定时巡检

独立进程

1M

Cauce Code 的/context

个 SesS/0n的真买上下文分配

session-dm-456

跟同事 Avatar 私信

A2A 对话

LRU 候选

1M

关键洞察

每张工作台独立IM•sessionld= session-froomldl-favatarld/

• System + Memory + Skills + MCP 合起来不到2%

同 Session 串行•跨Session 并行•LRU驱逐非 main

• Messages 占 63%+•聊越久越挤•压缩=遗忘

QCon

一个话题一张1M 工作合•Avatar 并行 10+张不抢资源•做完一件事就換一张 InfoQ 极客传媒

全球软件开发大会

## Page 023

ZillizTown 的4 个 MCP：补齐企业 Agent 缺的4个维度

深讲 Feishu MCP

它不是对飞书工具的透传，是对业务意图的封装

维度

9个工具

维度

10个工具

维度

维度

6个工具

时间

空间

外部系统

并发

Cron MCP

Hub MCP

Feishu MCP

Task MCP

让 Agent 自己设闹钟•主动干活

让 Agent 找 Avatar•组A2A 网络

让 Agent 主动操作《书“业务封装

让 Agent fork 后合进程•不阻塞

深讲•Feishu MCP的本质

不是对《书 API的透传封装一

一而是把 通知 owner/ 发到我的群/查多人忙闲/建带邀请的会 这些业务意图，变成一次工具调用

业务语义工具•Agent 说业务语言

典型组合场景•多个MCP协作

通知 owner

—一

notify_owner（msg）

告警通知

01 cron 触发 -Agent 查日志 一notfy_owner @值班人

发到我的群

send_to_my_group（msg）

02 請部料金评审” check avaliabaity - Greate mesting

查多人忙闲

feishu_check_availability （ids）

03 自动周报

建带邀请人的会

feishu_create_meeting（...）

Cron 周五触发 一Agent 写内容一create_document八知识库

经 Hub代理•业务封装在Hub

Avatar Feishu MCP >Hub（身份绑定＋消息模板＋token托管） 书API• bot token 只在Hub，不散发到 Connector

QCon

Cron 补时间•Hub 补空间•Feishu 补外部系统• Task 补并发一

-4个 MCP 撑起企业 Agent

InfoQ 极客传媒

全球软件开发大会

## Page 024

• Agent Cron：让 Avatar 表现得更像一个人

不等你开口。观察你。记住你。主动关心你

L1

主动性

L2

L3

不打执

自动创建

有状态执行

有分寸发声

Avatar 观察你•识别行为 pattern•自己调

Session 保持上下文•记得上次做到哪•能区分"

有新东西才说话•没有就静默•像朋友一样知道

cron create，你无感知

已做"和"新事"

什么时候该开口

场景1•自发创建

场景2•有状态＋有分寸

记得你忘记吃早餐这件事

每天扫 Anthropic 博客

•1 你某天随口说，

•1

你况：

"我经常忘记吃早餐"

"帮我关注 Anthropic 动态"

•2 Avatar 观祭到：

•2

Avatar cron_create：

识别出这是稳定的行为 pattern

“每天 9:00 扫博客，记录已收录列表”

Avatar 自己创建 Cron：

•3

每天9:00 Cron 触发：

cron_create（"每天8:00提醒"）

Avatar 读记忆—>知道哪些已收录

•4

从此每天 8:00：

•4。

发现新文章，

默默发一条"早安，记得吃早餐"

下载+记录＋推送

你说“今天提前吃了”

•5 沒有新文章.

Avatar 感知一当天跳过

30 天燒點耍史醛3天有新东西时说话

你从没说过“帮我没定时任务”

技术支撑：CLAUDE.md是 Avatar的心心“动关心的指令CronMCP是“于（创建任务的工具），Session上下文是“记忆“（有状态执行）

QCon

Avatar 因此更像一个人——观察你、记住你，主动关心你

InfoQ 极客传媒

全球软件开发大会

## Page 025

•

配置即人格＋自我进化：人格是三层配置的叠加

骨架定义（CLAUDE.md）•能力外化（Skills）•规则约束（MEMORY.md）

- 下面两层 Avatar 能自己改

自我进化

L1

CLAUDE.md

骨架•定X Avatar 是谁

Avatar 自己改自己

POST /api/avatars/｛id｝/apply-config

系统保护部分

用户自定义部分

Connector 每次启动强制校验•不可被改

他是谁•擅长什么•个性化指令

能自己改

核心框架：行为规范，记忆策略

角色＋专业＋性格＋特珠指令

1. L1 用户自定义部分

update_claudemd

- 调性格/规则.

2. L2 Skills

L2

Skills

能力的外化•人格的专业身份

install_skill / remove_skill

学新能力

3. L3 MEMORY.md

装什么 Skills，就成为什么人—专业身份的体现，不只是工具

日常自动追加＋写入强规则

装 review/ code-map 代码 review Avatar

装 milvus-testing 测试 Avatar

装 oncall-diagnosis SRE Avatar

装 copywriting 品牌 Avatar

x Connector 守住的底座

L3

MEMORY.md

规则＋记忆•运行时形成的铁律

L1 系统保护部分— 每次启动强制校验

能学技能：改性格，写规则但核心框架不可动

不只是记事—承载强制行约束，比 CLAUDE.md 更动态

强制规则：“个人隐私问题拒绝回答”，“财务数据需 owner 确认”

透明重启流程

日常记忆：用户偏好•踩过的坑•项目状态•人物关系

写配置一kill +-resume 一上下文恢复一新能力可用

用户无感知Avatar 自然说“装好了，可以用”

QCon

像人一样被定义（CLAUDE.md）、被训练（Skills）、被约束（MEMORY.md）|

InfoQ 极客传媒

全球软件开发大会

## Page 026

Training 机制：实时 • 智能•无感

训练的物理意义：改 CLAUDE.md / Skills / MCP / MEMORY.md-

—过程在对话里，用户无需切换界面

Training 到底在 training 什么？改四个配置点，对应 Avatar 的四种能力

CLAUDE.md

骨架

SkilLs

能力

MCP

手

MEMORY.md

约束+记忆

身份 /角色/ 行 规则

领域知识/工作流

外部工具接入

强规则/日常积累

三大特点—让 Training 实时、智能、无感

01 实时在线

AI 智能审核

无感重启

02

03

在飞书对话里训练

Training 过程本身是A/任务

自动加载，无感知

不切工具• 不上传文档•不进Web UI—

Avatar 不是机械地”照搬进文件”，而是分

写配置—>kill +--resume — 上下文恢复一

—直接在对话里说。

析•评估•决定。

Avatar 继续对话。

例如你说：

Avatar 做的判断：

用户体验：

"以后遇到告警先查Loki 再看 Prometheus"

适合放哪？•跟已有规则冲突吗？•会破坏核

Avatar 自然说"好，以后这样做"

心能力吗？

Avatar 理解一自动决定写到 MEMORY.md 规则区或

生成结构化 action 一写入对应配置文件

没有"切换管理界面/等待加载/重新连接”的割裂感

做成 oncall Skil

训练和使用是同一个界面，没有“训练模式”

Training 有 A参与，用户只管表达意图

像跟人说“以后这样做”，他说"好”，然后真这样做

QCon

实时在线•智能审核•无感重启——训练就发生在对话里

InfoQ极客传媒

全球软件开发大会

## Page 027

群消息收敛：让多个 Avatar 像一个团队

第一层 LLM 自主判断（SKIP/REPLY/THREAD）•第二层话题硬路由锁定一

-多 Avatar 不吵闹

［SKIP］•静默

［THREAD］•开话题

用户明确要求•Avatar 响应并开话题

用户三次 @：Avatar 二次已读不回

9円

Al小队271白6

◎消泉

熟云文档

•群公告

文件：

本Pin+

海巴綠，疫设活吧：不用鸡者了，親原在鸡滅标，职在效豬便總点儿修证類旅注在熱。◎

ttention is all you need.

姆巴佩你能憋的住不说话吗

◎

姆巴佩 cloud-ops 是中外隔离的服务

【經巴】在线，有缩要帮忙的孩术问盟荡时说。

◎

在线。有需要帮忙的技水向蹉顾时说。

”姆巴復说话吧，我们都想跟你那期 隨便統点儿陆◎

第一层

第二层

自主判断• LLM 推理

话题锁定•硬路由

Avatar 基于 CLAUDE.md（角色/专业/性格/输出三选一

-旦开了 THREAD•这个话题就锁定给 Owner

［SKIPI

不是我的领域，静默

Avatar 判定 【THREAD」 创建 Thread Room

“姆巴佩你能感住吗”•姆巴佩静默

［REPLY］

简单回一句

问候，感谢•短问题，不开话题

room.created_by_avatar_id = Avatar•锁定 Owner

LTHREAD］

开话题，深入讨论

“我在测你说点话”•姆巴佩开话题

后续话题内所有消息一 只路由给Owner

其他 Avatar 不再收到——从"广播“到”定向”

QCon

像团队里的人一样懂得收敛——会抢活也会静默

InfoQ 极客传媒

全球软件开发大会

## Page 028

• 记忆有分工• 搜索也有分工

短期记忆常驻•长期记忆按需— 各自对应不同的搜索形态，共同构成完整的记忆系统

记忆的分工•两层各司其职

短期记忆

长期记忆

MEMORY.md + CLAUDE.md

Milvus 向量数据库

工作合上的便签•每次启动自动注入

硬盘上的档案库•按需语义检索召回

容量 上下文预算内•2%左右

容量 无限•跨会话/跨 Avatar 沉淀

加载

每次 Session 启动自动注入

加载

语义检索•top-K 注入上下文

适合存 当前对话规则•用户偏好•近期状态

适合存 历史经验•全公司知识•集体沉淀

搜索的分工•三种形态并存，不互斥

传统 RAG

Skills RAG

Agentic Search

01

02

03

被动•一次性

浙进式披露•按需加载

自主决定•基于向量检索

流程

流程

流程

用户查询 检索文档 拼进 prompt 一生成

Agent 匹配 description — 加载全文一执行一释

Agent 自主决定搜什么 Milvus 语义检索 一注入

放

上下文

触发

用户主动提问

触发

Agent 识别到匹配的业务场景

触发

Agent 基于上下文主动发起

搜什么

外部文档•知识库

搜什么

Skill文件：工作流知识

搜什么

历史经验•集体记忆

QCon

短期记忆 ＋长期记忆• 三种搜索形态—不是替代，是分工

InfoQ 极客传媒

全球软件开发大会

## Page 029

• 集体记忆：从个人经验到组织智慧

所有 Avatar 的经验汇入同一份 Milvus 存储—个人记忆自然变成组织共享的知识

带来的业务价值

群体记忆的形成

N 个Avatar• 一份 Milvus Collection

新人上手

从第0天调用前人踩过的坑

SRE

Dev

QA

Data

Ops

oncall

架构

测试

数据

运维

不重复踩坑

一个人踩完•所有 Avatar 都知道

知识不流失

03

老员工离开•经验留在 Milvus

Milvus Collection

跨团队协作

集体记忆存储

04

Avatar 自动检索其他部门经验

每个 Avatar 自主写入•任何 Avatar 都能搜索全员经验

一份数据，两种视角

个人祝角搜自己的 Partition•公司视角搜整个 Collection

个人视角

公司视角

Partition Key =员工ID•只搜自己的经验

搜整个 Collection•整合全员经验

我们在 Milvus 上建了双图索引兼顾两种视角的召回—下一页用客户案例展开

QCon

个人记忆是点，集体记忆是网

Agent 让知识从点变成网

InfoQ 极客传媒

全球软件开发大会

## Page 030

•真实客户案例：C端 AI产品服务百万用户

—家头部 AI To C公司（Zilliz Cloud 客户）•*M+用户•Milvus 三级多租户已验证

客户业务场景

规模数据

AI To C+语义搜索

1.5M+

170+

• 硬件＋云端•会议/通话随手录

用户

国家

• 自动转写+AlI 摘要•112语言

1M+

$180M

• 对历年录音做自然语言搜索（RAG）

设备出货

ARR

Milvus 多租户三级方案•面对百万用户时该怎么选？

Level1 •Physical

Level 2• Logical

Level 3•Row-level

Database 隔离

Collection 隔离

Partition Key 隔离

每租户一个独立 Database•物理完全隔离

每租户一个 Collection•元数据分离

共享 Collection•partition_key 区分

隔离性

极高

隔离性

中等

隔离性

逻辑隔离

资源开销

极高

资源开销

中等

资源开销

极低

适用场景

VIP 客户

适用场景

元数据压力大

适用场景

海量长尾用户/

客户的选择：Partition Key—1.5M 用户下，只有Level 3 扛得住

配合 Resource Groups（计算资源隔离）：VIP用户绑定独立 QueryNode，避免 Noisy Neighbor

QCon

同样的架构•一家公司100人能用•1.5M 用户也能用

- Milvus 多租户的复利

InfoQ 极客传媒

全球软件开发大会

## Page 031

Partition Key Isolation：每个租户一张小图

多租户场景下，一张大图的召回会被跨租户边稀释— 按租户拆成独立子图，召回质量显著提升

默认方案

Isolation 方案

一张大图 • Collection 级 HNSW

每租户一张小图•独立 HNSW 子图

所有租户的向量连通在一张图里

按 Partition Key 拆分租户之间完全隔离

Tenant A

Tenant B

Tenant C

•

•

跨租户边连通，不同租户节点混在一张图

图内只有本租户节点•路径直达•零跨租户噪声

X 搜租户 A 时，路径经过 B/C节点

路径直达•不经过其他租户节点

X 过滤非目标租户后，图不连通

/ 图连通性好•召回质量显著提升

X 冗余扫描 召回下降＋性能损失

消除冗余扫描，搜索性能大幅提升

开启方式•Milvus 配置

schema.add_field（field_name='tenant_id'，is_partition_key=True， •.）

client.create_collection（

schema=schema,num_partitions=128，

properties=｛'partitionkey.isolation'： True｝）

关键限制

底层机制

适用场景

•filter 必须是单 PK 精确匹配

•按 Partition Key 分别构建子图（MV）

•百万级多租户 SaaS

•IsOlation 开启则直接去掉 base grapn

•总是按单租户搜索

QCon

大图保全局•小图保租户一

Partition Key Isolation 的本质

InfoQ 极客传媒

全球软件开发大会

## Page 032

InfoQ 极客传媒

QCon

全球软件开发大会

THANKS

Agent Engineering

Questions are welcome

陈彪• Zilliz 工程总监

个人微信

QCon 2026 北京Agentic Engineering

## Page 033

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
