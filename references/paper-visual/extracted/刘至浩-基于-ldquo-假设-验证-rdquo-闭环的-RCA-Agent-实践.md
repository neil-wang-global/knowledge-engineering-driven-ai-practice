# 刘至浩-基于-ldquo-假设-验证-rdquo-闭环的-RCA-Agent-实践

> Page-by-page information extraction from rendered page images. Content is organized by page and preserves visible text/layout as completely as practical.

## Page 001

```text
基于“假设-验证”闭环的 RCA Agent 实践



刘至浩
趣丸科技 高级平台研发工程师
```

## Page 002

极客邦科技 2026 年会议规划

副标题：促进软件开发及相关领域知识与创新的传播

右上：参会咨询二维码

四个会议卡片：

1. 6月 上海，1000人
   - AiCon 全球人工智能开发与应用大会
   - 会议时间：6月26-27日
   - 方向：AI Infra 系统工程；多 Agent 协作与实践；多模态融合；模型训练与推理创新；数据平台与特征服务
2. 8月 深圳，1000人
   - AiCon 全球人工智能开发与应用大会
   - 会议时间：8月21-22日
   - 方向：Agentic AI；轻量化与高效推理；多模态应用；AI + IoT 场景实践；AI 工业化落地
3. 10月 上海，1200人
   - QCon 全球软件开发大会
   - 会议时间：10月22-24日
   - 方向：AI Agent；Vibe Coding；智能可观测；热重构；模型攻防；AI x 创造力
4. 12月 北京，1000人
   - AiCon 全球人工智能开发与应用大会
   - 会议时间：12月18-19日
   - 方向：大模型架构创新；多模态 AI 产业融合；具身智能；AI for Science；大模型安全

## Page 003

```text
     01   困境与挑战


     02   设计与实践



目录   03   案例展示


     04   思考与总结


     05   未来展望
```

## Page 004

```text
困境与挑战
```

## Page 005

```text
需求背景
```

## Page 006

```text
 理想的样子


结果导向                           严谨可靠

拒绝无效拉扯，目标是一次交互出结论，             坚持“没证据就不乱说”，用证据说话。
不让用户陪着 AI 做填空题 。




快速排查                           自我进化

比“人”快，多方向思考与验证 。
                     RCA根因分析   通过持续的系统反馈闭环，不断沉淀总
                               结、自我进化，像“老司机”。
```

## Page 007

```text
现实的样子

  容易幻觉，结果不稳定     排障时会“脑补”出看似合理实则完全错误的根因结论。




  经验工程化          专家经验难提取，多轮后导致模型逻辑“失焦”。




  工具和系统集成麻烦      返回数据二次加工，工具集相互影响，跨团队协作与工具对齐成本高。




  长链路时很脆弱        一旦步骤变多、任务变复杂，成功率会明显下降，长链路自主执行尤其脆弱。




            生产很难跑“稳”，用户很难“买单”
```

## Page 008

```text
 Agent 层面




在根因定位场景下

• Context 中 Prompt “打架”
• 2-3轮后，成功率骤减
                                Thought      Action   Observation
• 低效信息噪音多
• 优化难，常常要追踪“模型
  输出 + 工具调用 + 重试 +
  上下文变化”




               一旦 Observation 带了噪声，整个 Plan 就会很容易跑偏。
```

## Page 009

```text
   工具缺陷



“可观测”对AI不友
好
• Schema 过于繁琐
• 观测数据的高维与冗余导
  致响应体（Payload）通
  胀，极易触碰 LLM 的上
  下文窗口极限




                   Agent 往往面临“心有余而力不足”
```

## Page 010

```text
   资源层面




服务亚健康状态

• 变更中、干预中
• 业务周期性噪声
• 导致 Agent 提前结束




                  每个资源有其“画像”，多轮分析后会导致Agent “水土不服”
```

## Page 011

```text
用户层面




 “并行排查，提升效率。”   “没有证据支撑的结论，比没有结论更可怕。”
```

## Page 012

```text
设计与实践
```

## Page 013

```text
     Agent 实践




       ReAct              Plan-and-Execute       Multi-Agent

•   容易在长任务中产生“幻觉”
                      •   初始计划如果出错可能导致       •   多轮会有噪音。
    或死循环。
                          全盘失败。              •   智能体间通信与协调成本高昂。
•   Token 消耗随步骤增加而剧
                      •   需要复杂的重计划机制。        •   “责任推诿”，调试难度大。
    增。
                      •   整体响应速度慢。           •   适合边界明确，协商推理场景。
•   缺乏全局观。
                      •   步骤相对固定的复杂任务
•   简单、交互性强、具有动态
                          （如数据分析、报告生成）。
    适应性。
```

## Page 014

```text
Hypothesis Agent
```

## Page 015

```text
Verification Agent Prompting
                                   Text 1
                                   � 事实： 磁盘已满。
                                   � 规则： 磁盘满属于“严重故障”。所有“严重故障”都会触发报警。
                                   ❓ 问题： 当前是否触发报警？
                                   � 答案： 正确 (True) （逻辑闭环）



                                   Text 2
                                   � 事实： 内存升高。
                                   � 规则： 磁盘满属于“严重故障”。所有“严重故障”都会触发报警。
                                   ❓ 问题： 当前是否触发报警？
                                   � 答案： 未知 (Unknown) （逻辑缺失）




  https://arxiv.org/abs/2405.067
  07
```

## Page 016

```text
   Verification Agent Prompting
标准 (Standard Prompting)
                                       A: 结论是 正确 (True)。 ❌
Model Input (示例 Prompt)：
                                       模型有时会直接凭直觉联想（内存高 -> 报警）。
Q: 根据 Text 1～N，判断结论‘正在报警’是否正确？N
A: 结论是 正确 (True)。
                               }
Q: 根据 Text 2，判断结论‘正在报警’是否正确？


思维链 (Chain-of-Thought Prompting)       A: 从‘内存升高’开始。内存高说明系统压力大，这属于‘核心故
Model Input (线性推导 Prompt)：             障’。根据规则，核心故障必报警。所以结论是 正确 (True)。 ❌

                               }
Q: 根据 Text 1～N，判断结论‘正在报警’是否正
                                   N   Input “通过思路去证明 True”，导致模型私自断言了“内存高 = 核心故
确？
                                       障”。
A: 从‘磁盘已满’开始，由于这是‘核心故障’，
而核心故障必报警。所以结论是 True。
Q: 根据 Text 2，判断结论‘正在报警’是否正确？
假设检验 (Hypothesis Testing
                                       A: 首先假设结论为真（正在报警）：规则要求必须满足‘磁盘已
Prompting)                             满’。但事实是‘内存升高’，没提磁盘。无法证实。
Model Input (双向验证 Prompt)：
Q: 根据 Text 1～N，判断结论‘正在报警’是否正           接着假设结论为假（没有报警）：这需要证明不满足核心故障。但规
确？
A: 首先假设结论为真：为了满足报警，需满足核心故      }   N   则没定义‘内存升高’是否属于非核心故障。无法证伪。
                                       结论：未知 (Unknown)。 ✅
障，即磁盘已满。事实确实如此。所以为 True。               Input 里的“假设检验”范式强制模型在推导 Text 2 时去寻找必要条件，从而
Q: 根据 Text 2，判断结论‘正在报警’是否正确？           发现了证据链缺失。

               AI 的“脑补”比“不知道”更危险；不需要一个‘猜对’的 AI，而需要一个
               ‘没证据就不乱说’的严谨专家。
```

## Page 017

```text
Verification Agent Tools
  工具过滤+命名+工件




               图片比文字更直观，让结果更有说服力
```

## Page 018

```text
Hypothesis-Verification Loop




                                      DAG




      当所有叶子节点均被证伪，或推理达到设定层级 -> 收敛总结
```

## Page 019

```text
Context Engineering




                        模型容易过早终止推理（着急收尾），压缩会导致遗漏
                        关键细节与排障重点。


                      当一个 Context Window 同时承担‘假设’与‘验证’任
                      务时（既当裁判又当运动员），产生证实偏差（结果偏乐
                      观）。
```

## Page 020

```text
Context Engineering




验证时新开单独的上下
文窗口，每一次都是
“单独提问”。假设
时，动态把根到该节点
路径注入上下文。
```

## Page 021

```text
SubAgent + Feedback




                      通过用户的反馈，形
                      成固定的SOP，提升
                      排查速度。
```

## Page 022

```text
Memory
Datadog Bits AI SRE

                          bits.md
                      1   定义诊断套路、过滤已知噪声、约束执行作用域；确保
                          Agent 在统一标准下一致性、安全的自动化操作。




                          Monitor Runbook
                      2   随告警同步推送，内置故障上下文与标准处置步骤;消除信息
                          差，指导 On-call 工程师快速进入现场并按 SOP 止损。




                          Memories
                      3   将人工核实的 RCA（根因）选择性回填至监控器记忆列表;
                          实现“历史排障经验”资产化，确保同类告警触发时知识的
                          精准召回。
```

## Page 023

```text
Memory
```

## Page 024

```text
 思维链 CoT
risk-platform-backend-              输入现象： risk-server 告警 - QPS 环比下跌 50%。
svc                                 输出互斥假设：
                                    H1：流量上游故障（外部因素）。
微服务 QPS 瞬时跌幅达                       H2：内部熔断机制触发（自保因素）。
                                    H3：节点发生 OOM 重启（资源因素）。
50%                                 H4：数据库写入延迟引发反压（依赖因素）。
                         假设（互斥假设）
                                    输入 (Input)： H1-H4假设 + 知识库Knowledge + 故障历史。
          1                         输出 (Output)：
                                    H1：upstream_req_count 流量同步下降 > 40% 则假设成立。
                                    H2：istio_503_count    503 突增则假设成立。
                         生成验证准则     H3：pod_restart_reason 历史记录含有 OOMKilled 则假设成
                                    立。
                                    H4：ck_write_latency   延迟超过 2s 且队列积压则假设成立。
 4                2
                                    输入 (Input)： 第二步生成的具体查询动作（PromQL / SQL）。
                         事实取证       输出 (Output)： 原始事实证据快照。
                                    证据 A： upstream_req_count 为 12k/s，曲线平稳（波动 < 2%）。
                                    证据 B： istio_503_count 全链路计数为 0。

          3
                                    证据 C： 检测到 2 次 OOMKilled 事件，发生在故障时刻。
                                    证据 D： ch_write_p99 为 200ms（处于正常 Baseline）。



                         结果判定
                                    输入 (Input)： 第二步的判定准则 + 第三步的事实证据。
                                    判定逻辑 (Logic Check)：
                                    ❌ H1判定失败： 证据 A 与准则冲突（流量未下降）。
                                    ❓ H2判定未知： 证据 B 与准则冲突（无熔断标志）。
                                    ✅ H3判定成功：证据 C 与准则完美匹配。
                                    ❌ H4判定失败： 证据 D 显示数据库响应正常。
```

## Page 025

```text
Benchmark

            1   最终响应评估（黑盒）
                测试输出质量。无论内部实现如何，
                均有效。




            2   轨迹评估
                验证代理是否使用了正确的工具序列。




                 过程的可控性远比结果的偶然正确重要。
```

## Page 026

```text
如何用起来




        带着具体问题去寻找答案，进而形成固定解法
```

## Page 027

```text
案例展示
```

## Page 028

```text
实践案例
```

## Page 029

```text
实践案例
```

## Page 030

```text
实践案例
```

## Page 031

```text
实践案例
```

## Page 032

```text
实践案例
```

## Page 033

```text
实践案例
```

## Page 034

```text
实践案例
```

## Page 035

```text
思考与总结
```

## Page 036

```text
Agent 演进
```

## Page 037

```text
AI Agent：标准化运维的加速器




                       自主决策和问题解决能力。
          Agentic AI


                       模型能力、上下文工程、知识库、
          AI Agent     记忆、MCP、Skills ......


                       数据关联体系、可观测（Metrics,
                       Logs, Traces）体系、运维标准化。


    反思 AI 局限性并回归工程本质
```

## Page 038

```text
未来展望
```

## Page 039

```text
 自主决策执行


权限、安全、受控执行、回滚
```

## Page 040

```text
 根因定位层级

                                                       L4: 决策层 (Action)

                                       L3: 溯源层         根因 -> 闭环动作
                                                       归类，确认怎么解决并验证。 给
                     L2: 定位层                           出止损动作并监控恢复情况。
                                    故障点 -> 逻辑根因
   L1: 感知层                          确认为什么出事。 挖掘深度原因
                                    （如代码 Bug、配置变更、告警
                  异常 -> 故障传播路径
                                    阈值是否合理）。
                  确认是谁出的事。 在拓扑中锁定
数据 -> 异常判定
                  故障点（如具体微服务、DB 实
确认出事了。 识别异常现象     例）。
（Symptom），过滤噪声。




                        AI 应该是解决“为什么”的问题
```

## Page 041

```text
 Agent-Native

 “AI First” 系统应优先考虑对 Agent 友好

 过去监控是给人看的，未来监控要给
 Agent “看”（提供语义接口 Semantic
 API）。



 “可观测性的语义化”

当你的
logging/tracing/metrics/events 能让
Agent 读起来毫无阻力时，真正的智能运
维才会到来。



                                    引用：
                                    https://x.com/sandro_vol/status/1993727421867294756
```

## Page 042

```text
THANKS
大模型正在重新定义软件
Large Language Model Is Redefining The
Software
```

## Page 043

AiCon 上海站宣传页

标题：AiCon 上海站

副标题：探索 AI 应用边界 / Explore the limits of AI applications

时间地点：2026年6月26-27日 / 上海张江科学会堂

右上：参会咨询二维码

专题卡片：

- 专题：世界模型与多模态智能突破；专题出品人：朱政；钛链视界 / 联合创始人 & 首席科学家
- 专题：Agent 系统架构与工程化实践；专题出品人：曾浩楠；OPPO / 大模型算法负责人
- 专题：AI 原生数据工程；专题出品人：王彦辉；火山引擎 / 数据平台产品总监
- 专题：Agent 安全、评测与可信治理；专题出品人：马传雷（岳立）；支付宝 / 业务风控技术部负责人
- 专题：Agent 数据、记忆与运行时基础设施；专题出品人：邓亚峰；EverMind / CEO
- 专题：企业级研发体系的重构；专题出品人：沈浪；快手 / 研发效能负责人
