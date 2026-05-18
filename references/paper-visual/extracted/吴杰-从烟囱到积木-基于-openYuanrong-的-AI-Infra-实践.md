# 吴杰-从烟囱到积木-基于-openYuanrong-的-AI-Infra-实践

> Page-by-page information extraction from rendered page images. Content is organized by page and preserves visible text/layout as completely as practical.

## Page 001

```text
从烟囱到积木：基于openYuanrong的AI Infra实
践



吴杰
华为 系统软件架构师
```

## Page 002

[No extractable text detected on this page from the source PDF/page image. Visual content may be image-only or unreadable.]

## Page 003

```text
     01   Agentic AI负载对分布式系统带来的变化和挑战

          openYuanrong Serverless分布式计算引擎简
     02
          介

          openYuanrong面向Agentic AI负载的关键技术
     03
          实践
目录
```

## Page 004

```text
Agent服务的变化：从毫秒级的无状态请求到小时级的有状态
session
                         Session 1 Session 2
          请求3

          请求2         请求2                 请求2

          请求1         请求1                 请求1

                              Agent网关
       微服务网关
                             Session路由

 请求3                   请求2              请求2
请求1             请求2   请求1                 请求1

                      Agent实例         Agent实例     session状态：
微服务实例     微服务实例       Session 1       Session 2   1. 历史上下文
                        状态              状态        2. 内部任务状态
                                                  3. …
```

## Page 005

```text
Agent服务的挑战：提升长程session并发度和资源利用率


                                       等待     问题2. session运行过程中的线程cpu负载低
                                      LLM推
                                        理           Session运行时间占比
             Agent网关
             Session路由                Agent          20%~40%

                                      执行                                  40%~60%


                                                       10%~15%
                                      等待
Agent实例（忙）             Agent实例（闲）     工具            LLM推理      Agent执行   工具执行

 Session状态               Session 状态   调用

 Session状态               Session 状态

问题1. 固定session并发数导致负载不均衡
```

## Page 006

```text
      沙箱系统的挑战：启动+回收速度提升一个数量级以上

     抽象成“函数调用”的沙箱成为AI Agent基础设施                            装载动态生成代码的一次性沙箱，快速启动+快速回收
                                                                     Agent“用后即焚”


                                                              快速启动       LLM          快速回收
                                                                        生成代码

                                  provision({}resources)                  沙箱
                                  execute(name, input)
                                  -> String

                                                                         沙箱池


                                                                     Serverless计算平台

图片来源：https://www.anthropic.com/engineering/managed-agents
```

## Page 007

```text
      大模型推理服务：回顾分布式KV cache系统

               分离式推理架构下的KV cache点对点异步传输                                                历史缓存加速


Prefill        Prefill        Prefill   Prefill          Prefill        Prefill          请求2
实例             实例             实例        实例               实例             实例
                                                                                         请求1
                                            put              put            put

                                                  分布式KV cache                        大模型推理服务集群

                                                   get                get             分布式KV cache

      Decode             Decode               Decode               Decode
       实例                 实例                   实例                   实例                  DDR+SSD

P/D模型实例之间无法基于同步                          分布式KV cache提供异步的                         分布式KV cache池化管理集群存
集合通信编程协调KV cache传输                      put/get接口实现KV cache传输                      储介质实现历史缓存加速
```

## Page 008

```text
    分布式KV cache的变化：从全局前缀共享到会话间时分共享

         基于前缀树全局管理                     Agent会话内共享历史KV cache，会话间不共享
        不同请求的历史KV cache
                                               第i轮           工具
                                    Agent 1                               第i+1轮推理         工具执行         ……
                                               推理            执行

                                                              第i轮         工具
                                    Agent 2    工具执行                                  第i+1轮推理           ……
                                                              推理          执行

                                    Agent n




                                    NPU 1
                                              Agent1
                                               推理
                                                         ②   Agent2
                                                              推理
                                                                           Agent1
                                                                            推理
                                                                                                       ……
                                                                                          Agent2
                                    NPU n                                      ③           推理




                                   分布式缓存                Agent-1                 Agent-2
                                                                                                   …
                                   DDR+SSD             推理历史缓存
                                                                      ①        推理历史缓存



图片引用
https://arxiv.org/abs/2312.07104
```

## Page 009

```text
 强化学习推动AI Infra控制面的架构演进，Ray/openYuanrong等分布式框架成为基础
 组件
                                                        异构动态负载
                                                      AI Infra控制面上移

                                   同构容器                      强化学习
                                                         Single Controller
                              AI Infra控制面下沉

平台只管资源       容器即微服务                 AI推理服务                   AI框架
                              Multi Controller AI训练     （AI Infra数据面）
不感知应用       微服务控制面下沉

                                                      Ray/Monarch/Pathways/
                微服务框架                AI框架                 openYuanrong
   应用
              （微服务数据面）          （AI Infra数据面）            （AI Infra控制面）



OpenStack       Kubernetes           Kubernetes          Kubernetes
（资源平面）      （微服务控制面+资源平面）    （AI Infra控制面+资源平面）       （细粒度的异构资源平面）



                    离线预设的固定控制逻辑                       应用基于业务逻辑
                                                      编程表达控制逻辑
```

## Page 010

```text
强化学习系统的变化： Agentic RL推动RL系统从训推同步共卡到训推异步分
离
           训推共卡架构下，Agentic model长短采样任务导致NPU资源空泡

Agentic mode RL采样阶段存在长尾推理请求                           训推共卡架构导致NPU资源空泡

                                     NPU              Req0推理                         Req4推理



                                               Req
                                     NPU        1         空泡                  Req5        空泡
                                           参                      参       参                      参
                                           数                      数 空   训 数                      数     空 训
                                           重                      重 泡   练 重                      重     泡 练
                                           排                      排       排                      排
                                     NPU       Req2        空泡                 Req6       空泡



                                               Req                            Req
                                     NPU                  空泡                             空泡
                                                3                              7
                  推理请求完成时间的累计分布：
                  90%的请求都在61%的时间内跑
                                                                Rwd                            Rwd
                  完了，95%的请求在73%的时间
                  内跑完了。推理长尾导致了1/3左   NPU
                  右的NPU时间浪费。

                                                                  Ref                            Ref
                                     NPU
```

## Page 011

```text
分离式异步训练核心功能：模型参数异步更新&样本异步传输

                                   Single controller
                  python rpc                                 python rpc


                 模型参数                                            模型参数
   训练引擎           (KV)         模型参数异步更新                           (KV)      推理引擎
                 高速传输                      DDR                   高速传输
  Train worker                                                            Rollout worker
                           CKPT v1          CKPT v2          …
  Train worker                                                            Rollout worker
                 样本数据                                            样本数据
                  (KV)             样本异步传输                         (KV)
  Train worker                                                            Rollout worker
                 高速传输                                            高速传输
                          prompt     response   reward   …
     ……                   xx         yy         zz       …                    ……
                          xx         yy         zz       …
```

## Page 012

```text
RL系统的挑战： Agentic RL的训推+环境的跨集群协同问题

 由于训练集群缺乏沙箱能力，Agentic RL需要另外部署一个集群，带来复杂度和资源效率问题

                                                     模型参数

 沙箱        沙箱          Agent   轨迹采集   Rollouter                    Trainer
                                                     样本数据
 代码       代码           应用逻辑    模型推理   推理服务                     训练任务


          沙箱池                                         RL系统

      Kubernetes服务集群                              Kubernetes训练集群

         CPU集群                                       NPU集群

                                        CPU利用率：15W+ core，<15%
```

## Page 013

```text
        RL系统的挑战：Agentic RL模型实例负载不均衡问题，需要多任务动态调度共享资源
        空泡

推理输出token个数
                                                                                 多卡资源成为基础调度单元，集合通信动态重组+模型状态快速切换

                                                                           进程     NPU      NPU        进程                 进程      NPU       NPU   进程


                                                                           进程     NPU      NPU        进程                 进程      NPU       NPU   进程
训练轮次


通过训推分离异步可以缓解长尾样本导致的资源空泡，但无法彻底消除空泡                                                动态调度其它RL任务的模型实例填充资源空泡，提升集群资源利用率

                                                               …                                                                       …
 训推资源         推                       推理资源    推 空                          固定的推理资源池                      模型
                   空泡                                推理                                          推理      空泡              推理
              理                               理 泡                                                        实例
                          训
                          练

                                                                     …                                                                           …
                                      训练资源      训   训      空     训         固定的训练资源池                                             模型实例
                  推理                                                                                  训练           训练                      训练
                                                练   练      泡     练                                                          模型实例

主对话     先导         中控     中控    VL     RL     通用     先导    教育任务 教育任务       主对话     先导     中控      中控          VL    RL       通用     先导     教育任务 教育任务
 任务    实验任务       规划任务   先导任务   任务    蒸馏任务   规划任务   实验任务     1    2         任务    实验任务   规划任务    先导任务         任务   蒸馏任务     规划任务   实验任务      1    2
         1                                            2                             1                                                2

JOB    JOB        JOB    JOB    JOB    JOB    JOB   JOB        JOB   JOB                              Multi RL Task Scheduler
                                Kubernetes                                                                  Kubernetes
                                 NPU集群                                                                        NPU集群
```

## Page 014

```text
   RL系统的挑战：Multi Agent RL下的资源利用率问题

Multiple Agent RL场景，训练阶段只选取Top K个Agent进                       Agent RL训练流程
行训练，其它Agent空闲等待，导致集群资源利用率低

               路径生成过程
                                            训练
                                                                        Reward
  • 主Agent：调用子Agent；调用工具；返回结果                        计算每个采样组的方差，挑方差最大的Top K个Agent训练
  • 子Agent：调用工具；返回结果给主Agent               主Agent


                  请求                                                        采样
                                          A1_Agent
                                                                      采样组        采样组        采样组       采样组
                  主
                                                     主
                 Agent                    A2_Agent   路径   主      A1         主          A2         …

                                            ……

                                                                        采样组
       A1         A2                      An_Agent              包含1个主路径和m个采样路径（替换A1）
                             ……
      Agent      Agent

      NPU        NPU         NPU
```

## Page 015

```text
     总结： Agentic AI多样负载带来的需求容易形成烟囱式架构，带来复杂度和资源效率问题



    AI Agent应用                                            Agentic RL
                    大模型推理


Session亲和    快速启动   Session缓存     控制面        KV存储         KV存储         集合调度    快速保存
  高并发        快速回收    时分复用       Python RPC   高速传输         高速传输         快速切换    快速加载


 Agent               分布式                     模型参数         样本数据         多卡资源动
             沙箱系统                  Ray                                         CKPT缓存
服务系统                KV cache                 异步更新         异步传输         态共享调度


      Kubernetes                             Kubernetes


      CPU集群                                  NPU集群
```

## Page 016

```text
     01   Agentic AI负载对分布式系统带来的变化和挑战

          openYuanrong Serverless分布式计算引擎简
     02
          介

          openYuanrong面向Agentic AI负载的关键技术
     03
          实践
目录
```

## Page 017

```text
openYuanrong Serverless分布式计算引擎发展历程

       2019~2020                                     2021~2023                                   2024~Now




            FaaS                                    有状态函数                                   Serverless异构计算

       函数计算底座                                 通用分布式计算底座                                     Serverless AI底座

           事件触发                              从FaaS到微服务/大数据/HPC                      从通算到AI训练/推理/强化学习/Agent

无状态、短时运行应用、不支持互调                        有状态、长时运行、函数互调、极致弹性                              原生支持NPU/灵衢等异构硬件



 YuanRong: A Production General-purpose Serverless System for Distributed Applications in the Cloud (ACM SIGCOMM '24)
```

## Page 018

```text
   openYuanrong：Serverless分布式计算引擎，单机体验编程，极致分布式运
   行性能
openYuanrong致力于以一套统一的分布式内核架构支持各类通算/智算分布式应用，屏蔽集群底层硬件
复杂互联和分布式处理细节，充分发挥集群算力优势，实现单机体验编程、极致分布式运行性能
                    通算/智算多样分布式负载                                                  分布式内核抽象               单机OS抽象
 微服务       大数据分析        HPC            AI Agent       AI 训练           AI 推理   …
                                                                                     函数                   进程

                                               veRL   vLLM    Spark     …
                                                                                    函数状态                进程私有内存
               Agent
 FaaS                          RLXF                                           …
              Runtime
                                                       adapter                      函数调用                  IPC
                                                                                   数据对象/流              进程间共享内存
           openYuanrong Serverless 分布式计算引擎
                    多语言函数运行时和分布式编程接口
                              Python | Java | C++                                 核心功能
                                分布式内核                                             1. 类单机的分布式编程，支持python/c++/java多
             函数系统                                       数据系统                         语言，部分接口提供ray的兼容适配层
        大规模函数调度 | 高性能函数互调                     数据对象/数据流 | 分布式异构多级数据缓存
                                                                                  2. 分布式异构数据系统，可用于kv cache、ckpt缓
                  CentOS/Ubuntu/EulerOS/…                                            存、模型参数更新等场景
                                                                                  3. CPU/NPU资源极速弹性伸缩，LLM秒级扩容
                异构算力集群（鲲鹏 | 昇腾 | …）                                               4. 多租隔离
```

## Page 019

```text
           多语言函数运行时：多语言单机体验分布式编程
                                                                                  方式2：少量修改自动分布式并行
             方式1：原生函数编程
                                                                       （无状态）                                           （有状态）

                                                    @yuanrong.invoke                              @yr.instance
public JsonObject process(String request, Context   def mc_simulation(spot):                      class Bill():
context) {                                              # 省略若干行单次蒙特卡洛模拟逻辑                           def __init__(self, customerName)
      // 省略业务逻辑若干行...                                                                                  self.customerName = customerName
                                                        return …
      // 库存管理函数调用另一出库函数“outbound”                                                                      self.totalMoney = 0
      Function func = new Function(context,
                                                    if __name__ == "__main__":                      def add(self, money):
“outbound”);
                                                        n = 100                                        self.totalMoney = self.totalMoney + money
      // 隐藏分布式调度、注册发现、弹性、LB、RPC通
                                                        s = …                                          return self.totalMoney
信
      ObjectRef<JsonObject> ref =
                                                                                                    def get(self):
func.invoke(request);                                    # invoke快速返回异步future
                                                                                                       return self.totalMoney
    JsonObject resp = ref.get(); // 获取调用的结果              # for循环隐藏n次分布式并行函数调度执
                                                    行                                             # 调用"记账"应用
    return resp;
                                                         futures = [mc_simulation.invoke(s) for   instance = Bill.invoke("Jimmy")
}
                                                    i     in range(0, n)]                         instance.add.invoke(1234)

                                                         # 同步阻塞获取n个并行处理结果                         ret = instance.get.invoke();
                                                                                                  # 打印出1234
                                                         outputs = yuanrong.get(futures)
                                                                                                  print(yr.get(ret))
```

## Page 020

```text
 函数系统：大规模分布式动态函数调度

                                       外部调用                            • 分布式分级调度：分级可扩展，避免中心单
                            FrontEnd           FrontEnd                 点调度瓶颈，支持大规模分布式集群细粒度
                                                                        函数调度

                                                   跨节点调度（如本
                                                                       • 动态生命周期管理：支持运行中动态创建/删
     快照极速冷启动                            Domain
                                                   地资源不足、指定
                                       scheduler
                                                   资源等）和迁移              除实例，支持自动休眠、唤醒、迁移
 RUNNING
   函数调用                                                                • 高效资源利用：快照极速冷启动，自动水平/
   特征分析         Fn   Fn                                      Fn   Fn

    动态驱逐
         IDLE
                                                                        垂直弹性和跨节点迁移充分利用各节点资源
    释放资源
SLEEPING
                 LocalScheduler                     LocalScheduler     • 实例间支持原生互调：根据实例ID互调，地
                                          …
实例空闲时自动释         (FunctionProxy)                    (FunctionProxy)
  放资源                                                                   址无关（不暴露IP），迁移友好，原生支持
                优先本地低时延调度
                                                                        分布式异步调用
```

## Page 021

```text
 数据系统：近计算高性能分布式内存数据多级缓存

             多语义分布式数据访问                                                       近计算分布式内存共享

• Object用于共享访问同一对象数据，支持                                        • 同节点访问支持本地共享内存免拷贝读写
  Future、自动引用计数、可变、多副本                                         • 跨节点自动同步用户无感，再次访问走本地共享
• Stream传递连续无界数据流，解耦多实例                                          内存

        object                          stream                       节点                                节点
    分布式invoke/put/get                 分布式pub/sub                   function                function         function
              invoke
 function1             function2   function3     function4
                                                                本地共享内存                   本地共享内存
        put                get             I/O           I/O

              object                                  stream                       分布式互联网络

        object访问模型                   stream访问模型                      节点                  节点                    节点
                                                                本地共享内存               本地共享内存                 本地共享内存

                         数据系统                                  function function   function function    function function
```

## Page 022

```text
    数据系统：基于异构内存对象实现点对点数据异步高速传输
             Runtime1                                          Runtime2              技术方案
              应用代码                                             应用代码


          put(keys, blobs)                                  get(keys, blobs)
                                                                               • 扩展分布式数据对象功能，支持异
                                   收发两端按照协调一致的Send、
                               4   Recv通信算子下发顺序触发通信
            Data Client                                        Data Client      构内存对象如HBM

                                                                               • 通过分布式数据对象的读写表达点
      1
              命名数据对象发布                                 1b      命名数据对象订阅
      a
                                                                                对点异步传输语义
                                     2   P2P通信顺序生成     3     通信域按需创建
                                                                               • 对于生产者和消费者都就绪的数据
             命名对象                        通信算子下发        P2P通信域创建
             发布订阅                         顺序控制          Root信息管理
                                                                                对象，数据系统全局排序下发通信
    完成通信算子下发后，
5
    清理对象元数据                               数据系统
                                                                                算子，解决死锁和并发问题
    控制消息图标：               对象发布订阅配对        P2P通信顺序生成   通信域按需创建

    数据流图标：                卡间直通传输          HBM数据块
```

## Page 023

```text
     01   Agentic AI负载对分布式系统带来的变化和挑战

          openYuanrong Serverless分布式计算引擎简
     02
          介

          openYuanrong面向Agentic AI负载的关键技术
     03
          实践
目录        3.1   Agent技术实践


          3.1   Agentic RL技术实践
```

## Page 024

```text
           基于有状态函数的分布式Agent Runtime方案
                                               Jiuwen Client


openYuanrong                         1）curl –H “X-Session: xxx”                                               public String handler(String event,
                                     /serverless/v1/functions/invocations
                                                                                                   是否存在
                                                                                                              Context context)
                                                                                           是        Session   {
                                                                                                                ……
                                                                                                  ID对应的实
                                                 FrontEnd                                             例

                                                  3）Invoke     2）Acquire (Session ID)
                                                                                                       否        session = context.getSession();
                                                                                                                List<String> histories =
                                                              FaaS-Scheduler                   弹性创建并发实例，            session.getHistories();
                                                                                                                ……
                                                                                                设置初始并发度

                                      1. Session 请求
                                                             2.1）Create
                                                                                                                EventPayload payload =
                                 4.1. 执行请求
                                                                                                                    parseEvent(event);
                                                                            4）TTL Delete        返回函数实例          ….
                         4.2. 请求返回                                                                              histories.add(payload.getEntry());
                                                                                                                ….
            Jiuwen Agent函数                    Jiuwen Agent函数                                   Sandbox函数      }
                                                                             4.1 调用沙箱
 3. 返回        Agent运行时                          Agent运行时                                       Agent运行时
 Session                            返回
                                    Session
                             5.保持Session
               2.加载Session                 6.同步Session


                       openYuanrong数据系统
```

## Page 025

```text
Session动态迁移提升集群负载均衡和资源利用率

                 负载均衡                              迁移长时任务回收空闲实例，提升资源利用率

            修改Session路由                                          修改Session路由
                  FrontEnd                                          FrontEnd


 Agent 函数实例 1                Agent 函数实例 2         Agent 函数实例 1    Agent 函数实例 ...     Agent 函数实例 N
    （4C8G）                      （4C8G）               （4C8G）          （4C8G）             （4C8G）

  Session NN                   空闲资源                 空闲资源
                                                                    Session N
                                                                                          空闲资源
                                                                   （1~3小时）

                                                    Session 1       Session ...        Session N
   Session ...                Session NN
                                                   （1~3小时）         （1~3小时）            （1~3小时）



                 状态(KV)迁移                                                      状态(KV)迁移

                                            openYuanrong数据系统
```

## Page 026

```text
大规模session-沙箱调度
                            网关                                         技术方案


        Frontend                      Frontend
                                                            • 沙箱超售：按最小资源规格预热多个沙
   Session路由缓存                      Session路由缓存

                                                             箱，在分配任务运行后垂直调整资源规格
                                            Session调度器
 Tool
                                          Session路由/弹性/迁移

 Code
                        Agent                               • 沙箱快速回补：基于镜像快照，秒级回补
                                                   数据系
                   调用Tool        调用Code
                                  统
                                            …
                                                             预热的沙箱实例
           低资源占用的大规模统一预热池
                                                            • Session并行调度：分离session路由和
               按需动态调整规格
  最小规格池
                                                 快速回补        session资源调度，基于一致性hash实现多
   OS                                      沙箱快照
                                                             调度器扩展
                            CPU集群
```

## Page 027

```text
 数据系统：基于内存对象聚合管理KV cache

                         Gather HBM Blocks到连续共享内存                                       合并KV cache减少对象元数据开销，16个32
           vLLM Cache Engine: LLMReq对应的KV Blocks HBM Layout：
                                                                                        层1MB对象put/get元数据开销 < 1ms
Block索引号                  i                                       j
                                                                                        Block索引号相同的KV cache合并为同对象，
 模型层1                   block1i                                block1j
                                                                                        确保相同前缀的KV cache同时换入换出
 模型层2                   block2i                                block2j
      …
                                         Put(objs, {{hbm-blksi}, {hbm-blksj}}
 模型层40



 keys                                  数据系统: 主机共享内存Layout：

 objIdi          meta             sz     off0   off1    off2     padding        buf1     buf2



 objIdj          meta             sz     off0   off1    off2    padding         buf3     buf4
```

## Page 028

```text
推理服务集群缓存资源在Agent会话之间高效时分复用，提升推理集群吞吐
20%+

   Agent-1             Agent-2             Agent ……
                                                                       技术方案
                                                          • 会话级推理历史缓存管理：面向Agent会话管理多轮请求
        推理请求+         推理请求+              推理请求+
        间隔预测          间隔预测               间隔预测              的历史缓存，结合高速网络实现异构多级缓存和高速迁移

                                                          • Session上下文缓存调度：基于Agent多轮请求间隔预测，
                      frontend
                   session上下文缓存调度                          提前控制缓存的换入/换出，提前迁移缓存确保负载均衡

                                                                    难点：预测工具调用时长
   推理函数实例                推理函数实例                                      下图是实测分布（s）
                                             推理函数实例
             本地缓                   本地缓
 vLLM                  vLLM                      ……
             存管理                   存管理


        缓存换入/换出/迁移            缓存换入/换出/迁移



 数据系统           Agent-1                 Agent-2
                                                      …
（DDR+SSD） Session-i 推理历史缓存       Session-k 推理历史缓存
```

## Page 029

```text
     01   Agentic AI负载对分布式系统带来的变化和挑战

          openYuanrong Serverless分布式计算引擎简
     02
          介

          openYuanrong面向Agentic AI负载的关键技术
     03
          实践
目录        3.1   Agent技术实践


          3.1   Agentic RL技术实践
```

## Page 030

```text
基于openYuanrong单集群实现Agentic RL示例（CodeAgent）

            函数调用                                               模型参数

函数沙箱        函数沙箱            Agent函数                Rollouter                 Trainer
                                         函数调用                  样本数据
代码            代码            应用逻辑         轨迹采集      推理服务                     训练任务
                                         模型推理

     openYuanrong AgentRuntime                           veRL/openYuanrong RLXF

                                  openYuanrong

                                      Kubernetes

                                      NPU集群
```

## Page 031

```text
          基于openYuanrong实现模型参数异步更新

             训练函数实例
                                                      推理                      推理                            技术方案
                                                     函数实例                    函数实例

      Checkpoint engine兼容接口                              Checkpoint engine兼容接口                •   将需要更新的模型参数从训练任务的HBM卸载
    NPU      NPU          NPU    NPU               NPU           NPU       NPU          NPU
                                                                                                  到DDR，每个参数分片对应一个数据对象
    T0       T1           T2         T3             T0           T1        T0           T1
                                                                                              •   利用CPU实现模型参数训推格式的分布式并行
1                 D2H                          3    RH2D               4   D2D
                                                                                                  转换
                                          openYuanrong
                                                                                              •   推理函数实例使用模型参数及分片编号作为对
                   Node                                  Node                    Node

                   DDR                                                                            象名称，从远程DDR获取对象至本地HBM
                          2
     T0      T1                 T0
                        训推格                                DDR                   DDR          •   推理实例可从其他推理实例的HBM中获取对象
                        式转换
     T2      T3                 T1

                                                                                                  至其本地HBM

    训练模型参数          推理模型参数                数据对象
```

## Page 032

```text
   openYuanrong作为TransferQueue数据面后端，实现RL样本数据分布式KV存储和高
   速传输
                       强化学习样本表格示例
                                                                         openYuanrong数据系统提供：

                                                                         • TQ的KV后端分布式存储能力

                                                                         • KV跨节点的高速传输能力
       推理/计算任务各自生产样本特定的列                             训练任务按行消费样本


                                                                        TransferQueue相关文档参考：
  Actor      Reward          ……
                                        Transfer        Actor Trainer
Generator
                                         Queue
                                                                        https://verl.readthedocs.io/en/la
  TQCli       TQCli          TQCli      Controller          TQCli
                                                                        test/data/transfer_queue.html

                         openYuanrong                                   https://github.com/TransferQueue
  Node        Node                                          Node
                                                                        /TransferQueue
 DDR/SSD     DDR/SSD                                      DDR/SSD
                       openYuanrong数据系统作为样本的数据面
  样本          样本        实现TB级样本的分布式存储和高速传输                  样本
  KV          KV                                            KV
```

## Page 033

```text
 集合调度实现多个RL任务动态共享NPU资源空泡，提升集群NPU利用率
 10%

                 模型实例_1                           模型实例_2
                                                                                            技术点
                                                                             • 函数集合共享资源调度：结合RL负载识别NPU有效资源空泡
                              RL框架
                       基于函数集合Single Controller编程                              并更新全局资源视图，结合拓扑重调度其它函数集合的多卡
                                                                              多进程实例来填充空泡
 动态负载信息                       openYuanrong
                         空泡资源                          函数集合状态管理
                         动态调度                                                • 函数集合状态极速切换：多卡多进程状态一致性换入换出，
           函数集合调度                      函数集合切换
                                                           集合实例1   集合实例2
                                                            状态      状态
                                                                              基于HBM-DDR的高速网络将切换速度从秒级优化到百毫秒，
     拓扑感知放置                                                                   使能NPU资源高效共享
 函数集合实例_1                       函数集合实例_1               函数集合实例_2
                                                                                          集合调度效果示意图
推理 推理 推理 推理                  推理 推理 推理 推理             推理      推理    推理   推理   NPU           模型    模型
引擎 引擎 引擎 引擎                  引擎 引擎 引擎 引擎             引擎      引擎    引擎   引擎
                             状态   状态    状态   状态       状态     状态    状态   状态
                                                                             NPU           实例    实例
状态    状态    状态    状态
                                                                                   模型实例                    模型实例
                                                                             NPU
                                                                                                模型实例
                                                                             NPU
                                                                             NPU
     部署阶段                                                                                 模型实例           模型实例
                                              切换阶段                           NPU   模型
                                                                             NPU   实例
                             高速互联网络                                                               模型实例
                                                                             NPU
```

## Page 034

```text
  异构函数自适应动态调度，提升multi agent场景异构资源利用率
  10%
                                           TO_BE                 技术方案：
     AS_IS
                                       函数创建时分配逻辑资源，
异构函数创建时分配物理资源                                                    • 异构函数实例动态调度：在
                                       运行过程动态绑定物理资源
                                                                 实例初次调度和再次唤醒时，
      FunctionEnd                           FunctionEnd
                                                                 根据各节点动态更新的实时
                                                                 异构资源视图，动态选取合
异构函数1             异构函数2               异构函数1          异构函数2
  主Agent          A1_Agent              主Agent        A1_Agent
                                                                 适的节点和NPU卡运行实例
                                                                 • 异构函数自动休眠和唤醒：
           静态绑定                               ② 动态绑定，资源复用        当异构函数实例空闲时，利
                                                                 用数据系统实现快速休眠，
NPU    NPU    NPU
                        …
卡1     卡2     卡3                      NPU     NPU   NPU
                                ①     卡1      卡2    卡3
                                                            …    释放算力资源；当有业务请
占用但闲置浪费                       自动休眠
                              释放资源
                                                                 求时快速唤醒，并充分利用
                    分布式缓存               Agent状态数据         数据系统
                                                                 空闲资源加速计算
                  资源空闲       资源占用闲置    资源使用
```

## Page 035

```text
openYuanrong支持一行代码平替Ray核心接口

修改方法：
……


import ray
import ray_adaptor as ray


……




                            更多示例参考：
                            https://gitee.com/openeuler/ray-
                            adapter/blob/master/README.md
```

## Page 036

```text
     基于openYuanrong积木式架构实现Agentic AI负载的分布式系
     统

    AI Agent应用                                         Agentic RL
                     大模型推理


Session亲和   快速启动     Session缓存      控制面         KV存储   KV存储         集合调度   快速保存
  高并发       快速回收      时分复用        Python RPC    高速传输   高速传输         快速切换   快速加载



   函数系统（服务/沙箱/Python RPC/集合调度）   openYuanrong    数据系统（状态/KV cache/存储/高速传输）



                                  Kubernetes


                                 CPU+NPU集群
```

## Page 037

```text
 openYuanrong作为统一分布式底座支持华为小艺Agentic AI全
 场景

模型团队            模型团队                  端侧应用               端侧应用

                                                                    业务收益：
  SFT           强化学习
                                 大模型推理服务               AI Agent服务   • Agent
          调用               调用                   调用                     单Agent万级session并发
                                  历史缓存加速                 秒级弹性
高性能CPKT          异步训练                                                  Agent毫秒级故障恢复
                                    秒级弹性                Session亲和
 故障自愈          异构资源共享调度                                                分布式KV cache访问性能提升1倍以上
                                 PD/EPD/AF分离             安全隔离
                                                                       大模型推理实例秒级启动

                          模型更新                 训练数据
                                                                    • RL
                   小艺Serverless AI平台                                 异步训推端到端时延减半
                                                                     集群NPU资源利用率提升10%
分布式训练框架        强化学习框架            分布式推理框架              AI Agent框架     训推参数同步时延从分钟级缩短至秒级


                       openYuanrong
```

## Page 038

```text
openYuanrong v0.8.0 正式发布，面向 Agentic AI 全面升级


                           openYuanrong开源仓地址



                           2026年4月13日，openYuanrong 团队正式发布
                           v0.8.0。新版本为 Agentic AI 场景全面升级，强
                           化对 Agent、强化学习、推理等场景的支持。多语
                           言运行时新增 Session 抽象与 wait/notify 交互原
                           语，支持 Agent 多轮会话与异步交互。调度方面支
                           持安全沙箱的管理和与 Session 弹性迁移，实现实
                           例资源动态聚合。数据系统支持分布式异构多级缓
                           存与 RDMA 协议，提升 KV Cache 跨机访问与样
                           本传输效率。

                           openYuanrong 开源以来受到了大家的广泛关注和欢
                           迎，并已开始落地互联网、AI、金融等各行业核心
                           场景。感谢每一位参与 openYuanrong 项目贡献的
                           开发者，同时欢迎更多的开发者加入我们！
```

## Page 039

```text
THANKS
大模型正在重新定义软件
Large Language Model Is Redefining The
Software
```

## Page 040

[No extractable text detected on this page from the source PDF/page image. Visual content may be image-only or unreadable.]
