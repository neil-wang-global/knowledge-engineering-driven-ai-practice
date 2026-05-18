# 季万强-面向-AI-原生负载的统一弹性调度体系-Aether-架构实践

> Page-by-page information extraction from rendered page images. Content is organized by page and preserves visible text/layout as completely as practical.

## Page 001

```text
面向 AI 原生负载的统一弹性调度体系：
Aether 架构实践
季万强
京东零售 高级技术专家
```

## Page 002

[No extractable text detected on this page from the source PDF/page image. Visual content may be image-only or unreadable.]

## Page 003

```text
 团队介绍




京东零售九数AI平台

九数是京东零售的AI基础设施平台，服务于零
售算法团队，为AI研发全链路提供底层算力、
引擎、平台能力，支撑算法团队的模型开发与
训练推理，提高研发效率，支撑业务增长。
```

## Page 004

```text
     01   背景与痛点


     02   整体架构设计



目录   03   关键技术挑战


     04   业务落地实践


     05   总结与展望
```

## Page 005

```text
背景与痛点
```

## Page 006

```text
 AI原生工作负载的“三驾马车”

高吞吐·高算力·低延迟

数据处理：高吞吐 · 并行清洗 · 特征工程
高吞吐并行处理，以数据管道为脉络，完成清洗、标注与特征工程，将原始数据转化为
高质量“燃料”



模型训练：迭代调优 · 算力密集 · 反向传播
算力密集的迭代探索，在反向传播中驱动参数寻优，于精度与泛化间反复博弈，
追求最优收敛



模型推理：低延迟 · 高并发 · 资源弹性
低延迟响应的实时推演，以轻量化部署承载高并发请求，将训练成果转化为业务价值输
出。
```

## Page 007

```text
训推集群面临的痛点



推理服务白天承载高并发    万卡级集群中，GPU/NPU   分布式训练需整卡甚至整   集群混部多厂商、多代际
流量，训练任务夜间抢占    故障、显存ECC错误、网     机规格，而集群中大量单   的GPU与NPU，算力规
算力资源。训推混部场景    络丢包等硬件异常从“偶      卡、半卡等碎片化资源无   格、显存容量、算子兼容
下，潮汐式负载波动引发    发事件”变为“常态存       法被大任务有效利用。资   性各异。上层框架需适配
资源争抢，如何在保障推    在”。训练任务频繁中断      源看似充裕却“看得见用   底层硬件差异，调度系统
理延迟SLA的同时实现训   需检查点恢复，推理节点      不上”，导致整体利用率   需在异构资源池中实现统
练任务的高效利用，成为    抖动影响服务可用性，集      陷入瓶颈，亟需精细化调   一抽象与智能分配，复杂
调度系统的核心矛盾。     群需具备自愈与韧性调度      度与碎片聚合能力。     度呈指数级上升。
               能力。


   时间复用           常态故障            空间错配          硬件多样性
```

## Page 008

```text
 弹性调度架构的关键特性



  条件            策略            粒度            速度



  何时触发          如何执行          以何粒度          多快完成

定义扩缩容的触发机制，   定义扩缩容的行为模式，   定义扩缩容的最小操作单   定义扩缩容的时间响应特
是弹性的“感知层”     是弹性的“决策层”     元，是弹性的“执行层”   性，是弹性的“效率层”
```

## Page 009

```text
整体架构设计
```

## Page 010

```text
      调度整体架构全景图


        Interface Layer                              REST APIs



Job Management Layer      Aether Job       Kubeflow Job         Ray Cluster    Deployment



Global Scheduling Layer      Strict FIFO          Best Effort FIFO              Gang        KV   DB




      Connection Layer       Connection             Connection                Connection



        Resource Layer         JDOS                       K8s                   Cloud
```

## Page 011

```text
如何实现大模型训练、推理、服务的弹性调度和SLA保障

                                        用户提供模型、数据/QPS
1   动态SLA规则
    • 人工设置：根究经验预先配置计算所需要的全部卡时
                                            生成SLA规则
    • 自动生成：依据模型复杂度、数据特征等多维指标




2   自适应资源调度                                  用户预期
                                              需求
    • 资源智能预测：基于集群空闲资源与在线服务的资源需求        符合                不符合

    • 智能弹性伸缩：基于SLA规则及资源画像，自动实现弹性伸缩
                                     提交任务              终止提交


3   预测性保障与自愈
                                              任务调度
    • 故障检测：及时发现故障机并将其隔离

    • 自动容错：节点故障后可以继续运行

    • 弹性计算：可以随时增减作业的节点数量                    运行时保障与自愈
```

## Page 012

```text
弹性调度核心引擎

      SLA规则引擎        规则管理                 规则知识库            数据分析器           模型分析器




                           工作流编排                  资源预测与编排                调度器插件

                            DAG                   资源预测模型               优先级队列插件

      调度编排引擎
                           状态机                     任务协调器                资源预留插件


                           触发器                    资源冲突仲裁                负载感知插件




                                  Aether-Driver（主节点）         Aether-Executor（工作节点）

Aether - 弹性计算引擎   Aether      探针        计划器      调度器    指标采集        进程监控     弹性组网
                   Brain
                                                       Ray
```

## Page 013

```text
弹性调度核心引擎交互流程


                 2. 生成SLA规则                  2.1 获取元数                    样本数据
                                             据            元数据湖
                              SLA规则引擎        2.2 返回元数据
                 3. 返回SLA结果                                                模型


                        a. 查找规则          b. 返回规则
             九                                                           自研框架
             数
                 4. 提交弹性作业                   e. 创建弹性作业
             机                                                           9N LLM
1. 选择模型、数据   器
                              调度编排引擎         f. 监听作业状态   弹性计算引擎
             学   5. 查询作业状态                                               9N Tritum
             习                               g. 调谐弹性作业
             平
             台
                        c. 调用插件          d. 返回结果

                                                                  开源框架
                                  调度插件
```

## Page 014

```text
调度编排引擎核心组件

                               工作流编排                            资源预测
1   工作流编排
                         DAG               触发器             模型      作业历史
    • 触发器：条件、定时等

    • DAG：完整描述作业的DAG图                                           调度器插件

                               调度器框架
                                                            优先级队列插件
                                                    Pre
2   调度器框架                        Enqueue
                                                            资源预留插件
    • 入队阶段：全局队列统一管理作业

    • 排序阶段：排序 + 打分               选择作业
                                                            负载感知插件
                                                    Post
    • 绑定阶段：绑定到具体的K8s集群
                                 作业打分                            ……

3   资源编排
                                             资源编排
    • 资源预占：预占K8s集群的资源
                         绑定到集群               资源预占                部署分发
    • 部署分发：分发到K8s集群
```

## Page 015

```text
Aether 核心架构图
                                                      Worker Node

                                                        Executor




  Global Serve               Driver Node              Proc    Proc


       Brain        Engine         Executor Manager

                                                      Proc    Proc




  KV           DB                                       Executor

                                                      Worker Node
```

## Page 016

```text
Aether 核心组件

1   Brain
    • 作业历史服务：收集Aether Job执行历史     Brain   Driver         Executor

                                 作业历史服务   探测器            健康检查
2   Driver
                                 参数优化服务   优化器            弹性组网
    • 优化器：请求Brain获取优化后的参数或资源配比

    • 计划器：生成逻辑执行计划               资源优化服务   计划器            进程监控

    • 调度器：输入执行计划进行调度执行
                                 智能代理服务   调度器            指标采集

3   Executor                      ……
                                                   Ray
    • 弹性组网：分布式动态组网

    • 进程监控：训练、推理、服务进程
                                            K8s

    • 指标采集：负载指标、硬件指标等
```

## Page 017

```text
关键技术挑战
```

## Page 018

```text
Aether 云原生融合



                2. 获取作业的资源计划
                                                       b. 上报作业的运行时数据
                                                                                Aether Driver
                                        Aether Brain
                3. 返回作业的资源计划
                                                                     c. 创建Executor         d. 上报状态
            弹
            性                                                                   Aether Executor
            作   4. 创建Job/Cluster资源                                               Ray Worker Node
                                                                               Ray Worker Node
1. 创建弹性作业   业                               KubeRay
                5. 监听Job/Cluster的状态                                                         d. 上报状态
            资                                          4.2 创建Ray Worker
                                                       Node
            源
                           4.1 创建Ray Head
            控                                                                  Aether Executor
                           Node
            制                                                                         e. 启动并监听
                6. 提交一个Ray作业                           a. 创建Aether Driver
            器                          Ray Head Node                                Procs
                                                                                 Ray Worker Node
                                                                               Ray Worker Node
```

## Page 019

```text
Aether 动态资源优化与调度
                                                                                                                           Worker Node

                                                                                                                             Executor




  Global Serve                                        Driver Node                                                          Proc    Proc

                    1. send resource            Engine              Executor
       Brain        plan
                                       parser        scheduler      Manager                 2.
                                                                                                 cr
                                                                                                   ea
                                                                                                        te
                                                                                                             /r
                                                                                                               ec
                                                                                                                 la
                                                                                                                           Proc    Proc
                                                                                                                      im



                                                                    3.
                                                                    registe
                                                                            r/unre
                                                                                   gister

  KV           DB                                                                                                            Executor

                                                                                                                           Worker Node
```

## Page 020

```text
Aether 自动故障检测与隔离
                                                                                        Worker Node                 {
                                                                                                                        "gpu": [
                                                                                           Executor                        "xid",
                                                                      new                                                  "ecc",
                                                             re quest
                                                           d
                                                  o   rt an                                      collector                 "connection"
                                            2. rep
                                                                                                 n                      ],
                                                                                               t io
                                                                                           la                           "npu": [
                                                                                         so
                                                                                        1. i                               "ddr",
                                                                                                                           "hbm",
Global Serve                        Driver Node                                                                            "network"
                                                                                        Proc                 Proc
                                                                                                                        ]
               4. report                                                                                            }
     Brain                 Engine      Executor Manager


                                                                          cr
                                                                            ea          Proc                 Proc
                                                                       3.
                                                                            te
                                                                                    w
                                                                                 ne




KV       DB                                                                                Executor

                                                                                        Worker Node
```

## Page 021

```text
Aether 动态组网与拓扑自愈
                                                                                                           Worker Node

                                                                                                              Executor
                                                            rt
                                                    2. repo
                                                                                                         ElasticAgent    collector

                                                              gister
                                                    5. unre                                        nc
                                                                                                     h                  1. i
                                                                                                a u                      so
                                                                                           el                              la
                                                                                         /r                                    t io
                                                                                a   im                                           n
                                                                             cl
  Global Serve                        Driver Node                       . re
                                                                       3                                  Proc             Proc
                    report
       Brain                 Engine         Executor Manager
                                                                              6.
                                                                                    ne
                                                                                       w                  Proc             Proc

                                                                                                              8. launch worker
                                                     7. regis
                                                              te   r
                                                                                                               ElasticAgent

  KV           DB                                                                                             Executor

                                                                                                           Worker Node
```

## Page 022

```text
Aether 动态组网与拓扑自愈




       启动worker的时序图   节点状态转换图
```

## Page 023

```text
业务落地实践
```

## Page 024

```text
 落地实践：京东零售 – 训练、批量推理、PD分离
训练：有效训练时间占比（ETTR）提升至 97%

批量推理：端到端任务处理时间缩短 10%，资源成本降低 30%

模型服务：部署 PD 分离服务的端到端效率提升 5%




           某弹性推理作业的扩缩频率

                                  某个集群提供的弹性卡时
```

## Page 025

```text
总结与展望
```

## Page 026

```text
 Aether Roadmap




                                                     • 弹性推理任务支持异构卡
                  • 弹性训练支持9N-LLM、PyTorch             • 支持aether checkpoint异步保存
                  • 故障诊断支持NPU

       v0.1              v0.2              v0.3             v0.4                 v0.5

• 弹性推理支持9N-LLM、 vLLM                 • 支持PD分离部署                           • 社区开源第1个版本
• 故障诊断支持GPU                          • 支持配置文件的动态更新                        • 故障诊断支持更多国产卡
```

## Page 027

```text
THANKS
大模型正在重新定义软件
Large Language Model Is Redefining The
Software
```

## Page 028

[No extractable text detected on this page from the source PDF/page image. Visual content may be image-only or unreadable.]
