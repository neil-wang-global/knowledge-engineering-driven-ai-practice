# 卢亿雷-DeepResearch-X-OpenClaw-实现路径与-Token-成本控制

> Page-by-page information extraction from rendered page images. Content is organized by page and preserves visible text/layout as completely as practical.

## Page 001

```text
DeepResearch X
OpenClaw：实现路径与
Token 成本控制
卢亿雷
白海科技创始人 & CEO
```

## Page 002

[No extractable text detected on this page from the source PDF/page image. Visual content may be image-only or unreadable.]

## Page 003

```text
     01   行业现状与挑战


     02   DeepResearch x 龙虾

     03   系统架构总览

目录   04   核心技术设计

     05   配置体系与平台化能力

     06   Token成本优化及总结展望
```

## Page 004

```text
行业现状挑战
```

## Page 005

```text
为什么需要 Deep Research？

    传统搜索                 RAG        Deep Research


 关键词匹配
              →   向量检索
                               →   多轮循环研究
 单次检索             知识增强             自主规划
 链接列表             单轮问答             完整报告输出




 核心价值：用户不再需要手动搜索、整理、总结 — 智能体自主完成从「问题」到「报告」的
 全流程
```

## Page 006

```text
Deep Research 行业竞争格局
2024.12 Google 首发 Deep Research → 2025.02 OpenAI 跟进 → 各厂商快速入局 → 2026 进入成熟竞争期




    10+                               3-30min                                           48.9                                        25%
   主要产品/团队                               报告生成耗时范围                              DR Bench 最高分 (Gemini)                       传统搜索量预计下降(2026)



主要玩家
  Google Gemini             免费可用 · Gemini 3 Pro · DR Bench 领先

 OpenAI ChatGPT             o3/o4-mini · 技术深度强 · 30次/月(Plus)

    Perplexity              速度最快(3-5min) · 100-300引用 · 过程透明

 Anthropic Claude           安全审慎 · 多视角推理 · 可验证引用

    xAI Grok                实时数据 · 与Perplexity集成 · 快速迭代
        数据来源: [1] DeepResearch Bench (deepresearch-bench.github.io) [2] Gartner 2024.02 预测 [3] Alici.AI Top 10 DR Agents 2025 [4] 各产品官方文档
```

## Page 007

```text
   主流 Deep Research 产品深度对比
        维度                     Google Gemini                    OpenAI ChatGPT                          Perplexity                           Claude

 底层模型                  Gemini 3 Pro                       o3 / o4-mini                        多模型混合                              Claude Opus 4

 生成耗时                  5-20 分钟                            5-30 分钟                             3-5 分钟                             5-20 分钟

 报告长度                  ~12,000 字                          10,000-16,000 字                     5,000-10,000 字                     视任务而定

 引用数量                  20-50                              20-50                               100-300                            20-40

 研究规划                  可编辑计划                              自动规划                                实时展示                               多视角分析

 核心优势                  搜索生态集成                             技术深度                                速度与透明度                             安全与准确性

 主要短板                  创意性不足                              速度较慢                                报告偏短                               搜索源较少



    市场洞察：Gemini 凭借 DR Bench 48.9 分暂时领先，但各家差距不到 4 分 — 竞争焦点正从「能力」转向「体验」和「生态」


数据来源: [1] DeepResearch Bench RACE Framework [2] 各产品官方文档 & Help Center [3] Bright Inventions AI DR Comparison 2025 [4] Perplexity/OpenAI/Google 官方博客
```

## Page 008

```text
   技术趋势与演进方向

           从 Chat 到 Agent                                                 深度研究民主化                                            生态与平台竞争

                                                                                                                         •   Google/Microsoft 生态优势凸
     •       对话范式已终结                                                                                                         显
                                                                   •      免费额度逐步开放
     •       竞争转向"能办事"的智能体                                                                                               •   企业 LLM API 份额:Claude
                                                                   •      ChatGPT 免费用户可用(受限)
     •       Gartner: 2026年 40% 企业应                                                                                          32% · OpenAI 25% · Google
             用                                                     •      Gemini 提供免费 Deep                                   20%
                                                                          Research
     •       将嵌入任务型 AI Agent                                                                                             •   企业 AI 投资 370 亿美元
                                                                   •      技术门槛持续降低                                           (2025)
     •       Agentic Search 成为新战场
                                                                                                                         •   差异化从能力转向体验




     定位
     聚焦企业级场景：可配置的研究流程 · 多搜索源适配 · 多租户隔离 · 双模通信保障稳定性 — 面向 B 端提供可运营的
     Deep Research 服务

数据来源: [1] Gartner 2025.08 预测 [2] Menlo Ventures 2025 Mid-Year LLM Report [3] Menlo Ventures 2025 State of GenAI ($37B)
```

## Page 009

```text
Deep Research 落地的核心技术难题
各家产品能力趋同，真正的壁垒在工程落地。以下是我们在实践中识别的共性难题：

     长任务稳定性
 1   研究任务 20-30 分钟是常态，SSE 长连接在这个时间尺度上极不稳定。如何保证内容不丢、进度可追、断点可恢复？



     研究过程的可控性
 2   模型自主循环检索，但用户和运营方需要控制研究深度、指定搜索源、随时终止任务、过滤无关输入。如何在"自主"
     和"可控"之间取得平衡？


     多租户下的配置复杂度
 3   不同客户对报告形式、搜索服务、澄清方式的诉求各不相同，且每次调用可能还要临时覆盖。如何设计一套不失灵活
     的配置体系？


     多格式输出一致性
 4   同一份报告要输出 PDF、Word、HTML 三种格式，还要精确还原引用角标。Markdown 到三种格式的渲染如何保证
     一致？
```

## Page 010

```text
DeepResearch X 龙
       虾
```

## Page 011

```text
OpenClaw：2026 年第一现象级 AI 项目

         320K+                               1,000+           30,000+
          GitHub Stars                         全球贡献者          Clawhub skills
       60天超越 React 十年纪录                      每周活跃提交者 1,000+   可扩展 Agent 能力边界




   什么是 OpenClaw？

   奥地利工程师 Peter Steinberger 于2025年11月发布的开源
   AI Agent 框架。

   核心定位：本地优先、自主执行。用户通过 IM
   （Slack/Whatsapp等）用自然语言下达指令，AI 自主规划并
   执行文件操作、浏览器自动化、数据抓取等复杂任务。

   2026.2.14 创始人被 OpenAI 收编，项目移交开源基金会。
数据查询与 2026 年 3 月 20 日
```

## Page 012

```text
OpenClaw的技术架构
Chat channels（聊天渠道）：通过 聊天工具与 OpenClaw 交互，
适配器统一各平台消息格式。

Gateway（网关核心）：Node.js 核心进程，含三大子系统——
Session manager 隔离会话、Lane queue 编排任务、Skill selector
按需注入技能。

Memory system（记忆系统）：双层结构。每日日志提供短期上下
文，MEMORY.md 存储长期信息，/compact 命令压缩时先持久化防
遗忘。

Trigger / heartbeat（触发/心跳）：通过 cron、webhook、Gmail
等机制主动唤醒 AI，无需用户先开口即可行动。

AI model（大模型）：Gateway 将上下文发送给 LLM（Claude、
GPT 或本地模型），返回推理结果和工具调用指令。

Local tools（本地工具）：浏览器控制、Shell 命令、日历邮箱等
50+ 集成，全部运行在用户本地，数据不外泄。
```

## Page 013

```text
「养龙虾」到底在养什么？

  操作电脑                   IM 交互

  浏览器自动化、文件管理、多步骤任务串联    企微 / 飞书 / 钉钉 / Slack /Whatsapp等原生接入




  培育专属 Agent             24/7 运行


  持续投喂指令 + 偏好校准 + 经验沉淀   Token 消耗是对话的百倍至千倍




  从「对话交互时代」迈入「行动执行时代」
```

## Page 014

```text
全球巨头 + 国内大厂全面入局

   海外巨头                                 国内「类龙虾」产品全景


   OpenAI 收编创始人，整合 Agent 能力；             智谱 AutoClaw/澳龙      月之暗面 Kimi Claw   MiniMax MaxClaw
   NVIDIA GTC 发布 NemoClaw / OpenShell

                                         阿里 CoPaw（开源）          字节 ArkClaw       百度 DuClaw


   国内企业动态
                                        腾讯 QClaw/WorkBuddy    有道 LobsterAI      小米 miclaw


   智谱、月之暗面、MiniMax、阿里、字节、百度、
   腾讯、有道、小米等 13+ 企业集体入局                   阿里云 JVS Claw
   云端 SaaS + 本地部署两条路线并行




© 2026 白海科技 版权所有
```

## Page 015

```text
在 OpenClaw 中实现 Deep Research：要点与难点
实现要点                                          核心难点

1   Skill 插件封装                                1   长任务与消息通道冲突
    将 Deep Research 三阶段流程封装为 SKILL.md 插件，复        研究任务 20-30 分钟，但 WhatsApp/Telegram 有消息超时和
    用 OpenClaw 技能系统                               长度限制，需要增量推送+断点恢复

2   多模型路由                                     2   多平台渲染差异
    利用 OpenClaw 的 model failover 能力，按研究阶段选择       Markdown 报告在 Signal/Slack/Web 中渲染效果不同，需要按
    最优模型（规划用强模型、检索用快模型）                           通道自适应格式化

3   消息通道适配                                    3   Token 消耗放大
    通过 OpenClaw 的 23+ 消息通道统一输出研究报告，适配             Agent 框架增加工具调用上下文开销，单次研究 Token 消耗可
    不同平台的消息长度限制                                   能是直连 API 的 3-5 倍

4   本地数据安全                                    4   并发与隔离
    OpenClaw 本地优先架构天然满足数据隐私需求，研究过                 多用户同时发起研究任务，本地资源有限，需要任务队列管理
    程数据不离开用户设备                                    与上下文隔离


我们的思路
不重新造轮子，而是将成熟的 Deep Research 引擎以 Skill 插件形式集成到 OpenClaw。核心研究能力（规划、检索、生成）由
后端服务提供，OpenClaw 负责通道适配、用户交互和任务管理。下文详述的架构设计正是基于这一分层思路。
```

## Page 016

```text
系统架构总览
```

## Page 017

```text
系统架构全景




         白海搜索




                8 / 29
```

## Page 018

```text
DeepResearch模型训练




                   8 / 29
```

## Page 019

```text
DeepResearch模型训练




                   8 / 29
```

## Page 020

```text
三阶段流程设计


        1                    2                  3

     需求分析                 研究规划               深度研究与报告
                 →                   →

•   意图识别与拒答判断        •   自动生成研究计划        •   循环检索与分析
•   需求澄清交互           •   复杂度评估           •   增量内容输出
•   自然语言 / 表单式       •   用户确认(可跳过)       •   进度百分比追踪
•   报告形式预判           •   搜索策略制定          •   多格式报告生成
```

## Page 021

```text
核心设计原则


    C          O            I            D
  可配置性       可观测性       多租户隔离       双模通信



三层配置逐层覆盖   实时进度百分比    账户级数据隔离     轮询模式保稳定
每个环节可定制    中间处理信息输出   独立鉴权Token   SSE模式保实时
灵活适应不同场景   多维数据监控     配置互不干扰      按需选择
```

## Page 022

```text
核心技术设计
通信方案 · 增量输出 · 进度追踪 · 任务控
           制
```

## Page 023

```text
通信方案选型：轮询 vs SSE
```

## Page 024

```text
增量内容输出机制

                      内容块设计                  输出流程

{                                   1   模型生成内容片段
    "task_id": "dr_20240315_001",
    "blocks": [
       {                            2   服务端缓存内容块 + 编号
         "block_id": "blk_007",
         "type": "content",
         "text": "根据检索结果...",       3   客户端轮询请求
         "sequence": 7
       }
    ],
    "progress": 45,                 4   返回增量内容块 + 进度
    "is_complete": false
}
                                    5   客户端拼装渲染
•       每个内容块带唯一编号
•       JSON 格式标识，支持客户端拼装           首次轮询返回第三阶段所有已产生历史
•       增量输出，仅返回新产生内容
```

## Page 025

```text
进度与过程可视化

             进度百分比                                          处理信息

                                       "process_info": [
    45%
                                         { "title": "搜索行业报告",
                                           "detail": "检索到 15 篇相关文献..." },
                                         { "title": "分析竞品数据",
进度 = 当前循环轮数 / 循环轮数硬上限                      "detail": "提取了 8 个关键指标..." }
                                       ]
循环结束 → 固定输出 100%




                                轮询间输出示意

     轮询 #1              轮询 #2                 轮询 #3                          轮询 #N
   全部已产生历史
                →    间隔内新增信息
                                   →      间隔内新增信息
                                                                →           最终内容 100%
      t=0s               t=5s                  t=10s                          t=完成
```

## Page 026

```text
任务控制：终止与拒答

        终止研究任务                  拒答机制

•   支持研究过程中随时终止      •    对用户输入进行意图识别
•   终止后释放模型和服务占用     •    拒绝与深度研究无关的输入
•   保证资源不被长期占用       •    判定拒答时直接终止任务
•   客户端收到终止确认后停止轮询   •    向客户端输出特定拒答标识

1. 客户端发起终止
                                 开关控制
2. 服务端中断模型调用
                         默认关闭
3. 释放计算资源
                         关闭时跳过拒答判断，直接执行研究任务
4. 返回终止确认
```

## Page 027

```text
端到端交互时序
```

## Page 028

```text
配置体系与平台化能力
  三层配置 · 搜索集成 · 报告输出
```

## Page 029

```text
三层配置架构


    白海搜索(默认）
```

## Page 030

```text
研究过程可定制
澄清形式               研究规划确认
自然语言澄清 · 表单式澄清     需要确认 · 跳过确认

默认：自然语言            默认：不跳过

根据场景选择最适合的用户交互方式   跳过时直接使用模型生成规划执行




报告复杂度              报告形式
简单 · 复杂 · 自动       通用 · 自动

默认：复杂              默认：通用

影响研究深度、循环轮数和最终质量   优先级高于需求分析阶段的模型判断
```

## Page 031

```text
多格式报告输出
          纯文本模式                            纯文本 + 可视化报告

Markdown 渲染结果输出为：                   在纯文本基础上额外输出：

  PDF         渲染后的排版文档
                                    •   纯文本的 PDF / Word / HTML
 Word         可编辑的文档格式              •   模型生成的 HTML 可视化报告
                                    •   包含图表、交互式内容
 HTML         网页版报告




文件角标还原
生成 Word & PDF 时，基于 URL 编号结果，使用固定格式替换模型原始输出的 [ref_n] 标记，实现引用角标的精确
还原。
文件支持按需查询、获取和分享。
```

## Page 032

```text
外部搜索服务集成

       白海搜索                  百度搜索         阿里搜索
        默认                       可选           可选


标准搜索引擎                  中文搜索增强        多模态搜索
内置集成                    需提供鉴权凭证       需提供鉴权凭证
无需额外配置                  适合中文场景        适合电商/技术




选择逻辑
•   调用接口: 参数指定 > 账户静态配置 > 系统默认
•   调用方提供外部搜索服务对应的鉴权凭证
```

## Page 033

```text
账户与鉴权管理

            账户体系                  Token 管理 & 数据隔离

                  账户
                              Token 管理
          唯一 ID + 账户名称
                              •   每个账户可拥有多个鉴权 Token
      数据完全隔离（输入 & 输出）
                              •   Token 支持设置别名（必须）
                              •   支持新增、禁用和恢复操作
 Token A (生产环境)          启用
                              数据隔离
 Token B (测试环境)          启用   •   传入 DR 服务的所有数据 — 隔离
                              •   DR 服务输出的所有数据 — 隔离
 Token C (已禁用)           禁用   •   不同账户间严格隔离
```

## Page 034

```text
数据监控与服务配置

        数据监控                      服务配置管理

支持任意数据 × 任意维度的交叉统计        账户级静态配置，通过独立 Config API 管理

统计维度     示例数据              基础服务设置
账户       调用次数 / Token用量    报告复杂度 · 搜索服务 · 拒答开关
时间       日均任务数 / 峰值并发

搜索源      各搜索服务调用量          外部服务设置
                           搜索鉴权凭证 · 服务端点配置
复杂度      简单/复杂任务分布

状态       成功/失败/终止率
                           偏好设置
                           报告风格 · 澄清形式 · 个性化项
```

## Page 035

```text
Token 消耗优化
```

## Page 036

```text
Token是智能时代的“电力”与“流量”

                   工业时代                                               信息时代               智能时代



                  电力                                              流量 / 带宽              Token
              没有电，工厂停摆                                             没有网，企业脱节          没有Token，AI停摆


      电力是一切工业生产的基础                                            流量是数字经济的血液         Token是AI Agent思考和行动的燃料


      国家电网 = 基础设施                                             CDN / 云计算 = 基础设施   Token优化平台 = 新基础设施


      电费 = 生产成本的核心变量                                          带宽费 = 运营成本的核心变量    Token费 = AI应用的核心成本


      省电技术 = 竞争力                                              流量优化 = 竞争力         Token优化 = 核心竞争力




                         谁掌揧 Token 优化能力，谁就掌揧 AI 时代的成本主动权——正如电力之于工业、流量之于互联网

Sources: Introl Blog, Sanand LLM Pricing, FinOps Foundation
```

## Page 037

```text
Token成本全栈公式
  Total Cost Per Request =
  ( Input × P_in ) + ( Output × P_out ) + Retrieval + Embedding + Orchestration +
  Observability − Cache




Input Tokens      30-40%        Output Tokens      40-50%        Retrieval           5-10%

用户Prompt消耗                      模型生成输出                           RAG检索查询



                                                                                          -
Embedding           3-5%        Orchestration       5-15%        Cache Savings
                                                                                    10~30%
向量嵌入维护                          Agent编排开销                        缓存节省（减项）
```

## Page 038

```text
Deep Research Token 成本分析
单次深度研究的 Token 消耗远超普通对话，优化空间巨大


         需求分析阶段                    深度研究阶段                    报告生成阶段


          ~10%                      ~75%                      ~15%
            总消耗占比                     总消耗占比                     总消耗占比

Input: 2-5K tokens        Input: 50-200K tokens     Input: 20-50K tokens
Output: 1-3K tokens       Output: 10-30K tokens     Output: 5-15K tokens
澄清问题+研究计划                 多轮检索+上下文累积                长报告+引用整理




核心发现
 深度研究阶段占 75% 成本，多轮检索的上下文窗口持续膨胀是主因。Output Token 单价是 Input 的 3-5 倍，控制输出长度的
 ROI 最高。
 单次研究总消耗可达 80K-300K tokens，Agent 框架（如 OpenClaw）还会额外增加 30-50% 的工具调用开销。
QCon 全球软件开发大会                                                              32 / 36
```

## Page 039

```text
Deep Research 龙虾 Token 降本策略全景

  1   语义缓存      请求前     2   Prompt Cache   请求前   3   模型路由     请求中



对相似研究请求做语义匹配，          固定系统提示词为前缀，利用             按子任务复杂度分流：规划用
命中则跳过 LLM 调用直接返回       API 原生缓存减少重复计费            强模型，摘要/提取用轻量模型




  4   输入压缩与裁剪    请求中    5   Output 精确控制 响应控制     6   研究轮次收敛     流程控制



滑动窗口+历史摘要替代全文，         中间轮次只要结构化摘要不要             设定信息增益阈值，新一轮检
控制每轮上下文长度上限            全文，Output 单价远高于 Input     索无显著新信息时提前终止



QCon 全球软件开发大会                                                     33 / 36
```

## Page 040

```text
Token 优化实战：行业数据与落地效果
按请求生命周期分层优化                                              行业实测数据

             语义缓存 · Prompt Cache                            优化手段                 实测效果                    数据来源
请求前
             命中即跳过，不产生调用                                   模型路由                 $10→$0.9
                                                                                                     Artificial Analysis
                                                          o3→o4-mini               /次

             模型路由 · 上下文裁剪                                                        ↓ ~73%
请求中                                                         语义缓存                                    Redis LangCache
             选对模型，压缩输入                                                          高重复场景

                                                                                 ↓ ~90%
                                                          Prompt Cache                              Anthropic/OpenAI
                                                                                 重复前缀
             Output 精控 · 轮次收敛
响应后                                                                               ↓ ~80%
             控制输出量，减少总轮次                                   上下文压缩                                     Zylos Research
                                                                               Input tokens

                                                                                 ↓ 60-80%
                                                            综合叠加                                      多源交叉验证
                                                                                  总成本


关键结论
单次 Deep Research 原始成本：o3 约 $10/次，o4-mini 约 $0.9/次（Artificial Analysis 实测 10 queries）
组合优化后可控制在 $1-3/次 — 模型路由是 ROI 最高的单一策略，缓存+压缩进一步叠加
先量化再优化，降本不降质 — 全链路 Token 监控 + 研究质量评测（RAGAS）守住质量红线
                                                         数据来源：Artificial Analysis, Redis, Zylos Research, Anthropic/OpenAI 官方文档
```

## Page 041

```text
前沿技术



LLMLingua 提示词压缩

                                                2-5x
 Microsoft Research

 压缩流程
                                          提示词压缩率，几乎无质量损失
              原始提示词 (845 tokens)
                       ↓
                 小模型计算信息熵
                                   技术演进
                       ↓
               低信息量Token被剥离        V1: 信息熵启发式压缩
                                   V2: GPT-4蒸馏BERT编码器，Token级二分类
                       ↓
                                   已集成: LangChain + LlamaIndex
                压缩后 (485 tokens)
                                   每次调用隐形节省360+ tokens
```

## Page 042

```text
前沿技术



FrugalGPT 模型级联策略
           小模型                   中型模型                              旗舰模型
        (Haiku / mini)   →     (Sonnet / 4o)        →             (Opus / o1)

        成本极低、速度极快               平衡性能与成本                            复杂任务兆底




 Stanford研究实证结果                        核心逻辑



          ↓ 98%
       推理成本削减            +4%
                                        • 小模型先试 + 置信度评估器
                                        • 绝大多数流量在低成本层消化
                                        • 只有复杂任务触发旗舰模型
                                        • 测试集: HEADLINES / OVERRULING / COQA
```

## Page 043

```text
前沿技术


推测解码 Speculative Decoding
              草稿模型                                                目标模型
               Draft Model
                                        →→→                       Target Model


        小、快、推测未来Token序列                                    大、并行验证草稿序列的正确性




     111%                        60%                      3x                     80%
       吞吐量提升                    预处理消耗降低                   吞吐量提升                  延迟缩减
       EAGLE-3                    Amdocs                   Snap                  Amdocs




NeurIPS 2025 / ICLR 2026: 奖励推测解码(RSD)—过程奖励模型动态判断何时调用大模型
```

## Page 044

```text
总结与展望
关键收获
    1   双模通信保障稳定         轮询保稳定 + SSE 保实时，按需选择


    2   三层配置灵活可控         默认→静态→参数，逐层覆盖满足多样需求


    3   开源框架可集成          OpenClaw 等开源 Agent 框架是 Deep Research 落地的有效载体


    4   Token 降本 65%+    缓存+路由+裁剪三层降本，质量不降


    5   平台化多租户           账户隔离 + 监控 + 服务配置，可规模化运营


未来方向

多 Agent 协作 · 更智能的自适应规划 · 多模态研究能力 · 实时数据源接入 · 开源生态持续降本

QCon 全球软件开发大会                                                     35 / 36
```

## Page 045

```text
THANKS
大模型正在重新定义软件
Large Language Model Is Redefining The
Software
```

## Page 046

[No extractable text detected on this page from the source PDF/page image. Visual content may be image-only or unreadable.]
