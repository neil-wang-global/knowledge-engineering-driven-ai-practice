# 徐翔-尽在上下文-mdash-mdash-JoyCode-的企业级-AI-Coding-实践

> Page-by-page visual information extraction from rendered slide/page images. Text is OCR-assisted and preserves visible page order; diagrams/tables are represented by their visible labels and relationships as line-by-line text.

## Page 001

InfoQ 极客传媒
QCon
全球软件开发大会
尽在上下文：
JoyCode 的企业级 AI Coding 实践
徐翔
京东科技 AI 架构师
负员 JoyCode Al Coding 架构设计、Harness 工程建设；过往经
历：先后就职于快手、蚂蚁，专注 AN Codling 领域、图汁算领域、图
可视化领域，中台能力建设。

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
企业在编码场景的核心挑战
目录
02
JoyCode 的创新解决方案
03
未来趋势：尽在上下文

## Page 004

企业在编码场景的核心挑战
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 005

企业在编码场景面临的核心挑战
京东作为电商巨头，业务场景
从初级开发工程师到资深架构师，
企业级开发任务往往涉及跨模
如庞大的代码海洋中，如
极其复杂，涉及零售、物流、
从业务开发到基础架构，从敏捷团
块、跨系统的复杂变更，单次
金触、健康等多个专业领域。
队到传统瀑布模型，京东内部用户
何快速定位相关代码、理
任务可能需要理解数干个文
大量自研框架、中间件和业务
群体呈现出高度多元化的特征。不
解业务逻辑、避免重复造
件、数十个服务。这种复杂性
组件构成了独特的技术生态，
同角色对A编码工具的期望和使用
导致上下文迅速膨胀，远超模
轮子，成为A编码工具必须
这对AI编码工具提出了极高的
方式存在显著差异，如何满足多样
型的处理能力，形成"上下文
解决的核心问题。
化的需求成为一大挑战。
专业领域知识要求。
爆炸"的困境。
业务场景复杂
用户画像丰富
复杂长任务
超大代码仓
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 006

JoyCode 的解决方案
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 007

• 企业知识增强
JoySpace
JoyAgent & JoyContext
在线文档、企业知识增强
多模态非结构化知识增强
企业知识
RepoWiki
DongDesign & Fely
“代码在哪里，知识就在哪里”
设计稿到企业 UI 组件通路
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 008

◎ 在线文档知识增强
$。
jd-joyagentidgenie.X
9 pl-joyagent-jdgenie
资源管理器
JoyGode
十
企业在线文档内容获取。
>jovcode
genie-backend
>genie-client
> gonie-tool
Jgycode
check_dep_port-sh
人 contributor EN:pdf
代码洪流，一念即成
contributor_ZHipdf
Deploymd
Dockerfile
S Genie_startsh
https:/ljoyspace.jd.com/pages/eeBfwy3AxdMVIDAKRE6l python
K LICENSE
mcp server 如何配送
E NOTICE-Third Party
4 README_DataAgent.md
• README_EN.md
沙-AutO？
4 README mrag.md
⑤ README.md
历史记录
S start cenie.sh
hups://avspace.ld.cam/oages/eeBfw.3月26日上午0:08
3当前的系统票构是什么
3月26日上午905
0 当前的系統架构是什么
3月26日 午9:04
）煮
》时翅
2HleTroa
g master & 8040
.JoyCode
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 009

多模态知识增强
JoyCode
JoyContext 为 JoyCode
提供多模态知识检索服务，
JoyAgent MCP Server
知识库
通过内置的知识库查询工具
实现上下文增强。
JoyAgent 则在多模态知识
JoyAgent
JoyContext
之上，提供了更加丰富的
能力，用户可以自定义智
能体，配置个性化的 MCP
Skills、工作流等。
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 010

• JoyAgent 工作流编排
◎PRD解折留消休.2
0③..
图 浏或用例好
0e：
◎9：
前人Si temelate Str Firstiona
u wt ougut
© 周 生 習金体-1
0③..
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 011

JoyContext 多模态检索
接入层
数据对象
Access Layer
Data Objects
JoyContext Core
查询服务
Service Layer
知识
Knowledge
INGESTION PIPELINE
文档/文本1代码
OCR/VLM
Layout
Embedding
系统界面
统一智能检索
Web UIUpload
Unilied Intelligent Search
input
记忆
MANAGEMENT
Memory
ChunkStrategy
Graph Build
用户画像/上下文
固 知识库查询
$>
Vector Store
Graph Store
#记忆检索
API 接口
数据 Data
RESTful API
API/数据库链接
日 数据库 询
Query Dispatcher
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 012

仓库代码知识增强
jd-joyagent-jdgenie
一B
OidHjoyagentjogenie
0日
⑧
资煦怡理器
JoyCode
v.ld-joyagont ldgenle
CodeWiki 通过AI能力生成
> .oycode
> doos
仓库 Wiki，形成清晰、结
> genie-backend
巴
2.genle-client
构化、「文字+图片」形式
> genie-tool
2 u
JoyCode
$ check_dep_port.sh
的知识体系，无需人工逐
人 contributor_EN.pdf
代码洪流，一念即成
A contributor_ZH.pdf
行梳理，让文档内容、可
昭
Deploy.md
Dockerfile
视化架构、源码交互一目
Genie_start.sh
当和的系统架构是什么
R LICENSE
E NOTICE -Third Party
了然，具备发生变化即时
•README Data/gent.md
0生码。
©Au5o-
# README_EN.md
更新的能力。
* README_mrag.md
⑦ README.md
历史记录
$ start_genie.sh
的系统委枸是什么
3月26日 上午9:04
3 梳理一下代码补全的逻辑
3月25日下午11:27
你妊
3月25日 下午11:26
〉大阪
> Fllo Troo
gmaster e ⑧oAo
A JoyCode
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 013

仓库代码知识增强
jdanyaoent-pgonie
C
E 多驾淤体系统
E 快速上手描而
E 火語置模型 成
E:AP设什与使用
E 多智能体框架 ×
•生欢状态
◎已完成
已完成：20120.失敗：0
多智能体框架
架构概述
IoyAgemt金智修体框架是一个甚于Jave的企业级智能代理系統，采用分只架构设计，支持多种智修体类型的协同工作，该框架通过抽象化的都能体坏送和灵活的工具调用机制，实现
核心业好惧炊
了可 展的多留 体协作模式。
督脂问饺荑护
核心设计理念
5
框架遵循”分层油象、职贡分离、工具坚动『的設计原则，通过B1s0Agcrt独象基关定义智舵体的核心行为模式，不同炎型的智窮体维承并实现特定的业务逻辑。系統采用RoAct
（Reasoring and Acting）模式作为智能体的基侣执行范式，礁保習能体且备提理和行动的双重能力！
供迪上 拍市：
系统架构
系搡采拘浚计
孕智溶休杯蔡
工其生态素取
源倍掇议汲计
巴
•校水实规組节
大语吉损型集后
向量投點与RAQ
訂罐粱构麥漿
•集成須式与款限
APIN9汁与使用
商定义工具开发
額署与沱约
Acentianu Lertectory
：理5日米
FlaaoingAgent
工真案合
•記忆数理
aroxng1o0
c60---3803210- 00
大鸡畜模型
你觉得 Repo Wiki是否有帮助？
8% Launchpud
Q0Ld
肉Jeycodn在
con
InfoQ 极客传媒
全球软件开发大会

## Page 014

仓库代码知识增强
个•：g-poytgem-deene
更斯
E 多艋熊体茶统
三 快速上手指南×
•生成伝态
Q
◎ 已充成
已完成：20/20 关散：0
快速上手指南
系统棷述
、目
坱乒邦述
Oanie AI国修体系统是一个巫于多模決架构的留能为话平台，集成了大语言模型（LLM）数坚分析。代码解程器和多神工具调用能力，系统果用前后選分高架构，支持多留的体协
核心业务濮款
作，館够处理复杂的任务规划和执行。
眵
冬晋酸您方線
哲節何效系線
核心架袀
见
工只席統系培
散選分析系统
系统由四令主要模块组成：
文件筒瑚系热
1:genie-backend-Spring Boot后蹦服务，基供孩心AP相智够体协词
快迪玉手指南
2.genic-client - Python客户端，实现MCP（Model Context Prolocol））服务
冖系统噪将设计
3 genle-tool-工具服务慢块，提供散据分析、猪索，代码执行等功能
乡暂能係布架
4.uI- Rea0t院端界面，碳供用户交豆界面
数痴处期奥构
工員生态系城
𡟶僵铳议没汁
入技水买现组节
前端界面 UI
大酒言模些集咸
山盈经肉与RAG
即继架肉纯旗
•类尿拟式与护展
后端服务 genie-backend
AP设叶与使期
回定火工具川发
交按与日志
MCP客户端 genie-client
工具服务 genie-tool
H2欲据库
大语言役型
向量效据库
搜索引擎
但觉得 Repo Wiki.是香有帮助？
图l1:Genic系统架构医（学生统架构區）
88 master：分8
88.° Launcrpad
成JoyCode血
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 015

仓库代码知识增强
R-pvaoent-jdoenie
BE0日
三 袋进上手指市
#大语言模型業成
API设计与使用>
生成状态
◎巴完成
客户端类型
已苑段：20/20，失散：9
Web前端
Python客户端
移动端
• 日录
核心业务摸坏
瑤
挈稲回数系氮
工同類成派
效指分析系况
加T协议
对还父江茶誌
文件管刊系统
快说上手报南
Server-Sent Events
RESTfUL API
客户端应用
lo
豸酲脂靴枢絮
数叔处理榮构：
工貝生森系统
通伭绞议玫计
•技术买R翱节
大语病模报集成
API网关层
向晨疫肉每RAG
欲斑库热象澀
的储实构定圾
•果成换式与扩底
AP/i针与表用
日定义汇具开发
控制器层
啟鬢与泌垘
监控5日志
业务服务层
©
数据访问层
密觉得 RecoWik 是百有燕期？白恩
16 mester&e &o Launchped 8oAo
肉dorcode
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 016

•
CodeWiki 的核心价值
痛点
解决方案
知识传递
知识传递
①
23 知识传递不畅，新成员上手难
吸品 基于代码整合项目背景、技术架构
登培训成本高，适应周期长
医缩短适应周期，隆低培训成本
技术债治理
技术债治理
②
历史技术债积累，代码结构复杂
Q
精准识别核心代码链路
依赖关系混乱，维护效率低
語 可视化呈现架构与模块调用关系
AI代码生成
AI代码生成
③
AI生成代码难符项目规范
基于结构化知识赋能AI
2”需要人工反复调优，错误率高
自动生成代码贴合项目规范
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 017

D2C-设计&企业组件知识增强
Design to Code 即设计稿转代码
5 ielwv..con teidesian?d=1985817731372979/2846cmc.da0%3A35node_k1=253A339
T限：
& Codng 社雞類作
◎ MDC 当参投繁濕加 ③ SUM 分析飲平
门 所有世擦
DongDesign 是京东内部的组件
烘氍
D2C变量版搭建（顶栏和左侧导航除外）
生态平台。
MOE.
W.1462-
H 1433
Relay 是京东内部的设计生态平台。
1台0
120
JoyCode 通过 D2C MCP Server
口 100%
实现企业级前端代码生成。
糖恕
# 用交量版指建
心 酸好现
忌进丝颗色
口 ftme
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 018

• 上下文工程管理
超大代码仓，模型如何理解
1
提供丰富地检索工具，把选择权交给模型
先定位，再读取
以检索为核心
2
提供代码行数、片段，減少上下文注入
提供预处理仓库级知识
3
Wiki、代码图索引提前构建
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 019

上下文检索
多路检索
1
2
3
4
5
？
！
？
grep_searcn
inverted_index
term_sparse_s
embedding_se
wiki_search
_searcn
each
arch
精确字符串/正则匹
快速关键词检索
带相关性排序的关键
语义相似度搜索
文档与知识库检索
配
词匹配
查询：maxRetries
查询：authentication logmn
token refresh session
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 020

grep_search
优势
劣势
精确性高：正则表达式精确匹配，结果无歧义
无语义理解：无法理解查询的语义含义
V 性能优秀：ripgrep优化，响应速度较快
模式依赖：需要精确的模式或关键词
V 灵活性强：支持复杂正则表达式模式
模糊查询弱：对模糊描述无能力
V 无索引依赖：无需预先构建索引，即搜即用
大型仓库慢：在超大代码库中可能较慢
上下文丰富：提供匹配行前后上下文
查询示例：搜索 class\s+\w+、查找 APLKEY 配置项
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 021

embedding_search（语义检索）
优势：
劣势：
X 索引耗时：需要预先建立索引，首次使用较
V 智能理解：理解自然语言描述，不依赖精确关键
慢
词
外部依赖：依赖远程服务，需要网络连接
相似度匹配：找到概念相似的代码，即使关键词
不同
精度损失：可能有轻微的精度损失
跨语言支持：不依赖特定编程语言语法
存储开销：索引占用存储空间
模糊查询强：适合不确定具体实现名称的场景
不适合精确查找：精确查找不如grep
概念性强：适合高层次的概念性搜索
查询示例：“用户认证流程”“错误处理机制”“排序算法实现”，自然语言查询、模糊搜索
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 022

wiki_search
优势：
劣势：
V 专注文档：专注于项目Wiki文档内容
范围有限：仅限于Wiki内容，不搜索代码
结构化：提供清晰的文档结构
X 不搜索实现：不包含代码实现细节
高层次：适合理解高层次概念和设计
＜依赖文档质量：结果质量依赖Wiki维护
查询示例：“用户认证架构设计““性能优化最佳实践”“API调用指南”“项目规范”
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 023

inverted_index_search（倒排索引搜索）
优劣势：
核心原理：
灵活匹配：只要匹配任意一个关键词就能找到
预先建立关键词到代码块的映射表，就像书籍的目
结果
录索引一样。
V 响应速度快：基于预先建立的索引，查询迅速
7 适合专业术语：对确定的技术术语效果最好
关键词来源：代码中的函数名、类名、变量名等
查询时：快速查找包含关键词的所有代码块
需要索引：依赖预计算的倒排索引
无语义理解：纯粹的关键词匹配
排序规则：匹配的关键词越多，排名越靠前
查询示例：“auth token login” “UserService UserDAO” 任一关键词匹配
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 024

term_parse_search（稀疏检索）
优势：
核心原理：
与倒排索引的区别
v 结果更准确：让最相关的结果排在前面
关键词来源：代码中的函数名、类名、变
InvertedlndexSearch 适合快速定位的
v 多词同时出现：优先返回同时包含多个
量名等
场景，能够快速返回包含目标关键词的
查询词的代码块
文档；
计算文档相关性分数，综合考虑以下因
V 精确匹配：适合查找包含特定词汇组合
素：
的代码
TermSparseSearch更适合需要相关性
词的重要性（常见词权重低，稀有词权重
高）
排序的场景，能够按相关度高低呈现更
依赖关键词提取：关键词提取的质量直
词的出现频率（出现越多越相关，但有上
精准的结果。
接影响搜索效果
限）
X 不理解语义：无法理解代码的实际含
多个查询词是否同时出现
义，只做字面匹配
查询示例：“user token validate” “fetch request response”词项共现关系
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 025

大型代码仓上下文理解
通过代码图索引实现对大型代码仓，针对仓库级理解，除了 CodeWiki 还为模型提供 Code Graph Search
CodleXGraph Viewer
CodeXGraph Viewer
© 4t6歩：wladPE: 17Im
节点详悄
Q 搜双过R
• Bn NTERESCR
＃基本佰息
Se（w80u.E
口.
VETHOD
cravcardshape m
- XR《MFLEUEXFSI
-岁N：MRL :AINTS！
口• JNIOWN
门 CONTANG
EI HS METHSO
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 026

大型代码仓上下文理解
通过代码图索引实现对大型代码仓，仓库级理解：为模型提供全局理解的工具，如项目复杂度、调用链等
180 日0
08000
008810
Qcon
InfoQ 极客传媒
全球软件开发大会

## Page 027

0. G6
+多E
项目复杂度分析
mecLco96_contex分折現世夏奶度
通过圈复杂度、参数数
既雄让没電看生老修着化府日录留构。补后用是杂这分价二科来台物项日：
量、调用数量、依赖数
已效真
现行计或使開女安忘分析二具来只新堂个功日时发总自共点：
量、继承深度等等多维度
三月 gat ceCo context MG2瓶
w @ enalyzo_xoment.comp esEy
加权评分
oiotertno tnenamo at s3.odo2amontto 2na0so. 1tostpetaod the :ootwou.mneccnp a06/ho.soreihn tectno.codasass
可用于重构、项目优化等
thirestoic comnisetytrroshein ton ketspot.norectce netusto （0.only uzon when aemonitams anatpinydcd
natric:Popoxtsmsetorhotosatcetectoncoclomabe tancutor Siaes Detauiteto:cuscmate ceuusd Dnonelomeetseane nofotguidod
场景
cie careleelty Hotspelv［Meirate eyctnratic. Thireshod-ml
-cycuomgeic tomlcxit: 183
10. oetiatost 1c （ME H0D| CreLorotae torpiet
Tistaal-icetites codwzocp6wxi-y.btentein thecesebasr:Uceit to.tine areas that nay ne.s cafactoring 6r.2dditiuead.zetlsg
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 028

Q G6
個：
函数调用链路分析
wl setLcodecomieat cP IR第
w& anayzu_el_chan ralationep：
日效 行
storor &iles: arorcuno-Fprowrcmrotn.orraiwmhorosp2a 2ooccn-Alemitl/e queryinstnodetaroantareALL flRrionmhipdarcotn:Emins calep.ootocilon wimhrrutrhe ftoeek arexeni- pagmionstc （hftnnpssomor.to irgojpeutseks- sorcroepce opliizat ansior azncira
查看代码变更传播影响范
围、循环引用等
anEs woxten muirotsot rorJl te roum oordrocon.Hocun 650,maomum.： 100
offsss Nuroecct raouse to sko, dofasitisO，
Sall Chozn Re-ocLonanios Arelysi: for gs: Conta-ror （FUNCTEON）：
mie Poth：（oackanewfo.fsnetpludn.xotilsconvast
wen nu Choinse （Oallee）
getEtenontBvts （PNeriC
BepthJ
This tnat.ssocysescael tan relatitnseipsfnr code eleiews.Tt sws toth /nconingealleeskdwl culielglca leesi teletsonstteteireweeerstono howetelents are usel arevtwl thes:epend on
Kalt Choua ReLosionanios nawysi: for gsa Lontouzer （ME1:H2）a
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 029

•模型检索策略
＃概念探索策略
＃关键词定位策略
场景：不确定具体实现
场景：有多个关键词，需快速筛选
EmbeddingSearchTool
GrepSearchTool
InvertedIndexSearchTool
>
TermSparseSearch
说明：自然语言定位—精确定位代码
说明：快速筛选 BM25排序
＃全面理解策略
＃精确定位策略
场景：需全面理解功能模块
场景：已知精确信息
WikiSearch Tool
GraphSearchTool
EmbeddingSearchTool
GrepSearchTool
6raphSearchTool
说明：设计文档 结构关系 实现代码
说明：精确定位 —结构分析
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 030

• 案例分析
项目
https://github.com/continuedev/continue
文件数：2600+
代码行数：64w+
模型：GLM5（thinking）
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 031

•
竞品对比
郡天
JONCODE
5×
查找“自动补全功能的触发還据！完成任务的时候列出各个工具调用的次数以及每次调用的原因
Searchod for 5 pattorns read 6 filos （ctrl+o to oxpand）
查務：自动补全功熊的胆发退辑“完成任务的时候列出受个工具谓用的次数，以及每次请用的原因冬
根据已读取的文件，我来总结自动补全功能的触发選辑：
自动补全触发逻辑概述
8 已深 思者2
1. 触发入口 （completionprovider.ts）
我来帮你查找“自动补全功能的触发泛辑”。让我使用搜秉工具来定位相关代码。
VS Code週过
InlineCompletionltemProvider 接口触发：
C CSR上下文引擎
autocomplete trigger logic
已拨至120栄结果《
public async provideInlineCompletionItems（
document: vscode.TextDocument，
position: vscode.Position，
context: vscode.InlineCompletionContext，
8 已源展思寺＞
token:yscode.CancellationToken，
C CSR上下文引擎
trigger de bouncelprovideinline Completionltems
已投到20条結果 0
工具调用统计
词用
调用原因
次数
JoyCode 读取了多个文件
4次
拨案
tr4naer,hcampletLan、tsbaunce, QEFAULI_ALTDCUMPLEIE_ODTS
定位相关文性和配置
G1o
1次
查扱
Hutocongletn 日录下所有文件，了帮模肤结构
工具调用统计
谈取核心文件：
• term_sparse_search ：1次—初步搜索目动补全触发逻辑相关代码
6次
（防抖）
ino.ta｛多行决策］：Holpcrvaza
｛上下文构评！
• grep_searoh:2次-精确搜索触发、防抖和预过滤相关代码
• read file:7次 -读取核心文件详细内容
总计：11次工具调用.
全面分析了自动补全的融发机制、防抖策略、
过滤学件和配音參数。
Claude Tokens
GPT-40 Tokens
Gemini Tokens
Characters
Claude Tokens
GPT-4o Tokens
Gemini Tokens
Characters
33,229
25,211（241%）
31,849（-42%）
94,643
20,319
16,332 （195%
18,546
（=8.7%）
58377
aCon
InfoQ 极客传媒
全球软件开发大会

## Page 032

• 案例分析
项目二
https://github.com/microsoft/vscode
文件数：4.2w+
代码行数：1000w+
Prompt：找出VSCode 中所有参与”工作区信任验证"流程的组件，包括触发点、验证逻辑、UI 提示
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 033

竞品对比
医示完成年多的时
找出KScode
聊天
JOYCODE
+35
我采帮你我出 VSCode 中“工作区信任验证“流程的历有组件，让我开给接零相关代码。
找出 VSCode中所有多与“工作区信任验证”流莲的组件，包括触发点、验征退辑、UI提示，完成任务的时侯列
searched ror i1 patterns. read 12 riies Cctri+0 to expand
出各个工具调用的次数，以及每次调用的原因
我在我已经收期了是够的信恩，
让我为你总结
YSCode 中工作多信任检证流栏的所有短件。
曰
VsCode 工作区信任验还流程益作过拉
编码
一、核心服务翠构
我会帮你找出VSCode中参与”工作区任验证”流程的所有组件。让我先搜素关代码。
calculatewcrkspacelrust（） — 什算信任状态
C CSR上下文引祭
workspace trust
已找当20発結泉
-onDidchangeTrust.fired）—触发估任变更事件
NorkspacoTrustContextKeys—更舞上下文健
Irus TramsiticaManeger:narticinste®- 我行球理希与刊
NorkspaceTrustUXHandler 更新UI指示路
八、工具调用绕计
五、工具调用统计
本次台析共进行了15次工具调用
调用次数：日次
调用腺因：
泼阏
inverted_Index_search（1次）
iwo=kap.ocoiru9tneauo=tBexvioeyrequentwprkapnccfrustx FoQuescopon/ =2a=TYuE、 MANAGE_IRUSI_COMMAND_1D
1 搜素
'wotspece inusi"-定位工作区信任相关文件
等关您词定位相关传码
grep_search（6次）
1 搜麥"WorkspaceTnuetManagementSenice-在找信任管理服多使用点
调用次数：10次
工具：Read
•搜裂aquestWorkepaceTruat-五找信任请求用点
调用原因：澳取板心文件：workspaceTrust.ts （平台農和工作台展）
.werkspBce.contxioution.taw.sNtaaeionhanifestpropertinsSg
3 搜网"WorkepacaTnuatllequaetServica - 查沈信征清苏服务引用
*搜粱：workapacoTruastcialog 食戏对酒枢相关代码
5 搜酒4onDidchangeTnst-这找信任状态发更监听器
工具：61ob
6 搜索/requestWorkspszefrusicnstartup直板店动时信任初给化
调用原因：本次任务术使用（主要用 Grep 搜索內容）
read_fille （8次）
1这取按口定义文件一了深服务接口契約2-5.连取信任服务实现 一理解晚证返楼6-8选取山五就点文件一了師讨结柜和提示必理
总计：18 次工具调用（8次 Grep+10次 Read）
2 读記信任报辑器一了粹餐理界面
3.設記护限府用戒渡参与容一了蘇扩展信任款动
Claude Tokens
GPT-4o Tokens
Gemini Tokens
Characters
Claude Tokens
GPT-40 Tokens
Geminllokens
Characters
52,652
35
，236 （-331%）
49,055（-68%）
131,505
46,443 34,793（251%）
40,195（-13:5%
121,779
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 034

• 竞品对比-为什么 token 消耗差距会这么大
上下文管理对比 -Comparison
grep 调用
某竞品方案
JoyCode 方案
grep +term_parse
展示上下文膨胀过程
展示按需注入过程
文件路径
文件路径＋行号
read 调用×N
VS
read 调用
read 调用 ×N
效率提升
read 调用xN
2000行以下全部读取
350-600行
上下文膨胀飞快
上下文按需注入
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 035

团队智能体
上下文管理
丰富地扩展工具
2
检索工具、短期记忆等是核心
MCP、Skills、BashTool
1
4
内置智能体
自定义智能体
实践经验沉淀的各类内置智能体，如规约编
用户自定义配置智能体，且支持相互调度
程、问题修复、前端页面设计等
多层次智能体协作体系
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 036

智能体团队
丰富地扩展能力、内置智能体、自定义智能体、智能体自由调度切换
Joycode 设置
舐遘背解体
doycode 识置
技能
通用
内置智能体
最入品 体名物 SST PA FXCT
0450
项目技能◎
＋新題技能
色特性
① 编码
學 模型
精逢多狩编程语言。杰架，设计模式和最佳实线的高级软
角色定义
设定专业方店
日 WC芝
baoyurartac.erastustraton
© 習諾体
2 智能体团队
目 McP
协调复杂任务的战略工作资给排资，将任务分配给专业的
•
讓场入绝色论安，阴如：
0果 Jov Code
，今拉后清发钢发寺家，你的關责尽处琛没惯并能次况有拉取请太中地问晒。放
规刘
generate-pdt
技能
收集任务信息，制定可热行计划，优化方累并拍导实旅的.
•
双 上下文
二缺限料分岬制玩日心以依断数8
架构图设汁
€ 规则
銀量代 、上下文、图片等信总设计和給写 Drami粘式•
自定义指令（可选）
json-reader
② Bota
前端页面设计
數支票烈県
设计前端网页，生成html页面，设计产品顾型
•
请格入自定义指会，例现
の可以棒並自生父：今来嘎葉盟靠华的药示。铅；
1.1 Loycade
一个批数请求親发专案，总州使開領半约工具收非培息以苏款任务的更多上下
用戶接能◎
问題修复
专门进行系统化问题冷断和解决的软件濯试专象
•
分析Pi國音界故以理認新费的部改
问答
：檢黛 CIC口工作龙以心以识鸟（先数越难到
精适多语言缩程，控长代码分析、问题诊断那最佳实践推.
使用场景（可选）
暂无可用的技能
规约缔程
刘时简建这警修停难适会的请累扣任务头是。这有那于 習招休世从为任多意接合动的曾能作。
支打说仅在inioycohe&ttay 下的歧战日茶
基于规约文档进行结构化編荏，按任务列表逐項实现功能.
收消
保存
acon
InfoQ 极客传媒
全球软件开发大会

## Page 037

•智能体团队- 自主调度
基于智能体团队的 Harness Engineer 实践：协调智能体、计划智能体、编码智能体、评估智能体
协调智能体
计划智能体
生成智能体
评估智能体
作为中央协调器，自主驱动整个开发生
负责将用户简短的1-4句话需求扩展为
负责根据产品规格和Sprint计划逐步
作为独立的质量守门人，负责审查和验证。核心
命周期。核心职责包括：
完整的产品规格说明书和Sprinti
实现功能代码。核心职责包括：
职责包括：
无限循环调度Planner、
划。核心职责包括：
与Evaluator协商Sprint合同
审查Sprint合同的完整性和可测试性
使用Playwright进行实际浏览器测试验证
Generator、Evaluator子智能体
需求分析与功能拆解
按合同实现所有功能
评估设计质量、原创性、功能完整性、工
管理Sprint状态机和状态转换
设计技术架构方案
进行自我评估和代码审查
艺水平、代码质量等维度
维护所有Sprint的执行进度
制定最多5个Sprint的迭代计划
确保每个Sprint产出可运行的
决定PASS/FAIL或APPROVE/REJECT
确保所有Sprint完成后才进行最
定义每个功能的验收标准
增量功能
拥有项目最终验收的独有权
终验收
为Generator和Evaluator提供
每次Sprint完成后交付给
（FINAL_APPROVED/
工作基准
Evaluator进行QA验证
FINAL_REJECTED）
Orchestrator
Planner
Generator
Planner
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 038

资漆曾理器
G Prevlew sprint-1-contract-review.md x
取天
JOYCODE
智能体团队
V PROJECTS
v.joycode
•Sprinl 2 QA Report
已验证正常功能
Yjoytasks
• Overiew
•风精灵編辐器茶本绘图（画笔、橡皮擦、琪
> plans
wsprints
Sprint 2 QA Report
• Scores
充）
Y Contract Test Criteria
•⑦ 工具快捷键（B/E/G/1/M）
自主运行6.5小
炒
•sprint-1-contract-proposa..
Verification
•团肉丘调色板奶淡（NES, Game Boy.
sprnt-1-contrect-fevlewl.e
• Feature 2.1: Pixel Art
CGA: PICO-8）
时。
spcnl-1-ga-report.md
Overview
Drawing Tocls
澱销/車依（按钮和Gtrl+Z/CIrI Y）
sprint-1-self-review.md
• Feature 2.2: Color Palette
•⑦西布缩放
# sprnt-2-contract-propos：
58
• spint-2-contract-review...
• Sprint Number:2
and Color Picker
动西嫔躬貓创廸
w sprint-2-contract md
• Theme: Sprite Editor & Assets - 精灵编辑器与资产管理系纷
• Feature 2.3: Sprite
•又资产库文件夹创建和搜索
每个子代理拥有
sprint-2-q8-report.md
• Test Date:2026-04-06
Animation Editor
必须修复才能通过验收
4 sprint-2-self-review.md
• Tester: Evaluator Agent
• Feature 2.4:Sprte Library
1 修复精灵保存到ndexedDB的功能
独立的上下文窗
orchestration-status.md
• Test Method: Playwright Browser Testing
and Asset Management/
2. 添加自定义调色板创建則
>rules
V Critical Issues Fcund
3. 添加RGB/HEX部色单人
v retro-game:maker
• issue 1：精灵保存功能不工
4.浓加调色板导入/导出
口，有效解决上
> dist
Scores
作（Critical- BLOCKER）
5.完善选区操作功能
> node_modules
• issue 2：自定义调色板创建
详细报吉：
下文窗口膨胀的
>public
U飲失 （Maior
> src
Dimension
Score
Threshold
Status
joycode/joytasks/5prints/sprint:2-qe-
• issue 3:RGB/HEX颜色输
Sepoct:mo
.gitlgnore
问题。
Design Quality
7/10
6
PASS
入U失（Major
◎ eslnt.configijs
• Issue 4：调色板导入导出功
> index.html
Originality
6/10
5
PASS
能缺失 （Major）
11 package-lock json
•issue 5：标签功能缺失
已成功调度 Evaluator 子代理进行 Sprint 2 的第二轮 OA
（i package Json
Product Depth
6/10
6
PASS
（winor
验收测试。Evaluator 将使用 Playwrgnl进行实际的引近
⑦ READMEmd
• Performance Test Fesults
器測试，丝证所有修复是否有效，井洪定 Sprint 2 是否
tsconfig.app.json
Craftsmanship
6/10
5
PASS
• Features Verified Working
通过驗欧。
m tscontigJson
Functionality
6/10
7
FAIL
• Features Not Working/
U tsconfig.node.json
Missng
綴可以猫时殷消并调摇任务
酸消任务
F vite.config.ts
Code Quality
7/10
5
PASS
• Decision: FAIL
>1安更文件
拒绝
Overall: FAIL - Functionality score below threshold
坦过“@”添加上下文，？使用快捷指令，个业"切换 史输
入会+ 换行
Contract Test Criteria Verification
〉大級
• Orchcstrotok
ZOUM:5
8aLaurchpad
⑧040（A:258 更新已准备好，单击以重启。
肉JoyCode
~ Prettier
con
InfoQ 极客传媒
全球软件开发大会

## Page 039

真实场景案例-某能源企业风险防控项目交付
AI交付提效项目背景 - Timeline Story
交付危机
解决方案
核心成果
成本节省：47万
供应商入场两月半后
AI驱动交付
违约撒场
毛利提升：8.11% 17.39%
仅余15天
架构师驻场指导
研发周期：7个月 4个月
V
单人快速完成需求
交付危机
到高保真原型
人力投入：31人月 14人月
仅余15天
客户高度认可AI生成成果
代码质量：缺陷0.93%0
风险等级：极高
成本节省47万
毛利翻倍
超预期完成里程碑交付
周期缩短43%
人力降低55%
Qcon
InfoQ 极客传媒
全球软件开发大会

## Page 040

某能源企业供应商风险防控项目交付
AI驱动软件工程全生命周期交付流程
七个阶段
主流程
资产库
需求输入
创意
资产反馈
PRD智能体〈PRD智能体
架构库
Spec文档
UI设计
返工
资产反馈
架构设计〉
100
模块库
返工
开发执行
资产反馈
测试验收
规范库
发布上线
发布上线
经验沉淀
经验沉淀
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 041

• 某能源企业供应商风险防控项目交付
AI交付流程框架- Conceptual Framework
Skills指导Docs和
Src的生成
AI技能（skills）
设计文档（docs）
交付代码（src）
作用：告诉AI怎么做
作用：AI生成的详细
作用：最终交付产物
设计文档
•包含：SKILL.md、
• 包含：生产级代
核心工作流、输入
•包含：架构设计、
码、测试用例
模版、输出要求、
Docs反馈优化
产品设计、技术规
Src验证Docs
自检查清单
Skills
范
的正确性
步骤1：输入模版
步骤2:Al处理（基
步骤3：输出要求
步骤4：自检查清单
（告诉AI需要遵循的
于skills进行处理）
（生成docs和src）
（AI自检质量）
标准和规范）
核心资产
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 042

• 某能源企业供应商风险防控项目交付
原交付模式
AI驱动交付模式
缩短43%
研发周期：7个月
人力投入：31人月
研发周期缩短
研发周期：4个月
人力投入：14人月
正岗10人月
外协21人月
正岗8人月
外协6人月
VS
岗位投入明细
岗位投入明细
减少55%
业务架物师（莱产品经理）：7人月
业务架物师（莱产品经理）：4人月
2技术架枸师：3人月
人力投入减少
技术架构师：4人月
前端研发：3人月
前端研发：1人月
后端研发：12人月
后研发：3人月
测试人员：6人月
测试人员：2人月
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 043

• 某能源企业供应商风险防控项目交付
项目预算总览
项目总预算：400万＋
当前成本：300万+
后续成本：约90万
毛利提升：8.11%-17.39%
节省成本：约50万
自研占比：69.01% 79.32%
After
After
79.32%
69.01%
Before
%
8.11%
％7
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 044

未来目标
原交付模式
AI驱动交付模式
缩短43%
研发周期：7个月
人力投入：31人月
研发周期缩短
研发周期：4个月
人力投入：14人月
1人月=>
正岗10人月
外协21人月
正岗8人月
外协6人月
15人天？
VS
1人天？
商位投入明细
岗位投入明细
咸少55%
业务架 师（ 产品经理）：7人月
业务架钩师（莱产品经理）：4人月
2？ 技术架抽师：3人月
人力投入减少
技术架构师：4人月
®前端研发：3人月
前研发：1人月
自后端研发：12人月
后 研发：3人月
国，测试人员：6人月
测试人员：2人月
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 045

•总结回顾
JoyCode 是如何应对挑战的
超大代码仓
复杂长任务
仓库级理解工具
CodeWiki 代码即知识的高阶知
用户画像丰富
识；代码图谱 提供仓库级别的理解
抑制上下文窗口膨胀
工具；多路索引保证性能和召回率
业务场景复杂
以检索为核心，按需加载；
自定义智能体
子智能体在独立上下文窗口运行，仅
将 Summary 回传；其他机制保障
系统提示词、指令、规则、工
知识来源多样化
具、skills、mcp 目由组合，多
在线文档、本地多模态、远程智
Agent自由调度
能体编排、自研组件、UI设计⋯••
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 046

未来趋势
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 047

• 未来趋势
上下文工程仍是核心
Harness Engineer 不会彻底消失
大展宏“图”
在有限的上下文窗口中注
模型能力不发生跃迁，
从 context7、git nexus、
入最准确的信息，仍是我
Harness 不会消失。
graphti 再到 supermemory
们的目标。
提供尽可能全面且高效的工
图技术在 Al Coding 领域的
在数百上千次工具调用之
具、Agent 驱动机制，让模型
应用会越来越广泛，甚至可
后，保证上下文仍然可以
可以灵活自主地进行选择、组
能会成为不同产品之间的核
保持稳定且高效地运行。
装调用，更好地完成任务。
心竞争力。
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 048

• JoyCode 算法团队热情招募-天才计划
JoyCode 算法团队专注大语言模型在软件开发全生命周期的深度应用，支持代码补全、智能编辑等核
心AI功能优化。
课题聚焦代码智能化：基于Code LLM构建代码补全、生成、优化等核心能力，打造世界一流产品。
诚邀对AI Coding 充满热情的你，共同定义下一代智能化开发范式。
欢迎投递：xuxiang.118@jd.com
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 049

InfoQ极客传媒
QCon
全球软件开发大会
THANKS
大模型正在重新定义软件
Large Language Model Is Redefining The Software

## Page 050

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
