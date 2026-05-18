# 晁岳攀-鸟窝-智能体架构的降龙十八掌-从原型到工程落地的-ldquo-生死取舍-rdquo

> Page-by-page visual information extraction from rendered slide/page images. Text is OCR-assisted and preserves visible page order; diagrams/tables are represented by their visible labels and relationships as line-by-line text.

## Page 001

InfoO 极客传媒
QCon
全球软件开发大会
智能体架构的降龙十八掌
晁岳攀
百度资深工程师

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
Agent 模式速览
02
OpenClaw 分析
03
Hermes Agent 分析
目录
04
AutoResearch 实战

## Page 004

Agent 模式速览
模式介绍
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 005

• 明星产品Agent的实现有啥套路？
Agent Loop 不就是下面的代码吗？
为啥我们做出的智能体远达不及明星产品（CC、OpenClaw等）？
核心模式
所有 AI编程 Agent 共享同一个循环：调用模型、执行工具、回传结果。生产级系统会在其上叠加策略、权限和生命周期层。
••• agent_loop.py
while True：
response = client.messages.create （messages=messages, too Ls=tooLs
if response.stop_reason ！= "tool_use"：
break
for tool_call in response.content：
result = execute_tool（tool_call.name, tool_call.input）
messages.append（result）
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 006

• 建造明星产品的基础
LLMs
根据场景选择最合适的LLM
RAG
01
Tools
用最有效的资料生成最精确的、
在最简单的Agent Loop上（发动机）
最全面的结果
堆砌复杂的产品（豪华跑车）
05
02
架构模式
04
03
Memory
选择合道的架构模式，
在 Agent Loop
上下文（内存）管理
上层层构建
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 007

RAG 模式
RAG（检索增强生成）通过从外部数据源获取数据来增强LLM 的输出
图 RAG
朴素 RAG
利用知识图谱结构化实体关系，支持多跳推理和全局信息聚合。
基本方法包括文档分块、索引、基于语义相似性的检索和生成。
高级 RAG
纠正性 RAG（CRAG）
通过检索前技术（查询重写、分解）和检索后步骤（重新排序、摘
集成自我验证机制，对检索到的文档进行批判，如果信息不可靠，
要）提高检索精度。
则触发重新评估或替代搜索。
Agentic RAG
模块化 RAG
使用自主代理进行规划、选择工具、迭代推理和解决复杂的多跳查询。
一种灵活的、专门化的架构，它将流程分解为功能组件（搜索、检
索、生成），这些组件可以进行定制和重新排列，例如在专门的引
上下文 RAG
擎中。
利用聊天历史和对话状态来改进检索，解决对话式AI中的“上下文盲点”
问题。
混合 RAG
结合密集检索（向量搜索）和稀疏检索（关键词搜索），以确保语
HyDE（假设文档嵌入）
义理解和精确的关键词匹配。
LLM 生成查询的合成假设答案，然后将其用于语义搜索以查找真实的相似
文档。
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 008

•
Agent 架构模式
序号
隶属部分
模式名称
核心概念（Core
核心驱
业务
常见的坑（外部知识补
（Architecture）
Concept）
动力
充）
1
第一部
反思（Reflection）
从单次生成转变为深思熟
输出质
提升单次
容易陷入无限修改循
分：基础
虑的多步推理，通过批判
量
任务精度
环；多次反思会成倍增
增强模式
和改进自身工作来提升质
加Token消耗。
量。
2
第一部
工具使用（Tool Use）
赋予智能体调用外部API
外部扩
跨系统自
模型可能幻觉出不存在
分：基础
和函数的能力，克服知识
展性
动化
的工具名称或参数；外
增强模式
截止限制并与现实世界交
部API不稳定导致任务
互。
失败。
3
第一部
编程式工具调用
允许智能体在代码沙箱中
上下文
海量数据
代码沙箱可能面临安全
分：基础
（PTC）
编排工具并处理中间结
与计算
批处理与
逃逸风险；模想生成的
增强模式
果，仅将最终输出返回给
优化
复杂逻辑
代码可能存在逻辑错
上下文。
编排
误；中间状态黑盒化导
致调试困难。
4
第一部
ReAct（推理与行动）
在自适应循环中动态交替
自适应
多步复杂
推理链条容易断裂；面
分：基础
进行推理（思考）和行动
逻辑
调研
对错误反馈时可能卡在
增强模式
（工具使用），解决复杂
死循环中重复相同动
的多步问题。
作。
5
第一部
规划 （Planning）
在执行前主动将复杂任务
过程可
预测性流
初始计划过于死板，在
分：基础
分解为详细的、分步的计
追溯
程管理
执行中遇到意外变化时
增强模式
划，确保结构化和可追踪
缺乏动态调整的灵活
的工作流。
性。
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 009

•
Agent 架构模式
6
第二部
多智能体系统（Multi-
由专业智能体组成的团队
专家分
企业级协
智能体之间的通信成本
分：多智
Agent Systems）
协同解决问题，通过分工
工
作流水线
高；可能因为目标不一
能体协作
合作在输出中实现极高的
致导致输出偏离主题。
深度和质量。
7
第二部
黑板系统
灵活的多智能体系统，智
环境感
动态诊
共享记忆区的数据可能
分：多智
（Blackboard
能体在动态控制器引导
知
断、物联
发生冲突或被错误覆
能体协作
Systems）
下，通过共享的中央记忆
网调度
盖；难以维持全局一致
（黑板）进行协作。
性。
8
第二部
元控制器（Meta-
作为一个监督智能体，分
任务分
企业多功
元控制器成为性能瓶颈
分：多智
Controller）
析传入的任务并将其路由
流
能服务中
（单点故障）；路由判
能体协作
到专家池中最合适的专业
台
断失误会导致整个任务
子智能体。
失败。
9
第二部
集成模式（Ensemble）
多个独立智能体并行分析
鲁棒
关链决策
消耗资源极大（多次并
分：多智
问题，最终由“聚合器”智
性/去
支持
发API调用）；聚合器
能体协作
能体综合输出，得出更稳
偏
在面对分歧极大的观点
健结论。
时难以得出有效结论。
**10**
第三部
情景与语义双重记忆
结合记录过去对话的向量
长期个
私人专业
记忆检索的准确率难以
分：高级
（Episodic +
存储和存储结构化事实的
性化
导师/顾问
保证；旧有的矛盾信息
记忆与推
Semantic）
图数据库，打造类人的强
可能污染新推理。
理
大记忆系统。
11
第三部
思维树（Tree of
在树状结构中探索多条推
深度逻
尖端科
极高的时间延迟和
分：高级
Thoughts, ToT）
理路径，系统性评估并修
辑探索
研、复杂
Token成本；评估分支
记忆与推
剪分支，从而找到最佳解
博弈
质量的启发式方法难以
理
决方案。
设计。
12
第三部
图谱与世界模型记忆
将知识存储为结构化图
关联推
商业情
知识图谱的构建和更新
分：高级
（Graph /World-
谱，通过遍历连接进行复
理
报、知识
成本高昂；关系提取常
记忆与推
Model）
杂的多跳推理。
图谱分析
常存在噪音和错误。
理
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 010

•
Agent 架构模式
13
第四部
PEV（计划、执行、验
高度稳健的自我纠错循
零失误
财务审
“验证者”自身可能产生
分：安全
证）
环，由“验证者”智能体检
容忍
计、合规
幻觉，错误地否决正确
性与现实
查每次行动结果，实现错
操作
的执行结果或放过错
交互
误检测与恢复。
误。
14
第四部
心理循环/模拟器
智能体在采取实际行动
风险预
交易策
内部*模拟器”的准确度
分：安全
（Mental
前，先在内部心智模型中
判
略、安全
通常受限，无法完美反
性与现实
Loop/Simulator）
测试行动，以预测结果并
关键系统
映复杂的真实世界动
交互
评估风险。
态。
15
第四部
演练测试台（Dry-
安全关键模式，智能体提
安全红
敏感系统
如果过度依赖人类批
分：安全
Run Harness）
议的行动首先被模拟试运
线
发布控制
准，会丧失自动化系统
性与现实
行，必须经过批准后才能
的效率优势，造成流程
交互
真实执行。
阻塞。
16
第四部
反思性元认知
拥有“自我模型”的智能
边界意
医疗、法
可能陷入过度自我怀
分：安全
（Reflexive
体，能推理自身能力与局
识
律高风险
疑，导致频繁将简单任
性与现实
Metacognitive）
限，自主决定行动、使用
咨询
务抛给人类，降低系统
交互
工具或升级交由人类处
自主性。
理。
17
第五部
RLHF/ 自我改进
智能体输出受到批评并利
自我进
持续优化
模型可能过度迎合批评
分：学习
（Self-Improvement）
用反馈迭代修改，保存高
化
的内容工
智能体的特定偏好（奖
与适应
质量输出以提升未来表
厂
励作弊），导致输出风
现。
格单一。
18
第五部
元胞自动机
通过多个简单的、基于网
群体涌
物流模
全局行为极其难以预测
分：学习
（Cellular Automata）
格的去中心化智能体的局
现
拟、空间
和控制；难以针对特定
与适应
部交互，涌现出复杂的全
分析
业务目标进行精准调
局行为。
试。
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 011

Memory 管理模式
序号
内存优化方法
核心概念与原理
适用场景与优势
顺序优化
最基础的按发生顺序记录和存储历史对话上下文的方法。
适用场景：简单的、短生命周期的聊天机器人。
（Sequential Approach）
优势：最容易实现，能满足基础任务需求。
2
滑动窗口
限制智能体的记忆范围，仅保留最近特定数量（如窗口大小设为2）的交互记录作为上下
适用场景：简单的短期机器人。
（Sliding Window
优势：易于实现，能有效防止上下文超出
Approach）
Token 限制。
基于摘要的优化
对之前的对话内容进行总结，用简短的摘要替代冗长的原始对话历史。
适用场景：长时间、富有创造性的对话。
（Summarization Based
优势：能够在不产生大规模 Token 开销的情况
Optimization）
下，保持对话的整体连贯性和上下文流向。
4
基于检索的内存
利用内存向量数据库（如 FAISS）将信息转化为嵌人向量，通过高效的相似性搜索来检索相
适用场景：需要精确、长期回忆的智能体。
（Retrieval Based Memory）
关记忆。
优势：这是目前的行业标准，功能强大且可扩
展，是大多数RAG（检索增强生成）应用的基
础。
5
内存增强型架构
引入额外的LLM 调用来从对话中提取和保存关键事实。虽然成本较高，但能保留核心状
适用场景：高可靠性的个人助手。
（Memory Augmented
态。
优势：能够将关键事实与日常闲聊剥离开来，在
Transformers）
漫长且不断发展的对话中可靠地保留关键信息。
6
面向多任务的层次化优化
模拟人类思维，为不同的目标和用途构建不同类型的、分层的内存系统。
适用场景：高可靠性助手及复杂规划任务。
（Hierarchical
优势：在极端有效地减少 Token 数量的同时，
Optimization）
完美保留任务的核心事实与逻辑。
7
基于图的优化
利用图数据结构（如Networkx库）创建和管理知识图谱，将记忆存储为节点和实体关系。
适用场景：专家系统和知识库。
（Graph Based
优势：在推理数据点之间复杂关系的能力上具有
Optimization）
无与伦比的优势。
8
压缩与整合内存
运用高级策略对存储的记忆进行持续的压缩和信息整合，消除冗余。
适用场景：需要长期运行且记忆不断累积的复杂
（Compression &
智能体系统。
Consolidation Memory）
9
类OS（操作系统）内存管理
借鉴计算机操作系统的内存管理理念：将LLM 的上下文窗口视为 RAM（速度极快但容量有 适用场景：大规模智能体系统。
（OS-Like Memory
限，用于活跃程序），将外部数据库/文件视为 硬盘（容量大、成本低但速度较慢，用于长
优势：能在保持活跃上下文（RAM）小且快的
Management）
期存储）。
同时，为智能体提供几乎无限的记忆容量。
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 012

12
OpenClaw 分析
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 013

•
Tool Use 模式
模式概念
Tool Use（工具调用）是 Agent Loop 中模型与外部世界交互的核心机制。当模型判断需要执行操作（读写文件、
运行命令、搜索网页等）时，生成结构化的tool_call 请求，由运行时调度执行并将结果注入对话上下文，形成调
用一执行 观测的闭环。
工具类型
类别
示例
来源
核心工具
read, write, edit, exec, apply_patch
createOpenClawCodingTools（）内建
网络工具
web_search, web_fetch
sre/agents/tools/web-tools.ts
消息工具
message
src/agents/tools/message-tool,ts
媒体工具
image_generate, video_generate, music_generate,pdf
src/agents/tools/
会话工具
sessions_spawn, sessions_send, sessions_list，
sessions_yield
src/agents/tools/
定时工具
cron
src/agents/tools/cron-tool.ts
MCP工
运行时从 MCP服务器动态物化
materializeBundleMcpToolsForRun®
具
Skil 工
模型通过 Skil 工具按需加载
src/agents/skills/
具
网关工具
plugin.approval.request
src/agents/tooLs/gateway.ts
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 014

•
ReAct 模式
模式概念
ReAct （Reasoning + Acting） 是一种将 推理 与行动交织的 Agent 执行范式，由 Yao et al.（2023）提
出。OpenClaw 在其嵌入式 Agent运行时中实现了完整的 ReAct 循环，核心特征是：
思考一行动一观察一再思考，直至产出最终答案
三阶段循环
阶段
机製
实现
Keasomug
模型在隐跛标签内
进行内部推理
标签对，内容不暴＆给用户
Acting
模型调用工具执行
createopenClawCodingloole（）注册工具
擦作
（read/write/bash/exec/web_search/messige等）
Observing
工具结果注入上下
SessAonManager管理tooL_response消息，经
文
wcapstreamFnsanitizekelformedToo1Ca11s（）清洗
循环终止条件
1. 自然终止：模型返回的 response 中不再包含 tooL_call，仅产出 efinals 文本
2.循环检測（src/agents/too1-1oop-detection,ts）：四级递进防护
• generic_repeat ；连续相同工具调用（阈值10、 warning）
• ping-pong：两个工具交替反复
known_pol1_no_progress：轮询型工具无进展
•global_o1rcuit_breaker：全局硬上限（阅值 30-critical， 强制中断）
3.上下文溢出：
instal1foo1ResultContextGuard（） 依据 contextWindowTokens 截断
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 015

—五种多智能体协调模式：ANTHROPIC CLAUDE 博客
• 多智能体 模式
1.生成器-验证器模式
input
output
feedback
核心概念
输入
输出
生成
验证 迭代
生成智能体
验证智舵体
快速生成质量把关 明确标准
OpenClaw 采用多智能体+层级式多
最终输出个
增加角色专精
智能体架构：
2.编排器-子智能体模式
编排器
主埋効调
• 多智能体：并列的顶级智能体
集中控制 任务分解 分派
主理协调
独立子任务
线性纨行
独立子任务
子智能体
子智能体
• 层级式：主 Agent按需生成专用子
平行团队协作
智能体，子智能体可继续嵌套生成，
3. 智能体团队模式
角色专精 交文职能
形成有深度的智能体树。
平行工作 长生命周期
主Agent
智能体
滋试
酱能体
文档
持久
共享上下文
溯试習笼体
/
\
异步可扩展
子Agenti
子Agentz
4.消息总线模式
发布者A）
订阅者B
类型词
发布订阅
分实训程
子Agents
子Agent4
异步 发布-订阅 解耦
事件驱动动态扩展
灵活接入
发布者
分布式共享知识
5. 共享状态模式
类型词
共同知识库
在线知识
去中心化 共同知识 实时
QCon
唯一事实来源 集体智葱
高并发
共享知识库
InfoQ 极客传媒
全球软件开发大会
资料来源：claude.com/blog

## Page 016

内层循环•attempt.ts
• 双循环架构模式
外层循环• run.ts
职责：单次对话 Turn 的完熬推理流程
职责：会话级错误核复与故障转移
nner Loopattenpr:ts）
Outer Loop （run.ts）
核心思枳
2 构理 Rrcapt
3 森式按理（板選脆》
将 Agent 运行时拆分为外层循环（错误恢复）和内层循
⑧ 提联工日初用
1f（可爱贷误）、修爱•津试
分 找行工具
（不可供餐）
*运回结果
公） 工晟结果追加系溯思
环（推理执行），实现关注点分离：
• 女曰enbodcedRunAetemptResu.t
处坦的错误类型：
• 内层专注对话流程
每 Turn 的执行流：Prompt 构建一 筷型推理一工兵调用一结果处理
销误
恢复策略
429 限流
认证配置轮转
• 外层专注系统韧性。
級别
阈值
动作
401/403 认证失败
标记失效，切换配置
500/503 販务不可用
模型回退（降級到备用模型）
严重
20次工具猶环
强刊提示改迸
上下文遊出
別发自动医络后重试
熔断
30次工具霸环
强制停止
系统过载
掐数迟避重试
优势
说明
OpenClaw Agent 双锻环架构
关注点分离
推理逻辑与错误恢复完全解耦，内层代码简洁清晰
外限源坏（run.ts）- 饼误恢复
渐进式容错
从最轻量的恢复手段开始，逐级升级，避免过度降级
工月洗菜
状态解耦
内层只关心 Turn 级状态，外层维护完整的故障恢复状态机
防止死循环
外层迭代上限＋内层熔断器，双重保障
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 017

Me
Memory Tools
Embedding Providers
User
Agent Loop
OpenAI
uman now：
coniversatfon Runzine
Memory Search Manager
-oidet w menm mogtr sotm
LLN+100LCauLing
Drchestratipn + Fallback
Genini
Incextanager | gMD （auto-fsLLbacks）
Voyage
Mesary FLusn
SLot: afory.backend Cpiek ong）
Mistral / 011ama
initbock
Gateway
Context Injection
builtin （SQLite）|
QMD
LocaL （GGUF）
System proapt enrichment
sLot: ptugins.sLots.menory - hetive Hemory （picl onp）
Hybrid Search Pipeline
menorY-core
Vector Search
BM25 Search
ounutad aefauir • Dreaningn nybntt seaocll
Cisine similarsty
Keyword FTSS
Menory Files （Atways-on, source of truth）
MEMORY.md
YYYY~MM-DD.md
Score Merge
Miahted: vec t text
curased ony-temi
Daruyappenu-onLy Logs
stot: pLugins.slots.cdntextEngine （pick one）
Temporal Decay
iB-dav haaf-btfa mcency
Legacy
1os3less-claw
1aut conLexE engine
dafauLt
File Natcher
ara manty
MNR Re-ranking
wac2an-enc2neei9g/cosscas s-cwan
ivensity dedur
pronata
Index Update
--------------
Citations + Top-K_
Dreaning（Experinental, in menory-core）
Memory wiki （BundLed Plugin）
ParaLLcL knowLecos vault- does M0T rerlsce activa neaory alucin
Light
Deep
Sant w 5a90
Scnme& aranntn
2oac0nt32n06
RXRRPLKOntSL
• HEHORY.rd
Legend
QCd
目 Plgin slot （exclusive）
1 core Engine
口 Ainays-pn Storage
•Enbedding
J Index Fipeline
C context Engine
Flssh / Write
口 Oreaming
Memory Riki
context Injectton FLow
Menary Write Path
Dreaning Pronotion
Slots ara indeaondent - comnino freey
全球软件开发

## Page 018

12
Hermes
模式
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 019

•
Tool Use 模式
Hermes 围绕"让Agent 自己更强大”—能学、能问、能搜、能委派；
OpenClaw 围绕"让平台更健壮"——多平台安全、类型严格、开发者友好。
【工具系统】Agent的手
【技能系统】Agent 的程序性记忆
•运行时动态创建技能：Agent 完成复杂任务后，主动将成功经验沉淀为可复
•自注册机制：每个 py 文件调用 registry.register（），
用技能
启动时 importlib 自动发现
。skill_manage（create）一创建新技能，写入 SKILL.md+ 子目录
• 工具集粒度控制：
。skill_manage（edit/patch） —编辑、修补已有技能内容
enabled_toolsets / disabled_toolsets 按任务场景组
。skill_manage（write_file/remove_file）—添加或删除引用文件
装工具包
（references/templates/scripts）
。skill_manage（delete） —删除不再需要的技能
•运行时自适应：check_fn（） 动态检查可用性，
。后续遇到同类任务一skill_view（加载完整步骤，直接复用
coerce_tool_args（ 自动修复 LLM 参数类型
• 渐进式披露：4 层 token 节约
•澄清工具：clarify（—Agent 主动向用户提问，结构
。skills_categories（ ->几十个 token
化多选交互
• skills_list（） 几百个 token
•skill_view（） 几千个 token
。skill_view（file_path） ->按需加载子文件
Openclaw：工具是平台管道节点，全局注册+too1A11owlist 白名单，无语义分组
•安全扫描：skills_guard 检测 prompt 注入模式
OpenClaw：插件是平台能力扩展，开发者部署 TypeScript 代码，Agent 只能使用不能创建；工具 schema一次性全量
注入，无分层加载
aCon
InfoQ 极客传媒
全球软件开发大会

## Page 020

• Agent Loop 模式
两者都有完整的容错能力（认证轮转、模型回退、上下文压缩）
• Hermes 把容错内嵌在单循环中用 continue 无缝恢复：Hermes 额外多了 per-turn
主模型恢复和LLM 参数自动修复
• OpenClaw 把容错抽到外层循环重新调用内层：OpenClaw 额外多了循环检测器和
thinking 降级。
【核心差异】
Hermes
OpenClaw
架构
单循环内嵌容错
双循环分离容错
错误恢复
同一循环内 continue ，无缝重试
外层循环捕获，重新调用内层
认证策略
4种轮转策略，1h冷却
profile 顺序轮转+cooldown
压缩时机
阈值触发（预防性）＋溢出触发
主要溢出后被动触发
主模型恢复
每轮目动恢复 （turn-scoped fallback）
无等价机制，fallback 后持续使用
循环检测
无
4 种检测器（默认关闭）
代码量
~350行循环+~800行分类器
~1800行外层＋~2400行内层
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 021

• ReAct 模式
• Hermes 对所有 provider 统一保留推理内容用于上下文回放，Hermes 的 Agent 在后续
turn 中能看到之前的推理过程。
• OpenClaw 只对 Anthropic 保留推理，其他 provider的推理在会话历史中被丢弃，
OpenClaw 的 Agent（非Anthropic）会丢失这部分上下文。
【核心差异】
Hermes
OpenClaw
推理保留
所有 provider 都保留推理内容到会话历史 Anthropic 保留；其他 provider 丟弃
用户输出 推理可实时显示给用户
推理标签始终剥离，用户只看 <final>
推理断裂
incomplete scratchpad 检测+重试
无等价机制
Provider 兼容
多路径提取兼容 5+种格式
Anthropic 结构化 thinking+其他 provider 标签剥离
推理深度
按模型前缀自动判断
ThinkLevel 配置+不支持时降级
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 022

Memory Tools
User
Agent Loop
memory / session_search
Human Input
fonvensation Runtime
Memory Manager
Security Scanning
* provider-stecific tools
LLM+ Toot Catling
Orchestraton + Fallback
200L
Bu2Lcin one excemat provaden
Henoey weites + context FiLes
enriaheer gontex
Nenery Syoc
Context Injection
xnemory -context> fencing
SLot: memory.provider （pick one）
Session Sedrch Pipeline
builtin （MEMORY.nd + USER.md）
FTS5 Search
sqLite state.db
Memory Files （hLways-on, frozen at session start）
Session Grouping
MEMORY.md
USER.md
LLN Sumnarize
User prorive （-1575 chars）
Genini Flash
！prampt Leyens
———一
SLot: context.engine （pick one）
context Compression Pipeline
compressor
hernes-Lcm
Prune Toot Results
Iterative Updstes
deFautt （boiltin）
plugins/context-gngino/Lcn：
shovtd_conpness - campress - on_ses91on_end
Protect Head + Tail
LLH Summarize Middle
System Prompt Assembly （9 Layers）
1. Anent iaentity （SDUL.nd / defauLt）
2: Nenory usage gulde （hardcaded rules）
3: NENORY snapshot ［frpzen fron NEMORV.nt）
4: USER PROFILE snapshot Gfrozan fram USER.ad）
5. SkilLs index （~80skilLs: 5068 chars）
6. ABENTS.md （up to 20K, head 78%： 1 tail 30%）
7. sessimnmetadsteotinemode onontoem
8. Platfurm hint （Telegran / Discord sperific）
9. Session context （source / groun / dolivery）
Legend
口 Pugin slot （exclusive）
目 core Engine
口 Atways-on Storage
-acs1an aanm
context Engine：
Prompt Assembly
传媒
• Sync / Security
Memory Write Path
somoression F:on

## Page 023

04
AutoResearch 模式
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 024

• AutoResearch 是什么？
AUTORESEARCH
自主完成「提假设-改代码 训练-评估—决策」的完整研究循环
核心架构 一 只有三件事
准备
Agent 可改
人来写
prepare.py
train.py
program.md
数据 / Tokenizer/评估
模型/优化器/训练
指令/约束/目标
固定不动
唯一可编辑
2人类定义
Modify Code
5-Min Train
Evaluate
on GPU
设计哲学
• 单文件约束 — Agent只改 train.py,diff 可审查，爆炸半径可控
固定 5分钟—每轮实验等时，公平比较，杜绝"跑得久=跑得好”
• 单一指标一vaL_bpb（越低越好），没有多目标博弈
• Git 即实验记录—好的 commit，差的reset, git log = 完整研究轨迹
QCon
全球软件开发大会

## Page 025

• AutoResearch 如何自主运行？
AUTORESEARCH
研究循环— 无限迭代，优胜劣汰，约束
观察历史 -提出想法-改 train.py-跑5分钟-量 val_bpb
个
好 - commit 保留
差- git reset 回滚
挂-修 bug 或放弃
为什么值得关注
Modify Code
5-Min Train
Evaluate
on GPU
•最小可行 Agent 系统—3个文件、1个GPU、1个指标，即可运转
•人机分工清晰—人定方向（program.md），机器执行试错（train.py）
•可复现可审计—每一步实验都有 git commit, results.tsv 全记录
•范式启发—证明了「AI做实验」不是未来，是现在
QCon
全球软件开发大会

## Page 026

AutoResearch for development 架构
AutoResearch for Developing 系统架构
人类
program.md
（人类定义的规则、
目标、约束）
Issue Selector
（优先级排序＋复杂度评估＋排除过滤）
Agent Orchestrator （run.sh） 使用 acpx 控制
奇数轮：Codex审核 Codex实现 测试一Claude审核 Claude实现
偶数轮：Claude市核一Claude实现測试 Codex审核 Codex实现
迭代循环（最多42次）
实现
测试
审核
反馈驱动
再父现
玉达極
质最检查点：測试涌过+评分≥9.0一自动 commit + PR+合并
results.tsv + workflows/
（全量过程日志，可回溯可审计）
Qcon
InfoQ 极客传媒
全球软件开发大会

## Page 027

AutoResearch for development 架构
#
原则
说明
01
program.md 即宪法
所有规则、约束、代码规范都在此定义，Agent 不越权
02
多 Agent 对抗
Codex 和 Claude轮流担任实现者和审核者，交叉验证
03
量化门槛
评分 ≥ 9.0/10 才算通过（5维度加权），主观判断最小化
04
反馈驱动
审核反馈直接传入下一轮迭代，持续改进直到达标
05
独立评分
实现 Agent 和审核 Agent 分离，避免"自己改自己评"
06
全量可审计
每次迭代、每次审核、每次测试结果都记录在 workflows/
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 028

• AutoResearch 思想实践
回放：https://asciinema.org/a/89626
& Closed
feat: enhance job execution with agent selection and timeout #21
1-#26
1202004-051022041公米
【2626-04-03 17:38:121 依赖松咨通过
Related
12026-04-03 27:38:231 Issue 标出：Teath ennance Job execution with agent selection and tineout
［2026-84-03 17:38:13］
•Issue©
feat: add backeround obs and queued task execution #10 （feat: add background jobs and queued task execution）
［2026-84-03 17:38:13）工作目承：/Users/chaoyuepan/ai/inclaw/.autoresearch/workflous/issue-21
［2026-84-03 17:38:131 准备 acpx session...
【2626-04-03 17:38:13］ 关闭旧 session..•
Create suhaissue
619d52ac-08f9-7e53-8314-9900813c157a
［acpx］ created session Cwa （019a5205 2037 7682-acfb-39d135c8c3bc）
［2026-04-03 17:38:15）创料 codex session..
o s smallnest added 2 commits that reference this issue last week
Tacpx! agent: codex
Teat: anoieent issue 2 -acd cimeout:suopart and enhance aaent se...
c54bbce
［2826-04-83 17:38:171创 claudc session...
00909200-2021-1002-260-29628o
feat: inplenent issue #21 - feat: enhance job execution with agent se...
Sddeedg
［acpxl created sessioncwd （b94a61a1-c30a-431f-a778-4282d30fbfb7）
［acpx! agent: Claude
smallnest mentioned this last week
［acpx］ cwd: /users/chaoyuepan/ai/imclaw
% feat:feat: enhance job exacution with agent selection and timeout （#21）#26
12026-04-03 17:38:26 acpx session 注备宗成
［2026-04-83
27:38:26］
创逢分支：feature/issue-21|
o smallnest added a commit that references this issue last week
［2626-84-03 17:38:261
Merge pull request #26 from smallnest/feature/issue-21…..
Verified） c509cal
［2026-04-03
17:38:26］
送代 1/42
t smallnest closed this as completed in #26 last week
［2626-64-83 17:38:26］
本轮：Codex 实现 -Claude 审核
［2026-04-03 17:38:26］
［2026-84-03
选代 1: Codex 卖现...
［2026-84-03 17:38:261
使用指令文件：/Users/chaoyuepan/ai/imclaw/docs/autoresearch/agents/codex.md
［acpx］ session cwd （01305205-2631=7082-ac16-39d135e8c3bc）•/Users/chaoyuepan/ai/imclaw•agent needs reconnect
［client］ initialize （running）
IcLientl authenticate （running）
cklent cession netmnnna
Model netadata forqwen/qwen3.6-plus:free"not found. Defaulting to fallback metadata; this can degrade performance and cause issues.
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 029

InfoQ 极客传媒
QCon
全球软件开发大会
THANKS
大模型正在重新定义软件
Large Language Model Is Redefining The
Software

## Page 030

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
