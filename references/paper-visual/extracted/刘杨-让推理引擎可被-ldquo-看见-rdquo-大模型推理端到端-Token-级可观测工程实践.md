# 让推理引擎可被“看见”：大模型推理端到端 Token 级可观测工程实践

- Source PDF: `references/papers/刘杨-让推理引擎可被&ldquo;看见&rdquo;：大模型推理端到端 Token 级可观测工程实践.pdf`
- Visual pages: `references/paper-visual/images/刘杨-让推理引擎可被-ldquo-看见-rdquo-大模型推理端到端-Token-级可观测工程实践/`
- Extraction mode: visual page-by-page information extraction
- Page count: 40

## Page 001

InfoO 极客传媒
QCon
全球软件开发大会
让推理引擎可被“看见"
大模型推理端到端Token级可观测工程实践
刘杨
蚂蚁集团可观测架构师

## Page 002

极客邦科技 2026 年会议规划
促进软件开发及相关领域知识与创新的传播
06月9上海
R 1000人
08月9深圳
281000人
AiCon
•Al Infra 系统工程
AiCon
•Agentic A！
•多 Agent 协作与实践
•轻壘化与高效推理
全球人工智能开发与应用大会
•多模态熟合
•多模态应用
•模型训练与推理创新
全球人工智能开发与应用大会
•Al+ IoT 场景实践
会议时间：6月26-27日
•数据平台与特征服务
会议时间：8月21-22日
•AI 工业化落地
◎10月9上海
2 1200人
012月？北京
R1000人
•Al Agent
acon
•Vibe Coding
AiCon
•大模型架构创新
•智能可观測
•多模态 Al 产业融合
全球软件开发大会
推理基建
全球人工智能开发与应用大会
•具身智能
•模型攻防
•Al for Science
会议时间：10月22-24日
•AI x创造力
会议时间：12月18-19日
*大模型安全

## Page 003

InfoQ 极客传媒
acon
全球软件开发大会
O1
推理全链路可观测体系
02
传统Trace的局限
Token为中心的可观测方案
目录
04
经典案例
（05
社区贡献与展望
06
QA

## Page 004

推理全链路可观测体系
acon
InfoQ 极客传媒
全球软件开发大会

## Page 005

总览
以推理为核心的统一观测解决方案
推理云服务
丨推理云核心组件全覆羞
AI应用
多语言跨协议端到端链路追踪
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 006

推理云服务：混合云架构•核心组件覆盖
推理混合云架构
蚂蚁主蛄
推理核心组件监控覆盖
Metrics
Logs
Traces
网关/模型服务层
E AntCollector （DaemonSet）
AIGW
ModelService
引擎层（多种部著架构）
otlp
蚂蚁主站
单机
PD分离
DataGW
清洗•转換•聚合
CeresDB/SLS每
基础设施屋
otlp
存储/KV Pool
云网络组件
蚂蚁其他站点
4 通算CPU系统指标
•I 智算XPU系统指标
Metrics
Traces
日 AntCollector （DaemonSet）
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 007

推理云服务：标准化-统一口径•消除孤岛
62 统计/链路指标标准化 一核心性能指标
TTFT
TPOT
E2E
I
Time to First Token
Time Per Qutput Token
End-to-End Latency
• 规范统一收益 —打破数据孤
首 Token 延迟
单 Token 生成时间
端到端时延
用户等待体验核心指标
流式输出流畅度指标
全链路服务质量指标
统计&链路指标规范
覆蓋排队＋ Prefill 计算
Decode + KV Cache 效率
网络＋排队＋推理全覆蓋
L 精准 FO3
P99
AVG
SLA
撑造化指标为引擎实例/AIGW节点故障自愈提供决策合
基于接队效/TPOT 等弹性策略，实现资源按需使用
V 严格成功率—超越 HTTP 200
SRE 与业务方共享同一视角，全平台横向对出
非严格成功的异常类型：
RequestEror
请求失败
EmptyOutput
模型输出为空
ErrorCode>80%
乱码超阈值
Repeat>80%
重复超 值
TTFT/TPOT
延迟超阈值
Qcon
InfoQ 极客传媒
全球软件开发大会

## Page 008

Al应用：端到端分布式追踪
端到端推理链路
Client
Ap
AIG
Engine
SOFA O1el协议 射
SOFATFaC
SOFPIraG
d.
OTel 原生链路
② request_id 精准关联
异构协议串联
多语言接入
解决问题
解决问题
接入策略
单 Traceld 关联多笔推理请求时的精准定位
SOFATracer 与 OpenTelemetry 两种协议 Span串联
日志转 Span+原生 OTLP 并行，按场景选择
• AIGW 生成全局唯一ID
• SOFA-Traceld - Parent-Traceld
Java
SOFATracer 日志 AntCollector Span
• 下游组件日志+Span 统一透传
• SOFA-Rpcld Parent-Rpcld 映射
Go
原生 OTLP
• 监控指标 •链路详情一键跳转
• 查询时自动扫描跨协议关联
Python
原生OTLP
打通指标一明细一Trace 充整闭环
双向可追汤，语义一致性県障
渐进式 OTel 覆盖•最终全链路统一
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 009

产品效果：指标下探Trace，
快速定界
AIGW视角推理服务统计指
严格成功率（%） 终计
【采祥！！】非 格成功的Traceld明
Valce•平均售司
Value •最太備？
Valve 會最小镇
非芦樯烗功僚圄
I00
21d22.
TTFT破线
引擎黑洞？
单Trace链路
m Frelein.nGim
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 010

传统Trace的局限
Token生产不可见
Qcon
InfoQ 极客传媒
全球软件开发大会

## Page 011

• 大模型推理的核心体验指标
T1
Tn
Acc
TTFT
TPOT
精度指标
核心论点
Time To First Token/
Time Per Output Token/
Accuracy Metrics
Key Insight
衡量大模型服务
首字响应时间
每Token平均输出时间
回答好不好
性能看Token速度，质量看
用户等多久看到第一个字输出
后续字输出快不快，有无卡顿
答非所问/乱码/复读等异常
Token分布与选择
Qcon
InfoQ 极客传媒
全球软件开发大会

## Page 012

性能异常：请求变慢，慢在哪
大盘指标
BEEY
无细粒康數据
BEEP
整个请求慢在哪里？
性能问题的难点
T557
请求延迟高
单个请求的Token生成时间线
麸乏肚粒隆＆
硤乏Token可视
Token
引擎黑盒
缓慢 缀馒
传统Trace到请求粒度截止，而回复是由Token构成，
逐次吐出来
PyTorch Profiler输出栈
〇00
cvess （Pytorthfroetter（CathT8.4l）
（整个请求变慢了10倍，但不知道慢在哪些Token！
并发干扰不可见
［Uninownl
［Uninoen！
现有工具只能报告發效性”，却无洗提供
［Unane
保型内部无理開
Token级的延退细分。无法精确定位瓶颈Tokeno
不知道本请求被谁阻塞、怎么阻塞，大请求对小请求的
拖累完全不透明
全源湿挺记异常，
但没有具体
Token分鮮，无法
短道具体源颈！！
关键拆解：慢在哪些Token 其他请求的干扰
Qcon
InfoQ 极客传媒
全球软件开发大会

## Page 013

• 精度难题：答非所问、乱码、复读
为什么精度问题难排查？
又来了！
随机性导致不可复现
同一Prompt，两次调用可能结果迥异，无法稳定复现
当然当然当然⋯
到底是哪里..
错误从某Token蔓延
一旦某Token出错，后续Token受其影响，像多米诺效应
采样参数是黑手
Temperature过高一乱码，过低一复读；错误参数隐匿其中
参数都试遍了！
BOS等特妹Token不显示
wmperature
peraity？
特殊Token在网关/引擎日志里面不显示
模型PKL文件？
关键需求：每个Token的概率分布是怎样的
Qcon
InfoQ 极客传媒
全球软件开发大会

## Page 014

归根结底是
Token生产的问题
性能异常
并发退化
精度异常
某些Token生产耗时过长
Token粒度上相互争抢
某个Token被错误选中
以Token为中心的引擎可观测
Qcon
InfoQ 极客传媒
全球软件开发大会

## Page 015

我们的愿景
打造一款"显微镜"
下探到Token粒度，透视引擎内部的每一个细节
让延迟与精度问题无处遁形
Qcon
InfoQ 极客传媒
全球软件开发大会

## Page 016

Token为中心可观测方案
acon
InfoQ 极客传媒
全球软件开发大会

## Page 017

核心技术挑战
1
3
恰当的数据采集
复杂异构环境适配
低性能开销要求
•深入理解引擎调度逻辑，结合业务
，三大引擎/三种Al硬件/多种部署架
，硬件昂贵，不能影响吞吐，也不能
场景精选关键数据
构/复杂并行与多样调度策略
影响TTFT/TPOT等体验指标
•粒度太粗无法定位Token级问题；
，必须深入理解AIInfra各层细节，
•生产问题难以线下复现，必须实时
太细则存储与性能开销爆炸
逐一适配采集逻辑
在线大规模采集
•需精准平衡数据粒度与采集成本，
，最终输出统一标准的可观测数据
•为还原请求间相互干扰，不能做采
有效刻画影响性能的关键因素
样，需全量采集
核心矛盾：既要深入引擎内部获取Token级精细数据，又要在复杂异构环境中保持极致低开销的实时在线全量采集
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 018

• 恰当的数据采集：推理引擎迭代循环
选取请求，组成批次
①
从等待队列中挑选请求，组成本次迭代的batch
推理引擎的无限迭代循环
1.选取请求，组成批次
批量执行处理
2
GPU上执行一次forward
4.进入下一选代，
循环往复
每个请求生成一个Token
3
Sampler从logits中采样，输出一个Token
无限循环
进入下一迭代，循环往复
4
回到步骤1，直到所有请求完成生成
2.批量执行处理
核心挑战
每次选代的batch组成不同，请求间干扰模式不同，定位极难
13.每个请求生成一个Token
Qcon
InfoQ：
极客传媒
全球软件开发大会

## Page 019

• 恰当的数据采集：在粒度与开销之间精准平衡
请求级 （Request） 传统Trace已支持
Token级 （Token） 我们采集到这里
阶段级（Phase：预处理/排队/KVCache/模型forward）— 我们采集到这里
层级（Layer: Attention / MLP / MOE）（不采集）
Kernel级（CUDA Kernel）（不采集）
太粗（仅请求级）
太细（到Kernel级）
我们的选择
无法回答Token级问题，精度问题/并发干
存储开销爆炸，在线采集不现实，影响推理
仅采集Token粒度及其子阶段数据
扰无从排查
性能
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 020

• 恰当的数据采集：Token粒度性能关键数据
分类
指标
口径
解决什么问题
Token
进迭代时刻
请求被调度到引擎迭代的时间
定位调度延迟
维度
出迭代时刻
引擎完成迭代计算，吐出Token的时间
定位计算延迟
Token执行耗时
出迭代时刻 -进迭代时刻
真正在迭代里的执行耗时
Token调度时延
当前Token进迭代-上个Token出迭代
捕获Decode被Prefill中断等场景
Token总耗时
当前Token出迭代-上个Token出迭代
用户实际感知的Token产出耗时
执行批
并发请求数
迭代执行批的请求数
粗略刻画迭代负载
维度
并发Token总数
选代执行批Token数目
精确刻画算力/显存带宽需求
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 021

异构挑战：多硬件 × 多引擎 X 多部署架构
应用
应用层
灵光
码小影
灵光，嗣福，码小財
標一AIM关
AIGW
了 网关与模型服务
模型服务
AIGW -> ModelService
OWEN3 Service
DeopSeck-Rt
DeepSeek-V3 Semice
Balling-Xx Servce
模型实例一异构架构
模型实例-骨松架构
单机实例-多机实例（PD不分离） PD分离实例一*PD大EP实例
单机实例
（PD不分液）
＆𢖯实例
PD分高实州
PD大EP空例
Conductor调度，专家井行EPLB，mP/nD分离
（专京共行EPL.D）
Gonductar
（rcnduoton
mP
POD
mP
* 模型执行一异构引擎
PODX
sglang•TensorRT-LLM，vllm-ascend•vllm
模型执行-异构引擎
1 昇构硬件资源
sglans
TonsorRT-LLM
vim-ascond
wllm
GPU/HPU/XPU/CPU•内存/显存/SSD•显卡间带宽，网卡通信带宽
弄构硬件资源
cpunpu/xpucpu
内存/显存/SSD
内存/显存（最卡间带宽
网卡通信带炎
可观测性必须跨引擎、跨硬件、跨部署模式统一
Qcon
InfoQ 极客传媒
全球软件开发大会

## Page 022

• 低性能开销：技术方案选择
推理引擎
以WLM为0
API Server
AP Sarve
Requestin
ULM
］
无侵入探针方案（未选）
Engne
无法获取引擎内部Token粒度上下文
Engnargs
AsyrctLMengme
LLMEngme
引擎迭代快，Hook函数签名可能变化，维护成本较高
cumum
性能不占优势，友商实践百分点开销
Schedier
Waitino
Runcine
KV Coche Monsger
Swapped
Henpcnse
Gonfg
侵入式直接埋点（我们的选择）
Model Config
woeker
Exeotcr
Cache Confs
直接获取引擎内部丰富上下文
norke
Token粒度精确数据
Ceche Engmee
同步维护引擎代码，稳定可靠
worker
wodervekght
黄色部分为埋点组件，核心执行层基本无侵入，埋点主要集中在API/调度层，最大限度减少性能影响
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 023

•低性能开销：极致优化-千分点损失
A 挑战：768高并发压测下，开启Token粒度可观测后TTFT增长10%＋
对于推理服务，10%的TTFT增长意味着用户体验的明显下降一这是不可接受的
四大优化策略
1
埋点逻辑上移
2 单请求单Trace节点上报
大部分处理放到上层API/调度层，而非引擎核心执行层
Token粒度数据作为属性附着到请求Trace节点
避免在热路径上增加计算开销
避免大量Trace节点上报开销，产品侧后算还原
3 高性能序列化＋批量操作+复用
4 异步批量上报＋完成时上报
json - orjson 替换，数组批量追加避免反复生成新数组
Trace上报批量异步执行，不影响主流程
复用引擎已转换好的detokenize数据
只在请求完成时上报，利用推理服务低QPS特点
TTFT/TPOT千分点损失，吞吐等成本指标无损
生产级大规模运行
推全可观测Trace功能，覆盖vllm-ascend/ sglang / TRT公共服务
大规模实时在线采集，无因可观測功能导致的任何故障及性能问题
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 024

产品方案：引擎显微镜-广角镜VS 高倍镜
从“混沌与盲猜”到”"清晰与精准”
引擎并发剖析（广角镜头）
Before•当前的痛苦
After-使用引擎显微镜后
多轨道瀑布图，清晰呈现引擎所有请求的并发、竞争和协
『角鏡头•井发哥析
作关系，快速识别资源冲突与性能瓶颈。
引擎
引擎
任务设
引擎Token分析（高倍镜）
高倍镜-Token分析
Pres/ PreflToken1 Toeen.2 Token.3
TckenX
FokenY
切换到单个请求角度，观察单Token生成耗时，可视化候
耗时：40ms
选词概率分布，精准定位延迟与精度根源。
黑盒状态：流量洪峰下，性能瓶颈成因不明
透视洞察：井发竞争与Token耗时，一目了然
实例故障？资源竞争？长尾任务？Token生成哪一步住了？
快速定位调度阳寒潆|稿准发观计算缓儍点
业界首个覆盖多引擎、Token级的深度可观测Trace产品，领先业界，独此一家
Qcon
InfoQ 极客传媒
全球软件开发大会

## Page 025

• 产品方案-Token分析：拆解每个Token耗时
核心功能
核心指标
输入/输出/排队/TTFT/TPOT/KVCache传输/预处理
等核心指标
Token执行耗时
每个Token的执行耗时、调度延迟精确到毫秒级
Token执行所在批负载
Token生产所在批的负载情况
关键拆解：拆解到Token，让性能问题定位不盲目
Qcon
InfoQ 极客传媒
全球软件开发大会

## Page 026

产品方案-选词分析：透视每一个Token背后的模型决策
× Token详情：
音乐
$.70mc
造瑪分析属性
透调依据
豊尔联时大于
能看到什么？
0.9
当前被选中的Token
ronetlion_ponaty（防出连续酸意》
prsenca perally（世兌酿复內料）
及其在候选词中的排名
Top候法词假串
Token名聊
Top-K候选词概率分布
青乐
101041
1041
展示前N个候选词的概率值和Token ID
双4
10742
1028
06s0
采样参数展示
vsts
201%
Temperature / Top-P / Repetition-Penalty
等
洞察：模型问题还是采样参数的不合理
Qcon
InfoQ 极客传媒
全球软件开发大会

## Page 027

产品方案-并发瀑布图：可视化多请求并发
• 多轨道瀑布图
•慢请求条件筛选
每条轨道代表一台机器，色块展示请求执行全过程
可按TTFT/TPOT/输入Token数等条件高亮慢请求
1∞s
1038
亮蓝色->Prefill
@
橙色->Decode
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 028

经典案例
真实线上例子
Qcon
InfoQ 极客传媒
全球软件开发大会

## Page 029

案例1:TPOT破线
sglang引擎•非PD分离
TPOT 54.77ms 破线
Token#125 调度耗时 6816ms
用户感知耗时 6.85s
推理引擎单笔请求Token分析 ®
开始时间：
2025-12-0817:38:27484
派态：
皮功
引擎絲型
sglang.
落餐限格：UPD分离
丷关褪指振
引紧井爰动斬
Prafl耗时
Decode耗时
TTFT
TPOT
预炉理
命中/新入Token数
粉出Taken做
排队
KVCache传料
474.00mg
7.298
474.48 ms
54.77ms
0.42 ms
10293/16261
134
4.18ms
0ms
replace alls/arg_keyz
Token生成耗时追踪
共洲透出2个Token，平均用户感！
carg valuezfalses/arg_values
mo
fSTokar
8156
77600
序号
热行联时
饮引发適承数
批井发Tocn数
474.00mgcoogge
$16.20mg
2.50ma
用产路雞證
执行耗时
善询没桥 托时船祈
renlace.alle/sg.xey
126
xag.vsheofaleedfarg.Y
第125个token调度花了6.8秒！！
选湖遊折
再附甜析|
其2条
发现异常：单个Token用户感知耗时高达6.8秒-转到并发视角寻找根因
Qcon
InfoQ 极客传媒
全球软件开发大会

## Page 030

根因：Decode被新请求的Prefill中断
A 请 2的Decode被清求1的Prefi中斷
非PD分离 下Prefill优先级高于Decode
林方案：启用PD分离/调整调度优先级
引擎并发剖析
◎ 帮助文档
分折时间：
2025-12-09 17:3327 - 2025-12-00 17:4327
•模聖服务ID：
•模型实例：
引擎井发瀑布图法：非PD分萬部要紧物，单引學而时好理Pt Decode pafe
docoda
A时分解の：5〇
17-38:17
17:38:19
17:35:22
17:3825
17:3828
17338:31
17:38:33
17:35:36
17:33-39
17:3次42
17:38:45
17:38
请求1
二
，请求2
请求2 decode 被请浓1 prefil 中斷
并发瀑布图揭示的根因
请求1
Prefil（大请求，占用全部计算资源）
大请求Prefil抢占一 Decode被挂起
请求2
坡中山年待 6816ms
Decodels
用户感知到的6.85s中6.8s在等待调度

## Page 031

案例2：答非所问
用户投诉：问的是医疗问题，模型回复了leetcode解题答案
推理引擎Token分析
状2：設坊
传统手段难点
每示拒时大于
me MIcken
0~100m 大5103
EOS/BOS在日志和网关中显示为“
P节点
没有Token分析，根本无法发现这个关键信号
東号
137233m6
推理引擎Token分析
开始时：20Q5-10.2815.50.04
模型報多后
特时5214
最大鞋到：80.50ms（第5个1060）
辅出Tckal题：111
號入Tskent：
810
D节点
定界
10ke数：111
平均尾时：44.0me
P节点，首Token是end_of_sentence
•D节点、
吐出Token是begin_of_sentence
s1bohd_samod
24830mc
70.70ms
BOS出现= 后续回答与Prompt完全无关
78.5cme
20.ms
Qcon
P节点输出了EOS，导致D节点认为请求结束，输出BOS，开启新的句子。
InfoQ
极客传媒
全球软件开发大会

## Page 032

深入：P节点为什么吐出EOS
× Token洋情：
< lend_of_sentence |> 370.10ms
选闪分析
閣性
访词依器
remperatiuro
［生成习机蛙》
便造 数量上双：
（襁选浸紫积概芈】
现象
froguency_penalty｛其制高效w
选中了第四位Token，不是前三
〈防止连续重築）
（混免重雲内容）
1.1
模型问题
Top候透词摄串
EOS概率高达10%，后续也确认是模型badcase
批序
TckenID
当肣选磋
<1 and_ot_acntaroel
1413
不低的发生概率
拟竅
3696
大概10%的发生概率
45%2
-
13.14%
•onolaantonsav
-
10.23%
缓解手段：控制采样參数，尽量选择概率靠前的候选Token。
Qcon
InfoQ 极客传媒
全球软件开发大会

## Page 033

案例3：小请求TTFT破线
#输入Token 700+
IIFT 7S+
首Token调度等待 2.25s
调度后执行耗时 4.88s（正常应<500ms）
Pretll耗时
Decode耗时
TTFT
TPOT
預处理C
命中/物入Token数
输出Token数
排队
7.13 s
1.06s
7.13 ：
353.85 ms
21.45 ms
128/726
4
0.03ma
UNC
Token生成耗时追踪
68342
3224
TToken，平均用户感知 时为353.85ms
用户悠知耗时大于
100
TokeniD
批井茇谓求数
批井发Token敬
序号
Tokon名称
执行耗时|
用户感知授时 ◎
7.134
2254.00ms
4.885
引擎耗时|
oretill
用户感知捲时
7133ms
引綮耗时
會宿耗时刻析
decode
1.069
FRT
① 发现异常：最后一次prefil所在执行批总共3224 tokens，耗时却高达4,88秒！
怀疑：虽然只有700个token，但是可能chunked prefi执行了两次。
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 034

并发瀑布图：9.6万Token长请求独占引擎
4 长请求96564 token，独占5次Prefil
其他请求全部在等待调度
？ 大清求結束后问题自动恢复
15:27:17
15:27:19
15:27:20
15:27:21
15:27:22
15:27:23
15:27:24
15:27:28
15:27:27
15:27:28
15:27:29
2
庖丁解牛：Prefil打包机制导致TTFT膨胀
先验知识：引擎每次Prefill最多执行16384个token
长请求5（96564）
Prefil 1 Preti#2
2#3#4¥5
Pretil#6（14644+4其1）
Prefill#7
异常造或4（700+）
在#6中坡打包执行～4.545
TII I
Prefill#6打包多请求拉满16384 token一耗时4540ms,Prefil#7仅336ms
异常请求在#6＋#7两次执行、总计（4540+336）=4876ms
结论：等待2.25s+被大batch打包执行4.888=TTFT 7s+
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 035

三个案例，三种典型根因
Case l
Case 2
Case 3
性能问题：TPOT破线
精度异常：答非所问
性能难题：TTFT异常
Q 现象
Q 现象
Q 现象
Token#125调度耗时6816ms
医疗问题回复leetcode答案
700 token请求TTFT 7s+
用户感知6.85s vs TPOT 54ms
日志和网关中看不到异常
调度2.25s+执行4.88s
根因
母根
母 根因
非PD分离架构下
首Token为BOS（begin_of_sentence）
96K token长请求独占5次Prefill
大请求Prefill抢占Decode
后续打包batch拉满16384 token
方案
方案
方案
启用PD分离架构
修复PD流水线EOS处理逻辑
长请求隔离
定位工具
定位工具
定攸工具
Token分析 + 井发漯布图
Token分析+选词概率分布
Token分析+井发瀑布图
9 共同点：传统监控工具无法发现这些根因，引擎显微镜从Token级精准定位
定位模式统一：统计指标异常 Token级异常发现 一并发视角根因定位
从“黑盒猜测”到”透视定位”，平均定位时间从小时级缩短到分钟级
Qcon
InfoQ 极客传媒
全球软件开发大会

## Page 036

社区贡献与展望
Qcon
InfoQ 极客传媒
全球软件开发大会

## Page 037

• 社区贡献：统一三大引擎可观测Trace标准
10+
2000+
3
提交PR数
代码变更行
开源引擎覆盖
合入10+个
跨三大引擎
VLLM/SGLang/TRT
SGLang
与阿里云共建，贡献Trace可观测能力，对齐VLLM/TRT，形成统一标准
VLLM
贡献Trace可观测能力
TensorRT
贡献Trace可观测能力，以及可观测指标
-LLM
2026年将持续同合作伙伴一起将内部优秀经验回馈社区，拓展在AI推理可观测领域的社区影响力
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 038

展望
愿景：让每一次推理请求都可追踪、可诊断、可优化
O1 Profiling
02
智能诊断
Attention / MLP / 卡间通信 分层追踪
Al自动识别延迟模武并推荐优化方案
基于历史案例库的智能根因匹配
从Token级下钻到算子级
从"人工分析"到"AI辅助诊断"
03
Talk to Engine
04|
实时告警
动态hook进程方法，暴露类arthas工具
基于Token级指标的异常自动检测
提供合适context
调度延迟/ Prefill抢占/重复输出 实时告營
基于Al Agent进行自然语言诊断与性能分析
从“事后分析/用户反馈*到“实时感知/主动监控”
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 039

InfoQ 极客传媒
QCon
全球软件开发大会
THANKS
大模型正在重新定义软件
Large Language Model Is Redefining The
Software

## Page 040

探索 AI 应用边界
AiCon
Explore the limits of Al applications
全球人工智能开发与应用大会
2026年6月26-27日/上海张江科学会堂
专题：世界模型与多模态智能突破
专题：Agent 系统架构与工程化实践
专题出品人：未政
专题出品人：鲁浩楠
极佳视界/联合创始人&首席科学家
OPPO /大模型 法员责人
专题：AI 原生数据工程
专题：Agent 安全、评测与可信治理
专题出品人：王彦辉
专题出品人：马传雷（岳立）
火山引擎/数智平合产品总监
支付宝 /业务风险技术部员责人
专题：Agent 数据、记忆与运行时
专题：企业级研发体系的重构
基础设施
专题出品人：沈浪
专题出品人：邓亚峰
快手/研发效能员责人
EverMind/CEO
