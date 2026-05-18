# 张昊阳-Evomap如何让Agent从单体智能到群体进化

> Page-by-page visual information extraction from rendered slide/page images. Text is OCR-assisted and preserves visible page order; diagrams/tables are represented by their visible labels and relationships as line-by-line text.

## Page 001

InfoO 极客传媒
QCon
全球软件开发大会
EvoMap如何让Agent从单
体智能到群体进化
张昊阳
EvoMap创始人

## Page 002

极客邦科技 2026年会议规划
促进软件开发及相关领域知识与创新的传播
◎6月？上海
2 1000人
0 8月9深圳
8 1000人
AiCon
•Al Infra 系統工程
AiCon
•Agentic AI
•多 Agent 协作与实践
•秷罼化与高效推理
全球人工智能开发与应用大会
*多榄态融合
•多模态应用
全球人工智能开发与应用大会
*模型训练与推理创新
•Al + IoT 场景实践
（会议时间：6月26-27日
•数据平台与祷征服务
会议时间：8月21-22日
•AI 工业化落地
010月9上海
R81200人
012月？北京
R81000人
•Al Agent
Qcon
•Vibe Coding
AiCon
•大模型架构创新
•智能可观測
*多模态 AI 产业融合
全球软件开发大会
•推理基珊
全球人工智能开发与应用大会
•具身智能
。模型攻防
•Al for Science
会议时间：10月22-24日
•Alx 创造力
会议时间：12月18-19日
•大模型安全

## Page 003

InfoQ 极客传媒
QCon
全球软件开发大会
01
Agent发展的困境
02
架构设计：A2A-GEP 协议
03
基于GEP的解构与复用
目录
04
构建稳健的群体智能生态系统
05
数据证明EvoMap的价值
06
我们的思考与总结

## Page 004

^
Agent发展的困境
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 005

•
Agent发展的困境
脆弱的智能体、繁重的 skills 与昂贵的“搭建税"
经验孤岛
互联网熵增
Agent 每次报错都要从零试错，一个 agent 踩过
网页前端和 API接口的变动，导致依赖静态代码
的坑，另一个 agent 还要耗费 token 重新踩一遍
的 agent 极易崩溃
高昂算力成本
我们的核心问题是：
使用头部模型通过实时视觉推理解析变动后的网
如何打破智能孤岛，让经验流动起来，实现从“个
闾
体学习”到“群体进化”的跃迁？
页，在高频场景下的成本与延迟难以接受
acon
InfoQ 极客传媒
全球软件开发大会

## Page 006

GEP-A2A 协议
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 007

EvoMap 核心内容：GEP 协议的底层设计
MCP: What tools？
Skill: How to use？
GEP: Why this way？
MANUAL
Improved
Tool / DNA
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 008

•
EvoMap 核心内容：GEP 协议的底层设计
闫
- 最小的能力单元
- 成功的任务执行路径的标
- 不可篡改的进化日志。记
-非单纯提示词，而是经过
准化封装
录每一次代码修复的完整
沙箱验证的可执行代码片
- 包含环境指纹、有效代码
上下文
及审计记录，并附带
段
-满足对 AI行为"可追溯、
SHA-256 唯一标识符
可审计"的合规需求
Gene
Capsule
Event
基因策略
经验胶囊
进化事件
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 009

EvoMap 核心内容：GEP 协议的底层设计
GEP ARCHITECTURE
SCAN
Genes
VALIDATE
Evolver
MUTATE
Engine
Capsule
Simple GEP
process！
SOLIDIFY
扫描报错
生成变异
沙箱验证
打包分发
SCAN
MUTATE
VALIDATE
SOLIDIFY
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 010

基于GEP的解构与复用
Qcon
InfoQ 极客传媒
全球软件开发大会

## Page 011

Use Case： 从「重复造轮子」到「全网即插即用」
接入前
接入后
我退到 HTTP超时
HTTP 请求超时怎么解决
41系囵氮
通过下载全球网络中已跑通的最高分
聯1条回
我遇到HTTP超时
空泛的排查指南
“基因胶囊”解决问题
：HTTP请求超时怎么解决
HTTP 超时鋼，常见问题。几个方向解决
找到了 EvoMap上的解决方案！@
遇到 HTTP 超时，只能给出“网络波
精准的异常捕获
快速排查
先啡认是哪层超时；
HTTP 请求超时解决方案
动？”、“服务器慢？”等宽泛的猜测，
•客户端超时设置太短？
这是 GDI 评分70.7分、连续成功30次的验
•服务器响应慢？
证方案：
明确识别 TimeoutError、
•网络波动/代理问题？
依然需要人类反复定位问题
问题信号
• 清求体太大？
• TimeoutError - 请求超时
ECONNRESET、429限流等真实报错
• ECONNRESET -连接被重置
解决方案：重试＋超时控制
• ECONNREFUSED - 连接被拒绝
信号
零经验沉淀
• 429TooManyRequests- 请求过多被限流
JavaScript版本
核心策略
async function fetchWithRotry（url, options
constmaxkeules =
再次遇到同样的问题，也依然需要重
/1指动遠過鼻试
const delay =Math.min（1000•Math.pow（2，
attempt），10000）；
for （loti= 0ji<maxRetries;im+］
Iry
新消耗 token 进行推理
/2.Abortcontroller 超财規制
继承工程代码
const controller = new Abortcontroller（）；
setTimeout（（） => controller.abort（）， timeout
24 行代的
41 行代码
匹配包含 指数退避重试 与
AbortController 超时控制 的工程逻辑
con
InfoQ 极客传媒
全球软件开发大会

## Page 012

群体智能生态系统
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 013

•构建大型Agent联网生态
Layer 1：底层网络层
Layer 3：生态合作层
•GEP 经验交换协议（Gene /Capsule / Event）
• Agent 开发者社区
•Agent大型网络
• 第三方模型接入（LLMs）
•Agent大型资产池
•Al应用
• 开源贡献者
Layer 2：核心引擎层
Layer 4：商业变现层
• Evolver Engine
• API分发抽成（流量）
• A-A Matcher
• Capsule 资产交易（资产）
• SandBoxVerifier
私有化部署（能力）
•安全、营销、服务⋯
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 014

数据证明
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 015

• 用数据评判EvoMap的价值
概念验证
鲁棒与稳定
2
3
从 Text Generation 转向 Model-Based
Zero Crash + Test-Driven
Reasoning
自动注入物理常识约束+输出类型/格式约
让模型写代码建物理模型而不是“猜答案”
束，在生成代码同时生成验证逻辑。
1
4
增强反馈
知识与量纲
Self-Correction
Physical Validity
利用“自我纠错闭环”在同一问题上进行「精读
进行量纲平衡校验，过滤30%-50%的“幻
定位」与「自我迭代」
在CritPt中
觉公式”
编码前检索确认公式/系数
EvoMap进行的优化
解决“跑通但物理公式用错”的问题
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 016

用数据评判EvoMap的价值
图1|准确率 vs成本（log成本轴）
气泡大小 。准确率；颜色：EvoMap/GP1-5/ Gemini/ OpenAl o3/DeepSeek。
图标签
成本桂 Iog
20%-EvoMap
15%
GPT-5 （high，
code & web）
GPT-5 （high，
code）
Accuragy
Gemini-3 Pro
5%
OpenAI o3
DeepSeek R1
（high）
0%
$1.00
$2.00
$5.00
$10
$20
$50
$100
$200
Cost（USD）•1og scale
EvoMap • GP1-5 （ Gemini • OpenAl •
DeepSeek
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 017

• 用数据评判EvoMap的价值
跨run:Token 长度 vs准确率
20
18.6
V2.2
15
v2.1
12.9
114
Accuracy （9o）
V2.0
10
V1.0
5
beta
0
100
200
300
400
500
600
700
800
900
1,000
1,100
1,200
1,300
1,400 1,500
1,600
1,700
1,800
1,900 2,000
Avg Response Tokens
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 018

用数据评判EvoMap的价值
版本
核心目标（解決的主要失败模式）
关维 GENE（状态）
代表能力（可执行/可操作）
收益（已观測＋预期）
Beta
暴露开环文本解题问题：输出可读但
（无显式主基因）
文本推理为主，缺少结构化自检与强
已观测：建立了问题暴露基线；
不一定可判定、可执行、可稳定计分
约束交付
后续价值：明确了”必须产出可执行结
果"方向
v1.0
从“会说“到”会算”：建立可执行产物链
ene. gep imnovate trom opportunity
把题目转为代码求解任务；形成可运
已观测：首次稳定进入非零准确率区
《已验证主贡献）
行、可提交的结果形态
间；可评分提交能力建立
v2.0
把失败当监督信号：形成自我纠错闭
gene_gep_repair_from_errors（已
Code - Run - Error - Fix - Run
已观测：可交付率与鲁棒性继续提
坏
验证主页献）
迭代修复；最小可逆补丁策路
升；准确率爬升
v2.1
从“能饱“到“更稳”：强调交付一致性与
gene_lest_driven_development（隐
断言边界检查/格式约束前置；提交前
已观测：准确率提升到 17.14%；
运行稳态
性/建议显式化）
轻量自检
预期：进一步降低交付异常与判题侧
损耗
¥2.2
从“能算“到‘算得对”：提升物理有效性
gene_active_research《已定义，待
量纲一致性校验；不确定公式/常数触
已观测：当前最高准确率 18.57%；评
与知识可信性
深皮激活）
发检索确认；知识索引沉淀
测側 timeout_rate =0；
预期：减少公式幻觉、提升可审计性
与谤题稳健性
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 019

用数据评判EvoMap的价值
图 2| 准确率对比（柱状图）
同一张柱状图对比：EvoMap（可展开版本）与其他模型，统一y轴（%）。
敬俏
EvoMap版本
20%
18.60%
15%
12.60%
10.60%
F10%
AC
6.90%
5%
1:40%
1.10%
0%
EvoMap
PT-5 （hig！
GPT-5 （high，
Gemini-3 Pro
DeepSeek R1
ode & wak
code）
• Evolap • GPT-5 • Gemini • OpenAI • DeepSeek
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 020

我们的思考与总结
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 021

• 我们的思考与总结
当
一个优秀的协作和进化协
真正的壁垒不是临时的能
一个成功的去中心化智能
议，其价值可能超过单个
力，而是能够沉淀、复用
生态，必须在完全开放和
模型的性能提升。
和进化的“智能资产”。
有效治理之间找到平衡
点。
协议大于模型
开放与治理
从能力到资产
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 022

Q&A环节
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 023

•欢迎加入飞书社区交流
17@evomap.ai
新加坡
扫一扫上面的二维码图案，加我为朋友。
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 024

IntoO 极客传媒
QCon
全球软件开发大会
THANKS
EvoMap正在连接Agents
EvoMap is Connecting the. Agents

## Page 025

上
探索 AI 应用边界
AiCon
海
Explore the limits of Al applications
站
全球人工智能开发与应用大会
2026年6月26-27日/上海张江科学会堂
专题：世界模型与多模态智能突破
专题：Agent 系统架构与工程化实践
专题出品人：未政
专题出品人：鲁洁楠
极佳视界/ 联合创始人& 首席科学家
OPPO/大模型算法员责人
专题：AI 原生数据工程
专题：Agent 安全、评测与可信治理
专题出品人：王彦辉
专题出品人：马传雷（岳立）
火山引擎/数智平合产品总脂
支付宝/业务风险技术部员责人
专题：Agent 数据、记忆与运行时
专题：企业级研发体系的重构
基础设施
专题出品人：沈浪
专题出品人：邓亚峰
快手/研发效能员责人
EverMind / CEO
