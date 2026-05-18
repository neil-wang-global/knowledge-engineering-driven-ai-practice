# 郭勇良-复杂业务场景下-RCA-Agent-的探索实践

- Source images: `references/paper-visual/images/郭勇良-复杂业务场景下-RCA-Agent-的探索实践/`
- Processing mode: page-by-page visual information extraction (OCR-assisted; not a summary)
- Pages covered: 47

## Page 001

InfoQ 极客传媒

QCon

全球软件开发大会

复杂业务场景下RCA Agent的探索实

践

郭勇良

快手 资深服务端架构师

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

## Page 003

InfoQ 极客传媒

QCon

全球软件开发大会

背景和痛点

02

业务场景的落地挑战

目录

03

核心机制和架构设计

04

总结和展望

## Page 004

背景和痛点

要解決的问题

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 005

Al浪潮之下.

编码工作大体上已被攻克

“Coding is

largely

solved”

Boris Chemy

Head ofClaude Code

Claude

软件工程被解决了吗？

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 006

为什么需要RCA Agent

Al Coding是不够的

随着人对代码掌控下降，

“排障是下个待解问题”

“AI排障从可选项变为必选项”

大型公司（微软）＋ 成熟团队

AI Coding后，组织效能 和个人效能 间仍存在巨大差

的“典型工作日”分配

OpenClaw在一场史上最大版本的更新后，因激进、无兼容层的破

图28展示了AI 采纳与这些结果之间的关系。

环性重构，大量用户反馈插件瘫痪、功能失效。

人工智能影响的格局演变

人工智 应用对关键结果的预估效应（89%可信区间》

r/openclaw•5d ago

Monobert Member

软件交付不稳定性

『班：北營效价增长募菲理恐易業

回会议沟进，

其他（学习/

23%

Do not install 2026.3.22- package issues

組給效能

文档/行政），

有价值的工作

36%

Just updated to 2026.3.22 - Both whatsapp and the control Ul are broken.

代码质量

产昌性能

Bug reports indicate this is a broken package. If you have already upgraded there is a workaround for Control UI

软件交付吞吐量

开发，18%

国以效能

差距

职业侉乾

https:l/github:com/openclaw/openclaw/ssues/52808 （Follow the instructions in the Chinese post）

摩揥

运维，4%

For whatsapp it's being reported but no solution yet：

0.00

0.05

0.10

0.15

0:20

•方案设计，7%

预估效应（标准化）

排障，12%

https://github.com/openclaw/openclaw/ssues/52813

微软《Today was a Good Day: The Daily

《2025年DORA报告：人工智能辅助软件开发现状调查报

Life of Software Developers》

告》

5971 份有效购应（购应率15.5%）平均从业年

限10年。

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 007

• 我们要解决什么场景？

问题场景…

基础设施层

中间件层

业务层

业务层问题特点

业务层异常是 用户体验、收入的直接体现

品 容器故障

Cache异常

My核心指标下跌

业务逻辑可能随时调整，是易变的

业务问题是“无法预测步骤数量"的开放问题

节点故障

DB异常

• 风暴告警

同样的“时长下跌”问题：

•

可能是Redis慢查询、GC、基础设施异常、代

品

网络故障

MQ异常

跨系统传播

码bug

每种根因的排查路径截然不同且无法预先枚举。

•

这种情况下，需要LLM动态決策下一步做什么

（继续追踪日志？查找变更、回滚版本？）

RCA

Agent

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 008

02

业务场景落地挑战

四个挑战：理解业务、对抗噪声、衡量不确定性、对抗幻觉

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 009

挑战一：如何让AI理解业务

可能引起告警或指标波动的事件

主动

活动放量引流，导致用

户点击量提升

程序/配置 变更导致故障

业务现实十分复杂

业务玩法、安全策略变

更导致指标下跌

压测、演练、逃生事件

主动&被动 /内部&外部 并存：

外部原因有相当一部分占比，这部分难以归因。

外源

内源

噪声和信号并存：

很多告警是噪声、但也有非常重要的“信号”。

大主播口播、导致直播

送礼量尖峰

Nginx宕机、DB宕机

并非都是故障：

很多“信号”是预期内的、少部分预期外外引发故障。

3.1日-3.5日，全国中小

巨大的状态空间：

学开学，用户流量下跌

Redis层大Key热Key

排查内部链路指标之外，也要考虑外部外部因素。

暴雪停课、春种秋收等

导致的流量上涨

服务容量不足

被动

aCon

InfoQ 极客传媒

全球软件开发大会

## Page 010

理解业务：业务场景案例——请求异常上涨

！用户请求异常上涨！

主站服务

0o

A服务是核心业务入口服务，指标异常。

0G

快手

日用冬

09.99%

直接下游有100+，包含多部门服务，成功率全部正常。

APP

首先，是不是问题？

• 是外部有热点事件发生，用户涌入？

． 还是内部有啥变更影响了？

A部服务

B部服务

其次，假设是问题怎么排查？

• 拉所有下游owner逐一确认？

• 变更列表中所有可疑变更全部回滚？

• 扩大到业务域范围上升？

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 011

理解业务：业务场景案例—— 真实根因

！用户请求异常上涨！

主站服务

推荐质量下降

反常识：

推荐质量下降反而导致了请求量的

快手

A的直接下游有100+，全部正常

增加。

APP

推荐质量下降导致

B

内部降级

用户反复请求刷新

异常传播中断：

中间服务降级、导致故障链路被

失败率增加

“掩盖”，传导中断。

A部门服务

B部门服务：

跨部门协同：

服务Core

E

auimnp

即使机制完善、效率再高，也有信

息传递成本和折损。

请求正常，

实际接口字段缺失

F

配置发布、引入

oug

一次排障，大量人员参与…

aCon

InfoQ 极客传媒

全球软件开发大会

## Page 012

理解业务：业务场景案例—— AI怎么解？

用户请求异常上涨！

主站服务

0G

推荐质量下降

断点1：

快手

A的直接下游有100+，全部正常

Metric无法关联，

APP

依赖业务经验

B

内部降级

X

失败率增加

A部了服务

B部门服务

Metrics

服务Core

E

dump

断点2：

三板斧是否足够？

请求正常，

实际接口字段缺失

Metric正常

业务Log缺失

F

配置发布、引入bug

技术指标外，必须理解业务

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 013

理解业务：建立业务上下文

通过读取链路相关代码，建立业务理解

Coding Agent买时代码分析：

新的效率瓶颈：多库关联分析（3-5个

Repo）

Metric

Claude Agent SDK

单库任务平均耗时30分钟..

Change

Event

换轻量库

慢、累计耗时长

Pl Coding Agent

链路服务多、SDK依赖复杂、一次排障涉及多个仓

单库任务平均耗时5分钟

5min*（3-5） = 15min ~25min+

GIT

累计耗时依然无法满足实时分析需求

代码是唯一真实的文档

如：某业务错误码语义、

开关变更的逻辑影响

aCon

InfoQ 极客传媒

全球软件开发大会

## Page 014

• 理解业务：建立业务上下文

低抽象导致的低效率

self.file

selfufingerprint

self:Logdupe

selfidebug oew

self.toggem

path：

self.file

self.file.

self.fingerprlnts.

Rclassmethod

def from_settings（clsssett

retum cls（joh.dtr（settings），

debug= settings.

46

def request seen（selt, Ts

fp= self. request.fin，

if fp in self.fingerprintss

self.fingerprints.add（fp）

return Tryg

1r self.file：

self.file.write（fp 05.11eegi

def request_fingerprint（self，

return nequest fingerprint（rea.s

代码虽然真实，但是抽象层次极低

人也记不住每一行代码⋯

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 015

理解业务：建立业务上下文

1.业务语义标准库

离线沉淀：通过coding agent生成关系

codevalue

业务Label

指标知识瘁管理

（eg.25667）

（eg.用户未授权）

提取错误码、metrcs标注含义

2.指标拓扑图谱

离线生成

抽象

在线沉淀：无业务资产时自动生成SKILL

业务代码

检索

3.开关变更影响地图

知识库

|Fallback

Feature Flag

PI Coding SDK

沉淀

建立开关对接口、上下游关系业务影响

在线生成

• 生成技能

业务资产

创建SKILL

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 016

理解业务：总结

本质是消除人和AI间的Context代差

代码逻辑

错误码28801表示”需升

级”；

Metrics

开关A可能影响xx下游；

指标关系

Trace

评论量 关联 推荐下发量

关联 兜底触发量等；

Log

Agent

业务常识

大主播口播可能导致流量上涨；

Change

RD

中小学开学可能让请求下降

Event

信息、信息、信息

运维事件/外部事件

今天下游有压测/演练，

流量上升；

故障注入可能导致错误率上升。

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 017

• 挑战二：如何对抗噪声

值班工程师时间分配

20%

告警确认（噪声），

19%

关键洞察：噪声占比 ＞75%，

真正需要关注的告警不足 259

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 018

• 对抗噪声：告警疲劳的危害

一个P2+case的复盘⋯

7.00K

140.00K

120.00K

6.00K

5.00K.

80.00K

60.00K

4.00K

40.00K

炔速偏离

20.00K

3.07K

1.49K

21:55

22:00

22:05

22:10

22:15.

22:20

22:25

22:30

22:15

22:30

22:45

23:00

23:15

23:30

min ：

max ：|

avg

total

min：

max一

avg

total

—today

3,359.00

6,702.00

4,152.32

153,636.00

today

3,359.00

126,205.00

32:078.87

2,630,467.00

-- today_上周同期值

3,165.00

4,058.00

3,668.70

135,742.00

-today_上周同期低

1,489.00

3,708.00

2,624.59

215,216.00

-today_昨日同期值

3,071.00

6,482.00

4,174.03

154,439.00

- today_昨日同期值

1,647.00

3,813.00

2,518.66

206,530.00

天薇

2025-12-16 20300g

一个指标、不定时波动报警，值班RD接收后点击静默

15min后业务指标迅速偏离，无感

知

•日微效

原因：该告警7天内报警次数超过15次，接麻了

已收蜇

2025-12-1/ 10:34:00

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 019

• 对抗噪声：如果让Agent处理全部告警

QO：

35,000

250K

30.000

200k

27.231

ReAct循环

150k

Agent

Tool

交互次数不可控

15,000

50K

10,000

oK

完整的Agentic推理一次消耗10w~100w Token

快手主站告警事件总量月均2~3w（要求接手率的部分）

单次深度排查Token消耗

全量告警

月均100亿+Token

年化数百万RMB

Claude sonnet模型计价

除成本不可控外、时间也无法保证

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 020

对抗噪声：置信度评估

Alert Time 分布（按小时）

KSN 分布

最大偏离值分布

【入水口】接入归因的告警

告營治理 估

告警置信度评估

评结结票：山酸售驾讯路不持合上达持征，葛天朗确的治理建这，需要人工分析。讲器：讓议信合公量的金务庙录、也營须軍，出藝影激够及常这行综合分析。

识别&过滤告警噪声

告警策略总体分析

岡脶性分析

偏窮分析

恢短分析

…娱質分析m：天有效圾嬗封长歆響，

.《金醫分数任各个时線，无能盟料怎欢四）

103，類国15:00,4.001-

税N分雞：

-共有122 个不同的值，总出灵次出10002

2.雙*每日报營量，二其3大，『均备人333.3次册

2 ！還大雪惠分折！！条次告營的放大官惠惯取的

webcericesocalre ston:1t18 63次l

归因排障推理

3.：注续报醫效區”；怡美51姐连堤报警，其

”旅高国他封限余“：577%約商餐在業196司

KSN： |1o03 KSN占出83.7%

识别问题告警根因

A分咨司间点陶輿洋情分

1分后： 果占102.热国广00.3001株3然

4…Top KsA分布洋積然

24

-4分分：中比1.03. 維军1/00,300］、性本数

-weoservice-lmimwe-wograd -bg k-

w-stam-nekby-prowince-fy-ca-

-含1521KSN 占此898% 898入

识别头部告警、重复告警的模式规律，建立告警画像，作为Agent的

1“外部记忆”

aCon

InfoQ 极客传媒

全球软件开发大会

## Page 021

对抗噪声：推理阶段的证据淹没

一些CASE：

【入水口】接入归因的告警

指标A波动—>服务刚好有GC，

—>

但是不足以影响业务

误判

告警置信度评估

识别&过滤告警噪声

指标B波动—＞刚好发布高峰期，

—>

时段内500+关联变

误判

更

归因排障推理

指标C波动—>下游扇出大有200+，—＞

识别问题告警根因

单服务抖动概率高

误判

过滤误报噪声之后…

推理阶段仍然存在噪声…

当系统庞大到一定程度技术指标波动极其频繁。

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 022

对抗噪声：证据分级

源码实锤

服务直接变更

因果性强证据

循证 RCA 流程（引入循证医学思想）

指标拓扑DAG关联

直接因果推断

历史故障模式匹配

2. 证据检索

1. 问题发生

链路关联变更

工具/知识库/案例检

定义问题，收集数据

metrics/tracs跨源对齐

索

多源融合证据

关联线索证据

单服务技术指标异常

单一metrics/trace/log异常

3. 证据评估

2 4. 根因分析

单点观测证据

可靠性与适用性分级

结合最佳证据与现场数据深度分析

工程师经验

静态服务依赖关系

灰色证据

外部事件趋势（热点、节假日、天气）

背景上下文

用户反馈（工单客诉）

告警触发（阈值告警）

原始信号

层级越高，证据质量与可靠性越强。

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 023

挑战三：如何衡量不确定性

生产级agentic系统共识

找good case超级容易，比如happy path、cherry-pick例子；

彻底消除bad case极其困难，edge cases、silent error等问题层出不穷。

Bob NgS

@bobng2049

PS: bobng是XerpaA/ CTO

相比程序的确定性一

一》不确定性是AI常态

80% of enterprise Al pilots fail to reach production.

Not because the LLMs are bad. Not because the data is messy.

Because nobody bullt the orchestration contract before writing a single

line of agent code.

After shipping agentic systems in production, I see the same failure

pattern repeatedly：

Demo: Agent receives request - calls APl - returns clean answer.

路径2

Builds in 10 minutes.

Production reality：

—API returns 503 at 2am

— Customer charged twice on retry

—Compliance requires a full audit trail

类似蝴蝶效应，状态空间的轻微扰动，

- Agent loops on a null response for 6 hours

都会造成结果偏差

Demos model happy paths. Production is 90% edge cases.

同一个问题输入，多次路径、结论可能不同

演示只管顺利的路径，生产90%是坏情况

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 024

• 衡量不确定性：真实案例—优化变负优化

问题：单点抖动

RPC可用性抖动

A

B

单实例问题

Agent开发的残酷真相

优化：增加【维度分析工具】

Pod

• Selection

root

与传统软件的“确定性修复”不同：

B

AZ

eleu BHeaei ｛ey O.Nee.Hej eJ fe e,Jey. C｝ fezeil

feey, eal

（ej, Cci

1Q.N

你优化了1个bad case，可能又引入了3个新

Region

的。

维度分析

引入经典异动分析算法

结果：整体准确度反而劣化

访问量下降是单实例问题…

单实例问题发生频

送礼金额波动是单实例问题⋯

率高，导致…

Agent

搜索量下降是单买例问题….

aCon

InfoQ 极客传媒

全球软件开发大会

## Page 025

• 衡量不确定性：评价体系建立一

- Benchmark平台

Andrej Karpathy

@karpathy

Armin Ronacher's Thoughts and Writings

blog archive projs

sorry just to clarify -the real benchmark of interest is：

"what is the research org agent code that produces improvements on

nanochat the fastest？"

Agent Design Is Still Hard

this is the new meta.

written on November 21, 2025

由 Google 翻译自 英语

抱歉，我再澄清一下—真正重要的衡量标准是：

我们发现测试和评估是这里最难的问题。这并不完全令人惊讶，但智能体的性质使它变得更加困

“哪种研究机构代理代码能够最快地改进 NanoChat？”

难。与提示不同，你不能只是在某个外部系统中进行评估，因为你需要输入的东西太多了。这意味

着你想基于可观察性数据或对实际测试运行进行检测来进行评估。到目前为止，我们尝试过的解决

这就是新的游戏规则。

方案都没有让我们相信它们在这里找到了正确的方法。不幸的是，我必须报告，目前我们还没有找

评价此翻译：山 9

到真正让我们满意的东西。我希望我们能找到这个问题的解决方案，因为它正成內构建智能体的一

上午7:35 2026年3月6日 12.6万 查看

个越来越令人沮丧的方面。

Benchmark是新meta

“测试和评估是这里最难的问题”

到一定程度后、必须引入Benchmark。

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 026

衡量不确定性：评价体系建立

Benchmark平台

Case收集阶段

Case评测阶段

评测集设计，目标：覆盖真实问题空间

故障发生

加入评测

来源线上真实故障场景，经专家标注后沉淀入库

每个任务结构化包含：场景上下文、任务描述、依赖数

琚、预期结果

智能归因

数据转储

评测数据构造，目标：复现真实排障环境

“快照式”存储策略：只存储在推理过程中查询过的数据。

快于每天产生巨量监控数据，存在数据过期问题，只

存储包含下游链路执行数据

专家标注

评测Agent

评测结果评估，目标：衡量模型效果

构建自动化评分体系，通过有效线索进行量化评估。

效果对比

核心指标

输出对比

线索命中率

预期效果评分

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 027

• 挑战四：对抗幻觉

一个有趣的CASE PS：在claude opus4模型下

提示词1（直接询问）

这是中国时间（UTC+8）：2025-11-2421:07:01

请帮我转换成时间戳

结果儿乎完全不准确

提示词2（工具约束）

这是中国时间（UTC+8）：2025-11-2421:07:01

请运行Python脚本帮我转换成时间戳

结果非常精准

关键洞察：LLM是概率预测器，不擅长数值计算类任务

QCon

InfoQ极客传媒

全球软件开发大会

## Page 028

• 对抗幻觉：用工程提高确定性

实际场景 ——识别监控图片简单趋势

传统机器学习算法

孤立森林算法进行召回+通过k-sigma

算法及切片相似度过滤进行降噪

20:00

LLM识别。

多模态识别：幻觉严重、依赖样式

延迟缩短、Token消耗降低、确定性增强

时序数据识别：耗token、计算出错

当确定性要求超过一定程度时，工程化封装Tool/Skill是更优解。

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 029

• 对抗幻觉：算子进化

趋势识别

降噪

特征提取

算子库

画像计算

7

抽象封装

自动化持续进化引擎

特定算法

标准化算子

Eg：识别监控图谱趋势

Eg：监控图谱趋势算子

AutoResearch

CodeAct

自动迭代最佳算子参

自动识别可工程化算法，编

接口标准化

数、不同算法得分对比

写和优化算子代码

可复用

参数可调节

强确定性

真实数据

评估系统

通过算子提升确定性，构建Harness层持续迭代

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 030

02

核心机制和架构设计

一些Agent的设计思考&落地形式

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 031

•

演进的路径

Al+归因的发展路线

Al Agent

Al Workflow

完全Agentic自主化

给定Tool、Skill、CLliAgent自

SOP +Prompt

Workflow +MCP

主决定何时继续何时停止

Rule Base

通过Workflow编排流程、提取公

通过Prompt编排SOP

共能力到MCP中提升扩展性

本质上是将if else用自然语言描

纯规则驱动 if else

述了一遍，让AI按步骤执行

根据对业务的理解，将处理流程

编排成代码step by step运行

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 032

• 从Workflow演进到Agent，一定更优吗？

确定性 Workflow

由 Al Agent

延迟个

优势 （Pros）

TokenT

优势 （Pros）

•稳定可控，执行结果具有高度确定性

•具备自主规划能力，动态决策排障步骤

• 逻辑白盒化，易于排查、回溯和调试

•擅长处理发散、跨系统的复杂不完全信息

局限（Cons）

挑战 （Challenges）

•严重依赖预设SOP，步骤缺乏灵活性

确定性个

•大模型存在表现不稳或产生 “幻觉”的风险

•仅能覆盖有限且可枚举的已知故障场景

•极度依赖完善的工程约束与多维评测保障

•维护成本随场景增加呈指数级上升

• 工具无限膨胀时容易导致推理能力下降

Agent不是“更智能”的代名词，而是“更灵活”的代价

对于跨系统传播.多信号并发、根因高度不确定的开放性问题，无法简单地被静态 SOP 所覆盖，这正是引入 Al Agent 的

核心价值所在

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 033

告警分层治理思路

场景：核心指标突变、可用性下降

复杂问题

目标：加速归因

Agent处理（深度推理）

场景：特定系统告警、单点异常

简单问题

目标：快速归因/自动处置

Workflow处理（浅层归因）

告警噪音

场景：日常抖动、节假日波动

告警抑制、降无效投入

目标：源头降噪（智能告警、策略治理）

Workflow快思考 + Agent慢思考

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 034

快思考—-

-确定性Workflow

告警事件生成

天问归因数据获取

回過业务归因 AI Workflow

Workflow = 确定可控

抑制规则判定

特征画像分析

复杂问题判定

简单AI月因分析

针对系统类告警：

比如Redis可用性降低、连接数量波动，JAVA异常等问

单实例判定-

频率+恢复时长

系统告警归因

贡献度检測

+偏离程度

尚未覆盖？

维度归因分析

题往往有固定的排查SOP、可枚举的排查步骤。

确定性高：

后动抖动判定

启动时间

加权计算

是否核心业务报警？

影购范围分析

Step By Step的排查流程可以明确步骤，只需要制定精

E=w1.SF+W2-SR+W3-SD

准的排查流程往往就可能快速取得效果。

周期判定-

告警是否已应急？

同环比指标情况

关联告警风暴？

关联指标分析

快速出结论：

Workflow中和LLM交互次数是可控的，可以保证在告

警发出同时也完成归因分析。

命中

走二阶段

同步归因

告警抑制

告警发出，异步分析

告警发出，归因消息

（二阶段：复杂问题）

（一阶段：简单问题）

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 035

慢思考

MultiAgent架构

SubAgent领域封装

触发事件

单代告營信料

告灣风票裝合

运城成后单

大盛指綜波动

主动巡發

类似服务领域拆分，将同领

Eureka！

域Tool封装成SubAgent。

平台

1O0P

Main LOOP

.... SubAgent

技术指栃能障 SubAgent

Plan-and-somve模式

主10OP Agent

代码异常 SubAgent

长任务异步执行

主Agent循环

业务指标归团 SubAgent

可解篷报告

汁划更新

变更店因 SubAgent

TOD0：

ReAct横式

投本原因

分析摇

CC后台代码分析

：灣如calback.

处潞建议

比如涉及到要代码分析的，

sopend上下文

2.第业.

第一步.状done

#三步 本1odo

状态 processing

需加快复杂问题排查速度、

：姆遂綺架

工具箱（Tool Box）

避免排查阻塞。

异步投递信箱

业务拓扑

技术捐际

维凄信戀

CodeAct

变更盎询

脲务链路

流猩沉淀

Agent Team通信

数据基建

业务资产

#100P Agent

Spown

天向平合

万擎平台

天琴平台

核心链路

业务拓扑

核心指标大盘

缩短排查路径，避免反复确

Approve/ Stop

Worker Agont

认。但管理难度增大，需防

工限藏（Tool Box）

Share Cantext

KDV平台

Kconf/Kswitch

WorkerAgent

止上下文污染。

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 036

Agent自进化—— 自动构建案例集

如何低运维成本保证效果？

Agent自动构建案例集/经验库

下一轮鑽环

顾貫SOP

人工

few-shot

评测case

Eureka！平台一送代模式

经验系统

平台排障主Agent

小参数模型。

temnperature

如何

评測Agent

降低成本？

Question

CaSe物

吉果郑別

XX服务在Xx指标下跌

Codeng

妇因过產

Planning

判定

good case

def main（arg1）

toolcall0

Thought-

稀要Agent

Tool-

型復区

Anwser

return0

安因过程料

few-shot

根因是..（变更单点）

安、保序

zero-shot

成

妇因结论

本

>

经验库沉淀

泛化

适度泛化

过拟合

故障召回效果

让模型在当前工具集的条件下进行自我探索，用这种机制将good case的推理路径积累起来。

（积累的few-shot路径，后续同样可以用于RL）

QCon

InfoQ

极客传媒

全球软件开发大会

## Page 037

Agent记忆

信息组织

Hook记录、采集

RCA Agent

Agent Memory

RD脑中的经验-业务事实

告警策略维度

ALERT

触发归因

告警画像信息

服务维度

xX可用性下跌

初始化Context

"单实例问题很难引发业务指标的波动"，

全局维度

RD录入

"送礼请求突增可能和大主播口播、直播间送

业务经验fact

礼弹窗有关"，

推理/思考

构建

react

离线业务资产

CCtask

git

告警统计数据-历史洞察

agentic search

工具调用

长期业务记忆

总结/沉淀

xx告警具有周期性，每天凌晨1点偏离30%。

场景化SKILL

memory task

xx告警虽然维持一定的告警频率，但本次告

警偏离幅度明显超过历史均值。

memory save

推理结论

关键发现总结

整理/合并

Agent历史推理-过往记录

〇筛选/评估

case save

纳入Benchmark

过程few-shot

语义匹配，发现过往曾经推断过x次类似线

索的case，推断原因为XX。

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 038

产品交互—— OpenClaw带来的启示

s Welcone to the claude code nesearch previem！

AUDE

PENCLAW

IM接入

心跳

walcoisuccessFut, Press.Enter to.continue

超级权限

Cron任务

Poactive

从Claude Code到Open Claw，增量是什么？

ssul.md

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 039

产品交互——从ChatBot到Al Native

从人触发的ChatBot模式，走向AI自主驱动的AI Native模式

输入问题

使用 Eureka！排查告餐/指标/服务

自动拉群

【已响应】【260404】主调调用下游RP.

說24 昭 提示：【曰遊急处證小引美】使用合助鱼海工

消息

话题

Agent

m 2.关键发现

1.推理过程

RD

3.链路拓扑实时绘制

实时推送

以Chatbot的产品形式对外提供能力。面向的场景包括“排障”

终态：自动接管并驱动实现“问题感知->归因排障->协同处

“巡检”等。用户在对话框内提问，Agent推理给出完整分析报

置-处置建议/分级自动处置-＞经验沉淀（自学习）”自闭环。

告。

aCon

InfoQ 极客传媒

全球软件开发大会

## Page 040

•落地成果——核心指标运营

结果指标

过程指标

核心关注指标

说明

缩短故障MTTR

整体告習 结果准确率

分子/分母

（含拦截、推理结果）

（所有归因推理case准确数/所有归因case数量）

（真正形成的故障样本集过

• 有效线索率

全部告蜜 推准率

分子！分母

少，可能面临较大波动和

• 归因准确率

（只看进入推理部分）

不确定性。需要结合过程

• 归因时长

（推理准确case数/所有进入推理case数量〉

指标收益综合评估）

异常告骛 推准率

分子/分母

（异第告箸、只者进入推理部分）

（推理准确case数/ 异常告警进入推理case数量）

异常告警 有效线索率

分子/分母

（实际业务异常、进入推理、命中关链线案）

（推理命中正确线索case数/ 所有进入推理case数量）

整体准确率80%+，推理准确率60%＋（含线索）

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 041

• 经验沉淀 —— 踩坑和认知

①

③

LLM层频繁失败

API 接口不匹配

模型性能差异

调用不稳定，业务层必须建立Failover机制，确

不同LLM切换后，参数结构与返回格式差异导

实验结论表明，不同模型在同一任务上的推理能

保服务可用性。

致API层兼容性问题。

力与耗时存在显著差距。

C

⑤

数据缺失处理

重试vS立即失败

当上下文缺失时，需设计降级策略或主动追问机制，

警惕Agent"钻牛角尖”，如遇到错误服务名，避免自

而非产生幻觉。

作主张修改导致数据失真，应适时Fail Fast。

回 本质是软件工程

① 拥抱不确定性

Agent 应用开发回归本质仍是软件工程。核心在于构建健壮的错误处

分布式系统本身即在对抗环境不确定性，而 AI将进一步放大这种不确定

理、故障预防及容错能力体系。

性，系统设计需从“确定性交付”转向“概率性容错”。

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 042

04

总结和展望

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 043

• 从面向人到面向Agent

“拿着旧地图，找不到新大陆”

面向人（现状）

面向Agent（新范式）

① 上下文有限

① 可处理无限的更复杂数据

只能处理高度抽象、结构化数据。对应着目前的监控曲线、告警规

能够直接消费多模态、多源异构数据，不仅仅局限于简单的指标和

则要足够简单。

日志。

② 高度分工

② 上下文同步成本更低

造成经验孤岛。现代软件工程高度分工，人只了解领域内知识，跨

共享记忆机制，链式推理无需人工中转，打破知识孤岛。

领域沟通成本高。

③ 透明即效率

③ 信息即权利

Agent取代协调功能，自动获取信息、识别关键服务、生成排查方向。

权限隔离和分散的平台信息造成的信息孤岛：谁掌握更多信息，谁

就掌握主动权。

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 044

核心沉淀

"Agent发展非常快，很多两个月前的结论就已过时。我们能积累下来什么？"

可复用的（稳定层）

弓容易被颠覆的（易变层）

问题域业务资产

具体框架与工具选型

可观测性领域知识与专家经验沉淀

LangChain / Spring Al/ AutoGPT 等快速迭代工具

Eval评价体系

协议与规范

*a

完备的测试、评估与体系，故障标注库

随着SKILL和CLI的流行，MCP 逐渐被抛弃

结构化案例集

Prompt描述

历史经过验证、归因推断成功的过程记录

随业务选代、模型能力提升而变化的提示词工程

人机协作模式

模型选型

明确何时交给人、何时交给Agent

基座模型能力的快速更迭

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 045

未来演进

向更加 AI Native自主化、AI自进化 的方向演进

辅助決策

由，自主执行

自我进化

人工主导

Agent执行，人审批

AI自主闭环

Al提供建议与洞察，辅助人进行可观测数

据的智能分析。

Agent自主执行告警分析、根因定位、自

AI自主优化自身的观测策略、告警规则和

动修复，人负责关键节点的审批与监督。

修复手段，持续学习进化，无需人工干预。

角色：AI作为副驾驶 （Copilot）

角色：Al作为代理人（Agent）

角色：AI作为自主系统（Autonomous）

关键挑战

C 可解释性

V 安全边界

S 人机信任建立

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 046

InfoQ 极客传

QCon

全球软件开发大会

G.YL

广东 深圳

THANKS

大模型正在重新定义软件

Large Language Model Is Redefining The

Software

扫一扫上面的二维够图案，加我为朋友。

## Page 047

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
