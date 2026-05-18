# 存量修复 + 增量拦截：B 站代码债务治理实践

- Source PDF: `references/papers/何之真-存量修复 + 增量拦截：B 站代码债务治理实践.pdf`
- Visual pages: `references/paper-visual/images/何之真-存量修复-增量拦截-B-站代码债务治理实践/`
- Extraction mode: visual page-by-page information extraction
- Page count: 35

## Page 001

InfoQ 极客传媒
QCon
全球软件开发大会
存量修复 +增量拦截：
B 站代码债务治理实践
何之真
哔哩哔哩/ 资深开发工程师

## Page 002

极客邦科技 2026 年会议规划
促进软件开发及相关领域知识与创新的传播
06月？上海
23 1000人
08月9深圳
8 1000人
AiCon
，Al Infra 系统工程
AiCon
：Agentic Al
•多 Agent 协作与实践
•轻量化与高效推理
全球人工智能开发与应用大会
•多模态融合
•多模态应用
全球人工智能开发与应用大会
•模型训练与推理创新
•Al + loT 场景实践
会议时间：6月26-27日
•数据平台与特征服务
会议时间：8月21-22日
•AI 工业化落地
010月9上海
81200人
◎12月？北京
2 1000人
•AlAgent
QCon
*Vibe Coding
AiCon
•大模型架构创新
•智能可观測
•多模态 AI 产业融合
全球软件开发大会
、推理基建
全球人工智能开发与应用大会
具身智能
•模型攻防
*Al for Science
会议时间：10月22-24日
•Al x 创造力
会议时间：12月18-19日
大模型安全

## Page 003

InfoQ 极客传媒
QCon
全球软件开发大会
01
技术债治理的痛点与 AI 的价值
02
双轨治理：总体架构与核心原则
03
存量修复：持续偿还历史问题
目录
04
增量拦截：把新问题拦在主干之外
05
总结与展望

## Page 004

技术债治理的痛点与AI 的价值
Qcon
InfoQ 极客传媒
全球软件开发大会

## Page 005

•
千万行级代码库的现实
闫
闫
代码仓库持续增长，历史
扫描平台里一直有大量历
做一次专项治理，告警曲
技术债不是没人发现，而
遗留 Bug 与安全漏洞不断
史告警，大家都知道，但
线会短暂下降，然后迅速
是没有稳定的偿还机制
累积
排期永远让位于新需求
回升
问题堆积
优先级低
专项不治本
缺偿还机制
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 006

• 千万行级代码库，季度新增百万行
W
过去半年单个大部门下各子部门的代码量变化趋势
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 007

人工修复的困境
专项治理
每次专项治理投入大量人力，但效果只能维持几周
引入速度
新功能送代不断引入新问题，速度往往超过修复速度
修复周期
人工修复周期长：定位一理解一修复 测试 一 Review 一合入
核心矛盾
修复是离散事件，但引入是持续过程
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 008

问题的本质：发现 解决
P
稳定的修复产能
风险分层机制
不依赖人工排期，能持续产出修复
不同风险等级采用不同的自动化策略
真正需要的 4
A
D
个能力
可信的验证链路
Owner 兜底机制
修复结果必须能被编译、测试、规则
失败了有人负责，不是"系统说了算"
复扫验证
C
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 009

• AI 介入的前提与边界
① 规则、意图是否清晰
3
能否通过编译、测试验证
AI 更适合处理规则清晰、重复出现的问题，
Al更适合处理能被编译/测试 /静态分析验
而设计意图不明确的问题更适合人工决策
证的问题，而跨系统、跨服务的架构改造更
适合人工决策
AI 处理
VS
2 上下文边界是否明确
4
是否有 SOP
人工决策
AI 更适合处理上下文边界明确的问题，而涉
Al 更适合处理修复动作相对标准化的问题，
及复杂业务语义取舍的问题更适合人工决策
而需要 owner 强判断的改动更适合人工決策
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 010

• AI 在技术债治理中的价值与定位
Al 是工程体系中的一个生产力组件，需要被验证链路和风险分层”框住"才能发挥价值
规模化修复产能
知识沉淀与复用
把人工逐个修复变成批量自动生成＋验证
修复经验沉淀为 Prompt 模板和评测集，持续优化
目
增量实时拦截
降低修复门槛
在MR 阶段实时识别风险，而不是事后扫描
开发者不需要深入理解每条规则就能完成修复
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 011

双轨治理：总体架构与核心原则
Qcon
InfoQ 极客传媒
全球软件开发大会

## Page 012

总体架构
风险付员/Promet 与 Skill/上下文构 /5果葉合現则/ ouner 兜您
存量修复流程：扫描常态化，修复选择性能发
增量拦戳流程AI 补强 cz，但不替代原有cI
然取应用当前问盟
Sonar持续扫猫
AR 创建/更新
进入带奶CI 和紅E能力流水线
起过阙值？
AI Code Kavev
商信号批示
生成 执行-俗短
庭 补分单期
浚盖率图动焱牛
態发 AL 修兒
结果汇总
CI 结果•A结论、阳塞建议
创修台 MR
自司片發变更
深要处理？
研发修复 期过
两条轨道最终汇入同一套准入闭环
编泽/单測/hvt/报口验证/福益本經计，再次确认改动没有引入新问限
統—验证
验证逛过7
壆所肿发⅜冰线
牡溪修蔗
路认合升/多同
问经报表、预茶率、失败梓本、
误报看报持续回流，优化现别。Prompt、
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 013

核心原则
存量修复和增量拦截必须同时推进，不能二选一
双轨并进
自动化级别必须按照风险等级进行分层，而不是一刀
风险分层
切
2
职责明确
规则和变更检测负责发现问题，AI负责针对规则清
晰、边界明确且可验证的问题进行处理，流水线负责
验证结果，owner 负责最终风险决策
3
回流优化
所有成功和失败结果都要回流，持续优化规则、
Prompt 和策略
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 014

12
存量修复：持续偿还历史问题
Qcon
InfoQ 极客传媒
全球软件开发大会

## Page 015

从扫描到合入的全流程
流水线验证
Sonar 扫描
MR 创建后，会自动执行一系列如编译、单测、
MR 合并后，会自动执行 Sonar扫描，获取应用
lint 等流水线来验证，等待应用 owner 来合并
最新的问题数
躕译梅鍷
代码质量扫搭
13:28 ID:57985345
19:90 0:57338346
代码质量扫描-最新代码..
06:38 |D: 57966943
BUG
瓜险
早味
AI 修复
当应用达到修复阈值时，触发自动修复的流水线，
让AI使用lint 工具并结合修复的要求进行全量修
复，最后提交变更并创建 MR，通知应用 owner
去 review 与合并
acon
InfoQ 极客传媒
全球软件开发大会

## Page 016

• 对应用进行选择性修复
扫描常态化，修复选择性触发
持续扫描
报表汇总
每个应用在MR 合并后都会自动跑 Sonar，获取
按应用等级、部门、问题严重程度等不同维度进行
最新的所有问题
汇总，直观看到债务的分布情况
owner 把关
阈值触发修复
应用的 owner 是最后一道门槛，需要人工的确认
当应用达到修复的阈值时，才会执行修复的流水线
kratos kratos lint自动修复
运行状态
持续时间 3分钟43秒
con
InfoQ 极客传媒
全球软件开发大会

## Page 017

AI 的介入与约束
AI 修复循环
MR 流水线验证
2
下载 prompt 作为修复的要求和约束，使用
MR 自动触发编译、单测、lint等流水线验证
lint 工具获取问题，逐项修复并再次使用lint
AI 的修复
工具验证，直至问题清零，最后提交变更创建
MR
1
4
Prompt 与 lint 工具
人工最终决策
prompt 写清楚修复的详细步骤、规则策略、
创建 MR后会通知应用 ower，应用 owner
修改边界，工具用于发现问题同时验证AI 的
负责最终决策（是否合并）
修复是否有效（解决了原有的问题，以及没有
AI 在约束下完成修
引入新问题）
复，并通过流水线验证
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 018

• 存量修复的效果：季度下降90%
过去半年内单个大部门下部分业务的代码异味的变化趋势
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 019

增量拦截：把新问题拦在主干之
外
acon
InfoQ 极客传媒
全球软件开发大会

## Page 020

•增量拦截整体链路
Al 并非替代原有CI流程，而是对它的补充和增强
1
2
3
4
5
！
？
常规流水线
AI 能力流水线
结果汇总
研发修复或跳过
owner 决策
包含编译、单测、lint
Code Review、单元测
汇总所有流水线的结
研发根据上述结果对
应用 owner 根据流水线
等基础能力，也可能包
试补充、接口测试补充
果，根据每个任务的要
MR 进行修改或略过
的结论确定是否合并
含接口测试等更长链路
等
求和状态对 MR 给出放
的验证
行或阻塞的结论
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 021

Al Code Review：传统 lint 的有效补充
1
从编写 linter 到构建自然语言规则
3
从需求视角切入：代码审查的另一面
传统 linter往往需要先把经验固化成明确规
很多代码问题并不体现在语法、风格或局部实
则，再交给工具执行；这意味着只有“能被形
现上，而体现在“代码是否真正满足需求”。AI
式化表达的问题”才能被稳定识别。Al Code
Code Review 不仅可以检查实现质量，还可
Review 带来的变化是，可以直接用自然语言
以进一步对照需求描述、接口约束和预期行
描述审查意图，将原本难以规则化的经验、
为，判断实现是否存在遗漏、偏差或误解。也
规范和风险判断转化为可执行的审查能力，
就是说，代码审查不仅是看“写得对不对”，也
从而显著降低规则编写与维护成本。
是看“做得是不是用户真正想要的”。
Al Code
Review
2
结合代码上下文，输出高置信度审查结论
4
构建数据闭环，形成持续演进的审查飞轮
相比仅基于单行代码或局部模式匹配的检查
Al Code Review 的效果并不是一次性确定
方式，AI可以结合函数、模块、调用链乃至
的，而是可以在使用过程中持续优化。通过
变更意图理解代码。这样的上下文感知能
沉淀审查结果、人工反馈、误报分析和问题
力，使它更有机会识别真实问题、降低无效
归因，可以不断迭代提示词、策略和样本数
告警，并输出更接近人工审查判断的结论，
据，逐步提升问题识别能力与结论质量。随
让审查结果真正具备可用性和参考价值。
着数据积累与反馈回流，系统会形成一个持
续增强的审查飞轮。
Qcon
InfoQ 极客传媒
全球软件开发大会

## Page 022

Al Code Review：自然语言维护的审查规则
［］热更新配置时，必须反序别忆到创建经要低羽象，再原子替換指汁。漿止对已有配置时象重复 Urmsanal公号致 slice 内 ouruct 宗段 morge而幸獲造。
×器鬆模式：加铁＋原地更新（morge 问通依依行在）go nu.Locks） tonl.Decode （nenC.enf18,SexistsngCont）2/ merge, 1日亨致值液比帮 mu.UnLock（I
国安全报式：
西附配道
GC-CONFIG-
qDang
每次创理对總，然后陳子營教：gD vr neaConf Config ioml.DocadeifncwToml, Brxcw.Con引 /i&对效，常值月验，不会 marge
mu.Locki） cont - newCorf I聚体器茨mu.UnlockC
-更：用atonic.Pointer［无做读）
no var corlPir aicmic.Ponter ton ignewcont = 2coniztoml.Dscods/ncwlcmi,newtonsconiPar.Storcfnewconf
芝
盒食仅a,user -： swsusero: feturn user.llane!ser感供用usen
kr u:usen, ern：= getuseriioif it err ！-nilsretrn er
上 源巨恒必录包含er井忽路才瀬足比3，如无arr影！不滿足皮规則
60-
［］景西在循坏中开后/交事好？
效熬窪愦造询
DATARASE-
00 00an
×盟表指出：1or《tx.Beginll； ...：tx.commit6）》
006
园安全搜式：在循环外开后一个大事务
鼓罴路餾直询
∞0g0ang
×幫類指式：UPDATL 1arge.table SeT fietd= 1太分批
007
图农全保式：分批班新，每北1000-5000条）
5o-
日是否在goroutine码弱修改外都的mop/sice/（变量，且元同歹保护？
JAIARACE。
X帮州模式：g go funcl½ 4 sharedfaolkey」- valac ｝0］1/ 并发写go furcll f snarcoStice - prpcnd［shoredS1ice, iten） J01 1/ 井发oppend go fune！） & counter++ H）！/ 井修改变量
：8o gning
图安全果式：go mu.Locki½sharedvop ［key］ - value mu.Unlocki）// 或使用sync.Nop.atcaica
日是否在goroutine中直授使用貓环进代变量？（C8-1.22）
∞o gdang
×富食仅式：foritom： rango itos L go funcl） L uselito
•@0 1.224已修無此同認
麩%苑于Race
co gdsng
×茶多板式：Tunc process（wn sync,WaitGroup）//值传溫会搭美
好出 u：tunc proceciva wsync.Nostbraup］/r）
人青含损定.vaL ：= data.stringfa不wpanc
co1
式：wal ok ：= cata.cstrina）： 1f ok retum ern
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 023

AI Code Review：增量拦截的分层处理
asilc @ogilc:2 wccks ogo
〝AI CodeReview 报告
agile @agile started a thread on an old version of the dilt 2 weeks ago
• Hide thread
原advisor AI Rovinw功能已注移至agileflaw，功能介绍 info，有任何票成/问豚调跃票心火羽白
app/service/pantheon/internal/service/common/company/tencent.go 应
审查通过，剩余9个问题待处理
423
log.Errorclctx，
"（TxLiveLink4idasToken! call TxLiveLinkStoreUrtParams err, req:ewv.
1. 审查任务进度（0aacb8f9）【进度查者】
rea. ern
return
432
433
actIdstr ：= strconv.FormatInt （storelrLParamsResp.ActId,18）
434
435
cxtranca：= modc t.JxbindlntoExtrakcaf
436
TXACtID:acticstr，
2. 审查结果
437
TScene.
438
•重点关注问题【规则查看】
439
bindAddress, err ：= s.GetBindAddress（ctx，&vlpb.GetBindAddressReaf
440
B12code：
reg.B12Codc，
441
uid：.
Fe9-Uid.
文件
何忍描遂
产要级烈
命中规期
状态
442
Ext raReo: utils.JsonMershaLIgnoreErrlextraReg），
443
｝.conf）
app/service/panthaonjinternal/daojc
URL解析错设后仍使用
GO-PANIC-002
444
if err ！=nilC
成动日志打印完整请來体
醬已的决
agile @aglle 2 weeks ago
Maintiner：
lient.t.go
【 已解决】忽略错误后继续解引用（高危）（GO-PANIC-002）
app/service/panthecnjinternal/servi
忽路铠讽后爆矮解引用
亮危
CO-PANIC-002
己肝决
ce/ccmmcn/company/tencent.go
问题描述
apo/service/pantheon/internal/servi
忘频跸径打印完鬯委数
中危
CO-RESOURCE-004
@已艇决
1.具体问题点及位買：在1encent.go第444-453行，GelBindAddress返回 err 后仅记录日志未返四，随后直接汤问
bindAddress.Livelink.Sign/Code/Timestamp 等子段。
2.影响范田：当 GotBindAddross失败返回的Livelink为空时，该链路会在生成params时触发空指针panic，影响
3.总体评价
TxLiveLinkMidesToken 接口稳定性，
3.风险深估：高风险，城上请水在异常配置或下游失败场景下可直接所溃当前请求处理流程。
蒂求实现
修复建议
区 新增米，大师tokan查询按口
•& 开故平台新造盗权入口
GetBindAddress 这回错误时应立即这回；并在使用 bindAddress/Livelink前培加 nil核验，避免对空指针取字段。
o bind.bn.ge: LiveLinh!idasToken ~HTTP 銘由定义
Editec by agle 2 weeks ago
• servar.go:Nev: PathBinaLiveLankfidasToken 避权注入
•& 调用水大师并返回token
• service,bind.v2.00:LiveLinkHidasTokenbindLink 解析与 Pantheon 鋼用
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 024

AI Code Review：持续迭代与优化
MR总数
问题总数
洖报盏
暂不处理数
已解决数
准确率
281
1,124
168
547
387
85%
描述
仓库
文件
commit_sha
MRID
类型
问题状态
核验状态
修复备份字节未判空
operation-data-plat...
OpenclawDomain...
89f9320c
135
空指针
符解决
• 未复核、
异常日志链式调用NPE
operation-data-plat...
OpenclawDomaln..
89f9320c
135
空指针
已解决
• 未复核
硬编码SYSTEM绕过鉴权
game-providence-S•
OrderCommandS..
cce25396
11
安全
待解决
• 未复核
+
外部结果可能返回null
go-bdjs
processor_archiv..
dfa27716
19673
结构体岑段变更
• 未复核
+
外部结果字段可能由仔变null
go-bdis
processor_archiv..
gfd71df3
19673
结构体字段变更
待解决
• 未复核
+
末检查的类型断言
go-ott
view_history.go
e223dd79
7487
panic
巴解决
•未复核
未检查的类型断言
9O-0tt
view_history:g0
a603119d
7487
panic
已解扶
• 未复核、
高频路径Info日志
go-operational
guess.go
766095ea
3082
资源泄露
己豚涋
• 未复核、
循环内错误日志可能刷屏
go-operational
reserve_counterg.
766095ea
3082
资源泄露
已解决
• 未复核
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 025

AI 补充单元测试：围绕MR变更函数的自动生成与修复
远端存储
存在
下载
target func
AST+LSP
变更后的
一不存在-
*ait
先编译成二进制，用
MR diff
prompt
•AI
est.go
-tag区分不同的文件.》|
避免互相干枕
code base
downstream
>
一修复编译问题
人工确认，后续回流优化-一
执行测试
V
第二轮
让 AI 结合完整 code
让 AI 结合分析好的上下
分析结
base，对第一轮分析结果
第一轮
文，对失败的 case 进行归
果
中再次分析，去除无效
分析结
-因，去除非代码问题导致的
测试结果
case
果
失败 case（如环境依赖、
框架等）
- 保存有效 case
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 026

Al 补充单元测试：结果输出与报告
kerdls&= |
no-teyuaich. amos:smamenodnsiolncsmnet..mnd.
oseel e:otns
cudpmnfeccad 4v200e7wwww88oerece.comor satv a_t1e032
#en:Somnrt/harvcescrvc:/tud.m:nfsctmd. 44628:c367880c888 Savce cnon cd.n. 1：.g026
irewrrsamos/dthihmr/oyntonce/recseyS, Ansrtemrs/ko/te i5：.J23%
不仅生成单测，还把生成结果变成可审计、可量化、可回看的报告
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 027

•AI 补充单元测试：试点效果展示
MR总数
变更函数数量
覆盖率
145
2,580
84.9%
Case总数
成功Case数
失败Case数
异常Case数
13,719
13,246
348
125
AI标注有效Case
人工标注有效Case
人工标注无效Case
正确率
28
12
10
54.5%
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 028

•
AI 补充接口测试：覆盖率驱动的迭代闭环
围绕覆盖率盲区自动生成测试用例，使用基于 mock 的回放工具通过回放发现缺失
mock，并按协议逐条修复，持续提升目标接口覆盖率。
AI Agent 生民新的新试用的
构造测试用例
使用泰干 woeke 的追就工具进行四放数保
结合接口的源码、调用链路和覆盖详情，让AI设计测试用例以最大程度覆盖当前未覆盖
的链路，明确测试场景、输入参数、预期响应和预期下游调用（包含MySQL、Redis、
HTTP、gRPC等）。
存克 mod 請演？
持续回放验证与 mock 修复
先通过回放执行，发现缺失 mock，按顺序修复，一次只修一条（避免级联问题）；再持
续通过回放执行来验证修复是否正确，如果有问题，则基于源码、预期等内容修改
AI Agent 生n moce.報传算
mock，或 bypass 带有时间戳、随机值等内容的下游调用
数据链路复盘与差异对比
陘盖平迟际踬还野
当 mock 问题均已修复，对比接口的实际响应与预期响应是否一致，如果不一致则根据
日志进行数据链路复盘，对比整体接口和每一处下游调用是否一致，最后交由人工确认
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 029

•AI 补充接口测试：试点效果展示
场景：Startlive happy path-合法参数开播（android 平台，竖屏，普通直播类型）
StantLive（streaming.go:L38 L60）-福盖率50%
fakeCommand.SceneNeedFaketommand -HIT
请求参数：
facadeStartLive.BlinkStartLive Cfacadestant_Live.go:L54-L120）一覆盖率18%
method: PosI
FixRawParams
HIT（通过）
path:/live.streaming.Streaming/StartLive
BuildStartLiveLocatorFromRequest - HIT
RawParamsCheckHIT（迪过）
headers：
applicationstartLive.BLinkStartLive （application_start_Live.go:L48-L144）-溫盖率
14%
：authority: 127.0.0.1:9000
LoadRoomAggregateloLoc HIT（成功）
：method: PosT
GetRoomAggnegate - HIT（成功，返回
uid=8522261）
：path: /live.streaming.Streaming/Startlive
LoadStreamMngToLoc- HIT
：scheme:http
startLiveRoomstatusCheck - HIT（失败|uid 不匹配）
content-type: application/grpc
L IsRoomBeLongToMid （10001）+8522261 + ErpUnauthorized
te:trailers
未覆盖：LoadMemberAggregateToLoc（L69）
body （protoscope）：
未 盖：checkSpeclgLTypeRoom （L77）
1:10991
未沼蓋：
staptLiveLock（L105）
一未覆盖：BlinkStartLiveCheck CL119） 149
uncoy Lines
2:Wandroid"！
末覆盖：
StartLivebetUpStreamInfo（L126）
3:33
未覆盖：blinkStartliveComnand （L139）- 59 uncov 1ines
15： ｛1: 10001 2：
［192.168.1.1"｝
朱覆盖：setRoomStatusStartLive
-59 uncov Lines
BuildStartLiveResponse
HIT（错误处理）
预期响应：
未覆盖分支：resp=nil && err=nil（L42-44）
status_code: 200
grpc-status:0
关键未覆蓋节点（按
uncovered_Line 降序）：
body：包含
stat / Live_ key /rtmp 等字段
1. BlinkstartLiveCheck - 149 uncov Lines
2.
MemberCheck - 72 uncov Lines
3.
BLinkstartLive（app） - 62 uncov Lines
预期下游调用：
GalaRiskeheck - 62 uncov Lines
［Redis］
fake_command 查询 返回不需要fake
5，
RoomCheck - 62 uncoy Lines
LMySOL］
room_status 查询•返回房间状态
6.
blinkstartLiveCommand - 59 uncov Lines
［gRPC］ room/member 聚合查询，返回房间和用户信息
7.
setRoonStatusStartLive - 59 uncov lines
［MyS0L］ Live_record/flow_necord 写入，成功
Acguire （oistriboted_Lock）
5l uncov Lines
Qcon
InfoQ 极客传媒
全球软件开发大会

## Page 030

总结与展望
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 031

总结
技术债治理不是一次专项，而是一条持续运行的工程
流水线。
持续运行
存量修复负责偿还旧账，增量拦截负责止损，两条轨
双轨并进
道缺一不可。
2
验证优先
真正決定上限的不是模型，而是问题选择、风险边界
和验证链路。
3
先建立信任
AI 只有进入工程系统并被验证、分层、兜底，才会变
成稳定生产力。
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 032

• 局限与挑战
当前局限
现实挑战
- 存量修复目前仅覆盖部分低风险规则类型
- MR 合并效率仍影响自动修复闭环的最终
- AI 补充单测和接口测试仍处于小规模试点
效果
阶段
-覆盖率提升依赖稳定环境、mock 质量和
运行链路
一模型成本、上下文长度和执行性能仍需持
续优化
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 033

• 落地方法论
先证明局部成立，再做平台化扩张
阶段四
阶段三
平台化扩张
逐步扩大规则覆盖、仓库范围和
阶段二
双轨打通
自动化级别。
阶段一
把增量拦截接入 MR 流程，形成
跑通局部闭环
“偿还＋止损”的联动机制。
在少量仓库验证扫描、修复、验
选一类问题
证、合入的完整流程。
规则清晰、验证充分、风险低，
是最好的起点。
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 034

InfoQ极客传媒
QCon
全球软件开发大会
THANKS
大模型正在重新定义软件
Large Language Model Is Redefining The Software

## Page 035

上
探索 AI 应用边界
AiCon
acon
Explore the limits of Al applications
全球人工智能开发与应用大会
2026年6月26-27日/上海张江科学会堂
专题：世界模型与多模态智能突破
专题：Agent 系统架构与工程化实践
专题出品人：朱政
专题出品人：鲁洁楠
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
快手/研发效能负责人
EverMind/ CEO
