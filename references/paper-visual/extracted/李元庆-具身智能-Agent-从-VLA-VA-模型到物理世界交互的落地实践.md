# 李元庆-具身智能-Agent-从-VLA-VA-模型到物理世界交互的落地实践

来源PDF：`references/papers/李元庆-具身智能 Agent：从 VLA:VA 模型到物理世界交互的落地实践.pdf`
页面图像目录：`references/paper-visual/images/李元庆-具身智能-Agent-从-VLA-VA-模型到物理世界交互的落地实践/`

说明：以下为按页信息提取，尽量保留页面可见文字、标题、列表、表格与图示标签。
## Page 001

```text
InfoO 极客传媒
QCon
全球软件开发大会
具身智能 Agent： 从VLA/VA
模型到物理世界交互的落地实践
李元庆
```

## Page 002

```text
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
```

## Page 003

```text
家庭机器人的“理想”与“现实”
                    离身智能能力                   具身智能能力
                 • 语言理解      • 知识广度      • 物理交互     • 鲁棒性
                 • 视觉识别      • 推理能力      • 场景适应     • 持续学习

                          “ 还不                    “ 还不
                           错”                      行”
                家庭场景的“四座大山”


                 交互的多模态与情感化               非结构化的室内环境
                                 “需要被照顾的电子设备”


                  隐形的需求与意图              出厂即定型，无法真的成长


                 家庭场景中，机器人的价值不在于它出厂时会多少技能，而在于它能否持续学

                 习这个家庭的习惯、预判需求、并安全地融入日常生活。这需要我们从根本上

                 改变设计逻辑：从“交付功能”转向“交付成长能力”
```

## Page 004

```text
   从“功能固化”到“持续进化”的最新技术栈
                                                                             Learning-Based:
                                                                                  End-to-End
                                     Learning-Based:
                                         Modular-Based
Rule-Based                                                                       Latent隐式特征

                                                       显式特征                      信息复用
                     Reasoning/AI/Memory/Verification/Locomotion/Evolution       模型能力
                           Manipulation：Learning with Auxiliary Tasks            • NVIDIA WAM
Perception
                                                                                 • Physical Intelligence
Navigation                               Agent                                   • Helix
                                     •     OpenClaw
基于规划的Manipulation
                                     •     Claude Code                           References
• Rules/Constrains                                                               a) World Action Models are Zero-shot
                                         Skills                                     Policies
                                     •     RL: HIL-SERL                          b) RL Token: Bootstrapping Online RL

                                     •     Diffusion Policy                         with Vision-Language-Action Models
                                                                                 c) A Vision-Language-Action Model for
                                                                                    Generalist Humanoid Control
```

## Page 005

```text
                                                                                   智能机器人扩充技术层

 技术层拓展                                                                             传统机器人已有技术层


交互层       HMI         VR     AR        MR         XR       动作捕捉技术      新型交互方式


                                                                                     安全保障

                                                       通用大模型           自然语言处理
          交互层                                                                        数据安全
                           智能决策层     HMI
       数孪虚拟测试                                 深度学习             强化学习     生成式AI


      高保真仿真技术                                 优化算法             统计学习   生物学一体控制        网络安全


                           控制层      姿态控制      导航定位             运动控制   生物学一体控制
                                                                                    恶劣环境保护
       控制模型层

  可视化建模         多体动力学建模                                           云化操作平台
                           操作平台
                                                                                     能源保障
 数据驱动建模         模型融合技术                 硬件抽象与虚拟化                  开源定制化操作系统


                                                                                   高密度能量电池
                           通信层     传统有限通信技术             物联网协议              5G/6G

            模型层

                                                           执行驱动技术                  能源-结构-感知一
 几何与结构建模        数字孪生模型              传统感知技术
                                                                                       体化
                           感知层                    执行层                 一体化硬件技术
      模型轻量化与部署                     多模态感知技术                高动态响应执行
```

## Page 006

```text
Learning with Auxiliary Tasks

                                辅助任务学习是一类训练范式，它在核心操作任务目标
                                之外，引入额外的自监督或弱监督目标，以强化策略学
                                习。这些辅助目标促使模型学习环境、动作与目标的结
                                构化表征，从而提升样本效率、泛化能力与鲁棒性。


                                           主要路径


                                    世界模型          图像/视频预测


                                    对比学习           掩码重建


                                    文本驱动           视觉驱动
                                    目标提取           目标提取
```

## Page 007

```text
       OpenClaw 技术架构
    大模型 LLM                                    工具 Tools                          记忆 Memory                    调度 Scheduler                   通道 Channels
understand ->task-> decide       read/write Shell web calender 邮箱 scripts        context state history        轮询 任务调度 automation              Telegram 飞书 Discord


 执行大脑：Pi Agent 与 技能系统                                                                                         连接生态：多渠道通信（Channels）

 Pi Agent运行时             Tool              Block                                                                             支持WhatsApp、Telegram、Slack、Discord、
  （PRC模式）            Streaming           Streaming               Gateway 网关：控制平面                               多频道集成         Google Chat、Signal、iMessage、Microsoft
                                                                                                                             Teams、Matrix 等多种通讯平台

   ClawHub
                      自动搜索               扣取新功能
                                                            RP                                      S
                                                                              控制设置                 W
   技能注册表
                      内置技能               工作空间技能
                                                        C                                                       路由规则
                                                                                                                             复杂的群组路由逻辑，包括提及门控、回复标签处理
                                                                                                                             以及针对不同频道的自动消息分块


   聊天指令集             Think       Reset       Status              状态管理                        配置

                                                                            WebSocket                          执行终端：Nodes & Apps
 安全与部署层                                                                     网络通信
                                                                 Cron                    Webhook

              •   非主会话在独立Docker中运行                               定时任务                     网络钩子                 跨平台支持         macOS 菜单栏应用、iOS 节点和 Android 节点
 安全沙箱         •   限制对主机的访问权限
                                                                                                         WS
Sandboxing    •   敏感工具黑白名单管理                                                                                    硬件能力
                                                                                                                             摄像头拍/录像、屏幕录制、地理位置获取等
                                                                        多代理路由与会话隔离
                                                                                                                  调用
  部署与         •   本体/远程灵活部署
                                                                                                               Voice Wake
 远程访问         •   内网穿透                                                                                                       始终在线的语音唤醒和连续对话能力
                                                                                                               & Talk Mode
```

## Page 008

```text
    Agent核心架构与优势
 三大机制                           Multiagent架构                       Pi Agent Core

  Corn定时调度机制 = 计划执行能力                    多Agent隔离与路由                                  极简Agent
                                每个 Agent 都拥有自己的独立区域，拥有独立的工作         无需冗长系统提示词和复杂规划模块，<1000 tokens，
支持一次性提醒、周期性任务、标准Corn表达。无需
                                区、会话记录和记忆库；每个 Agent 只能访问属于自         内置read、write、edit、bash 四个核心工具，覆盖 90%
手动配置，可根据对话上下文，主动给自己安排任务
                                己的对话流，同一个 Gateway 上可同时运行多个专职        的需求，其bash工具支持自我调用。运行逻辑：入队与加
                                Agent。                              锁→构建提示词→调用模型（含回退）→处理响应


  Heartbeat心跳机制 = 主观能动性
                                         Agent间协作会话工具                            架构分层与核心逻辑
Heartbeat.md 文件记录了待办事项和周期性检查任
                                sessions_list：查看当前有哪些活跃的会话          分层架构：Applications（应用层）→ Core（核心层：
务，基于系统定期自动发送的隐形信息，Agent扫描上
                                sessions_send：向另一个会话发送消息            pi-agent-core）→ Foundation（基础层：pi-ai）
下文和清单，时刻处于“待命”状态                sessions_history：查阅其他会话的历史记录        核心运行5个文件：types.ts、agent-loop.ts、
                                sessions_spawn：创建新会话来委派具体任务         agent.ts、proxy.ts、index.ts


  Soul.md机制 = Personality 性格             多样化会话排队模式                           多双层while循环&流式应答
 Soul.md 文件可定义Agent的语气、边界和优先级   Sequential：串行模式   Concurrent：并发模式    外层循环：FollowUp 消息驱动，实现任务连续推进；
                                Collect：收集模式      Steer：干预模式         内层循环：ToolCall 和 Steering 消息驱动，“注入消
                                Followup：跟进模式                         息 → 调用 LLM → 执行工具 → 结果反馈”闭环；
                                                                     Steering 中断机制
                                                                     流式应答：最晚转换，上下文实时更新
```

## Page 009

```text
 Robot Agent 流程图
   用户自然
                                                      Agentic Loop
   语言指令
                                                                          NO
                                                   是否调用工具                            Response
        输入连接：                                         YES      YES                    Path
                                                                                     渠道适配器
        机器人本体
        /App
                                                  工具B：导航规划
                                                                                     流式分块器

   网关服务器                                          工具C：机械臂操作
                                  携带
                                 新上下文
                                        收集执行结果
会话路由器      通道队列
                       LLM API                    工具D：多模态感知                        机器人执行层
                                        返回继续决策


        Agent Runner                                                 记忆库

   会话历史加载器                                         工具A：语义地图          查询           空间记忆
                                                 （查询物体相关所有信息）                  （空间+时间+语义）

    模型解析          上下文窗口保护

                                        查询空间记忆
   系统提示构建器
```

## Page 010

```text
             HIL-SERL系统的“Human-in-the-loop”强化学习
                                                                                                                                                结果 在RAM插入任务中，仅32,000次RL转换即可达97%准确率，动态任
                                                                                                                                                务如翻转物体展示了预测控制的潜力。相比纯模仿学习，提升了适应性、速
   HIL-SERL操作策略系统
                                                                                                                                                度。
   1. 通过遥控操作机器人收集正负样本，并训练一
                                                                                                                                                结论 HIL可桥接模拟与现实差距，推动机器人向人类级灵巧性发展，适用于
       个二元奖励分类器
                                                                                                                                                工业组装、家庭服务等领域。未来可扩展到多模态输入或零样本学习。
   2. 收集一小组演示数据，这些数据在强化学习训
       练开始时被添加到演示缓冲区
   3. 在线训练期间，使用二元分类器作为稀疏奖励                                                                                                                       HIL-SERL 系统核心组件
       信号，并提供人类干预。初期，提供更频繁的                                                                                                                      • Actor process
                                                                                                                                                 Step：现实环境，10Hz作为动作执行与观测更新的频率；默认RL agent
       干预，以演示从各种状态解决任务的方法，并
                                                                                                                                                 自己出action，操作员可以随时介入，介入一个固定的动作序列长度，然
       防止机器人执行不良行为。随着策略成功率提                                                                                                                      后将控制权交回
       高和循环时间加快，逐渐减少干预的次数                                                                                                                        Reward：稀疏奖励，只判断任务是否成功，成功给1，不成功为0
                                                                                                                                                 Reset：在不同的任务中，采用人工操作或脚本，实现环境的随机化重
   核心原理：
                                                                                                                                                 置，以保证泛化性
   1. 样本高效的离线强化学习（RLPD）                                                                                                                          • Learner process
   2. 稀疏奖励 + 二分类奖励器（告别复杂奖励工程）                                                                                                                    在 GPU 上持续训练，使用 RLPD 算法（高效离线 RL）优化策略，均匀
   3. Human-in-the-Loop 动态干预机制                                                                                                                   采样“人类示范数据”和“机器人交互数据”
                                                                                                                                                 网络设计：用一对actor-critic网络来训练出关节动作的策略，再单用DQN
   4.感知与状态表示优化
                                                                                                                                                 去训练夹爪开合的策略
   5.数据与流程优化                                                                                                                                     • 双Replay buffer
   关键机制：                                                                                                                                         采集人类示范数据放入Demo Buffer；训练过程，机器人与环境交互数据
                                                                                                                                                 放入RL Buffer，其中由策略网络推理得到的动作产生的数据，对应Policy
   奖励设计、 RL算法（RLPD）、系统设计（模块
                                                                                                                                                 Transitions，其中人类操作员介入数据存入Demo Buffer
   化、高效）、训练流程（渐进式自主）                                                                                                                             网络更新：从RL Buffer和Demo Buffer里平等地采样，拿到Training
                                                                                                                                                 Batch，用于更新网络

Luo, J., Xu, C., Wu, J., & Levine, S. (2025). Precise and dexterous robotic manipulation via human-in-the-loop reinforcement learning. Science Robotics, 10(105),
eads5033.
```

## Page 011

```text
              Physical Intelligence 全新机器人在线学习架构
   大模型负责感知和通用知识，小网络负责在线适应和精细控制                                                                                      第二层：决策执行层，即轻量级 Actor-Critic
                                                                                                                     •   输入：RL token ➕ VLA 生成的 Reference Action
                                                                                                                     •   限制：Actor被BC正则化约束，确保在线RL的局部优化
   第一层：信息压缩层，即RL Token                                                                                               •   优化：训练时随机将部分batch的参考动作置零，保障Actor
   •     小型encoder-decoder transformer                                                                                   独立的动作生成能力
                                                                             阶段一：表示学习                     阶段二：在线RL


                                                                                                                                                结果：
                                                                                                                                                •   关键阶段执行速度提升最高 3 倍；
                                                                                                                                                •   拧螺丝全任务成功率从20%到
                                                                                                                                                    65%；
                                                                                                                                                •   扎扎带从接近0到60%；
                                                                                                                                                •   以太网插入任务只用了约 5 分钟的
                                                                                                                                                    关键阶段数据就超过了基础策略


                                                                                                                     第三层：时间抽象层，即动作块级 RL
                                                                                                                     •   RL 策略操作在动作块（action chunk）级别，减少决策次数
                                                                                                                     •   动作块子采样（subsampling）优化，transition增加，数据
Charles Xu, Jost Tobias Springenberg, Michael Equi, Ali Amin, Adnan Esmail, Sergey Levine, Liyiming Ke.(2026). RL
Token: Bootstrapping Online RL with Vision-Language-Action Models. Physical Intelligence.                                利用率提升
https://pi.website/research/rlt
```

## Page 012

```text
                 NVIDIA 世界动作模型WAM：DreamZero
        WAM核心思想                                                                                                                                           维度          模型                   模型

        先视频预测 “会变成什么样”作为“隐式视觉规划器” ，再根据                                                                                                                  输入输出   观察动作（直接映射）       观察 语言动作（联合预测）
        视觉规划生成对应机器人动作
                                                                                                                                                        物理学习   无，依赖   静态语义先验    从视频扩散模型继承时空 物理先验
        联合建模：建立在预训练的视频扩散模型之上，同时预测未来的视频帧和对
        应的动作
                                                                                                                                                        数据利用   依赖重复、结构化任务演示      利用异构、多样化、非重复数据
        物理先验：通过学习视频，继承视频数据中的物理动力学常识，知道“世界
        该如何演变”，从而推导出“该如何执行动作”                                                                                                                           泛化能力      语义 物体泛化         零样本泛化，任务 环境 形态
        数据效率：由于具备这种物理直觉，无需大量重复演示，既可从多样化、非
                                                                                                                                                        迁移能力   依赖动作标注数据，效率低      支持       无标注数据迁移
        重复的异构数据中有效学习


    14B参数自回归扩散 Transformer（DiT）                                                                                                                                       推理加速与闭环控制
    •   输入端： 接收当前的视觉观测、语言指令、机器人本体
                                                                                                                                                                      1）自回归架构设计：天然适合利用 KV Cache（键值
        感知状态
                                                                                                                                                                      缓存）技术来加速推理
    •   核心处理： 因果DiT模块，负责联合去噪
                                                                                                                                                                      2）38 倍的推理加速&7Hz 的实时闭环控制：系统、
    •   输出端： 双解码器，生成未来视觉帧与可执行动作序列
                                                                                                                                                                      实现、模型三层面优化。并行化+缓存优化推理吞吐
    Joint Flow Matching流匹配与联合去噪
                                                                                                                                                                      量；编译器+量化+内核优化，降低硬件开销；
    •   输入：双模态（视频、动作）噪声联合建模
                                                                                                                                                                      DreamZero-Flash，解耦噪声调度实现单步去噪
    •   输出：联合速度场预测


        结      泛化能力提升超2倍，实现跨环境、跨任务、跨具身泛化                                                  从多样化异构数据中高效学习，打破对重复演示的依赖                                            跨具身迁移能力，纯视频学习+小样本适配新机器人
        果     对比VLA模型：平均任务进度提升超过2倍                                                        对比VLA模型：平均任务进度提升10%                                                  仅需30 分钟的无标注玩耍数据，就能保留零样本泛化能力


Ye, S., Ge, Y., Zheng, K., Gao, S., Yu, S., Kurian, G., ... & Jang, J. (2026). World action models are zero-shot policies. arXiv preprint arXiv:2602.15922.
```

## Page 013

```text
一个目标，三个聚焦


             在探索中寻找融合点，在家庭中验证有效性

            目标：让机器人拥有持续成长能力


 从“功能堆砌”          从“技术驱动”              从“单机智能”
 转向“场景深耕”         转向“数据驱动”             转向“家庭共生”


            期待同合作伙伴与开发者一道，构建开放的进化生态，
            让每一台部署的机器人，都成为整个系统成长的贡献者
```

## Page 014

```text
InfoO 极客传媒
QCon
全球软件开发大会
THANKS
大模型正在重新定义软件
```

## Page 015

```text
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
```
