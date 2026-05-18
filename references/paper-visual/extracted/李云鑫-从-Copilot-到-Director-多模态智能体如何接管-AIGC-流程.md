# 李云鑫-从-Copilot-到-Director-多模态智能体如何接管-AIGC-流程

来源PDF：`references/papers/李云鑫-从 Copilot 到 Director：多模态智能体如何接管 AIGC 流程.pdf`
页面图像目录：`references/paper-visual/images/李云鑫-从-Copilot-到-Director-多模态智能体如何接管-AIGC-流程/`

说明：以下为按页信息提取，尽量保留页面可见文字、标题、列表、表格与图示标签。
## Page 001

```text
InfoQ 极客传媒
QCon
全球软件开发大会
从Copilot到Director：
多模态智能体如何接管AIGC流程
李云鑫
计算机科学与技术学院
哈尔滨工业大学（深圳）
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
     01   AIGC智能化的挑战与路径


     02   基座模型与核心技术突破

目录   03   从 Copilot 到 Director


     04   通用 AIGC 智能体的构想
```

## Page 004

```text
AIGC智能化的挑战与路径
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 005

```text
从工具堆砌到智能整合

 技术红利：单点效率飞跃
 文生图、文生视频等工具成熟，内容产出速度大幅提
 升，单点生成能力爆发。


 落地困境：流程繁琐反成负担
 工具越多，创作越复杂，手动搭建工作流耗时耗力，
 AIGC从“解放”变为“消耗”。


 核心本质：仍处于工具辅助阶段
 当前AIGC缺乏真正的智能主导，更多是作为辅助工
 具，尚未实现全流程自动化。              复杂的AIGC工作流：节点繁琐，操作门槛高
```

## Page 006

```text
以语言智能为核心的AIGC智能体

   规划无逻辑
   长叙事、结构化内容无整体思路，工具只
   会单点执行，缺乏全局规划能力。


   调用无统筹
   多模态工具各自为战，无法用统一指令协
   同，导致执行过程碎片化。


                        核心解法：构建以语言智能为中枢的AIGC智
   评估无标准                能体，不仅能精准理解我们的创作需求，还
   生成内容的连贯性、一致性不稳定，无法   能进行推理和规划，并向所有多模态工具发
   自主校验，人工评估成本高。        出统一指令，实现全流程的智能调度。
```

## Page 007

```text
  以语言智能为核心的AIGC智能体
 构建一种能够处理多种模态（如文本、图像、视频、音频等）数据的多模态
 智能体模型，支持复杂任务规划与长程交互式推理
 设计高效的多模态智能体框架，旨在驱动智能体与复杂环境进行自主、深度
 的交互，并实现基于经验的持续学习与性能进化

                       推理规划
       基座模型
                 智能体            环境
                 系统           （应用实践）
       框架设计
                       经验学习

              大模型智能体
```

## Page 008

```text
）2
基座模型与核心技术突破
支撑 AIGC 智能体跃迁的底层能力
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 009

```text
语言智能原生的全模态大模型 Uni-MoE-1.0
   以大语言模型为核心，率先提出了多模态数据理解的多专家混合架构，
     突破大模型跨模态协同交互瓶颈，构建了统一多模态理解大模型

   模型架构                                                              渐进式三阶段训练策略


      Uni-MoE: Scaling Unified Multimodal Large Language Models with Mixture-of-Experts. IEEE TPAMI 2025
```

## Page 010

```text
  语言智能原生的全模态大模型 Uni-MoE-2.0-Omni
        从统一多模态理解，迈向理解与生成兼备的综合型多模态大模型，
        通过渐进式架构演进与训练，将大语言模型逐步拓展为全模态大模型
                                                                                                           Codec        VAE
                                Codec Decoder                                                             Decoder      Decoder


           Text                                      Text                       Text

    Dense LLM                                                                                                 MoE-LLM


                                                                                                         Qformer        MLP

  Audio            Vision           Audio           Vision             Audio            Vision            Audio        Vision
 Encoder          Encoder          Encoder         Encoder            Encoder          Encoder           Encoder      Encoder

    Alignment                        Expert Warmup                   Mixture-of-Experts                 Uni-MoE-2.0-Omni
    Pretraining                       SFT for MLP                   SFT & Annealing & RL               Audio & Image Training

大语言模型                                                                                                                 全模态大模型
            Uni-MoE 2.0: Scaling Language-Centric Omnimodal Large Model with Advanced MoE, Training and Data, 2025
```

## Page 011

```text
语言智能原生的全模态大模型 Uni-MoE-2.0-Omni
  从统一多模态理解，迈向理解与生成兼备的综合型多模态大模型，
  通过渐进式架构演进与训练，将大语言模型逐步拓展为全模态大模型
  模型架构                                            语音生成                                            图像生成


   Uni-MoE 2.0: Scaling Language-Centric Omnimodal Large Model with Advanced MoE, Training and Data, 2025
```

## Page 012

```text
  语言智能原生的全模态大模型 Uni-MoE-2.0-Omni
在85项基准评测中，Uni-MoE-2.0-Omni（75B Tokens）实现了最优或极具竞争力
的性能；在76项可对比任务中，超越 Qwen2.5-Omni（1.2T Tokens）逾50项
      关键优势领域
 视频理解8项任务平均提升 5%
         z
 全模态理解4项任务平均提升

 7%
 视听推理任务最高提升 4%
      专项性能突破

 语音问答：5项任务上领先 4.3%
         z
 长语音理解：词错误率降低 4.2%

 图像处理：5项指标上领先 7%


       Uni-MoE 2.0: Scaling Language-Centric Omnimodal Large Model with Advanced MoE, Training and Data, 2025
```

## Page 013

```text
语言智能原生的全模态大模型 Uni-MoE-2.0-Omni
自研并开源统一多模态大模型Uni-MoE系列，得到国内外同行的广泛关注


   Uni-MoE 2.0: Scaling Language-Centric Omnimodal Large Model with Advanced MoE, Training and Data, 2025
```

## Page 014

```text
 智能体模型：模型构建
UI-TARS: 通过引入统一动作建模、推理思维链以及迭代式在线强化学习，将通用
视觉-语言模型扩展为纯视觉驱动的GUI智能体模型，提升模型的规划推理能力
   模型架构                                         动作空间                                           实验结果


    UI-TARS: Pioneering Automated GUI Interaction with Native Agents, 2025 (Github Star 27K+, 单篇引用400+)
```

## Page 015

```text
  智能体模型：迭代式强化学习
VIPO-R1: 融合GRPO-Verifier-DPO循环的迭代策略优化，增强对采样数据的利用率
 通过GRPO的主动探索和DPO的定向优化，提升推理逻辑的一致性和答案的准确性


                                                                         (Explore)                       (Target)


                                                                                                  (Direct)


       VIPO-R1: Cultivating Video Reasoning in MLLMs via Verifier-Guided Iterative Policy Optimization, 2025
```

## Page 016

```text
  智能体模型：迭代式强化学习
• Uni-MoE-2.0-Think 在视觉数学任务上相较于监督微调变体实现平均4.5%的提升
• Uni-MoE-2.0-Omni 能够在生成最终图像前输出完整的思维推导过程
         实验结果                    样例展示


       模型推理能力稳定提升
```

## Page 017

```text
  智能体模型：多目标强化学习
针对模型工作流规划不准的问题，提出了多元奖励驱动的强化学习算法，构建了涵盖工
作流节点、结构和信息准确性的多元奖励机制，显著提升了智能体的工作流规划能力

       多元奖励驱动的深度强化学习                                        模型            节点F1      工作流F1   幻觉通过率

 多方面                                                    GPT-4o
                                                                           0.50      0.29    0.70
        节点匹配奖励                                         （OpenAI）
                           反馈          工
                                                      Claude 3.7
  节点                                   作             （Anthropic）
                                                                           0.51      0.35    0.74
                          策略           流
        工作流结构奖励           梯度           推              ComfyUI-R1           0.62      0.51    0.96
 工作流                      优化
                                       理                 节点调用更准确，任务规划更合理，幻觉现象更少
                           学习          模
  信息    信息准确性奖励                        型              我们的 7B 模型实现了 96% 的幻觉通过率；节
  幻觉                                                  点级和图级 F1 分数，超越了采用闭源模型（如
                                                      GPT-4o 和 Claude 系列）的最先进方法。
             ComfyUI-R1: Exploring Reasoning Models for Workflow Generation, 2025
```

## Page 018

```text
    智能体模型：多目标强化学习

指
令
                    指
                    令

工
作
流
和                       工作流和执行结果
执
行
结
果


对
比
工
作
流
和
执
行
结
果
```

## Page 019

```text
）2
从 Copilot 到 Director
四大视觉生成智能体实践
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 020

```text
  从辅助执行到统筹主导

Anim-Director                            AniMaker
基于多模态大模型的自主动画制作智能体，                      由导演、摄影、评审、后期制作四大智能体
从简短叙事指令中自动生成连贯、内容丰富                      协同工作，通过 MCTS 驱动的片段生成与
的可控动画视频，实现从创意到成片的全            Director   叙事感知选择，从纯文本输入生成全局逻辑
流程自动化。                                   连贯、视觉一致的多角色、多场景动画长片。


ComfyUI-Copilot               Copilot    FilmAgent
面向 ComfyUI 的智能助手，自动推荐节点                  虚拟 3D 空间中的端到端电影自动化多智
与模型、一键构建可视化工作流，解决复杂                      能体框架，遵循创意开发、剧本创作、镜
参数配置难题，已接入ComfyUI官方插件，                   头调度的工业化流程，实现从创意到虚拟
                           从简化操作到自主创作
落地阿里国际、RunningHub AIGC云平                 影片的全自动协作生成。
台。
                           从单点辅助到全流程主导


                           视觉生成智能体实践
```

## Page 021

```text
  AIGC 助手：ComfyUI-Copilot
提出多智能体AIGC助手ComfyUI-Copilot，以多模态大模型为核心，结合自研节点、
      模型知识库及调试工具，实现工作流的自动化构建和调优


 用户输入任务     模型检索知识      生成工作流   调试修复    结果验证
```

## Page 022

```text
 AIGC 助手：ComfyUI-Copilot
ComfyUI-Copilot的核心功能包括：工作流自动生成、ComfyUI工具问答、节点和
 模型和推荐、Debug调试、参数寻优、提示改写等，显著降低ComfyUI使用门槛
         演示视频                                                                       开源影响

                                                                   ComfyUI                      GitHub


                                                                 研发的AIGC助手
                                                                  ComfyUI
                                                                  Copilot

                                                     已作为原生插件被国际著名创                           项目获得GitHub星标
                                                     意设计软件ComfyUI官方集成                      4.8K，曾位居GitHub全站
                                                                                                 热榜第1
       ComfyUI-Copilot: An Intelligent Assistant for Automated Workflow Development. ACL 2025
```

## Page 023

```text
  AIGC 智能体：电影智能体 FilmAgent
                             首个基于多智能体协作的电影生成框架
搭建3D虚拟电影片场，专业知识驱动的导演、                                           引入多智能体合作机制，通过协同反馈以提升
     编剧、演员和摄像智能体                                                剧情的连贯性、动作的准确性、镜头的合理性

3D电影
工作室
俯瞰图


       FilmAgent: A Multi-Agent Framework for End-to-End Film Automation in Virtual 3D Spaces. SIGGRAPH Asia 2024
```

## Page 024

```text
  AIGC 智能体：动画智能体 Anim-Director
                         首个基于多模态大模型的动画视频生成智能体

无需人工干预，多模态大模型管控视频生成所有过程，                                                          在视频的多个场景转换之间，
     细化、评估和迭代工具生成的内容                                                              大幅提升了视觉连贯性和质量


   Anim-Director: A Large Multimodal Model Powered Agent for Controllable Animation Video Generation. SIGGRAPH Asia 2024
```

## Page 025

```text
  AIGC 智能体：动画智能体 AniMaker
多智能体协作，引入多镜头动画评估智能体AniEval和启发式视频生成策略MCTS-Gen


       AniMaker: Multi-Agent Animated Storytelling with MCTS-Driven Clip Generation. SIGGRAPH Asia 2025
```

## Page 026

```text
   AIGC 智能体：动画智能体 AniMaker
引入首个面向多镜头动画的评估框架 AniEval：从文本视频对齐、视频一致性、动作质量
和整体视频质量四个方面对多镜头动画进行全面评测，兼顾单镜头质量与镜头间的衔接


   面向多镜头动画的多角度评估框架 AniEval (14方面)                                   本方法 AniMaker 可连贯地表达故事，并保持角色一致
          AniMaker: Multi-Agent Animated Storytelling with MCTS-Driven Clip Generation. SIGGRAPH Asia 2025
```

## Page 027

```text
AIGC 智能体：动画智能体 AniMaker
MCTS-Gen：每个视频片段作为树节点，长视频生成转换为路径搜索问题

                          扩展：在当前路径的末端节点生成若干个
                          候选视频片段，并使用评价指标对它们进
                          行打分和排序

                          模拟：基于打分结果，继续生成新的扩展
                          片段，用于探索不同的可能路径

                          回传：子片段的得分会向上传递，更新父
                          节点的整体评价分数

                          选择：从候选片段中挑选出得分最高的片
                          段加入到生成路径中，然后重复这一过程，
                          逐步扩展完整的视频序列
```

## Page 028

```text
• AIGC 智能体：动画片
小王子
Qrle day, ine winid saurried. anMy
known seed dhet grew into a mysterious plent.
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 029

```text
• AIGC 智能体：宣传片
《哪吒之魔童降世》票房突破80亿美元
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 030

```text
• AIGC 智能体：广告片
汇源
100%
橙汁橙汁
1L
你说这天气，喝冰可乐最爽了
AA超粥
LYCHEE
可口可乐广告
品牌橙汁广告
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 031

```text
AIGC 智能体：AIGC-Claw

   全流程自动化生成
   一句话灵感→成片，将分散的AIGC工具链整合
   为统一的自动化工作流。


   分镜驱动的可控创作

   基于结构化的剧本与精细的分镜规划，提升角
   色一致性、画面风格及镜头语言的可控性。


   灵活修改与无限续写
   支持编辑剧情、角色、分镜等任意中间产物，                   Web 前端            飞书/微信集成    素材资产留存
   同时支持故事的无限续写，集数随心扩充。
                                         可视化创作面板            IM 对话式交互   高质量成片交付


                   https://github.com/HITsz-TMG/AIGC-Claw
```

## Page 032

```text
 AIGC 智能体：AIGC-Claw

程序员男主之前天天被老板PUA，最后惨遭裁员。后来用OpenClaw 创建一人公司，翻身收购原老板公司。


                     ......                          续写


          第二集：深夜启程                                        第七集：技术反噬
第一集：被优化                       第五集：收购星耀   第六集：新生与回望
           与首单突破                                           与坚守伦理
```

## Page 033

```text
   AIGC 智能体系列工作外部评价
开源AIGC系列工作FilmAgent, Anim-Director, AniMaker, 得到国内外同行的广泛关
                             注


                         美国知名电影制
                         片人与导演黄路
                         对FilmAgent进
                         行了高度评价，
                         获得25万人的关
                              注。


      海外博主分享推荐    HuggingFace每日论文#1

       浏览量32w+
```

## Page 034

```text
14
通用AIGC 智能体的构想
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 035

```text
     测试时算力驱动的动态推理
    统一框架下的测试时算力扩展             视觉交织思维链实现多轮解构           多级奖励的 Agentic RL
•   在生成过程中自主实现多轮次的推理、     •   引入“视觉交织思维链”，打通抽象叙   •   引入端到端的智能体强化学习，将智
    生成与自我评估闭环。                事与具象画面。                 能体的认知与生成过程进行解耦。

•   以算力换质量，缓解模糊Prompt带来   •   以生成中间态为视觉上下文，实现“所   •   在自我博弈中，推动智能体的审美水
    的对齐问题。                    见即所思”的多模态逻辑深度解构。        准与工具策略自主进化。
```

## Page 036

```text
通用AIGC智能体构想


深度整合底层工具智能   具备可自主迭代的学习   拥有跨模态灵活迁移能   实现从“输入需求”到
与高层叙事智能，构建   能力，通过多级奖励与   力，可适配文本、音视   “输出完整内容”的全
具备理解力与执行力的   多维批判机制持续优化   频等多模态创作场景，   链路闭环，让交付产物
双引擎。         生成路径。        实现能力高效复用。    从可用、好用到实用。


 双层能力整合       自主迭代进化      跨模态灵活迁移      端到端自主创作
```

## Page 037

```text
 Takeaways


• AIGC的演进方向，是从Copilot辅助协作走向Director全流程主导。
• 语言智能是多模态智能体的“大脑”，搭配全模态基座模型、强化学习等方法，才能实现思考推理、
 工具规划与自主决策。
• 四项智能体应用（ComfyUI-Copilot, FilmAgent, Anim-Director, Animaker）展示了从工作流辅助
 构建到长视频内容创作的全流程接管能力。
• 持续优化现有智能体，完善通用智能体的自主学习与迭代能力，让内容创作不再被技术流程束缚，每
 个人都能靠想法产出专业内容。
```

## Page 038

```text
InfoQ 极客传媒
QCon
全球软件开发大会
THANKS
大模型正在重新定义软件
Large Language Model Is Redefining The
Software
```

## Page 039

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
