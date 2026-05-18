# 曹偲-DSL-Spec-TocoAI-的后端-Harness-Engineering-实践

> Page-by-page visual information extraction from rendered slide/page images. Text is OCR-assisted and preserves visible page order; diagrams/tables are represented by their visible labels and relationships as line-by-line text.

## Page 001

InfoQ 极客传媒
QCon
全球软件开发大会
DSL-Spec: TocoAI的后端
Harness Engineering实践
曹偲—TocoAl创始人，原网易云音乐CTO

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

个人介绍
•15岁进入浙江大学计算机系，2008年硕士毕业加入网易
曹偲
•2012-2022年，作为核心创始人参与网易云音乐从初创到上
市
TocoAl 创始人、CEO
•领导千人技术团队，同时负责产品策划团队
前网易云音乐CTO
•2022年底离职创业，致力于研究和实践软件研发新范式的变
革
•2026年1月，带领研发的核心产品 TOcOAI上线
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 004

你了解设计时么
运行时
编译时
设计时
无类型，
有类型，
有约束，
维护难度最高
维护难度其次
有动机，最易维护
i AI 工湿的发展趋
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 005

About Spec
什么是 Spec
人和 AI 共建的手段
为什么要 Spec
软件和脚本的区别
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 006

Al Coding 是低门槛的，
Spec Coding 却未必
怎样长时间维护好Spec
怎么协作 Spec
2
3
现实业务的持续变更会导致规约迅
除了Merge代码，还需要Merge
速熵增，保持长期的逻辑自洽远修
Spec么。如何保持在团队中Spec能
补代码补丁更难
很好的运作
1
4
怎么定义Spec
怎么验证 Spec
需要本身对架构知识有一定了解的，
规约层缺乏像编译器一样的硬性物
而不只是被动接受Al输出
理反馈，导致Spec本身会慢慢变
得矛盾重重
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 007

Spec 的发展方向
Spec As Source
Spec 能一定程度上取
Spec Anchored
代代码，代码变成一
种表达方式
Spec First
规约不再是临时文
档，而是与代码同步
AI 动手写代码前，先
演进的“真值中心”
写一份详尽的功能需
求文档（Spec）
建模驱动：DSL描述软件结构
• 规汇Spec描述格式
成为的“唯一信源”
2 TocoAI
可管理、可检查
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 008

DSL-SPEC:SPEC的合理形态
“形式化符号是排除各种胡说/道的极其有效的工具。自然语言的自然性，不过是我们能轻松地用
它说出那些荒谬性并不显而易见的话。
"— Edsger Dijkstra,EWD667, 1978
缩略版，含公司和设置信息
user_detail_dto ｛
sdtoy：f
UserwithsettangsAnaCorpanyDto.java
-60
DTO 结构定义，含助套
的用户信息
Eong d 主键账
00id"： nult.
Company 和UserSetting
nanes： "user_with settings:and_company_dto"，
Suesng:hame 姓名
descrzptionl：“用户详情，包合所展公司后只及用户设工列表”
tromEntity t "user，
ComganyBaseDtoejava
130
Company绝相定X
Long age年龄
oxpandList：［
完整版，用户基本信息，以
UserSettingBaseDto java：
~35
UserSeting 造构定义
Stpang nick 死称
user 为根实体、包含id.
"foreignkeyInThisEncity "company_id".
#d toFLe2dNaoe"："companyl.
UserWithSettingsAnaCompanyDtoManager.java
-25
Manager 接口，产期
Date created_at 创建时间
name. age niok.
#dtok：
gctByid/gctByidList/
geateo-at.updated_at 字
pate
updated_at.更新而间
wauid : nuzl.
getlyCompanyld 今
"name ： "company base.dto"，
段。通过 user.company_id
compapyBasepco
company｛公司外銀护限
MfromEntity"： "company"
UserWithsettingsAndCompanyDtoManager Base!mpl,java
~120
Manager 基出实规：公批
#deseriptionl公司基本信品"
外键正向扩展出所属公司信
贵查询和防N+1逻号
Long sd 主從 PR
息公司信息包含id..
StpinE name 名称
UserWithSettingSAndCompanyDtoManagerImpl.java
-15
Manager 扩無实观，供业
name: locatlons created_at.
reversefxpandList"e［
务自定美
String
Aocation.油址
updated_ato通过
#foreignkeyinotherEntity"s "user_id".
UserwithsettingsAndcorpanyDtoconverterojava
~80
Endity- DTO字段政射转
user_setting user_id 反向注入
Cate cneated_at 创建时间
"dtoFieldName"：/user setting list，
用户设置列表，列表元素包
updated_at 更新时间
NdtoweE
wooid :nuzs
UserWithSetti ngsAndCorpanyDtoService.java
-70
Service 层预定义方法，公
含id、keys valuey以
"name :Wuser setting_base dto"，
company 止向折装
MfromEntity"："luser setting"
useT_setting反向注人
user_setting 为根实体.
唯一
BistaUsensettingBaseoto> uson setting_list（ 主能
#deseriptionls！用户设置基本信息”
键为（user_id, keyl。
Userwichsett=pgsAnoCorganyDtoBaselataAssembLer.］ava
-110 效据拼装基关，自动处理嵌
LonB id 主往
PK
套关顶岌据旅取
String
key 役置项
UsarwithSettingsdndComoanyDsoDatanssemuergava
~20
拼装术展点，供业务实现
Strtng
value 设置推
postProoessData
文本表达
视觉化表达
数据格式
可对应代码
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 009

DSL-SPEC：构建研发的“本体”
自然语言 Spec
崔序式 lac
DSL-Spec
像自然语言一样可读，像程序一样精确，模糊即编译错
含义明确、可读性强
人人能读，但歧义不报错，只在生产事故里现身
精确，但需理解执行流程才能看懂意图
误
细节清晰（What +
只有模糊的What,How全靠AI 自由发挥
只有 How，架构意图藏在执行逻辑里无法单独审查
What（数据意图）与How（结构約束）同时显式表达
How
可校验、易维护（变更
可执行但无独立意图层，变更影响面需依赖分析工
机器可解析可校验，改 DSL-Spec，引擎自动级联同步所
机器无法校验，改一个字段靠人肉追踪影响范围
可查）
具
有受影响结构
始终和代码一致
启动时准确，三个月漂移，六个月成历史文献
代码即实现，但架构意图随迭代逐渐丢失
Spec 与代码的关系永远是，不是
对研发全链路的本体价
无法作为本体，测试/CV/变更管理各自维护一份对系
可作为执行层本体，但意图层缺失，下游流程难以
—Ontology.测试断言、DDL变更、影响面分析均从
值
统的近似理解
校验设计意图
同一真相派生
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 010

•
Programming：Harness的最佳范式
TocoAI
Al Modeling
DSL-SPEC
需求文档
（Harness Layer）
建模引擎
持续约束
稳态渲染
结构性代码
胶水/流程代码
交付系统
（~80%）
（~20%）
持续演进，始终如一的Harness Engineering实现
Agent（处理泛化和非确定性问题）+ Programming（处理一致性和确定性问题）
对于描述具体行为，一行代码胜过于言万语
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 011

•
Harness + Human-In-The-Loop
Al是信息不全的
结构、状态（存储）
Al是“懒惰的”
数据流转
Harness
Human-In-The-Loop
Al是“缺乏大局观的”
复用性
Al是“不懂审美的“
性能
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 012

•
Beyond Harness
存储驱动
建模驱动
本体论
（DB+流程）
（DDD）
（Ontology）
烟囱式构建系统
业务即模型
AI原生语义支持
逻辑碎片化、黑盒化
Al时代系统构建不是单
逻辑解耦
理解业务
纯的代码问题
知识资产化
流程驱动的数据模型（能跑就行）
决策驱动的数据模型（对数据模型的正确性、一致性、因果关系都有要求）
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 013

TocoAl
降低Spec Coding门槛
Conventional
TocoAI
提高Harness能力
Message
Spaghetti
Prompt
Command
提供长期维护方案
API
Code
/Query
TBD
Architectural
ER.BO
ETC
Model
2 开源共建的模式
Technical
Refactor
Debt
高效的设计时迁移方案
Maintainable Code
Al Powered
Github
https://github.com/toco-
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 014

• 实践案例
项目背景
•M Rkerst nnuktit
xo Hasn
构建新一代信创HIS，120+核心模块，200+业务流
程，800+页面，参与人数30人（对应传统开发数百人
mnww
以上规模）。是经典的超大型严肃系统开发。
目國圓國雞醫.
难点
多人协作，统一语言；医疗业务零容错；Code Base巨大。
效果
大幅提效：仅投入传统团队1/10人力，整体研发效率提升300%+
可持续性：项目后期代码AI率依然保持近100%
Al-Ready系统：为基于系统的BI/AI提供标化地图。
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 015

研发将去向何方
去UI而不是去软件
行业
去职能化而不是去程序员
“效率革命” 走向为“效果革命”
模式
重构变成GC
左移再左移
流程
小团队将是主流
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 016

InfoQ 极客传媒
QCon
全球软件开发大会
TocoA Github
https://github.com/toco-
THANKS
al
大模型正在重新定义软件
Large Language Model Is Redefining The
Software

## Page 017

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
