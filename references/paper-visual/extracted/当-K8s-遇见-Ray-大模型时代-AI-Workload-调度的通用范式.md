# 当-K8s-遇见-Ray-大模型时代-AI-Workload-调度的通用范式

> Page-by-page visual information extraction from rendered slide/page images. Text is OCR-assisted and preserves visible page order; diagrams/tables are represented by their visible labels and relationships as line-by-line text.

## Page 001

InfoQ 极客传媒
QCon
全球软件开发大会
当K8s遇见Ray
大模型时代 AIWotkload 调度的通用范式
宋顾杨
腾讯TEG Ray引擎负责人
Ray开源社区Committer
李冲 博士
腾讯 高级工程师
Ray开源社区调度专家

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
AI 基础设施技术栈发展趋
01
势
02
Ray-based Al workload 调度
03
K8s + Ray 调度通用范式
目录
04
K8s + Ray 在腾讯内的落地实践
05
未来展望

## Page 004

Tencent
Al基础设施技术栈发展趋势
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 005

Tencent
Open Source Landscape
- Model Training, Development and Serving
Serving
3ollama
LLMOps
Inference Deploy
NVIDIA Dynamo
& Xorbits Inference
3s ramalama
GPUStack
mlflow
Inference Eng！
VLLM
&SGL
nVIDIA
TensorRT-LLM
OpenVIN®
LLaMA爸
① 1Panel
Training
© Langfuse
swift
Fine-tune
unsloth
LLaMA-Factory
Reinlorce Learning
verl ©PENRLAF
mAReaL
Weights & Biases
AlInfra
Paddle
Distributed Training/
nVIDIA
Megatron-LM
Copik
Training Platfo！
◎
PyTorch
deepspeed
②
nVIDIA
NeMo
Phoenix
Distributed
ERAY
spairk
APACHET
compute
VOLCANO
MLRunS
promptfoo
Al Kernel
RAPIDS
TransformerEngine
Flashinfer
Library
Al Compiler
Triton Modular
FlashAttention
ML
mon CUTLASS
W DeepEP
Dagger
github.com/antgroup/llm-oss-landscape
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 006

Tencent
Ray-based Infra
Agentic f-
Data
Pre-
Post一
Serving&
LLM apps
Controller
SkyRL-v0.1
Training control flow
Processing
tralning
training
Inference
& Agent
Generator
Model rollouts （actions）
Trainer
InferenceEngine
Environment
Backends：
VLLM
Trajectories
& Rewards
Bao
Environments：
Pytorch
VLLM
SkyRL-Gym
Policy Model
IAPI
Bring
Parameters
your
PyTorch
Policy Model （Agent）！
Policy Model （Agent）
Search, SQL
own！
Environment feedback
Ray
（observarions, rewards）
Ray Train Ray Serve
Data
Ray
Ray Core
Pod 1
Pod 2
Pod N
K8s
K8s
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 007

Tencent
VLLM + Pytorch + Ray + K8s
SIMON MO
JOE SPISAK
DAWN CHEN
ROBERT NISHIHARA
LEADIVULM
DIRECTOR OF PRODUCT MANAGEMENT I META
SOFTWARE ENGINEER | GOOGLE
CO-FOUNDER | AMYSCALE
VLLM
OPyTorch
RAY
Ray Summit 2025
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 008

Tencent
社区活跃度
5年趋势
2021-2025 年度 Commits 趋势图
』年度Commits统计详情
10000
9037
8627
项目
2021
2022
2023
2024
2025
总计
• VLLM
8000
7511
7169
7082
7137
Kubernetes
9,037
7,169
7,511
7,082
7,137
37,936
• Kubernetes
Ray
3,988
4,680
4,766
3,195
5,136
21,765
6000
5136
4680
4766
• Ray
Flink
4,085
3,218
2,036
1,734
1,096
12,169
3988
4000
4085 •
3762
4085
3218
4109
3410
• Spark
Spark
3,085
3,218
4,109
3,762
3,410
17,584
3218
3361
3195
2036
2000
1734
1808
WLLM
614
3.361
8,627
12,602
• VERL
614
•Flink
50
1096
VERL
50
1,808
1,858
2021
2022
2023
2024
2025
年份
•WLLM：增长最迅猛，2025年达到8,627commits，显示出极高的社区活跃度
•Ray：保持高位稳定，持续活跃，是 AI 基础设施的重要组成部分
•Vetl：作为新星项目，2025年实现爆发式增长，潜力巨大
•Spark：表现稳健，作为大数据领域的基石，维护力度依然强劲
•Kubernetes：从高速扩张期过渡到成熟稳定期，社区持续活跃（年均7587commits）
•Flink：星现明显下降趋势，进入成熟稳定期，开发重心可能转向维护
QCon
nroo
馗极客传婃
全球软件开发大会

## Page 009

Tencent
More Open Source project
Data-processing
Pre-training
Post-training （RL）
Serving & inference
LLM-apps & Agents
Data-Juicer
电PRover
A
veRL
VLLM
ROCK
5.8k
* 1.6k
*18.6k
* 50k+
318
Daft
Ray Train
OpenRLHF
AIBrix
Agentic-Ray
* 5.1k
Built-in
*8.9k
* 4.6k
100+
inel kaylr
SLIME
Ray Serve
Syftr
56③
*3.5k
Built-in
*326
DeltaCat
AReaL
* 267
*3.4k
Cosmos Curate
ROLL
* 137
* 2.7k
Ray
NeMo Curator
SkyRL
K十
*1.5k
周下
裁量
Ray Data
NeMo-RL
趋势
Built-in
* 1.3k
Powered bygRAY
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 010

Tencent
•
Ray 国内落地情况
日 核心场景：多模态数据处理（国内头部科技公司广泛使用）
蚂蚁
阿里
Iail ByteDance
2 HUAWEI
Tencent
小红书
深度求索
月之暗面
强化学习 （RL）
心 在线推理（Inference）
◎ 云服务（Cloud）
蚂蚁
阿里
蚂蚁
Ii ByteDance
字节
阿里
Iu ByteDance
字节
Ie ByteDance
字节
Tencent
腾讯
HUAWE
华为
Tencent
拇讯
HUAWEI
华为
Tencent
腾讯
|蚂蚁集团特色场景
•其他细分场景
• 在线学习
C 图计算
Agent Sandbox
阿里巴巴
搜推离线索引
隐私计算
bilbkain
预训练（Pre-training）
Biibii
流批一体（Streaming/Batch）
小红书
Powered Dyg RAY
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 011

Tencent
02
Ray-based Al workload 调度
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 012

Tencent
Al Workload： 多模态数据处理
异构资源
• CPU 密集型：抽帧/格式转换
GPU 密集型：OCR/ASR/模型推理
批
量
数
CPU
GPU
GPU
CPU
预处理
预处理
模型推理
Output
据
动态分配
• 各阶段动态调整资源量/并发度
• 背压感知 +自动扩缩
Resource Pool （CPU + GPU + memory）
高容错
• 局部故障：OOM.， GPU error, pod 回收，etc.
• 局部故障 Pipeline 重启
• 容错粒度：Stage/Pod/进程
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 013

Tencent
AI Workload： 强化学习
Actor
多角色
Gen
• PPO: Actor, Critic, Reward, Reference
• 独立的运行时，进行策略，资源需求
Ref
RM
Critic
多个异构角色（Runtime * Parallelism * Resources）的协同调度
Fwd
Fwd
Fwd
②
非线性流水线
• 任务在角色间多播传递
Actor
Critic
【raining
Training
HybridFlow：
A Flexible and Efficient RLHF Framework.
EuroSys 25
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 014

Tencent
•
Al Workload： 强化学习
Multi-Controller （SPMD）
• 用于主流分布式训练框架（FSDP,Megatron，
etC.）
•
同构进程，
同步 Barrier，集合通信
Single-Controller （MPMD）
低灵活性
•
中心 Driver + 异构角色
自然表达异构角色
中心 Driver：全局视角，统一编排跨角色任务流
•
角色内部保持 SPMD
•
角色粒度独立容错
低容错
然单点故障 ~通信组崩溃
• Pathways: Asynchronous Distributed Dataflow for ML, Proceedings of 5
MLSYS Conference
无全局视角
• HybridFlow: A Flexible and Efficient RLHF Framework, EuroSys'25
＜ 跨角色编排任务流
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 015

Tencent
• AI Workload： 调度需求
异构资源
• 管理与调度CPU、GPU 等多种异构计算资源
动态分配
• 根据实时负载，动态分配计算资源
高容错
• 局部故障不影响全局任务，自动重新调度＋恢复状态
Single-Controller
• 原生支持 MPMD，统一编排任务流
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 016

Tencent
Ray： 编程 API 示例
def mainC：
中心 Driver
ray.init（）
cray.remote
定义（异构）角色
CLass RolloutWorker：
def generate（self,prompt）：
return "Hi there"
remote_worker = Rolloutworker.options（
num_cpus=2，
（异构资源需求）
num_gpus=1，
） remote（）
创建远程计算单元（进程级））
response = remote_worker.generate.remote（"Hel1o"））、（远程调用（編排任务流））
QCon
InfoQ极客传媒
全球软件开发大会

## Page 017

Tencent
Ray：调度能力
异构资源
动态分配
高容错
Single-Controller
def main（）：
中心 Driver
ray.init（）
@ray.remote
）
定义（异构）角色）
class RolloutWorker：
def generate（self,prompt）：
return "Hi there"
remote_worker = RolloutWorker.options（
num_cpuS=2，
异构资源需求
num_gpus=L，
）.remote（）
response = remote_worker.generate.remote（"Hello"）
远程调用（编排任务流））
QCon
InfoQ极客传媒
全球软件开发大会

## Page 018

Tencent
Ray：调度能力
异构资源
动态分配
高容错
Single-Controller
init_group_size = 10
@ray.renote（num_gpus=1，（max_restarts=-1）
自动重启）
CLass RolloutWorker：
def
init_
（self）：
1f ray.get_runtime_context（）.was_curFent._actor_reconstructed？
重启时恢复状态
self, recover state（）
（rollout_group = ［Rolloutworker. remote（） for _ in range（init_group_size）］
创建 Worker Group/
while True：
# Need to scale up
动态调整 group size，
rollout_group.append（Rolloutworker.remote（））
创建更多计算单元
Con
InfoQ极客传媒
全球软件开发大会

## Page 019

Tencent
Ray: Driving RLHF Workload
Ray Driver：编排/分发任务 Jecorated by ray.remote
Driver Process
WorkerGroup
Resource Pool
Call API
Actor
Worker O
Worker 1
异构资源调度
Receive Future
Call API
Critic
Worker O
Worker1
GPUO
GPU1
Resource Pool O
Receive Future
CallAPI
Rollout
Worker O
WorkerL
GPU 2
GPU 3
Resource Pool 1
Receive Future
Call API
Reference
Worker 0
Worker 1
GPU 4
个
Policy
GPU 5
Resource Pool2
Receive Future
CallAPI
Reward
Worker0
Worker1
Model
Receive Future
https://verl.readthedocs.io/en/latest/hybrid_flow.html#overall—execution-diagram
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 020

Tencent
Ray: Overall Architecture
调度
远程调用（gRPC/RDMA）
创建计算单示（讲程）
调度策略：
Worker None
Woiker Node
Driver
Worker
Worker
Worker
Round-Robin
堆叠水位
Object Store
Obyect Store
（Shared Memorv）
（Shared Memory）
Node Affinity
• Label Affinity
Raylet
Raylet
• Gang Scheduling
• Data Locality
Head Node
Global Control Storage
Dasnpoara
集群元数据管理
Backend Storage
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 021

Tencent
分布式计算引擎对比：调度能力
Spark
Flink
PyTorch
Ray
计算范式
BSP
流式
SPMD
无范式
（批处理）
（通用分布式）
异构资源
右吸
支持
（进程粒度异构资源需求）
Ray： 最大程度满足 Al workload 调度需求
动态分配
支持
（静态 DAG）
（静态 DAG）
（静态通信组）
（动态创建/销毁进程）
容错
粗粒度
粗粒度
粗粒度
细粒度
（RDD Lineage 重算）（Checkpoint回滚）
（整组重启）
（进程级重启）
Single-Controller
支持
支持
不支持
支持
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 022

Tencent
K8s +Ray 调度通用范式
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 023

Tencent
Ray： 部署方式
SUNIT Ray on HyperPod Architecture
SUMMITT
Ray on Kubernetes: Distributed OS for AI/ML
Angpcale and Goog/e tays purtnared ta enable the maa
intsgrated platform tor uouir produetion workleadm
Rau distributed apolications on GKE
• High-petormanoe ateace.networking. ana
AWS
Microsoft Azure
Google GKE
国外三大主流云厂商齐聚Ray Summit，探讨 K8s + Ray 云服务
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 024

Tencent
• Ray：生产环境快速落地
需要 K8s 作为底层基础设施
大规模资源池统一管理
容器化部署、服务发现、存储编排
监控、运维、权限体系
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 025

Tencent
• K8s & Ray： 职责分工
K8s
Ray
定位
集群基础设施层
应用计算引擎层
资源管理
大规模物理节点资源
Ray cluster（pod 组网）资源
生命周期管理
容器/Pod
Worker 进程
调度
Pod 一 物理节点
Worker 进程- Ray Node （Pod）
弹性
Cluster Autoscaler
Ray Autoscaler
接口
YAML 声明式
Python 编程式
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 026

Tencent
K8s & Ray：协同调度
K8s：分配资源给 Ray
Al Workload
Data Proc
Inference
Training
Ray：分配资源给任务
Ray Scheduler
KubeRay Operator： 连接 K8s 与 Ray 的
Ray Cluster
桥梁
Head Node
Worker Node
CRD
功能
描述
RayCluster
集群管理
明創建金製會品看琴.管理 Pay node对应的
KubeRay Operator
RayJob
作业管理
自动创建 RayCluster 一 提交 Job 一执行完毕一
自动回收集群。适合批处理/一次性任务
K8s Cluster
Physical Resources
RayService
服务管理
部署 Ray Serve 在线服务，支持滚动升级和流量管理。
（CPU/GPU/MEM/Disk，
适合在线推理
etc.）
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 027

Tencent
K8s +Ray 在腾讯内的落地实践
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 028

Tencent
腾讯 TEG Ray 平台架构
多模态数据管道
强化学习训练
在线PD分离推理
广告样本与训练
因果推断
ComfyUI
数据平台
机器学习平台
通用分布式
通用分布式
通用分布式
Ray 调度内核
数据处理
训练
在线服务
Ray Data
Ray Train
Ray Serve
DAGFlow
分布式调度
异构调度
数据面调度
Iceberg
离在线一体
开放湖仓
故障检测
负载均衡器
流式处理
自动续训
服务发现与编排
峰峦
单层联邦调度
双层联邦调度
全局智能调度
kuberay 联邦调度
K8S 云原生架构
CPU、GPU、 XPU••
GPU 在离线混部
弹性、潮汐资源
QCon
InfoQ极客传媒
全球软件开发大会

## Page 029

• 云原生联邦架构
Tencent
峰峦 K8s 联邦架构
虚拟集群统一接入
腾讯内云原生环境特点
apiserver
峰峦联邦方案：单层/双层调度，
支持
workload
不同业务场景
-大规模云原生基础设施通常存在联邦架构
controll
pods
aggr-apiserver
policy
- 生产环境存在上百个 K8S 物理集群
scheduler
workload-
workload
translator
scheduler
proXy
-CPU算力和GPU算力的物理集群隔离
apiserver
syncer
workload-syncer
- Data平台和AI平台底层两套基础设施
GPU集群
GPU 集群
CPU 集群
CPU 集群
CPU 集群
CPU 集群
CPU集群
GPU集群
CPU 集群
CPU 集群
CPU 集群
CPU 集群
Ray落地挑战：融合计算的范式与算力基础设施的矛盾
GPU集群
GPU集群
CPU 集群
CPU 集群
CPU集群
CPU 笑群
- 〝CPU +GPU”统一调度难
AI资源
大数据资源
低优算力资源
统一资源湖
“数据处理+推理”融合计算难
>
统一管理高优、低优、异构资源
多种手段挖掘在线空闲资源，进一步扩充资源
在线资源
“Data + AI统一平台难
QCon
nroo
遵极客传婃
全球软件开发大会

## Page 030

Tencent
云原生联邦架构
核心需求是要实现Ray跨K8S集群的联邦调度
创建Ray集群
创建Ray集群
创建Ray集群
平台
平台
创建Deployment
创建Ray Cluster
Ray Cluster
国89
国89
二层
Ray
调度
Cluste
K8S-CPU集群K8S-CPU集群28S-GPU集群
K8S-CPU集群K8S-CPU集群X8S-GPU集群
K8S-CPU集群K8S-CPU集群8S-GPU集群
二层调度方案
standalone组网方案
kuberay联邦
放弃kuberay，
形成了“K8S +中
间层 + Ray
三层调度系统，
复杂
放弃kuberay
继承原生kuberay的Cluster/job管
度增加
理、
autoscaling.history server管
理等能力
X
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 031

Tencent
•
云原生联邦架构
新一代架构
基于 virtual kubelet 的架构
Kuberay 联邦架构
wedata欲据平台
太极AI平台
wedai数据平台
太极A平台
autoscaling Quota校业
RayService
统一 Service
Quota管理
蜂呇
RayCleter
scheduler
创建服务
峰峦单展租户乘群
峰峦双层管控面
服务1
服务2取务8
演进
Kuberay
RayCusiar
HayChuster
scheduler
GPU您理集群
SPU物理集跬
»
kuberay
Heed］ Pod••Fod
VK
Ray联书紫荐
Pod
CPU物理结料
GPU牧理集萃
• Data Infra、 AI Infra 分离架构
• 最大瓶颈：一个Pod 对应一个AI 服务
• Data + AI Infra 统一架构
• 最大支持2k卡
• 支持1w 卡以上
（规模提升5倍＋）
QCon
InfoQ极客传媒
全球软件开发大会

## Page 032

Tencent
K8s + Ray 协同方向一：跨层弹性调度
业务场景：多模态数据处理（离线推理）
业务痛点：资源配置和任务画像不匹配
（1）通过人工配置异构资源折算产能，不准确且效率低
高优 CPU
*？核米？台
CPU
GPU
GPU
CPU
预处理
模型
模型
后处理
如何评估
混部CPU
*？核*？台
产能
高优GPU
*？卡*？台
？亿/天
混部GPU
*？卡*？台
CPU tasks
Actor pool
St Get-aResize
on GPUs
Actor pool
CPU tasks
on GPUs
（2）用户资源选择很难顾及运行时效率
$3 GetiResize
Segmentation
Classification
Mode！
ModeL
Wite Result
华南
华北
华南
CPU Pods
GPU POds
GPU Pods
Data streamed through memory
Ray Cluster
预处理
10 瓶颈
推理
预处理
摊理
CPU 瓶颈
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 033

Tencent
K8s +Ray 协同方向一：跨层弹性调度
解决方案
K8s资源调度层
K8s联邦调度+KubeRay
算子＋
预期产能
平台
智能调度器
动态自动扩缩容
Pod 重调度
任务重调度
（资源弹性）
（故障恢复）
（跨资源池迁移）
Ray任务调度层
运行时
运行时
运行时
资源调整
故障检测
产能评估
Pod
Rescheduling
敞障
CPU
GPU
CPU CPU GPU
Ray Cluster
Pod
Pod
Pod
Pod Pod
Task
Rescheduling
初始状态/低负载
中间状态/负载增加
有故障状态
恢复后
批量数据
CPU前处理
GPU模型
GPU模型
CPU后处理
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 034

Tencent
K8s+ Ray 协同方向二：跨层自动化容灾
业务场景：强化学习
业务痛点：任务对故障敏感，缺乏故障感知能力
（1） Ray RL 框架层无法感知 K8S 算力层故障
Controller
SkyRL-v0.1
Training control fiow
RL 框架层
训练
故障卡导致任务
人工确认
重启
失败
原因
任务
Generator
Model rollouts （actions）
Trainer
故障処理时间卡
InferenceEngine
Environment
Backends：
K8S 算力层 故障感知
故障GPU卡屏藃
Trajectories
Deep
Speed
FSDP2
& Rewards
Backends：
Environments：
Policy Model
VLLM SGLang
cusTom
CpenAIAPI
SkyRL-Gym
Bring
Parameters
Math, Code，
your
Policy Mode！ （Agent）
Soarch,soL
Policy Model （Agent）
own！
Environment feedback
（2） Ray RL 框架层无法参与 K8S 算力层故障机发现
（observations, rewards）
同一放障卡导致多个任务失败
Pod 1
Pod 2
Pod N
RL 框架层
训练任务1
故障卡导致任务
失败
训练任务2
同一张故障木
导致任务失败
K8S 算力层
未感知故障卡
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 035

Tencent
K8s +Ray 协同方向二：跨层自动化容灾
解决方案
故障机替换
• kuberay
K8s apiserver
算力
故障感知
标记故障机
故障机替换
Ray Cluster
替换续训
故障机替换
Head
任务重启续训
训练任务故障感知
Ray Dashboard
Train Monitor
训练任务
重启
故障标记
Ray集群内标记
K8S 算力层标记
标记故障机
worker
worker
Dashboard
Dashboard
故障感知
节点内感知
Agent
Agent
任务级感知
节点内故障感知
节点内故障感知
算力层感知
训练自动化容灾
同步日志
日志服务
aCon
InfoQ 极客传媒
全球软件开发大会

## Page 036

Tencent
未来展望
||
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 037

Tencent
未来展望
更原生的Ray联邦架构
更通用的分布式底座
目前实现的 kuberay 联邦架构需要接入层感知，
面向多模态数据处理、预训练、强化训练、在线
不是一个完全的联邦调度方案；未来需要收敛到
推理、Agent应用等场景，建设更通用的分布式
K8S+Ray技术栈内部。增强易用性和普适性
底座和平台，强化调度、通信、存储等通用分布
式能力
腾讯TEG
Ray
更统一的Agentic RL Infra
更强的技术团队
在训练＋推理 统一到 Ray 计算范式的基础上，
We are hiring
解决Agentic RL 场景更广泛的调度统一问题，如
欢迎联系
Agent和Sandbox运行环境
吣
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 038

InfoQ 极客传媒
QCon
全球软件开发大会
THANKS
大模型正在重新定义软件
Large Language Model Is Redefining The
Software

## Page 039

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
