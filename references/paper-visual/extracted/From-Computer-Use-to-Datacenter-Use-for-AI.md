# From Computer Use to Datacenter Use for AI

- Source PDF: `references/papers/From Computer Use to Datacenter Use for AI.pdf`
- Visual pages: `references/paper-visual/images/From-Computer-Use-to-Datacenter-Use-for-AI/`
- Extraction mode: visual page-by-page information extraction
- Page count: 23

## Page 001

InfoQ 极客传媒
QCon
全球软件开发大会
From Computer Use to
Datacenter Use for Al
演讲者
谈鉴锋 蚂蚁集团操作系统研发经理
周天昱 蚂蚁集团高级开发工程师

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
881000人
：AlAgent
Qcon
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
引言：AI 开发者被基础设施"劝退"
AKernel 架构：Monorepo + AI 辅助的工程实
02
践
03
开发者体验：像调用本地函数一样使用数据中心
目录
04
一站式部署：一键从零到多云
05
Agent 时代三大技术支柱
06
实践验证与总结展望

## Page 004

引言
AI 开发者正在被基础设施"劝退"
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 005

模型能力日趋强大
大模型推理与 Agent能力持续突破
Computer Use 已经实现
Datacenter Use 才是AI基础设施的终局
模型能力
基础设施使用门槛居高不下
从资源接入、调度器、网络配置到监控体
系—无论个人还是企业，都不可避免陷入
基础设施
开发者体验严重滞后
"Build Your Own Cluster"泥潭
依赖冲突、部署复杂、运维繁重
团队间重复造轮子
开发者体验
AI原生基础设施的三大挑战
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 006

AKernel 的回答
A
Al Native DevOps
Deploy anywhere
All powered by Al，从讲发到部署，
从 single server 到公有云，一键部署
再到监控和问题排查。
Datacenter
A
D
Use
Advanced
Feature
Friendly SDK/CLI
Checkpoint/restore.镜像加速，分布
面向 agent 生态设计，可拓展
式数据存储
F
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 007

）2
AKernel 架构
Monorepo + Al-powered
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 008

AKernel Develop
统一代码库（Monorepo）+ 14 个 Git Submodule
从沙箱运行时、资源管理、网络到SDK与调度，全栈组件集中管理
通过 submodule 锁定外部依赖版本，消除分布式多仓库的版本矩阵爆炸问
题
AI 辅助开发：＜=3 人全栈团队
80%代码由 AI辅助生成，覆盖 Go/Rust/Python/C++ 多语言栈
无传统的需求/研发/测试/运维分工，一人端到端负责，打破“基础设施必须
大团队"的固有认知
L
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 009

AKernel on Public Cloud
镜像中心
VPC
托管 K8s
公网 IP
Traefik
ECS XN
gateway
•Daemonset
8
SDK/CLI
scheduler
proxy
resource collector
User
Client
sandboxd
image manager
Dragonfly PoD
Grafana
Data Worker
stub
Agent/User Code
ebpf-NAT
Prometheus
Sandbox
ENI
OpenYuanrong
OTEL
Opensourced
Tobe opensourced
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 010

02
开发者体验
像调用本地函数一样使用数据中心
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 011

•
Sandbox/FaaS/Spark/..
Sandbox SDK
from akernel_sdk import Sandbox
with SandboxCcpu=2000,memory=4096） as sb：
sb.commands.runC"python train.py"）
•自定义镜像
• checkpoint/restore
• 双向代理（本地 to sandbox, sandbox to本地）
•多种可选的 sandbox运行时（gvisor, firecracker 等）
L
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 012

基于开源标准方案的监控体系
：（metric/log/trace）
实时资源监控
Per-node snapshot
®
host_name S
CPU usage %5
CPU limit （cores） 习
Memory usage %T
Memory total R
/usage %T
/capacity R
akernel-0-0060020
36.4%
48.00
0.6%
1.111B
2.8%
400 GIB
akerne|-0-0060022
36.3%
64.00
05%
1.97 TiB
5.6%
400 GiB
akernel-0-0060021
35.3%
48.00
0.8%
1.11 TiB
2.5%
400 GIB
Sandbox 创建链路 trace
Service & Operation
mOuS
12.86ms
25.73ms
38.59ms
51.45ms
v frontend /serverless/v1/posix/instance/create （48.47ms）
Lo
48.47
x.http.create （48.45ms）
Lo
48.45
v function_proxy yrcreate （14.21ms）
14.21ms
w yr.schedule.forward （11.24ms）
Ko
11.24ms
~ function_master yt.schedule.domain （8.86ms）
Lo
8.86ms
v function_proxy yr.schedule.local （1.08ms）
1.08ms
yr.instance.deploy （1.92ms）
Lco
1.92ms
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 013

nA
一站式部署
Terraform 一键从零到多云
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 014

• 一站式部署：Terraform + Helm,10分钟就绪
Fresh Apply （23:18:27 + 23:27:06,8m39s）
多云 Terraform 模块化部署
已支持阿里云 ACK 与华为云 CCE
阶段
耗时
仓库内置 Skill, claude code 自动部署
Data
souPCeS
~1s
Helm 自动编排核心组件
VPC
6s
所有集群组件 Helm Chart 一键部署
VSwitch
14S
ACK 集群创建
4m16s（256s）
极简运维闭环
Node pool
88s
ak CL: list / delete / exec/...
Namespace + StorageClass
2s
Grafana仪表盘与日志自动生成，开箱即用
Helm 部署
149s（2m29s）
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 015

04
三大技术支柱
Agent 时代的核心基础设施能力
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 016

openYuanrong 分布式调度与数据系统
核心运行时（C++/Python/Go）+函数系统＋数据系统，协
同构成完整分布式执行引擎
数据系统提供高性能分布式缓存，支持跨节点、跨资源类
型的高效数据流动
RL 训练数据高效流通
Agent 多实例间状态共享
Spark 分布式计算
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 017

极致冷启动：AFaaS 安全沙箱（OSD！'25）
10ms 节点侧冷启动，40ms 端到端延迟
性能指标
相较传统容器方案（秒级启动） 提升 2个数量级
nanovisor（gVisor） fork
技术实现
distill-fs （Rust FUSE）镜像按需懒加载
Dragonfly P2P 加速镜像分发
核心应用场景
Agent Sandbox 高并发冷启动（蒸馏、RL、评测、Serving）
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 018

• 状态持久化：Checkpoint / Restore 全链路支持
SDK/CLI
•SDK、调度器到节点端全栈实现，完整
OpenYuanrong 函数系统
覆盖 Agent 生命周期的状态快照与恢
复链路
Node B！
Node A
sandboxd
sandboxd
checkpoint
checkpoint
• Agent 长期待机时挂起释放资源，唤
checkpoint
restore
image
image
醒后从断点继续
sandbox
sandbox
• 应用于多 Agent 长会话状态迁移，带
OpenYuanrong 数据系统
状态的快速启动
持久化云存储
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 019

实践验证与总结
从真实场景到未来演进
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 020

• 典型场景
Agentic RL 全链路（蒸馏、RL、评测）
Serverless Function
Q
P
Spark 大数据处理
\
L
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 021

总结：AKernel 核心价值与展望
Monorepo +<=3人团队+80% AI 辅助，覆盖
Go/Rust/Python/C++多语言栈，为中小团队提供
可借鉴路径
可持续的工程范式
端到端 40ms 冷启动
Checkpoint/Restore
Agent friendly
Sandbox API 开箱即用
2
一键部署，随处运行
基于 Terraform 的多云部署（阿里云ACK +华为云
CCE）+ Helm Chart 一键编排，10分钟从零到可用
集群
3
未来演进方向
XPU 支持
Win/macOS/Android sandbox
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 022

InfoQ极客传媒
QCon
全球软件开发大会
THANKS
让 AI 开发者专注于模型与应用，而非基础设施
AKernel — From Computer Use to Datacenter
Use

## Page 023

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
