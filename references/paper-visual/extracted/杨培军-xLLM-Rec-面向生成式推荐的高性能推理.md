# 杨培军-xLLM-Rec-面向生成式推荐的高性能推理

来源PDF：`references/papers/杨培军-xLLM-Rec：面向生成式推荐的高性能推理.pdf`
页面图像目录：`references/paper-visual/images/杨培军-xLLM-Rec-面向生成式推荐的高性能推理/`

说明：以下为按页信息提取，尽量保留页面可见文字、标题、列表、表格与图示标签。
## Page 001

```text
InfoQ极客传媒
QCon
全球软件开发大会
XLLM-Rec： 面向生成式推荐的高性能推理
杨培军
Al Infra主架构师
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
 个人简介


                    “
                        京东零售AI域主架构师，xLLM开源项目架构师/核心贡献者。曾就职于阿里妈妈
                        负责搜索广告架构和AI Infra推理系统研发，现于京东零售智能平台部专注大模型
                        推理及生成式推荐能力建设。


                             ”
     杨培军
京东零售 AI Infra主架构师
```

## Page 004

```text
     01   业务背景与挑战


     02   行业方案


     03   技术方案&创新

目录   04   核心成果


     05   未来展望
```

## Page 005

```text
业务背景与挑战
生成式推荐的技术范式变革与核心难题
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 006

```text
传统推荐：多阶段级联架构

                        特征工程依赖

               特征工程“矿山”基本被挖掘殆尽，“精心”设计的手工特征，迭代成
               本骤升且泛化性差


                        模型工程天花板

               现有架构无法有效建模“世界知识”、“用户意图Reasoning”，对
               多领域、多模态、用户行为等吸收、表达有限


                        级联架构误差放大

               级联多阶段架构，算法目标被分散到不同阶段和不同算法团队去优化，
               出现了严重的目标割裂和误差传播

                        GPU资源利用率低

               推荐训练、推理MFU 10%以下，LLM在H100上训练时MFU可高达
               40-50%
```

## Page 007

```text
生成式推荐：行业级技术升级趋势
                       端到端生成架构


                  业界生成式推荐正往端到端生成架构方向快速发展，
                  初步验证了Scaling Law和Scaling Up的收益潜力


                       多模态深度融合

                  引入图像、文本等更多模态信息，结合MoE等模型结
                  构设计，实现更丰富的特征表达


                       Reasoning推
                       理
                  基于世界知识+全场域联动的Reasoning推理能力，
                  提升推荐的准确性与多样性
```

## Page 008

```text
 DLRM vs LLM vs GRs：技术架构对比
关键洞察：GRs（Generative Recommendation System，生成式推荐）模型融合了 DLRM 的稀疏特征处理能力和 LLM 的生成能力，在保持推荐系统核心优
势的同时，引入了LLM模型参数规模和自回归生成范式，实现更准确、更多样化的推荐结果。
```

## Page 009

```text
     核心技术挑战
     系统融合挑战
01
       TB 级稀疏参数    推荐系统的大规模稀疏嵌入参数                 十B 级稠密参数     LLM 的稠密参数规模

                                 工业级部署要求端到端时延控制在百ms以内


     技术生态切换挑战
02
            TensorFlow生态    原有搜推体系基础                        Torch生态      生成式推荐所需


                                 需要完成技术生态的平滑切换，确保业务连续性


     技术范式瓶颈
03
     LLM计算Kernel和Beam Search机制在生成式推荐推理场景下，存在以下核心瓶颈：

           重复访存               Block频繁拷贝          混合Mask计算                    端到端时延过高

                                 LLM 的优化技术栈并不总是能在生成式推荐场景直接生
                                 效
```

## Page 010

```text
02
行业方案
业界主流方案与我们的差异化路径
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 011

```text
    业界主流方案 – 生成式推荐推理

      方案一                              方案二
A                                B
      编译优化路线                           大模型框架复用


技术路径                             技术路径
离线训练整图导出，使用TensorRT（GPU）直接编译优化   直接复用大模型推理框架加速方案（FlashAttention/PagedAttention
                                 等），基于TensorRT-LLM框架

优势
• 充分利用硬件加速能力                     优势
• 静态图优化潜力大                       • 成熟的Attention优化
                                 • 社区生态丰富

局限性
                                 局限性
• 难以处理动态Beam Search逻辑
• 缺乏对KV Cache的精细化管理              • 未针对推荐场景优化，Continous Batching调度成本高
                                 • Beam Search效率存在性能瓶颈
```

## Page 012

```text
xLLM-Rec：xLLM生成式推荐

大模型         多模态    文生图/视频     生成式推荐


                                             xLLM 项目地址：https://github.com/jd-opensource/xllm
                                                       https://github.com/jd-opensource/xllm-
      高性能          易开发           高可用
                                             service

提升吞吐、降低时延         主流模型天级      智能集群调度
                                             xLLM 技术报告：https://arxiv.org/pdf/2510.14686
  最大2.3+倍          适配上线     高效Failover容错架构
```

## Page 013

```text
技术方案&创新
面向Beam Search和混合Mask的系统性优
化
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 014

```text
  Beam Search性能分析
技术背景：在生成式推荐中，系统以自回归方式生成3个token id（代表一个商品Item）。在每个Step中，Beam Search会并行扩展并保留概率最高的多个候选序
列，保证推理结束时得到整体最优的推荐商品。


                                              重复访存
                                          各候选序列共享Prefill上下文，Decode Attention计算每个序列单独访问KV
                                          Cache
                                             造成相同数据被多次加载，内存带宽成为瓶颈

                                              Block频繁拷
                                              贝
                                          KV Cache按照Block管理且需对齐，候选序列在更新时需要拷贝旧序列的KV Cache

                                             引入了频繁的复制开销 ，严重影响推理效率


                                              时延过高
                                          传统Beam Search的筛选在Host侧进行，需要数据拷贝到内存，同时CPU处理筛
                                          选过程耗时过长。

                                             端到端时延难以满足推荐系统要求，端到端百ms时延约束

            Beam Search流程实例
```

## Page 015

```text
混合Mask性能分析


                               关键问题

                         •   序列结构复杂：生成式推荐场景通常会将输入序列划分为多个语义区段，每个序列
                             段可独立配置为 Full 或 Causal 注意力模式，形成混合结构。

                         •   开箱性能差：FlashAttn并无法有效应对这种场景，其他开源实现如FlexAttn /
                             torch compile虽然可以处理这种复杂的Mask，但性能差。

                              大Shape全局 Mask 生成 / 搬运 / 存储成本高
                              存在冗余计算问题，Block分块可能会圈进去白色区域


  生成式推荐模型输入序列Masking示例
```

## Page 016

```text
xGR创新方案

           核心创新点

               KV Cache分级管
           1
             理
          共享缓存 + 非共享缓存


               xAttention优
           2
             化
          三阶段Attention计算


               Schedule优
           3
             化
          整图下沉Device执行，减少CPU参与


               混合Mask优
           4
              化
          Kernel内部生成异构Mask，防止显存爆炸
```

## Page 017

```text
创新1：KV Cache分级管理机制
                          共享缓存
                     Shared Cache - 在Prefill阶段生成，所有候选序列共享同一份Cache

                        避免了重复存储和冗余计算


                        显著减少内存占用


                        提升Prefill阶段效率


                          非共享缓存

                     Unshared Cache - 在Decode阶段，每个候选序列独立生成新的KV Cache

                        Token粒度进行动态管理


                        支持细粒度更新和回收


                        保持存储连续性
```

## Page 018

```text
      创新2：xAttention计算优化
  核心思想
对比传统的Page Attention， xAttention 将attention计算拆分为三个独立
部分，实现更高效的计算模式。


  三阶段计算流程


  1   共享部分处理

 对所有序列的 Shared Cache 进行统一计算


  2   非共享部分处理

 对每个序列独有的 Unshared Cache 进行计算                         与传统方案对比

                                                       传统Page Attention   每个序列独立加载全部Cache
  3   合并与归一化

 基于 Softmax 融合两部分输出，生成最终注意力结果
                                                       xAttention         共享部分统一计算，减少重复加载
```

## Page 019

```text
   创新3：Schedule优化与Device侧执行
 核心策略
将Beam Search核心逻辑 下沉至设备侧 实现，结合约束解码的早停机制，将整个候选序列的打分、排序与筛选，完整在GPU device设备上高效执行。


 优化收益

              减少大规模D2H（Device to Host）数据传输开
    减少数据传输                                    发挥并行能力   充分发挥GPU并行计算能力，大幅提升推理效率
              销


    降低关键路径    减少CPU参与，降低关键路径耗时                约束解码早停   结合约束解码的早停机制，提前终止无效计算
```

## Page 020

```text
 创新4：增量分段Mask计算
关键思路：将自定义掩码注意力转化为前缀 KV 复用 + 增量片段计算问题，以分层缓存 + 细粒度计算阶段拆分，实现无损精度、极致性能的优化。


                                           核心优化

                                     •   区域化分块策略：按掩码稀疏性拆分多个子计算stage，Target 段二段式
                                         精细化调度
                                     •   局部掩码：子stage仅维护专属小mask，同时局部mask在kernel内部生
                                         成，消除全局 Mask 搬运与同步开销
                                     •   级联 Online Softmax：子stage独立计算 + 结果累加，规避大矩阵单次
                                         计算，硬件流水化拉满
                                     •   无效区域零计算：直接裁剪掩码屏蔽块，彻底剔除无效 QK / Softmax 与
                                         KV 访存
```

## Page 021

```text
04
核心成果
从实验到生产环境的全面验证
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 022

```text
 性能收益：搜推迁移案例

      首页生成式推荐                                 生成式搜索

                           +92.4                                   1x
性能提升                                   性能提升
                           %                                       +

 TP99时延优化                                TP99时延优化
优化前                          优化后        优化前                        优化后
76m                                    118m                        47m
                             26ms
 s                                       s                          s
             时延降低 65.8%                               时延降低 60.2%


 迁移落地xGR方案，性能显著提升                        线上高峰时期毛刺现象明显缓解


   生产环境验证
   xGR方案在首页生成式推荐和生成式搜索两大核心业务场景成功落地， 性能提升显著，时延大幅降低。
```

## Page 023

```text
开源评测

 性能对比数据


TRT-     TensorRT-LLM
                               baselin
LLM      业界开源SOTA
                                     e


 xGR
        xGR（我们的方案）               ~1x
        业界性能SOTA水准


       相比TensorRT-LLM性能提升约1倍
```

## Page 024

```text
 业务收益：核心场景落地
                                        OxygenRec场
    搜推场景
    首页推荐 + 搜索
                                        景
                                        多场景覆盖


 资源节省                               覆盖场景
支撑首页生成式推荐/搜索等核心业务场景落地， 节省近一半卡资源    百补   包邮   结算页    爱购


     UCTR提升            UCVR提升
                                    性能指标
   +10.3%             +6.9%       端到端TP99
                                                                       <
                                                                       70ms

 核心业务指标显著提升
                                    业务效果

                                  UCTCVR提升 +2.27% ~ 6.07% (显著）


    首页推荐               生成式搜索            百亿补贴                     结算页
```

## Page 025

```text
    学术价值

xGR创新性技术方案，在核心典型业务场景效果提升明显，撰写论文投稿SC26。


   论文链接

 https://arxiv.org/pdf/2512.11529
```

## Page 026

```text
05
未来展望
生成式推荐的技术演进方向
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 027

```text
 技术趋势预判

   Sparse Scaling             Dense Scaling              Generation
   Up                         Up                         Paradigm

核心方向                       核心方向                       当前主流
用户序列中的稀疏特征仍然非常重要           基于世界知识+全场域联动的Reasoning推理   广度优先的束搜索（Beam Search）生成方式


技术目标                       技术目标                       演进方向
在全站全域数据以及全生命周期万级用户长        引入图像、文本更多模态，结合MoE等模型       借鉴大语言模型（如DeepSeek）中的MTP并
序列建模的加持下，实现TB级别            结构设计，实现10B级别模型的高性能推理       行解码技术，以及扩散模型（Diffusion
Embedding的十分钟级别更新                                     Model）的并行生成能力


 稀疏特征持续演进                   稠密模型规模扩大                   生成范式多样化


   技术演进洞察
   生成式推荐技术正在从单一模态向多模态融合演进，从判别式向生成式范式升级，从中小规模向大规模Scaling Up发展。xGR为这一演进路径提供了一种技
   术优化方案，支持未来更大规模、更复杂场景的落地应用。
```

## Page 028

```text
三大核心挑战


             生成式推荐正在重新定义推荐系统
     Generative Recommendation Is Redefining The Recommendation
                              System


                    联系交流                    论文链接
                                            arXiv:2512.11
                    欢迎技术探讨
                                            529
```

## Page 029

```text
InfoQ 极客传媒
QCon
全球软件开发大会
THANKS
大模型正在重新定义软件
Large Language Model Is Redefining The
Software
```

## Page 030

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
