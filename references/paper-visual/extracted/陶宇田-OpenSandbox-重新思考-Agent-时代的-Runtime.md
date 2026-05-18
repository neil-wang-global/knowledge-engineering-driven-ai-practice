# 陶宇田-OpenSandbox-重新思考-Agent-时代的-Runtime

> Page-by-page visual information extraction from rendered page images. Text below preserves the visible text recognized on each page; pages with diagrams include every OCR-readable label captured from the image.

## Page 001

InfoQ 极客传媒

QCon

全球软件开发大会

OpenSandbox：重新思考

Agent 时代的 Runtime

陶宇田

阿里巴巴高级技术专家

## Page 002

极客邦科技 2026年会议规划

促进软件开发及相关领域知识与创新的传播

◎6月 ？上海

2 1000人

◎ 8月9深圳

8 1000人

AiCon

•Al Infra 系統工程

AiCon

•Agentic Al

•多 Agent 协作与实践

•秷罼化与高效推理

全球人工智能开发与应用大会

*多桢态融合

*多模态应用

全球人工智能开发与应用大会

*模型训练与推理创新

•Al + IoT 场景实践

（会议时间：6月26-27日

•数据平台与祷征服务

会议时间：8月21-22日

•AI 工业化落地

010月9上海

81200人

012月？北京

R8 1000人

•Al Agent

Qcon

•Vibe Coding

AiCon

•大模型架构创新

•智能可观測

*多模态 AI产业融合

全球软件开发大会

•推理基珊

全球人工智能开发与应用大会

*具身智能

。模型攻防

•Al for Science

会议时间：10月22-24日

•AIx 创造力

会议时间：12月18-19日

•大模型安全

## Page 003

InfoQ 极客传媒

QCon

全球软件开发大会

01

Al Agent 执行环境的新挑战

02

OpenSandbox 的核心设计

03

池化调度与极速交付

目录

04

Agent 场景下的安全执行

05

典型应用场景

06

未来演进方向

## Page 004

AI Agent 执行环境的新挑战

aCon

InfoQ 极客传媒

全球软件开发大会

## Page 005

Agent Workload 的新要求

•需要文件系统、命令执行、服务访

．需要大规模并发交付和环境一致性

• 需要海量短生命周期环境

问和长连接

•单环境冷启动可接受，批量交付放

•希望高吞吐交付，同时兼顾复用和

•Runtime 既要能执行，也要能承

大控制面成本

成本

载 IDE/Browser /Notebook

•必须快速回收，避免评测系统资源

•运行环境本身会影响训练效率和可

•外网访问必须可控，而不是简单的

堆积

重复性

开关

Autonomous Agent

批量评测

RL / 训练

共性诉求：高并发、短生命周期、可控联网、统一执行与统一访问

不同场景的表象背后，是同一组 Runtime 约束被不断放大

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 006

•

为什么传统 Docker / K8s 不够

它们能运行任务，但并不是为 Agent 时代的执行模式设计的

传统容器路径

Agent Runtime 真正需要

批量交付时，控制面写放大明显

统一执行契约

•单环境没问题，批量交付时对象创建和状态同步

•先定义生命周期和执行能力，再决定底层如何承

成本迅速上升

载

•吞吐瓶颈常常不在执行本身，而在控制面协调

•让 SDK 面向稳定抽象，而不是基础设施细节

统一访问与细粒度安全控制

访问路径分裂，交互体验不统一

•HTTP、SSE、WebSocket、IDE、VNC通常分别

•服务访问、联网策略、交互式入口都进入平台治

处理

理

•业务方被迫理解底层端口、网络和暴露方式

•表达“允许访问哪些域名、通过什么入口访问”

问题不在于容器能不能跑，而在于缺少一层面向 Agent 的统一执行模型

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 007

OpenSandbox 的核心设计

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 008

OpenSandbox Architecture Overview （OpenSandbox 架构概览）

Evaluation

Application

Training

App

System

System

Layer

评测系统

训练系统

User Interface

SDK（Python/JS/Java/C#）

cli

~MCP

Ingress

Layer

Protocol

OpenSandbox Server

Routing Layer

Layer

Runtime

Docker

K8s

Layer

Sandbox Control Plane

execd

（sandbox 控制面）

Sandbox

Agent

Instance

egresS

network policy

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 009

• OpenSandbox：从容器抽象到协议抽象

它不是单—Runtime 实现，而是一套稳定的能力边界

SDK Layer

Python /JS / Java/C#/Go 等多语言统一接入

Specs Layer

Lifecycle / Execution / Access / Policy 契约稳定暴露

Runtime Layer

Docker / K8s / Custom Runtime 独立演进

Sandbox Instances

Commands / Filesystem / Interpreter / Services 统一承载

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 010

• 先定义契约，再实现 Runtime

Protocol-First 的目标，不是 API 数量，而是稳定的能力边界

1 Lifecycle Protocol

2

Execution Protocol

• create / get / list / delete

• commands / filesystem / code interpreter

• renew / pause / resume / endpoint

•metrics/ session/background execution

•把环境生命周期抽象成标准接口

•把“进去之后怎么做事”抽象清楚

SDK / 业务

逻辑

Network / Policy Contract

④

Access Contract

•FQDN 级 egress policy

•endpoint +proxy 统一承载服务访问

只感知统一

•统一表达连网能力和约束

• HTTP / SSE/ WebSocket / IDE 一致暴露

sandbox 语义

• SDK 与 Runtime 解耦

•让交互式 Agent 也有统一八口

价值：上层依赖的是 Runtime Contract，而不是具体 Runtime 实现

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 011

12

池化调度与极速交付

Con

InfoQ 极客传媒

全球软件开发大会

## Page 012

•极速交付：Pool +BatchSandbox

从资源预热到批量分配，重构的是交付链路本身

1

2

3

4

？

Pool

BatchSandbox

Sandbox

Optional Tasks

Delivery

维护预热资源，降低从0到

把批量创建环境建模成统一

为评测和训练场景交付成批

按需注入异构任务或补丁，

可用环境的等待成本

对象和批量分配语义

可用的运行环境

支持更复杂工作负载

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 013

•为什么快：优化的是系统级交付效率

不是某个环境启动更快，而是批量交付路径更短

k8s agent-sandbox 交付 100x sandbox

客户比提交请求

APi Server：创建

etcd 持久化

（100个）

Sandboxclaim （100x）

1100x/

传统 K8s 路径

x100

100

交付请求

×100

X100

创速

etcd

从 Poo！选泽可用

AP! Server

SandboxCiaim

Sandbox（100x）

• 创建 N 个资源对象

Client

• N次状态同步与回写

APl Server：更斯 Sendbox

•控制面成本随规模接近线性增长

（月属/标记，秘记，100%）

etcd持久化（100x）

X100

从 PooL选择月用

Sandbox （100x）

Sandbox 资源池

（Sandbox Pool）

更動 Sandboctlaim 状态 （100x）

etcd持久化（100%；

BatchSandbox 交付100xsandbox

100次1次

K8S API Server

BatchSandbox Controller

即时获取100个

OpenSandbox 路径

白白自目

（原子管理）

Ready Pods

曲曲曲曲

Labeling & Claiming

即时获取100个

99%6 交互减少

（打标并划拨）

Ready Pods

（无需100次APi用）

Utmostspeed,no

• Warm Pool + BatchSandbox

wait for Cold Start

• 更少对象写入与更少协调步骤

• 吞吐优化发生在系统交付层

从 Pool选择

可用 Pods

Client： 发送1次

1个BatchSandbox

（100x）

x1000+

批量交付请求

CR（bsbx）

100 1Pod

（replicas: 100，

replicas:100

poolRef=pool-a

创建

99% 交互減少

Custom Resource，

无100次API调用）

Sandbox Pool

原子化管理100个副本

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 014

1A

Agent 场景下的安全执行

acon

InfoQ 极客传媒

全球软件开发大会

## Page 015

•隔离、联网、访问治理三位一体

AI 时代的安全不是简单禁网，而是可控联网与可控执行

Ingress Architecture

Routing Layer

Unified Endpoints

© Egress Controller

Forwarding Layer

Egress Controlier

DNS Query

Agent

Layer 1:DNS Proxy

Auto Renew TTL

Access Audit

Intercepts all DNs

Secure Container Isolation

Layer 2. Network Filter

iptables allow sets

Target Sandbox

1 AoEnt: Worklosd

60 Paent/Worklosd

/etc/resolv.conf

runsc gYisor Runtime）

Faecracker VMM

gVisorsantr

武件劃批代（肉疫洗w）

Hast Ds Keme/推于瓶四政muy

Hardware （cPU.Mcmory/ IO）

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 016

05

OpenSandbox 典型应用场景

aCon

InfoQ 极客传媒

全球软件开发大会

## Page 017

•

实际案例：Autonomous Agent 的执行架构演进

场景特点

长程任务、行为管控、可控联网

Al Agent App

Sandbox

run code

LLM

Jupyter Kernel

OpenSandbox 角色

“运行器”->“运行时工作空间”

（Reasoning）

PrintCHi, OpenSandbox

results

关键能力

生命周期、安全容器、Egress Control

Traditional App

Message Channel

web

create Sanabox，

Sandbox

install claude-code

claude -p "Compute 1+1=2"

guest kernel

Egress Control

Sandbox

Model Provider

Open Claw Gatewoy

claude-code

Claude

agent session-1

agent session-2

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 018

实际案例：Coding Agent 大规模评测架构

评测框架

场景特点

高并发、强隔离、环境一致

OpenSandbox 独立评測环境

result.json

OpenSandbox 独立评測环境

OpenSandbox 角色

提供评测执行层

外部独立 Reporter 模块

解析 resultjson

评测平台，完成上报

关键能力

批量交付、环境隔离、环境可复现

OpenSandbox 提供评测执行层

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 019

实际案例：Agentic RL 后训练基础设施

通过标准化环境申请，批量交付与安全执行，支撑大规模 Agentic RL 训练

RL Framework

Launch tasks

Agent Policy / Sampler

Request environments

OpenSandbox

场景特点

高吞吐、短生命周期、训练闭环执行

SDK

Request environments destroy sandboxes

Sandbox Pool

Sandbox Controller

OpenSandbox 角色

提供训练执行环境层

Atton T / Obseraton ->Revard ！

Secure Execution Environment

Samcboyaii

Sandbox 12

Sandbox #N

Agen

Agenr］

Agent

关键能力

Sandbox Pool、生命周期管理

Enviroament

Environment

• Feregs cnntro

• Flesystem Isclation

•Fllesystem isolation

• Filesystem Isolation

• Runtime Policies

• Runtime Policies

• Runtime Polcies

OpenSandbox / Agentic RL Infrastructure

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 020

未来演进方向

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 021

OpenSandbox 未来演进

从“沙箱运行时”演进到“Agent 执行平台”

K8s Pause / Resume 能力

状态管理

更完整的长会话生命周期管理

Fast Sandbox Scheduling

极速交付

Client-side Sandbox Pool

Persistent Volume / Workspace Continuity

工作区持久化

OSS / NAS / PVC统一挂载能力

OpenTelemetry Instrumentation

可观测能力

Metrics / Tracing / Audit

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 022

InfoQ 极客传媒

QCon

全球软件开发大会

THANKS

OpenSandbox

GITHUB TRENDING

#1 Repository Of The Day

© Stars

Ask DeepWiki

lieense Apache 2.0

pypi package 0.1.5

npm package 0.1.5

CNCr Landstape

DingTalk

Real E2E Tests

Passing

愛 Kubernetes nighdly build （Monorepo） passing

## Page 023

上

探索 AI 应用边界

AiCon

河

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
