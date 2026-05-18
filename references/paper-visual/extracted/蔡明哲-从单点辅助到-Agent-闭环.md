# 蔡明哲-从单点辅助到-Agent-闭环

说明：以下为按页从渲染图片进行的可见信息提取；保留页码并尽量逐行转录页面文字、标题、标签与数字。

## Page 001

InfoQ 极客传
QCon
全球软件开发大会
从单点辅助到 Agent 闭环：
基于Agent Skills、
MCP 与 Playwright 的
全链路智能化测试实践
蔡明哲
Ubiquiti
Quality Assurance

## Page 002

极客邦科技 2026 年会议规划
aCor
促进软件开发及相关领域知识与创新的传播
06月9上海
281000人
08月 9深圳
88 1000人
AiCon
•Al Infra 系统工程
AiCon
•Agentic Al
•多 Agent 协作与实践
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
2 1000人
：AlAgent
Qcon
•Vibe Coding
AiCon
•大模型架构创新
智能可观测
•多模态 AI 产业融合
全球软件开发大会
推理基建
全球人工智能开发与应用大会
•具身智能
模型攻防
Al for Science
会议时间：10月22-24日
•Al x 创造力
会议时间：12月18-19日
•大模型安全

## Page 003

About Me
蔡明哲（Max）
Ubiquiti（优倍快）Quality Assurance
深耕测试与品质工程领域，专注于测试效能提升、自动化测试架构与Al驱动
测试方法。曾于多场技术研讨会担任讲者，包括中国互联网测试开发大会、
DevOpsDays、Test Corner 等。着有 UI 自动化测试与AI 应用实战一
书，并制作软体测试相关线上课程，在实务上，曾设计测试架构与方法，使
回归测试时间大幅缩短最高达 95%，并参与 LLM 与 Multi Agent 系统品
质体系建置，持续探索如何以工程化、自动化与智能化手段，全面提升产品
品质与测试效率。
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 004

InfoQ 极客传媒
QCon
全球软件开发大会
背景与挑战
02
工程实践
目录
03
核心技术底座
04
未来展望

## Page 005

背景与挑战
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 006

Al 对 QA 是帮助比较多？
还是威胁比较多？
aCon
InfoQ 极客传媒
全球软件开发大会

## Page 007

AI 加速研发：别让 QA 成为 AI 时代的瓶颈
975 contribations in 2026
随着 AI赋能开发端实现显著提速，若QA 环节未能同步进化，测试
端将不可避免地成为专案交付的效能瓶颈。因此，QA 体系也必须深
Contribution ectlvity
度整合大模型力量，从自动化脚本生成、边界案例预测到异常分析进
2220
Created 295 commits in & repositoriss
行全面优化，确保『测试速率』能与『开发速率』并驾齐驱，实现端
Tobias Liitke
1obi
日 Ceated S repositories
对端的研发效能转型。
Follow
Qtobiyonix
833 contributions in 2025
Feb
Mar
May
Sep
Nov
2025
Mon
①
需求堆积：待测功能在 QA 阶段形成严重排队。
Wed
2026
喘期 眼
Leamn naw we count contributions
Less
2022
2 品质风险：为了赶上发布时间而压缩测试覆盖率。
94 contributions in 2024
2026
Aug
2025
③ 协作断层：开发已进入下个冲刺，QA 还在处理上个版本的 Bug。
Mon
Wed
2026
2022
Shopify CEO 历年 GitHub Contributions
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 008

• 工具链的「破碎化」与「孤岛现象」
人机分工模糊不清
①
团队未清晰界定 A1与人工的职责边界，常让 AI 承担复杂业务逻辑设计、
缺陷深度根因分析等高阶认知任务，同时却让人工长期重复执行可被自动化
的基础工作，造成双方能力错配与资源浪费。
对 AI 产出信任失衡
过度依赖 AI，将其视为万能解決方案，直接使用生成的测试用例却不做业
务校验，导致场景脱离实际；或是因不信任AI准确性而完全排斥使用，错
失提升测试效率与覆盖率的机会。
工具孤岛内耗
受工具孤岛影响，QA需要在测试管理、缺陷平台、AI工具、需求文档等
多个系统间频繁切换，手动复制数据、补全信息、对齐上下文，大量精力消
耗在非核心的机械性工作中。
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 009

• 认知偏差：将 AI视为工具而非协同伙伴，忽视人机配合价值
你是一位资深的QA工程师，
上下文断裂，知識局限在個人
擅长撰写测试用例，
许多 QA 对于 AI 的使用仅仅使用 ChatGPT 等网页的聊天介面，
请帮我撰写一份关于xxx功能的测试
上下文永远断裂，无法累积业务背景与测试脉络，改一次需求就要
車来一遍 prompt
工具效能未释放，业务任务错配
一句简短单一的指令
未结合业务领域、测试规范与技术栈做深度适配与能力增强，缺少
针对性配置、prompt 工程优化与场景化微调，导致AI 生成内容
通用性强、业务贴合度弱，难以真正发挥自动化生成、智能分析与
生成低质量、低可用性测试用例
决策辅助的最大价值。
业务知识无沉淀，无法复用
业务知识、测试上下文难以与 AI有效结合，适配业务的提示词、
放弃使用
AI使用经验仅停留在个人层级，未系统化沉淀为组织资产，无法在
团队内复用于同类业务测试。
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 010

02
工程实践
从案例生成到自动修复的全流程落地
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 011

QA 日常工作內容
QA 核心工作围绕 STLC与日常任务展开，传统模式依赖人工执行效率受限，通过在需求分析、用例设计、脚本开发、执行调试、缺陷
管理全流程植入 AI能力，可全面自动化、智能化升级测试工作。
1.
Sprin
Kickoff|
需求伴用
设计评审
DoD Ready
Reguirements
6.
Test Closure
Analysis
t
开始前
测试计画
測试案例开发
测试案例评审
RD 程式开发
2.
5.
STLC
Test
Sprin
Test
Planning
土
自动化测试开发
开发自测
功能测试
回归测试
Execution
进行中
测试不通过则回到程式开发，除非能够接受后续修复
3.
Test
Test
Development
Environment
Sprin
环境部署
正式环境冒烟测试
线上监控
用户问题定位
Setup
t发版
PM +RD +QA
只有 RD
只有 QA
QCon
Infoo极客传媒
全球软件开发大会

## Page 012

• AI 赋能测试革新：从单点突破到全域提速
以智能技术重构测试全流程，实现从单点优化到全链路提效的跨越
测试用例生成
测试脚本生成
基于 Al 的分析能力，快速解析需求文档与接口定
Al Agent 自主理解测试场景，自动生成可执行脚
义，透过结构提示词，精准生成测试用例，大幅缩
<
>
本并完成自动化测试执行，支持多场景适配，降低
短用例设计周期，摆脱人工编写的低效重复。
脚本编写门槛，提升测试执行效率与稳定性。
产品业务知识提取
用户反馈 Log 分析
通过大模型处理与知识图谱技术，从产品文档、历
Al 智能解析海量用户反馈与日志，自动定位高频
史项目中高效提取核心业务规则与逻辑关联，快速
问题、异常场景及潜在风险点，将零散数据转化为
构建测试知识底座，减少业务理解成本及作为测试
可落地的测试重点。
案例设计参考文档。
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 013

AI 赋能测试效能提升：四大核心能力量化实践成果
凸
测试用例生成 60%
测试脚本生成65%
依托 Al 深度解析需求文档与風險变更，结合结构
Al Agent自主理解测试场景并自动生成可运行脚
化提示词精准输出高覆盖测试用例，用例设计周期
本，完成全流程自动化执行，脚本编写效率提升
缩短60%，用例覆盖率与合规性显著提升。
MCP
65%，大幅降低人工编码成本与维护成本。
产品业务知识提取 75％
Agent
用户反馈 Log 分析 70%
Skills
通过大模型与知识图谱技术，从产品文档、历史项
Al 智能解析海量日志与用户反馈，自动识别高频
目中提取核心业务规则与逻辑关系，快速构建测试
问题、异常场景与潜在风险，问题定位效率提升
知识底座，业务理解成本降低70%，知识沉淀与
70%，风险前置识别率提升60%，为测试重点与
Playwright
文档输出效率提升 75%。
质量优化提供精准依据。
Agents
四大核心能力量化成效与业务价值
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 014

• AI 赋能测试革新：从点效突破到全域提速
以智能技术重构测试全流程，实现从单点优化到全链路提效的跨越
测试用例生成
测试脚本生成
基于 Al 的分析能力，快速解析需求文档与接口定
Al Agent 自主理解测试场景，自动生成可执行脚
义，透过结构提示词，精准生成测试用例，大幅缩
本并完成自动化测试执行，支持多场景适配，降低
短用例设计周期，摆脱人工编写的低效重复。
脚本编写门槛，提升测试执行效率与稳定性。
产品业务知识提取
用户反馈 Log 分析
通过大模型处理与知识图谱技术。从产品文档、历
Al 智能解析海量用户反馈与目志，自动定位高频
史项目中高效提取核心业务规则与逻辑关联，快速
问题、异常场景及潜在风险点，将寥散数据转化为
构建测试知识底座，减少业务理解成本及作为测试
可落地的测试重点。
案例设计参考文槛。
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 015

•
Agent Skills 落地测试案例生成：核心应用与实操技巧
Agent Skills 赋能 AI 自动化生成测试用例，核心是将大模型調适为贴合业务的测试专家助理，通过投喂历史测试数据、需求文档与代码库，让AI
自主识别功能边界、用户行为路径与异常场景组合，大幅提升用例生成效率；落地过程中掌握关键实操技巧，能进一步保障生成用例的可用性与稳
定性，让 Agent Skills 的能力充分发挥。
name: test-cases
收集需求，如产品需求文档
QA 基础认知：QA 需理解 AI 生成用例核心逻辑，
description: This document describes a
U
process for generating structured QA test
明确 AI 可自主识别功能边界条件、用户行为路径、
cases from product requirements or feature
异常场景組合等三类核心测试场景，精准把控 AI能
specifications.
力边界与应用方向
# Objective
识别测试场景
拆分测试类型：摒弃 all in one的生成思路，按
Transform product requirements into
2
organized and actionable test cases that
压力测试、功能测试、PICT 测试案例等不同测
validate：
试类型独立配置 Agent Skills，适配各类型测试
- Core functionality
定义测试用例结构
的专属需求
- Edge and boundary conditions
- Failure scenarios ane error handling
规范输入结构：以结构化的方式向 Agent Skills
- Workt ow or state transitions
提供需求、业务规则等信息，结构化输入是 AI
The goal is to ensure each requirement has
生成测试用例
生成可用、稳定测试用例的关键前提
sufficient testing coverage and can be verified
by QA.
QCon
InfoQ极客传媒
全球软件开发大会

## Page 016

•
AI 驱动测试点生成：先点后案的敏捷测试策略
Test Case ID
Test Descrption
Test Env
Preconditions
Test Sleps
Expecled Resull
Status
1. 開啟設州設定貢面
2. 贴擊 NFC 功能開啟
3. 投下绒定儲仔
1 興啟 NFC 開門後開門成功
AII
• 綠製NFC卡片並分配權限
4.別卡
网卡開門成功
Pass
1. 開啟級描設定受面
2. 點擊 NFC 功能關閉
2 關閉 NFC 開門後開門失敗
• 錄製NFC卡片並分配權限
4. 別卡
誤提示
脫卡開門失敗，登音描報鉛
受限于业务逻辑认知不足，大模型难以生成完整的测试步
Pass
骤，但透过高质量的上下能，大模型也能高效产出「测试
完整测试案例示意图
点」，可作为测试案例产出或是完善测试点，面对高速迭
UA Card
代，我们采取「先点后案」策略：先由 AI快速生成测试点
NFC
UA Pocket
以匹配开发节奏，待发布后再将高价值场景转化为回归用
3rd party
例，兼顾灵活响应与资产沉淀。
Unlock
Mobile
Aople
Touch Pass
目
大模型升级测试点，人工检阅后采用，并在迭代稳定
Goog e
后补齐完整测试案例内容
心智图测试案例示意图
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 017

Agent Skills 案例 - PICT 成对组合测试
依規格換取可組合的參數與語項，建立 Pairwise模型。
烈我閱讀 PIN cede 的新功熊規格後，創建測試紫倒
透过将微软 PICT 算法封装为 Agent Skills，赋予 AI 极致
# PIN Untock 功能— 參致與選值
PIN_Length: 4_Digits, 6_Digits, 8. Digits, Variable_Length
1. 知識庫檢系結果（PIN 功能規格）
Keypad_Layout: Standard, Randonized
從 peferences/Conf igur ing-PIl-Uniock-in-UnFI-ACES
的测试减法能力。当面对8参数系统，PICT 能将19,440
cehssueunen.cuscomacncereanRancommcenera.ed
5.nd S期出：
Reader_Type: Intercom,Reader_Pro
•抗派 PIN：Settings > Admins & Users > Users 使用者
+ Assignment： - Add PIN（可手動綜入或隨機產生）
个穷举案例压缩至仅 30个（减少 99.88%），同时完整
參豉說明：
愛長度（套用所有讀卡機）
•PINELength：全讀卡機的PIN 長度定（4/6/8 位固定或可愛）：
覆盖所有成对交互风险。透过此技能，Agent 可直接从自
•經盤裝面：Devices >Readers >［Intercom/Reader Pro］>
• Keypad_Layout：單一讀卡機的鍵鄉版面（橡準/機）、
AccdSS Methods> PIN > Keypad Layout Standard成
•PINLAssignment：指派 PIN 時為手動輸入或系絲腿機產生。
Randomize0.
• Reader_Type：讓卡機扒空（經盤版側殺定適用 Intercom與 Reader Pro）。
• 隔門煮程：讀卡機上點 PIN Unlock 輸入PIN Enter
然语言需求提取参数、应用约束逻辑，并输出最优测试
的束：规格未限定上逗四者之間的互斥條件，故無 PICT 約束：僅以 Pairwise劉蓝組合。
•業務規膳：位使用者僅能有一個PIN。
集，以最小成本实现高覆盖率的测试。
=、Generated Test Cases （Pairwise）
2.測試案例 （PICT Test Designer）
旅規格抽出4假參教並做 Pairvnise組合：
Test
交易类型
（5）：提款、存款、余额查询、转帐、变更 PIN码
PIN_Length
Keypad Layout
PIN_Assignment
Reader_Type
Expected Output
參數
塘值
卡片类型（3）：EMV 晶片卡、磁条卡、无效卡
可設定4位PIN；模準鍵盤；手
PIN_Leogth
4_Diglts. 6_Diglts, 8_Digts,Varlable_L
A_Digits
Custom_Entered
Intercom
助輸入 PIN成功：Intercom上可
正常解甜。
PIN状态
（4）
：有效、无效（尝试1-3次）
PIN_Assignment
Custom_Entered Random_Canerated
可設定4位 PIN：冠機鍵盤；隘
帐户类型
（3）：支票帐户、储蓄帐户、两者皆有
4_Digls
Randomized
Random_Generated
Resder_Pro
碳產生 PIN成功：Reader Pro 上
可正常解袋。
•PICT 模型：無級外的来（規格未定義參欺互后）。
交易金额
（4）
：在限额内、达到最大限额、超过单笔交易限额、超过每日限额
可設定6位 PIN；樣準選盤隘
•商出：8 係 Palrvise 測試累例，每條都有预期結果料明。
6 Diglts
Standard
Random_Generated
Reeder_Pro
號產生 PIN成功：Reader Pro 上
•補充：文件內另建議「一使用者一PIN』「结級 PIN」「访容
现金可用性
（3）：充足、不足、已用尽
可正樂解敬。
可設定6仪PIN：讀機提盤；手
2Flee：
UndcAllKeepAl
网路状态（3）：主要网路、备援网路、已断线
6 Digits
Randomized：
Custom_Entered
Intercom
動輸入 PIN 成功；Intercom上可
正常解鉗。
卡片状态（3）：正常、损坏、已过期
可設定8位PIN；横準健组；手
可能的总组合高达数：19,440
PICT Agent Skills 实际运用
aCon
InfoQ 极客传媒
全球软件开发大会

## Page 018

Agent Skils 案例- 基于代码变更的智能测试
透过分析代码变更自动严出结构化测试计画，核心价值在于只测改动风险点，而非全量执行。整体流程透过 GitHub MCP 解析变更资
讯，分析程式影响范围与风险等级，结合 BM25、Cosine Similarity + HNSW 与 RRF，从 TestRail 与产品知识库精淮匹配测试案
例，并完成测试缺口分析与案例补充，实现精准、高效、风险导向的智能测试规划。
1
2
3
4
5
代码变更解析
业务依据关联
变更风险评估
智能案例匹配
测试规划输出
通过 GitHub MCP 自
自动关联对应 Jira Ticket
分析代码影响范围、调
基于 BM25 检索从
完成测试缺口分析、缺
动提取代码提交、文件
MCP、产品文档与技术
用链路、模块依赖与改
TestRail 中精准召回最
失案例判定与案例补
文档，基于 BM25、
修改、依赖变动、函数
动程度，评定风险等
相关测试案例，提取后
充，输出结构化、风险
Cosine Similarity +
变更等信息，精准锁定
HNSW 与 RRF构建语义
级，划定高优先级测试
由大模型再次分析，保
优先、可直接执行的测
改动范围与影响入口。
索引，建立变更与业务需
边界与回归范围。
证匹配结果稳定、可复
试计划与报告。
求的完整映射。
现。
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 019

MCP 驱动 TestRail 的集成与智能编排
核心增益
升級相關的測試案例和計劃
•历史用例复用：查询上一版测试案例，自动在 TestRail 创
我想要找跟升級有關的 test case 有思些，幫我找到這些 test case 後創理一 新的 test plan 用來
将 MCP 与主流测试管理工具 TestRail 完成
建新 test run，提升用例复用效率。
測試 retrofit hub 的
• 智能测试建议：基于当前 TestRail 中的 test case， 结合
授要更多相關關鍵字（如 upgrade、retrofilt、hub），以找出更多測式案例。
技术整合，打通测试管理与自动化执行的链
业务场景输出针对性测试执行建议。
•Ran senrch_casestesttmi
路，依托 MCP 的拓展能力实现 TestRail 上
•进度数据统整：提取 TestRail 中的测试进度数据，可嵌入
V.Ran search_cafesitestrai
测试用例、测试计划的自动化操作与数据联
标准化测试报告。
动，同时为测试执行提供专业建议、测试报
Thought for 8s
告沉淀核心进度数据，大幅减少测试管理的人
整理搜尋結果並建測拭計畫；
落地挑战
升級相關（中文「升級」）：
工操作成本；但在企业级落地过程中，也需应
• 9211654—
Hub）
对多项目管理、个性化架构适配等实际问题，
•多项目管理难题：企业内 Project 数量过多时，易出现范
Upgrade 相關：
需针对性优化解决方案。
围混乱，需制定专属规则或限定操作范围。
• 9118378一使用小王具驗澄
• 9117459一使用小工具驗證
•个性化适配需求：企业内部test plan 架构、操作流程多
• 9215602-
为定制化，开源 MCP 工具难以完全匹配，定制化 MCP
Retrofit Hub 离於
•正在连立用於測試 Retrofit
Hab 的測試計畫，紡入
的升毃相闕茶例
wget_kast_testinfo
Terun_tast
适配性更优。
6 Running create_plan_frcm_cases:testrail
Vistprojects
• 权限管控挑战：多团队共用 TestRail 时，MCP 整合需精
project.jd
细化权限设计，避免跨项目数据操作风险。
plan_nare Ret rofit Hub 升級激計畫
NewMCP Server
suite_ld
ndoa custom MCR Server
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 020

Skills 构建的核心准则：领域知识为基，高效复用为果
agents
使用 Skil-Creator 构建 Skills 是高效、可复用的最佳实践，但必须建立在扎
ana lyzer.md
comparator.md
实的领域知识之上。只有先具备完整的测试方法论、验证逻辑与质量标准，才
grader.md
assets
能设计出稳定、可靠、可被 Agent正确执行的 Skills。
— eval_review.html
eval-Viewer
- generate_revlew.p
逻辑确定性化：关键验证逻辑改由 Python/Bash 脚本执行，
- Viewer.htm
①
Skills仅负责调度。彻底消除模型幻觉，确保测试结果具备工
LICENSE.txt
业级的准确性与可重复性。
references
— schemas.md
scripts
显性激励约束：在 Prompt 中植入「品质优于速度」等强指
② 學採型被基是擁在的做間，“强制其执行深度育产通的期出检
_init •py
aggregate_benchmark.py
查。
generate_report.py
improve_description.py
Header 权重优化：将不可违反的守则置于 SKILL.md 顶部
package_skill.py
③
并标注 ## CRITICAL，利用注意力机制确保核心规则在长上
quick_validate.py
下文中始终最高权重。
run_eval.py
run_Loop.py
utils.py
像团队一样分工：在创建agent skills不需要建造 all-in-one
SKILL.md
4 的超级 agent，而是像 QA 团队一样分工各司其职
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 021

• AI 赋能测试革新：从点效突破到全域提速
以智能技术重构测试全流程，实现从单点优化到全链路提效的跨越
测试用例生成
测试脚本生成
基于 Al 的分析能力，快速解析需求文档与接口定
Al Agent 自主理解测试场景，自动生成可执行脚
义，透过结构提示词，精准生成测试用例，大幅缩
本并完成自动化测试执行，支持多场景适配，降低
短用例设计周期，摆脱人工编写的低效重复。
脚本编写门槛，提升测试执行效率与稳定性。
产品业务知识提取
用户反馈 Log 分析
通过大模型处理与知识图谱技术，从产品文档、历
Al 智能解析海量用户反馈与目志，自动定位高频
史项目中高效提取核心业务规则与逻辑关联，快速
问题、异常场景及潜在风险点，将寥散数据转化为
构建测试知识底座，减少业务理解成本及作为测试
可落地的测试重点。
案例设计参考文档。
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 022

• 测试场景下 RAG 的应用痛点：效率与适配的双重瓶颈
input一
User Query
Prompt
Vector
Data
过去 RAG 方案在测试提效中的落地难题
Dalabased|
Source_1
Agent1
Data
当前RAG 在测试领域的落地瓶颈，其中一点在投入建置完整工具的
Datahara/
Source_2
成本过高，通用工具难以处理高度异构的测试数据与严密的业务逻
Response
LLM
Router
Agent
Agent.2
Functionts
辑，Top K 影响最终输出结果，这会导致最终的结果难以作实际
APL1
测试场景中使用。
Agant3
Etensions
AFL？
透过代码建立 Multi Agent RAG systems
技术落地门槛高：需专业人员做数据清洗、向量库调优、检索
①
策略配置，测试团队自主落地成本高、周期长。
③ START
场景适配性弱：对测试用例、业务知识等专属场景的语义理解
E KNOWREDOE RETREVAL
2 采定，检索结果精准度低，难以直接支撑测试工作；
知识更新成本高：产品业务、测试需求迭代后，需重新做数据
③
入库与向量更新，无法实现实时、自动化的知识同步。
透过 Dify 建置知识库示意图
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 023

Agent Skils： 替代传统 RAG，打造测试专属智能能力
Interaction & Intent
我想知道跟 Retrofit Hub 接线有关的背景知识
（交互与意图层）
如何接、有哪些需要注意的问题
传统 RAG 存在建置门槛高、落地难度大的问题，Agent
Skills作为高效替代方案，可通过自定义规范定义参考文件
并完成技能初步分级，既大幅降低建置难度，同时更贴合业
指令层识
分析检索
根据定义
务实际执行需求，成为解决传统 RAG痛点的高效路径。
元数据＋指令
别用户意
结果是杏
好的
匹配对应
（Metadata +
图，动态
与问题相
template
Skills
Instructions）
载入对应
符
s格式输出
设备文档
建置更简易：无需复杂的向量库搭建、高质量资料
①
萃取、检索调优等操作，相较传统 RAG的繁琐流
程，Agent Skills 落地门槛更低、实施更高效
retrofit hub.md
hub_ door.md
enterprise.md
规范可自定义：技能的参考文件、分级标准均由
②
参考
业务侧自主定义，可精准匹配实际业务场景，让
（References）
mini_hub.md
pocket.md
viewer.md
技能落地更具针对性
g3_reader.md
g3_pro_reader.md
Tlex reader.md
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 024

• AI 赋能测试革新：从点效突破到全域提速
以智能技术重构测试全流程，实现从单点优化到全链路提效的跨越
测试用例生成
测试脚本生成
基于 Al 的分析能力，快速解析需求文档与接口定
Al Agent 自主理解测试场景，自动生成可执行脚
义，透过结构提示词，精准生成测试用例，大幅缩
＜>
本并完成自动化测试执行，支持多场景适配，降低
短用例设计周期，摆脱人工编写的低效重复。
脚本编写门槛，提升测试执行效率与稳定性。
产品业务知识提取
用户反馈 Log 分析
通过大模型处理与知识图谱技术。从产品文档、质
Al 智能解析海量用户反馈与目志，自动定位高频
史项目中高效提取核心业务规则与逻辑关联，快速
问题、异常场景及潜在风险点，将寥散数据转化为
构建测试知识底座，减少业务理解成本及作为测试
可落地的测试重点。
案例设计参考文槛。
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 025

• Agent 执行测试并生成脚本
在 protect的 alarm manager 中，任一device，
person objects 是30秒内出现3次时发送通知。
设置任— device 的 Sound 的 Audio File是 Sundrops
Yoeane the:2（ayriantTest Heaier.
1.点重进人 Protect Application
oroken Plawwriaht tests:usinnn metncoica！
dtaancie:a.tAx
2. 点击进入 alarms 页面
3. 点击 Create Alarm
4.选择人物的 Objects
using testorun too to scentitytasdino
5. 勾选 Person
6. 勾选 Count
capture poge soapshot to undsrstand
Exastne the nrree detatls
7. 设定 count exceeds 是30
eheContext
8. Within 选择 Custom
9. 设定时间为30秒
unaerlying.cuse of the fAflure by
10.选择任— camera
11.选择 Sound
12.选择 Play On
13.选择 Audio Sound
14.点击新增
Playwright Agent Planner/Generator/Healer loop
|透过探索页面生成测试案例，
能够处理需要展开后取得资讯的复杂操作
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 026

Healer Agent：自动化测试维护的智能修复引擎
o.：83 np:inRe.109.224/prxoctalsme
Healer Agent 针对大型测试套件
ane/igwer
creteafy
的核心维护痛点设计，打破「测试
walt pago.：ocasor ultntb-cntld（2）
失败即手动修复」的传统模式。面
anest pesessesaynoler Eutton，
对UI 结构变更、Flaky行为、时
Smuts
await, exsect /eg）ccolaveinL （AVprotectV）
序异常等常见问题，它以「智能检
aalt expect/page.getByRote（checktox
测」的角色实现从错误诊断到修复
Noy
Smkse
wwlt woct/pgw.getByRo tet/checktok,/
pago-tocutonlLaleL/）-fHltortt hus
验证的全流程自动化，同时通过人
anait pogeigetDyHolel'sptchutkon J.ficst
机协作保障测试意图不偏离，大幅
降低资深工程师的重复性劳动。
Healer Agent 智能修製
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 027

UI 自适应执行与 API 测试同源生成
Alamm managortostscenario
［GET］ https://292.169 :24/api/uscrs/5e1f 214821
［GET! hetps：（/192.168.1.24/api/esysten = ［280l
测试开启 protect 设定温度单位为华氏，
https：（/2.92.168.224/favicon:acozv3 wo ［200］
然后跑 UI 的时候就观察 api怎么 call 的，
https://292.168.124/ap_/usels/self = （482）
一起产出 api & ui 的测试脚本
httpse//192-168.1:23/avicon.sug2v3e
2801
［GET） https://192.168.1:24/proxy/users/ap1/v2/user/self - 2001
［GET1 https://292.168.1.24/proXy/uSOFS/0p1/W2/into［208］
•wtch ypreey/etecuct/aeL/users/（uiwrsd）-便地習放！溫受单飲！
【GET】 https://292.268.1.24/proxy/users/api/v2/users/adnin/uos/pagc nun=16pagc.5izc=999 =2 1208］
IPo5Ti httos://192.168*1:20/apL/contro Wters/eheekUpdates =s （204］）
也理3：選择Fahrerhe：&料寶AP！
Playwright Agents 不仅可用于开发UI 自动化测试脚本，
［GET】https://292.168.1:24/ap1/cLoud/backup/settings/list2 ［2083
［GET］ https://392.168.2.24/favicon.sv91u3 =2- （2001
IGET! hstps://192/168.1.24/favicon.aco2u3 z2 （200］
还能在自适应执行UI 操作、观察用户真实业务流程的过程
GE hetp：：/.492.168.2.24 oroxv:procect apzbootstrap # o3.
［GET］ https://192.168.1.24/proxy/protect/api/video archive/fetch-pending •［200］
IGET！
httpsn..static.ui.con naeror nt nw muatic. con ey 223.
［GET! http：：//192 469.1.24/favicon.：wg208 = （200］
中，全程监听、捕获并记录所有网络请求与 API调用详
GE8 hCLpS：：192 168-2.26/.avkcon.2c24s =206
［PATCHI https://192:168.1.24/proxw/proteet/api/users/6981595t81813c83ei108dec - ［288）
成功！看到rChanene haw bren upehsted ouncoeeduly、双在進取描强 Apple
［GET! hetp：：///192.168.1.24/nroxy/proteet/api/recognition/vehicke/aroupsghaslenestruefpegc=1.8pagaSixc=1088008 = ［280］
情，基于真实运行流量自动生成对应的接口测试脚本与断言
IGET! http：：///192.168.1.24/oroxy/protect/ap_/recoonition/face/aroups7hasNane=uruefpa.g2=16pageS1xe=1088088 = ［200］
［GET］ https://192.168.1.24/oroxy/protect/api/active-se5sions
逻辑，让UI 自动化与 API自动化形成天然联动，一次场景
https://192.168.1.24/oroxy/protect/api/events7end=27789681987516start-1770881798751&types=aLorocessorTaskOueveInfo！
https://192,168.1.24/proxy/protect/api/events？.anit-5&oroerbirectlon=desc&typesesmartDetectLine&types=snartbetectZ
https：：//192.168.1:24/oroxy/protect/apa/spotLinhts（2001
https://292.168.1.24/proxy/protect/api/statistics/detections/and=1778968198752Speriod=360088088tort=1770883280080
执行即可同步覆盖界面校验与接口逻辑验证，大幅提升测试
资源利用率与场景覆盖度。
纪录 api 调用生成测试脚本
一次交互录制，双维度测试产出，实现 UI 与 API 自
动化一举两得
QCon
Infoo极客传媒
全球软件开发大会

## Page 028

• 基于 Skills 实现 JS 脚本到 Pytest 标准化迁移
name: playwright Is-to-pytest
description: Converts Playwright JavaScript/TypeScript test code to Playwright
pytest Python test code. Irigger this skill whenever the user provides a Playwright
JS/TS test file or code snippet and asks to convert it to Python, pytest, or
olaywright-pytest format. Even if the user doesn't say"playwright-js-to-pytest"
explicitly, trigger this skill when they say things like "convert this playwright test to
python"， "convert playwright JS to pytest"， "| want to run these playwright tests in
oython"， or "playwright typescript to python".
当前 Playwright Agent 原生仅支持 JavaScript 脚本生
成，无法直接适配 Pytest技术栈，通过构建专用转换
# Playwright JS - Playwright pytest Converter
Your job is to accurately convert Playwright JavaScript/TypeScript test code into
Skills 可实现无缝兼容：先由 Al 基于 Playwright Agent
Playwright pytest （Python） tormat. A good conversion is more than a syntax swap, it
produces idiomatic Python code that a Python developer would feel at home with，
生成标准 JS 测试脚本，再通过转换 Skils完成语法、结构
while faithfully preserving the intent and logic of the original tests.
与断言的自动化迁移，最终输出可直接执行的 Pytest用
例，低成本实现跨语言测试自动化落地。
## Core Conversion Rules
### |. Import Statements
javascript// JavaScriptimport｛test, expect ］ from'@playwright/test；
mport｛ Page ｝ from @playwright/test；
工具實踐部分 prompt
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 029

基于大语言模型，一键生成高稳定、易维护的 Xpath
聚焦自动化测试痛点，AI赋能 XPath 高效生
成
针对传统方式生成XPath 稳定性差、可读性低、需大
量手动调整的痛点，推出基于大模型的 Al定位小工
具，实现一键提取与智能优化，显著降低脚本开发与维
柠碎奢能优化生成：依托大模型理解测试场景，生成精
简、鲁棒、高可读的 XPath，避免冗余与兼容性问
题，减少调试开销
自定义规则适配：支持自定义生成规则，优先选择
旦
带id 元素，自动避开乱码 ID、随暗黑模式变动的
class 名，提升 XPath 稳定性与可维护性
工具操作画面
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 030

•基于大语言模型，一键生成高稳定、易维护的 Xpath
You are a Ul automation test engineer tasked with writing XPath expressions. Your
工具
結果
goal is to create an XPath that is suitable for automated testing based on the
provided HTML elements.
Playwright
page.locator（I）.filter（nas_text=Interface
Designer）.locator（a.click（
You will be given three pieces of information：
//*［@id="access_fcOffldb-77f8-47fe-b89a-
1. The HTML of the current element
Cheome
2. The current XPath of the element
6105c113fd3d"］/div/div［1］/div［1］/nav/div［1］/ul/li［3］/dliv/a
3. The HTML of the parent node （up to three levels）
srd party
（//a［@class='componentrHEvxowz icon-dark_rHEvxowz is-
When generating the XPath, follow these rules：
accessible_rHEvxowz］）［2］
1. Prioritize unique identifiers：
- First choice: Use attributes like 'data-testid' if available
//li［contains（@class，'auto-interface-
- Second choice: Use parent containers with clear meanings （e.g. containing
自餅工具
designer）］//a［contains （@class，'component）］
root, pane）
- Use meaningful class names or text in the XPath
2. Avoid classes with random characters：
- Do not use classes that contain UUIDs or unclear business semantics
在透过JS 获取目标元件 DOM 后，我们采用向上回溯三层父节点
3. Class name processing：
的策略为 AI提供上下文依据；然而，面对 SVG 等庞大结构时，
- Filter out meaningless class names
- Use contains（）'or starts-with （）' for partial matches
为避免 Token 浪费，系统会预先执行过滤机制，剔除对大模型推
4. Structural Stabiity：
- Use relative paths such as .//div and avoid absolute paths like /html/body.
- Generated XPath should be robust and not require describing the entire HTML
理无效的冗余数据，仅保留关键特征以优化上下文效率。
structure layer by layer.
工具实践部分 prompt
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 031

• 测试稳定性与执行效率优化
善用 IDE Prompt 功能技巧
IDE Agent Mode 强化协作
2
3
善用 Cursor 内置 Prompt 工具，通过 @文
善用开发工具中的 Agent Mode 可以突破单
件引用与/Command 指令强化上下文输入，
纯的代码补全限制。在此模式下，Al具备更
可在人机协作中引导AI快速聚焦、收敛问题，
强的专案感知与自主执行能力，能跨档案理解
有效避免思路发散，提升交互精准度。
测试架构并自动修正错误，将Al 从「助手」
1
4
提升为能独立解決问题的「代理人」。
人为介入特殊行为
模型能力决定测试成效
在 AI执行自动化操作时，浮动的 Toast 讯息
测试生成的稳定性高度依赖模型的推理能力。模
常会遮挡元素导致点击失效。建议将其视为环
型愈强，对复杂逻辑与异常流程的处理能力就愈
境前置处理，比照 Fixture 的逻辑，在测试开
高；不管是测试规划或是对当前框架架构的理解，
高效精准人机交互
始前透过脚本将其移除或停用 pointer-
虽然高阶模型运算成本较高，但其带来的高成功
events，避免 Al 在探测路径时因遮挡而报错。
率能显著减少人工回头 Debug 的成本。
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 032

• AI 赋能测试革新：从点效突破到全域提速
以智能技术重构测试全流程，实现从单点优化到全链路提效的跨越
测试用例生成
测试脚本生成
基于 Al 的分析能力，快速解析需求文档与接口定
Al Agent 自主理解测试场景，自动生成可执行脚
义，透过结构提示词，精准生成测试用例，大幅缩
本并宗成自动化测试执行，支持多场景适配，降低
短用例设计周期，摆脱人工编写的低效重复。
脚本编写门槛，提升测试执行效率与稳定性。
产品业务知识提取
用户反馈 Log 分析
通过大模型处理与知识图谱技术。从产品文档、质
Al 智能解析海量用户反馈与日志，自动定位高频
史项目中高效提取核心业务规则与逻辑关联，快速
问题、异常场景及潜在风险点，将零散数据转化为
构建测试知识底座，减少业务理解成本及作为测试
可落地的测试重点。
案例设计参考文槛。
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 033

•AI 驱动 Log 分析与 Skills 从人工排查到自动诊断
通过 AI辅助完成用户日志的智能诊断与问题定位，构建人工协同排查一经验沉淀一自动分析的完整闭环流程，同时通过日志前置过滤实现
Token 成本与分析效率的双重优化。
。 第一阶段，资产沉淀：RD通过与 AI对话式协同排障，将零散的专家经验标准化封装为可复用的 Skills，构建组织级知识库。
• 第二阶段，自动闭环：新日志上传即自动调用 Skills 进行智能预判；配合 Python 前置过滤引擎清洗噪声，在大幅降低 Token 成本的同
时，实现从「人工排查」到「自动诊断」的效率跃升。
CSu betboad
5
Agent Skills
RD-
adjustment
Upload
Performance
script
analysis
references
database
script
analysis
references
Support / QA
Python
Platform
log
script
analysIs
references
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 034

核心技术底座
Agent Skills + Playwright Agent +MCP 的协同架构
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 035

关於 MCP （Model Context Protocol）
Model Context Protocol （MCP）是一种用来让大型
MCP
米Claude
语言模型与外部工具、资料来源和系统安全互动的开放
architecture
MCP clients
协议。它提供标准化的方式，让模型可以像使用「外
Client.py
MCP hosts
MCP
挂」一样连接资料库、AP、档案系统或各种应用程式，
并在需要时取得即时资讯或执行操作。透过MCP，开发
者不必为每个工具单独整合，大幅降低整合成本，同时
MCP
server
也能让AI系统更可扩展、可控。
MCP
ANTHROPIC
server
MCP connects Claude to external services and
Remote
MCP
Localdata
data sources. Skills provide procedural
services
server
sourCeS
knowledge —instructions for how to complete
specific tasks or workflows.
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 036

• 关于 Agent Skills
当前的大模型已经具备非常强的通用能力，但是专业技能才是解
决特定领域问题的关键。AI必须透过专业领域知识克服『懂而
2026/01
不精』的局限，而 Agent Skills 的诞生就是通过赋予 Al Agent
专业技能与知识，让 AI Agent能够更有效完成任务。
2025/12
Agent Skills 时代
在 Anthropic 推出标准化框架后，
2025/12
Anthropic 推出标准
Cursor, GitHub Copilot 与扣子纷
纷将 Agent Skills 整合进其生态系。
2025/10
Anthropic 进一步发布跨平台标准化
各大平台的强力支持，促使 Agent
社群及 OpenAI加入
Agent Skills， 旨在解决不同 AI系统
Skills 实现了跨平台的互通互操作。
间的相容性问题，推动 Agent 像软体
Agent Skills 诞生
在 Agent Skills 发布后不久，开源生态
AP| 一样具备通用性与互通性。
系，涌现大量相关开源专案，OpenAI
推出以文件夹为核心的技能机制，开启
将 Agent Skills 整合进 ChatGPT 与
AI 任务模组化时代，让大模型能自主
Codex体系，验证了 Skills 框架的可扩
读取特定文件夹中的指令与脚本，学会
展性。
操作 PDF、Slack 等特定工具。
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 037

• Agent Skills 渐进式揭露：实现上下文的效能最大化
Agent Skills 的核心创新在于「渐进式揭露」机制，将技能资讯结构化为三个层次并采按需逐步载入，在确保任务细节完整性的同
时，有效避免一次性过度占用上下文窗口。
系统启动时仅读取 SKILL.md 的 YAML 中的 name&
元数据（Metadata）
description 栏位，让模型在不占用过多上下文的情况下，快
（~100tokens）
速检索并识别所有可用功能。
仅在任务匹配时载入详细操作指引，确保模型在执行特
指令 （Instructions）
2
定任务时，能获得精确的步骤与逻辑规范，同时避免无
（< 5000 tokens recommended）
关资讯的干扰。
将复杂脚本、庞大数据集或详细参考文档独立存放，
3
参考 （References）
仅在任务执行需要时加载，在使用 scripts/档案时
（as needed）
也仅会执行脚本不读取，达到节省上下文目的。
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 038

• Agent Skills 专案架构与文件规范
pict-case/SKILL.md
pict-case/references/pict_syntax.md
name: pict-case
# PICT Syntax Reference
Agent Skils作为上下文工程核心方案，其专案架
desoription: Design test cases using PICT
（Pairwise Independent Combinatorial
## Model file structure
构以标准化文件为核心载体，整体遵循插件化目录
Testing）.
1. Parameter definitions （one per line）
设计逻辑，核心文件与结构化内容构成技能落地的
2. Sub-model definitions （optional）
3. Constraint definitions （optional）
# PICT Test Designer
关键，同时明确的文件规范让技能具备高复用性与
Use PICT to design test cases from
## Parameter definitions
requirements or code
场景适配性，解决了通用 Prompt 碎片化、复用
Model structure：
pict-case/scirpts/pict.py
性低的问题。
- Syntax and constraint grammar:See
［reterences/pict_syntax.md］（reterences/
import json
pict_ syntax.md）
Import sy/S
from pathlio import Path
### 3. Execute model and get test cases
- Or use Python to build the model （and
def generate_model（config_path: str） -x
my-skill/
optionally run via pypict: pip install pypict）
Str
- SKILL.md
# required: instructions + metadata
See
'Read JSON config and return PICT
model text
-scripts/
# optional:executable code
［scripts/pict_helper.pyl（scripts/pict_helper.p
with open（config_path） as f：
references/
# optional:documentation
config =json.load（f）
assets/
# optional:templates, resources
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 039

• 什么是 Playwright Agents
Playwright Test Agents 是一种以AI为核心的测试自动化机制，能自主规划（Planner）、生成（Generator） 与修复（Healer） Playwright
端对端测试流程，从而提升测试覆盖率与维护效率。
Generator（生成者）：撰写脚本自动生成
Planner（规划者）：意图转化与自动化导航 Planner
Generator
根据测试计画自动撰写 Playwright脚本，并在生
将自然语言描述的测试目标（如：输入帐密后登入成
成过程中即时对照真实UI 验证选择器
功）转化为结构化的Markdown测试计画，透过自
Playwright
（Selectors）与断言，确保产出的程式码具备高
动探索应用程序路径，确保测试覆盖逻辑精准且易于
Test Agents
可靠性与立即执行力。
人类审阅。
Healer
Healer（修复者）：自我修复与降低维护成本
监控测试执行状态，当 UI变动导致失败时，自动分析 DOM 结构并修复定位器
或同步逻辑，透过自动重跑验证修复结果，大幅减少人工维护脚本的负担。
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 040

Playwright Agents 核心依赖：两类 MCP Server 定位与差异
playwright- mcp
playwright -test - mcp
测试专属、面向
核心定位
通用浏览器自动化 MCP
Playwright Test 的MCP
Server
playwright- mcp 与 playwright - test - mcp
支撑 AI生成、运行、修复
核心定位
让 AI 操控浏览器、操作页面
同为微软推出的 Playwright MCP 工具，二者名
Playwright 测试脚本
称易混淆，但定位、能力、场景完全不同。
E2E 测试开发、CI 故障修
playwright-mcp 面向通用浏览器自动化，让AI
面向场景
网页操作、爬虫、自动化交互
复、测试脚本维护
直接操控页面；
playwright - test- mcp - server 面向测试工
browser_click、
test_run、test_list、
AI 能力范围
browser_navigate、
planner、generator、
程，支撑 AI完成测试编写、执行与自修复，是本
browser_fill 等页面操作
healer 等测试能力
次 Playwright Agent 的核心底座。
單独仓库：
源代码
内置于 Playwright 主仓库
microsoft/playwright-mcp
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 041

AOM（Accessibility Object Model）自动化测试的语义化革新
讓我先了解現有的測試結構和種子檔案、
Explored 2 files Ssgarthes
好的，我來幫你建立這個測試。首先讓我設定買面並逐步執行測試流程。
AOM 作为网页无障碍访问的核心技术规范，通过 JavaScript API 直接操
讓我先用種子榴案設定頁面，然後逐步祭作。
作页面无障碍对象模型，自动化测试提供了超越XPath/CSS 的定位与交
w Ran generatorsetup.nngercursor-playwrighepiaywright-test
互方案。其核心价值在于将元素定位从 “视觉属性依赖” 升级为“语义逻
Running 1 test using 1 worker
Paused at end of test. ready for interaction
辑关联”，为自动化测试在元件的选择上开创了更多的可能：
Page state
• Page URL: https://192.168.1.24/protect/dashboard
• Page Title: Dashboard | Network Video Recorder Pro- Max
• Page Snapshot：
语义化定位更稳定：直接基于元素角色（role）、标签
- generic ［ref=ezl：
- generic Lref=e3］：
④（abe） 等元瞳得语义属性定位、來受DOM 结构、lass/id
- banner ［ref=e4］：
- button Site Switcher"：
动影响，从根源解决传统定位脆弱性问题
- generic：
- img
-：generic "Network Video Recorder Pro Max"
- generic ［ref=e5］：
2点 AlI 协同提效：AOM 将复然 DOM 转化为标准语义树，消
- Link "Protectw Lref=e6］ ［cursor=pointerl：
除无效士扰，便AI能够精准识别业务逻辑，大幅提开目动代
- Jurl:/protect/dashboard
- generic Vrefee7l：
脚本的生成成功率。
Thought tor 2：
頁面已登入並在 Dashboard上。現在我逐步執行測試流程。
孩脱ID 依赖的天联定位：文拨自接建立兀素旧的尤障得天
> 2 Files
Review
3地如 aria-controls），无需为成千上万的动态元素生成唯一
Plan@for conext, /forcommands
D，大幅简化复杂UI（如无限滚动列表）的测试逻辑与维护成
co Agentclaude-4.6-opus:high
本。
实际 AOM 架构图
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 042

分层协同的 Skills +MCP 混合架构
Interaction & Intent
查看这张 ticket后撰写测试案例，
（交互与意图层）
再根据撰写的测试案例执行测试并生成脚本
Skills 与 MCP 并非替代关系，而是形成分层协
作的混合架构，通过关注点分离实现能力与智慧
的互补，构建高效、可维护的智能体执行体系，
Agent Skills
挑选技能
根据工作流执行
根据工作流执行
执行脚本
（代理技能层）
在实际工作流中完成从任务识别到结果输出的全
技能库
pict-case
StresS-test
product-knowledge
链路闭环，同时实现成本优化与能力复用的双重
价值。
MCP Tools
工具调用
访问外部工具
参数填充
获取工具清单
模型上下文协定
Grafan
MCP Server
寸 Jira
TestRail
X Confluence
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 043

14
未來展望
Agent Skills + Playwright Agents + MCP 的协同架构
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 044

基于代码依赖分析实现测试范围精准聚焦
将代码库构建为全量知识图谱，可精准解析代码
修改内容与模块间的依赖关系及调用链，让测试
工作从全量覆盖转向基于变更风险的精准聚焦。
借助图谱变更影响检测能力，可量化代码修改的
风险，识别高风险依赖模块，让测试资源集中投
入到风险高发的变更关联区域，实现测试效率与
测试深度的双重提升。
• 精准识别：通过图谱解析代码修改点的上下游
9.Gt ou 影理 所積費
依赖系，明确变更影响边界
• 风险量化：对修改影响进行深度分级与置信度
评估，标记高风险的核心模块与执行流程
• 精准测试：基于风险等级规划测试范围，聚焦
高风险变更关联区域，减少无意义的全量测试
GitNexus 開源工具
aCon
InfoQ极客传媒
全球软件开发大会

## Page 045

构建预先冒烟机制，实现 Al自动生成、执行与代码化回归
开发提交 PR 后，调度AI 基于代码变更精准生成用例并执行冒烟测试，生成冒烟测试案例；验证通过后，AI自动将测试逻辑转化为标准
自动化脚本反馈至仓库，同步推送结构化报告给 QA，实现「测试左移」与回归资产的自动沉淀，让 QA 专注于高价值场景复核。
PR 触发
Skills 生成
Playwright
自动化生成
测试代码
QA 高效介入
前置校验
测试用例
Agent 执行冒烟
测试资产
上传
闭环
测试
研发提交代码 PR
提取 PR 代码变更
基于生成的测试用
测试执行完成后，
将生成的自动化测
推送测试完成通
后，自动触发 CI
内容、关联需求文
例调度 Al Agent
AI 自动输出结构
试代码自动推送至
知，同步 Al 测试
流水线，联动 AI
档与产品业务知
自动执行冒烟测
化测试报告（明确
GitHub 对应分
覆盖范围、用例通
完成多层级前置测
识，驱动 Agent
试，快速验证核心
通过/未通过场
支，与业务代码同
过率及生成的脚
试，包括 Linter
Skills自动生成针
功能可用性，过滤
景、问题定位建
步版本管理，确保
本；QA 仅聚焦末
代码规范检查、单
对性测试用例（覆
基础问题
议），同时将验证
脚本可追溯、可迭
通过项与关键场景
元测试执行、安全
盖核心功能、边界
通过的测试用例转
代。
复核，且生成的脚
漏洞扫描，以及
场景）：确保用例
化为可复用的自动
本可在后续迭代中
Al Code Review
与变更点高度匹配
化测试代码。
触发，作为回归测
（智能识别代码风
试的核心资产。
险与优化点）。
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 046

Al 对 QA 是帮助比较多？
还是威胁比较多？
aCon
InfoQ 极客传媒
全球软件开发大会

## Page 047

• 欢迎交流
明哲
臺北市，中國臺灣
掃描上面的 QR Code，加我為朋友。
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 048

InfoQ 极客传媒
QCon
全球软件开发大会
THANKS
大模型正在重新定义软件
Large Language Model Is Redefining The
Software

## Page 049

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
OPPO/大模型算法员责人
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
