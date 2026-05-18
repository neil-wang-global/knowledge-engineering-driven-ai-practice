# 有道龙虾 LobsterAI 的养成与实践

- Source PDF: `references/papers/刘刚-有道龙虾LobsterAI的养成与实践.pdf`
- Visual pages: `references/paper-visual/images/刘刚-有道龙虾LobsterAI的养成与实践/`
- Extraction mode: visual page-by-page information extraction
- Page count: 69

## Page 001

InfoO 极客传媒
QCon
全球软件开发大会
有道龙虾LobsterAI的养成
与实践
刘刚
网易有道

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
有道龙虾产品全景
02
有道龙虾的起源
03
架构选型与设计实践
目录
04
Vibe Coding实践
05
未来规划

## Page 004

有道龙虾产品全景
全场景个人助理 Agent
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 005

• 工具碎片化的困境
每天在 5-10个工具间反复切换
更深层的问题
•写文档 工具 A
工具不互通一搜完信息还得手动粘贴
•做表格 工具B
无法自动化一重复性工作每天手动执行
•搜信息 工具C
不记得你一每次从零开始
•发邮件一工具D
只能坐在电脑前—离开就无法操控
•做 PPT 工具E
QCon
5
InfoQ 极客传媒
全球软件开发大会

## Page 006

什么是有道龙虾
打造 PC端全场景个人助
告别繁琐的命令行配置。
国内大厂首个全面开源的
告别全量文件云端上传，
理 Agent，深度覆盖数据
作为一款标准的PC 桌面
Agent 级产品。2026年
支持本地构建知识库与代
分析、文档处理、PPT 生
端应用，双击即可完成安
2月上线首周 GitHub
码执行。完美兼容本地私
装，为用户提供零门槛、
成、视频制作、邮件工作
Star 突破3000，与全球
有化大模型，让企业敏感
沉浸式的 AI交互体验。
流等日常生产力场景。
开发者共建开放的AI生
数据真正留在本地。
态。
全场景Agent助理
极简安装开箱即用
100%开源龙虾
数据隐私安全可控
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 007

•
开源开放的AI生态
一 Star History
4K
netease-voudac/L obster
3K
2K
1K
Feb 22
March
Mar 08
Mar 15
Date
> star-history.com
QCon
7
InfoQ 极客传媒
全球软件开发大会

## Page 008

OpenClaw 创始人公开称赞
21小小时
×
个
Post
Here is the list of 31 Claw variation from China.
oinice s Weixin. WNeChat they are support openclaw @steipete now you can
2.腾讯 QClaw
control your lights or almost everything at your home via We ChatClawBot
3.腾讯龙虾管家
E YoudaoLobsterAl
4.腾讯云保安
Here is I made a quick prototype using ESP 32
5.腾讯乐享知识库，龙虾版
6.字节ArkClaw
7.智谐 AutoClaw
8.月之暗面 Kimi Claw
9.阿里云 CoPaw
10.阿里公JVSClaw
11.阿里云 QoderWork
12.百度红手指 Operator
13.白度 DuClaw
14.科大讯 AstronClaw
16.网易有道LobsterAl
18.智麻 ChatClaw
19.矽速 PicoClaw
20.博云 BocLaw
21. ZeroClaw
22.万得WindClaw
23.小米 MiClaw
24：.猎豹 EasyClaw
25.猎豹元气AIBot
26京东灵军Claw
27.快于KClaw
28.美國 Claw
隐藏
0:02
⑦15
16
③ 153
i1 3.8万
◎1
01
I260
Peter Steinberger
Peter Steinberger W0
X.com
@steipete
@steipete
dope
Love LobsterAl
3:09 PM•Mar24,2026•240 Views
aCon
8
InfoQ 极客传媒
全球软件开发大会

## Page 009

• 有道龙虾— 全场景 Agent 助理
一句话驱动
技能
定时任务
“帮我分析数据，生成报告，发到邮箱"
文档/表格/PPT/视频/搜索/邮件
“每天9点收集科技新闻”
手机远程操控
越用越懂你
跨平台
钉钉/K书/Telegram/Discord
记忆系统，跨会话记住偏好
macOS/ Windows/ Linux
QCon
9
InfoQ 极客传媒
全球软件开发大会

## Page 010

有道龙虾-功能概览
一商A新闻总结PDF生成
E prcjec：
臼 New Task
总结一下最近一周的AI新闻，生成一个pdf文档
c Search Tasks
© Scheduled Tasks
作 Skills：
•Read:/usars/admtn/Lobstere_/pro1 egt/mienorv/2026-04-15.mg
1ine dfcutput
88MGP
•Read
ryLlbrarwsApotication suppart/tobstarAt/SktLEs/par/5kt.
S My AgenS
好的，
先去抓一下最近一度的 A新间，然后生成 PDF。让我用浏览留搜索一下。
main
• browsert vactzomWsg"opentw'turNe Kottps://wwy-g00gke.com/3ga）
• browser vactionwt"snapshouwe/wtargetidW NFDD8S8F599A2E114日米
已经拿到一些新闻线索，再深控几篇关链文章内容。
test
• weo_fetch nttps/ww.saplta rutures.som.sw/zi-ty（Ftnanc4al/Brea-
Task History
• wen_tetch https://coaao/com/zn/news/2026.0g/brea king-tecn-new5.0.
一周AI新闻总结PDF生成
now.OMPLETE）
• wen_tetch http://www.china.com.cn/txt/2026-84/25/content_1184377.
净到不少信总了，再补充搜索几条主要新闻。
一周国际新闻总结PDF生成
120.wwMPiETEd，
• browser Hactson"w "hewgate. "nargetTdlFhbBS8F5P9A2E131E.
• browser yacttonwe: wonapshot"iowrargetid" %FDD858F589A2EL11EA
［9Q1 acte74ab675g
2d:CDNPLETED
素材够了，
现在开始生成 PDF.
［QQ1 77262a10b41e
• Bash ed /usersyadniry1obeterit/projeet-00 python3 元 Gmporm
2dCDwPLETED
• Write,xUsers/admih/1obsteran/project/genuai_neys_pdf.px.
［oa1 4d409ae2aaeo
ontinue theconversation..
［Discord］ 860667867203
6T. CONPENTEO
Kimi K2.5
8 Login
2 Sertings
aCon
10
InfoQ 极客传媒
全球软件开发大会

## Page 011

有道龙虾-Skill
技能
技能安全扫描
（ 所过任总
为成的贸能体提供預划發旦可鐵复的瓶住实跃与工具
O 授素行旁］
O 投素技維：
◎ 添加
test-malicious-skill 技能的以下行为请悉知：
© 定时钰务
已安装24
技能市场
v•提示注入
• 覆盖系统指令
docx
web-search
SKILL.md:9
任努记燉
Iggore alL prevtous Instructtons
［定封］掍鷄瑪¥
【出前統息，對新文名誼順所緝嶼任衛的出外佩垂止日期。
Im 三克出
JHTE
文件访问
［微信］xleekdrtekoy
ppix
•访 0 SSH密钥
全西的日于录柿创，瞬惟和分析二具，夫式，格式冠置，
seripts/evil:shs3
双6分行推三表化：当Clmidn N曼处理电于长比
《palx2件）可用于
鱼沟最近10条电件
SEGE
catw/.s3h/2d.130
• 访问 SSH密钥
seripts/suspicious:S:5
［金街］aliuzhiqieng
建涩时色劳，当用户想设簋。节威双笔我屋期日敲规扫的住效
新建和響理定时任务，文师盒着，将改，台用/烧用，也絲及性
sconst ssnkey =fs,readFilesyne（process.envHONE +0-sSh/.id2FsaV0tf8'
•访间 AWS兌证
：scnpts/suspicious.：5:6
.consowscFeos= isone8uk （e-yncvpnoceesrenysh.cawskeredenwade
［S书）695be78f16a0
彩试造拜时使布：沒夏小的更过，运行基于eapwnaht的2.
23115日
取消
安装但禁用
仍然安装
会设置
playwcight
create-ptan
QCon
11
InfoQ 极客传媒
全球软件开发大会

## Page 012

有道龙虾-定时任务和MCP
定时任务
创建任旁
尼置和管獲 MCP IModel Carkax: Protocol） 限多8，刘妳的置需作款及一具能刀
输入往务路
Aacnt：.1
市燥住
日定义
成 IACP
ymom
侯用默減模曰
计期
。
Gittab
N CantexT7
多裂詰佛兼時畏綠所闻搜翌
逐妇粢道
亭習能綠篤群周报新阳携果
G∞ge Orte
Gmzl
72515）83t428761051
【 书J$3162a7c1151
GmF那卡路理：娱花-没出，推路53件复将日对从低
【DingTalkJ 274430672511
TDia Talk） 274430872514
cd aaxt
Googe Calendar
［Ding Talk）274430672514
IDbgTaIk/274630572534
TFeisnu） 83t428761b5
Fathiiaot2mictb5：
R.E
QCon
12
InfoQ 极客传媒
全球软件开发大会

## Page 013

有道龙虾-多Agent和多机器人
我的 Agent
我的 Agent
Q 涨紫任品
阶设 Agent
网股票肪手
公 豉就
3 MGR
胺票助手
登司！
whaialk2012三蒜序種理效
多祖指济撕群皮報矫间帑裝
•FesH1.8013
民+：3142a3cta51
金业资作
mem
T0aglek）274420022514
期盐 Agemt
OAUk234430672514
示始
使用北 Mgent
［Feshul 8314287c/651
QCon
13
InfoQ 极客传媒
全球软件开发大会

## Page 014

•有道龙虾-核心功能
只需要输入最终目标（比
内置丰富 Skills技能，自
支持自然语言设定灵活周
全面打通钉钉、飞书、企
如“帮我分析这份财报并
动执行复杂工作流；深度
期任务，后台独立静默运
微等主流IM。一部手机即
做成 PPT”），它会自己
支持MCP协议，一键打
行互不干扰，完成后自动
可随时远程唤醒 Agent 派
思考第一步干什么、第二
通本地与企业外部数据孤
将结果推送到指定频道，
发任务，不在电脑前，也
步干什么，遇到问题自主
实现 7×24 小时工作流闭
能用手机微信/钉钉指挥它
岛。
调用工具解決。
环。
干活。
Agentic 架构
skills & MCP
定时任务
手机端控制
QCon
14
InfoQ 极客传媒
全球软件开发大会

## Page 015

• 使用案例
用户输入
执行流程
场景 1
USER
①
定时任务触发
scheduled-task
每天需要追踪行业动态
“每天早上9点，搜索A/领域最新新闻，生成一份
Word 日报，发到我邮箱”
②
搜索并抓取新闻
web-search
每天早上自动获取最新资讯，
无需手动操作。
最终产出
③
生成.docx 日报
docx
全程无人值守，第二天打开邮箱就能看到
④
发送邮件
imap-smtp-email
QCon
15
InfoQ 极客传媒
全球软件开发大会

## Page 016

•
使用案例
用户输入
执行流程
场景 2
USER
①
IM 消息触发
IM gateway
出差路上临时需要处理
“基于电脑上XX的资料，结合竞品XX最近的融资
所闻，整理成一页 PDF 发给我”
任务
②
搜索抓取新闻
web-search
手机上发一包话，桌面 Agent
自动完成复杂任务。
最终产出
③
生成 PDF 报告
pdf
手机上发一句话，桌面 Agent 自动完成
④
IM 回复文件
IM gateway
QCon
16
InfoQ 极客传媒
全球软件开发大会

## Page 017

• 使用案例
用户输人
执行流程
场景 3
USER
①
数据下载
销售/运营每天下载报表
“帮我下载XX平台昨天的销售数据，根据要求 XXX，
生成一份数据报表，发送到 XXX 邮箱”
进行数据分析
②
匹配用户需求
从数据下载到分析再到发送，
Agent 一条龙搞定。
最终芹出
③
生成数据报表
从数据下载到数据分析再到邮件发送，Agent
一条龙搞定
④
发送到指定邮箱
imap-smtp-email
QCon
17
InfoQ 极客传媒
全球软件开发大会

## Page 018

使用案例
用户输入
执行流程
场景 4
USER
①
抓取招聘网站简历
HR 自动简历筛选
“帮我把XX 网站上近7天未筛选的简历，按如下要
求筛选出来，具体要求为：XX”
②
按要求自动筛选
自动化筛选简历，HR 只需最终
审阅微调。
最终产出
③
生成筛选报告
简历筛选自动完成，用户只需审阅微调
④
发送完成提醒
QCon
18
InfoQ 极客传媒
全球软件开发大会

## Page 019

Claw类产品对比
维度
OpenClaw
云端Claw
其他桌面端 Claw
有道龙虾 （LobsterAI）
纯命令行操作，需配置
订阅逻辑，卖云主机+模型
上手与交互体验
开箱即用，双击安装。
开箱即用，双击安装。
开发环境。
token
CLI 配置或手动修改底层
深度绑定自家模型，送免费
自由配置 DeepSeek/Kimi 等全球顶尖模
大模型自由度
一般绑定自家模型
配置文件
token，用完卖订阅服务
型，并完美兼容 Ollama 本地私有模型。
业务报表和敏感文档必须全
必须登录才可用，隐私不可控
开源，完全免费，不上传任何用户私人数据
安全性
开源
量上传至云端，极易造成企
重度依赖云端APT交互，核心业务 和埋点，仅上传给大模型必要的片段数据。
业机密外泄。
数据依然需要“出网”。
产品定位
个人助理
云端助理
桌面端助理
桌面端助理
QCon
19
InfoQ 极客传媒
全球软件开发大会

## Page 020

有道龙虾的起源
从chat工具到全场景个人助理 Agent
QCon
20
InfoQ 极客传媒
全球软件开发大会

## Page 021

• 有道龙虾的起源
团队：Al+教育
硬件产品
Hi，我是小P回
专属AI助手，解決你
的学习，
生活问题
词典笔、答疑笔
秋风怒号
拍题答疑
作业批改
知识挑战
看走茅草茅屋沟秋风所破歌
唐•杜甫
• 公元七六一年
你可以问我
• 生活困顿＜
小P老师
什么是莱法涤法？
• 忧国忧民
K12全科答疑
成都浣花溪草堂
Chat模式
12×8等丁多 ？
名词和动词的区别分别是什么？
语文
视频讲解
C換一换
讲解《茅屋为秋风所破歌》还原当时的场景
8 深度思考（R1）
1对1辅导
基于用户输入生成2分钟图文讲解视频
教育场景AI Agent
① 请输入文本
QCon
21
InfoQ 极客传媒
全球软件开发大会

## Page 022

• 有道龙虾的起源
突破垂类Agent边界，布局通用场景
现有痛点
垂类Agent能力局限，仅能解决单一场景问题，普适性不足
需求洞察
2025年AI编程Agent工具普及，非技术人员急需易用的AI办公工具
原型诞生
基于Claude Agent SDK，开发产品原型，适配普通用户交互逻辑
aCon
22
InfoQ 极客传媒
全球软件开发大会

## Page 023

有道龙虾的演进
LobsterAI
内核切换为
FisherChat
OpenClaw
作为开源项目，积极拥抱
FisherChat
OpenClaw生态
支持IM和定时任务
FisherChat
受到OpenClaw启发，增加IM和
态携紫W调用，扩展办
定时任务功能
基于claude-agent-sdk构建，支
大模型chat工具
持skill，扩展使用场景
支持多种模型，主要给产品研发
团队使用
Con
23
InfoQ 极客传媒
全球软件开发大会

## Page 024

•
FisherChat
团队内部工具
Fisherchat
Chat功能
Claude Sonnet 4.58
十 新建河话
支持多种模型，内置支持 OpenAI （GPT 系列）、Anthropic
Q 搜多聯天
（Claude 系列）、Google（Gemini 系列）、DeepSeek、
E COWORK
我能帮你做什么呢？
Ollama（本地模型）等主流提供商
白 项目
你的聯天
蠶赤对斑
Skills功能
基于claude-agent-sdk构建，支持skil，扩展使用场景
项目管理
支持为不同使用场景创建独立的 Project，配置专属 System
Prompt
谄间任何问感。
指定工作目录，让AI在明确上下文中工作
多会话管理，历史记录持久化存储
用户
QCon
24
InfoQ 极客传媒
全球软件开发大会

## Page 025

FisherChat
开源桌面Agent
• 蓓新版本
kiml K2.5
定时任务
区新溫饪务
C 按帶任务，
支持通过桌面端软件，IM 机器人设定定时任务
0宗阿任券
EIMCR
开始协作
纭势记菜
7X24 小时帮你干活的全场景个人則理Agent
多智解仲集群圖报新闻摘要
MCP
A4 E8鱼
妳配一个性务双堪问任何回通
书l a3i4za7ctbsi
支持MCP功能，允许用户安装第三方MCP工具
hpoiodt
［Ding Talk 274430672514
：84 已空衣
【初274430672514
口 制作幻好片
出 数据分析
0 创强网站
60-日报利；
IM
支持IM软件：钉钉，书，Telegram和Discord
［QQ） 77262a10b41e
［DingTalk］ 274430672514
QCon
25
InfoQ 极客传媒
全球软件开发大会

## Page 026

LobsterAl
有道龙虾
KimlK2.5
◎ 安全防护中
OpenClaw内核
9 黃発低劳
© 足河低务
内核从claude-agent-sdk切換为Openclaw运行时
% MCR
开始协作
8 我的Agent
7824小时帶附干活的全现景《人肌理Agant
多Agent
分配一个任务戴提简任何问盛
支持配置多个agent，提升不同场景的使用效率
任务记条
教習能倅集胖网抿新闻搁娈
日 制炸幻对方
致指分析
四 教育地习
6 创珠腐站
［］a3142a7C1b51%
IM多机器人
［Ding Talk］ 274430672514
飞书，钉钉，QQ等支持多机器人配置
TCing Talk: 274430672514
［Feishul a3f42a7cfb51
R 算录
QCon
26
InfoQ 极客传媒
全球软件开发大会

## Page 027

架构选型与设计实践
QCon
27
InfoQ 极客传媒
全球软件开发大会

## Page 028

架构选型
有道龙虾技术框架
Electron框架
跨平台，支持windows，mac和linux
模型支持友好
React框架
React框架实现UI层渲染
模型支持友好
Typescript
静态类型，有利于构建复杂项目
模型支持友好
TS
QCon
28
InfoQ 极客传媒
全球软件开发大会

## Page 029

• 有道龙虾架构-claude-agent-sdk内核
LobsterAl Architecture
整体架构
Elactron + Roact Qoskiop Al Asslsiant
• Renderer Process
Cowork View
Skills Vicw
Scheduled Tasks
MCP Manager
IM Sottings
Settings
SkiiNarkatnaac
Cnn Manacsrran！
SatarCenl
B Fattomms
Prontar/Thama/36n
anthropic格式
8ervices: CoworkSemvIce / ContigService /ApiService
State: Redux TooIi （7 5Iicos）
Rendering: Moridown/Mermald/ KaTex
第三方模型需要转換为anthropic格式
IPC Bridge
• Main Process
E10c10020006g8
IM 机器人
CoworkRunner
OpenAl Compat Proxy
Skill Manager
Scheduler
AJ Sesasion Enaine
Mhub Prevster LLN Ndaptor
Lactl istu/Canoeor. Mod
werrapc:OpmdNetoca
基于飞书，钉钉，Telegram等平台开放API实现
连接，状态，富媒体信息需要处理
Memory System
IM Gateway
MCP Store
Sandbox Runtime
Mamory Extroetox + usge
Mun Pattcem Chat Atuptar
MCP Saiver Managamerg
atao dseiE/HilN:carespr
SQLite Persistenco （sq JS）
沙箱
cawork.zeszions ||cawark_meseasas | usat_mennories J mrep_senveirs Facheduied_tasks （kv
IPC Channels
osnors.nessiom"|cowcrk ylream：'1:0waikpormason"1skale？|mep："| i*1ysheoiuooTnee*mtce1e
Qemu+自定义镜像
windows运行较慢，需开启硬件加速
External Services & Integrations
Claude Agent SDK
Al Model Providers
IM Platforms
Sandbox VM
CU Sobgroosss Ec.son
Antropic1 0penA/ |090p36ek 1 Qwon/GLM1Semn:1018mgl-
CEMU cout0d Errotment
aCon
29
InfoQ 极客传媒
全球软件开发大会

## Page 030

OpenClaw
一个开源的、自托管的AI Agent执行框架
从“对话”到“执行”
不只是像 ChatGPT 那样聊天，而是能接管键盘、鼠标、浏览器和终端执行任务。
全天候自主运行
支持 7×24 小时在线，甚至在你睡觉时也能自动处理邮件、监控数据或编写代码。
强大的连接性
原生支持WhatsApp、Discord、Slack等通讯工具。
持久化记忆
具备基于 Markdown 和上下文压缩技术的长效存储能力，比普通聊天机器人更懂你的习
QCon
30
InfoQ 极客传媒
全球软件开发大会

## Page 031

•
OpenClaw
数据见证奇迹-
OpenClaw 的现象级爆发
Star History
垂直式爆发
a opencaw/openclaw
300K
2026年2月起，
GitHub Star 曲线呈90度垂直上升，被社区称为〝龙虾大爆炸”。
250K
星标里程碑
72小时：狂揽 100,000+ Stars（创 GitHub历史最快纪录）。
GitHob
60天：突破300,000 Stars，正式超越 React（10年积累）和 Linux，登顶 GitHub
I50K
实用软件榜首。
100K
流量冲击
50K
官网一周内录得 2,000,000+次独立访问。
December
2026
Februacy
March
Date
必 star-history.com
QCon
31
InfoQ 极客传媒
全球软件开发大会

## Page 032

OpenClaw生态
优势
OpenClaw内核的优势
1） 生态成熟
2）功能高度复用
生态成熟
第三方支持会更好，例如微信，QQ等
Core
Skill 插件生态 （ClaWHub）：内置上万种开箱即用技能（办公、开发、运
Functions
维等）
功能高度复用，避免重复造轮子
Plugin
Plugin
迁移
封装
ClawHub
原有功能可快速迁移、封装、复用，不需要重新设计交互与调度。
新功能如多agent可直接复用
EcoSystem
Recycling/Reuse
3） 长期维护成本低
长期维护成本低
桌面端系统环境复杂，降低修复bug成本
社区活跃，问题修复、功能迭代更快
LOW
Community Support
QCon
32
InfoQ 极客传媒
全球软件开发大会

## Page 033

OpenClaw生态
OpenClaw内核的劣势
劣势
1）桌面应用vs服务
2） 问题响应速度慢
桌面应用vs服务
•000
Waiting...
LobsterAl是桌面应用，对交互响应速度要求较高
OpenClaw是个服务，一些配置变更必须重启网关，导致响应慢
Queue
桌面应用
服务
问题响应速度慢
部分功能如IM依赖第三方，bug修复需要等待
OpenClaw自身的一些bug，需要等待官方修复
Delayed
Response
Slow
Fast
：Queue一
OpenClaw问题
3） API变更频繁
V4.0-beta
OpenClaw 目前处于极高速迭代期，API变更频繁，需要投入人力进
Breaking
行版本对齐
Changes！
OpenClaw功能多，依赖复杂，运行占用资源较高
Update
Deprecated
Again？
QCon
33
InfoQ 极客传媒
全球软件开发大会

## Page 034

•
有道龙虾架构
OpenClaw内核架构
LobsterAl Architecture
Rerierer Proces8 IPC Bridge• Main Process -OpenClaw Runtime
• Renderer Process
© IPC Bridge
• Main Process
Electron
• OpenClaw Runtime
Bundlec
OpenClaw运行时
React UI
IPC Handlers
Gateway Server
40+ chanrak•rcutst rezourae•avant pushi
ws./927.0.0.1fpcet） Token Aut （48-byte hex）
ArllactPatel PanrssionMocal
Chot Emne
Segson Mamt
cron Engine
agent核心功能通过OpenClaw实现
Redux Store
Sesaicn routig •Event tormardig- Engine dispatch
coweikShceBgereslce skilsioe
OpenClawRuntimeAdapter
RPC Interface
Event Stream
chat idea （Trall
Services
OpenClawEngineManager
towutk.Senvice"agmniServc
Picoiss sporwt~soath chetk wif-rustett
HnmP calbocs
Porinission Flow
IM机器人
ssen 22:alrmpeald -Li-ssec.arpcr alreaone （alce l9am）
Sostons Mossmses
Auth&API
HTWSVG Redt
fos-twahaithssE
McpServerManagwr
NepBridgeServer
HTTP Calitack
openclaw.json
通过OpenClaw的插件实现
okto/ SSE1HTTP
wrTP. altaae rksy
User
Skills & Plugins
10pstioms
Sehodiked Taka
MCP Bridzetrostt
SQLite （bettor-sqlite3, WAL）
mM Channole
VeChat WeCom•DinTak,Foishu Telegram: Dicodd-Q0 NIMPOnC
MCP
Gateway Client
MCP Bridge： 在 LobsterAI 侧启动 MCP
server 发现工具一转为 OpenClaw 的自
Legend
-IPC ioke/WS RPC
•m--conn Synd
定义工具注入
Recponse
Catnay-•W/S Event-.Adipat- Roufer_webContents sand- IPC Brisga-.0wick.Senice lterer Reduy dspatcn_ Reanl re-rnder
QCon
34
InfoQ 极客传媒
全球软件开发大会

## Page 035

设计实践-OpenClaw
集成方案
LobsterAl Main Process & OpenClaw Runtime
• Main Process
• OpenClaw Runtime
源码集成
CoworkEngineRouter
Engine Manager
RPC （chat.send / history）
Prcc88s Ifecyde & portallccation
实现函数级别的功能调用，灵活性强
Core Managers
MCP & Memory
Runtime Adapter
Sessiens!Agenls
MCP BralneServer
同一个进程，数据共享方便，功能延迟低
SKESJMGP
Events （chat /agent/ lick）
Sessin & mossage handling:Seq cedup
侵入性较强，OpenClaw升级成本较高
OpenClaw Gateway
OpenClaw Config Sync
Config Sync （JSON + Emv）
Chat
Tools
Sessions
Cron
Modeis / Agents /Skils/IM !MCP•cpend.aA.son
独立进程 （runtime）
Hstory - Plugirs: WCP Bndge: M Chamets
Scheduled Tasks
IM Integration
Permission （approvaly|
Lifacycle：
只能通过OpenClaw提供的接口调用功能
SQLite Persistence
OpenClaw runtime独立，OpenClaw升级成本较低
HTTP Callback （MCP exec）
openclaw.json （Configuration）
通过patch形式实现必要的功能修改（OpenClaw版本）
Gateway Client （WebSocket）
WebSocket
已有功能和OpenClaw独立存在，方便功能迭代和替換
ws%127:001：（pom
Workspace
Skills & Plugins
Process Spavn & Environment
Al Providers
IM Channels
RPC Request-，
一 Evont Stream
•--. congia Sune.
QCon
35
InfoQ 极客传媒
全球软件开发大会

## Page 036

•
设计实践-OpenClaw
runtime构建
Openclaw Runtime Build Pipeline
• Phase 1:Source
• Phase 2: Build & Package
• Phase 3:Post-Build
源码管理
Read Pinned Version
Cache Check
Symlink Current
packagajson - ogendaw.version
version + palches hash matdh skio
支持版本配置
Build from Source
Ensure Source Version
pegm instail- pnpm buitd—- wlbule
Extract.asar
Not exist- git clone -depth1
Windaws only: ESM cannot load from .asar
Wrong lag 一 fetch &. checkout
Pack & Extract
Correct tag- skip
npm peck.tgz - tar exract to ruintime dir
OPENC.AN_SKIP_ENSURE=1 to Bypuss
Bundle Gateway
插件管理
ebuild： -1100modulkes•singleomjis
Install Production Deps
Load: 2-135.428 8h:1005 unbundlnd）
Apply Patches
npm install -omit=dev （cross-platform）
OpenClaw插件配置
Reset source git apply per patch
Install Plugins
macOS-darwin
Windows - win32
Linux linux
Version-specific patches directory
8 I ptugins （DingTalk, Felshu. cQ..）
cinammaaauononwio.ou
Cached:versanmi
Pack gateway.asar
Source Path
Pre-compile Extensions
@electron/asar pack keap cantro-ui bare
OPENCLAW_SRC or Jopenclaw （oefault）
TypeSeript - JavaScript （esbuild）
Patch管理
Validate Layout
npm run openclaw:ensure
Check.asar, node_modules.entry fies
PruneRuntime
npm run openclaw:patch
patch支持不同OpenClaw版本
npm run openclaw:runtime:starget
Build Targets
Output
macemns4 mac-x54
OPENCLAW_FORCE_BUILD=1 to ovoride cache
vendorlopencaw-runtime/current
QCon
36
InfoQ 极客传媒
全球软件开发大会

## Page 037

设计实践-OpenClaw windows启动慢
Windows 启动慢的三个根因
原因1：~1100个 ESM 模块逐个加载
80-100s
每个模块经历完整的 读取一解析一编译一链接 流程
NTFS 文件系统对大量小文件的随机读取性能极差（相比 macOS APFS / Linux ext4）
V8 需要为每个模块独立编译 JavaScript 一 字节码，没有跨文件缓存
macOS/Linux 同样的1100 模块加载仅需~20s, Windows 上的额外开销来目 NTFS IO
原因 2:Electron utilityProcess 的 V8 隔离开销
25X
utilityProcess vs child_process 冷编详同一 28MB bundle: 163s vs 34s
utilityProcess 运行在受限的V8 Isolate 中，ESM 编译优化路径不同于标准Node.js
Windows 驱动器号 C：被 ESM loader 误解为 URL scheme 无法直接加载.mjs 文件
utilityProcess 在 macOS/Linux上表现正常，这是 Windovs 专属的严重性能退化
原因 3:asar 解压 +Windows Defender实时扫描
～120s
gateway.asar 解压 ～3000个文件触发 Defender 实时扫描
Electron utilityProcess 无法从.asar 内加载ESM（驱动器号问题），必须解压到磁盘
NSIS 逐个安装数千小文件在 NTFS上极慢，传统 extraResources 方案不可用
macOS/Linux 的 utilityProcess 可直接从 asar 读取 ESM 模块，无需解压
叠加影响：冷启动＞160秒
aCon
37
InfoQ 极客传媒
全球软件开发大会

## Page 038

• 设计实践-OpenClaw windows启动优化
四项核心优化方案
1 ChildProcess 替代 UtlityProcess
单文件 Bundle 替代1100模块
child_process.spawn + ELECTRON_RUN_AS_NODE
esbuild 打包为 gateway-bundle.mjs（-27MB）
避免 V8 Isolate 开销和 ESM loader 限制
消除模块图解析和 NTFS 小文件 V/O
163$ 34s（5x）
80-1008-22-12$（8x）
③ B过 asar全量解压
④）
V8 Compile Cache 二次启动
有 bundle 时直接加载，无需解压 gateway.asar
enableCompileCache （CJS） + NODE_COMPILE_CACHE（ESM）
+ NSIS TAR 归档+Defender 排除路径
首次编译后持久化字节码，后续跳过编译
1205 10s（12x）
128 -55（2x）
优化叠加效果
原始
+ ChildProcess
+ Bundle
+ Skip asar
+ V8 Cache
>160s
~34s
~12s
~10S
~5S
关键支撑：CJS Wrapper （gateway-launcher.cjs）
Windows 驱动器号问题的解决方案—运行时生成CJS 包装器，内部 pathToFileURL（） 转换
enableCompileCache（）
argv 1i Patch
setinterval Keep-Alive
pathToFileURLC +import（
QCon
38
InfoQ 极客传媒
全球软件开发大会

## Page 039

设计实践-OpenClaw启动流程
OpenClaw Gateway启动流程（分平台）
doStartGateway（）
1. resolveRuntime（）
2. Health Check 已有进程
3. ensureBareEntryFiles（）
4. resolveOpenClawEntry（）一平台分支点
macOS / Linux
Windows
Entry: openclaw.mjs（ESM 直接）
Entry: gateway-launcher.cjs〈生成）
或 gateway.asar/openclaw.mjs
內部 import（gateway-bundle.mjs）
Fork: utilityProcess.fork（）
Fork: child_process.spawn（）
asar 选明读取 无需 wrapper
ELECTRON_RUN_AS_NODEwindowsHide
5. waitForGatewayReady（）
Health Probe × 5并行
6.自动重启
600ms 轮询，300s超时
3s 5s 10s:20s-30s 退避
环境变量注入：
NODE COMPILE_ CACHE•OPENCLAW_GATEWAY_TOKEN OPENCLAW_SKIP_ MODEL_PRICING• TZ-PATH （shims + python + node）
QCon
39
InfoQ 极客传媒
全球软件开发大会

## Page 040

•设计实践-MCP
LobsterAI MCP Architecture
MCP功能
Modei Gontex: Protocol. Brioge Pattem- Tool Proxy
• Renderer
• Main Process
• OpenClaw Runtime
MCP管理
McpManager
McpStore
McpServerManager
----
opencawgon
mcp-bridge Plugin
registarTodl（）- mop_lserver）_｛toofy
提供MCP的应用市场
McpService
IPC
允许用户安装自定义的MCP
McpBridgeServer
OpenClawConfigSync
Agent （LLM）
mcpSlice （Redux）
HTTP Bridge
mcpRegistry
SQLite
IPC Handlers
• External MCP Servers
EnterpriseConfig Sync
Secret Env Vars
wCP SDK
stdio
SSE
NCP_BRIDCE_SEORET
Streamable HTTP
Marketplace
Teviy:CIHub:Slck
@modelcontextprotocol/sdk: stdlio /SSE/ Streamable HTTP
ICP Protocal （les: Tocls•cal Toot）
Legend
— IC
--•-- Config Sync
HITP Bridge
— MCP SDK
［ Main Proces8
OpenClaw
Exernal MCP
QCon
40
InfoQ 极客传媒
全球软件开发大会

## Page 041

设计实践-MCP核心设计
MCP Core Design
Main Process Service Layer OpenClaw Plugin Bridge collaboration
• Main Process 一服务管理层
src/mainlibs！
OpenClaw Runtime
Agent側
LIFECYCLE
McpServerManager
CONFIG
OpenClawConfigSync
Transport 连接
写入 openclaw.json
stdic
SSE
HTTP
plugins.entrtes/mep-brdge1.conlig
PLUGIN
mcp-bridge
工具发现
配置内容
写人配置
client.listTools（） Manifest］
tools （manifest）
1. 读取配置
工具执行
openclaw. json - config
Secret 注入
callTool（server, tool, args）
env LOBSTER_MCP_BRIDGE_SECRET
2. 注册工具
api.registerTool（） mcp_｛server）_｛tool｝
callTool
callbackUr
3.工具调用时
POST callbackUn + secret- result
McpBridgeServer
4.返回结果
监听地址
HTTP response 一 Agent stream
127.0.0.1:srandom-port
端点＆鉴权
POST Imcp/execute
POST /mcplexecute
gecret骑证
tool rosult
Legend
內部鸡用
-- -配置同步
— HTTP 谐求
----- 结果返回
Main Process
OpenClaw
QCon
41
InfoQ 极客传媒
全球软件开发大会

## Page 042

• 设计实践-MCP启动流程
MCP Startup Flow
Application Bootstrap — Tool Discovery - Bridge Setup — Plugin Registration
• Main Process
OpenClaw Runtime
（1 应用启动
2 连授＆发现
启动 Bridge
写入配置
注册工具
McpStore
McpServerManager
MicpBridgeServer
OpenClawConfigSync
mcp-bridge Plugin
读取已启用的
创建 Transport 连接
启动本地 HTTP服务
生成 openciaw.json
加裁插件配置
MCP 服务器列表
调用 listTools（）发现工具
127.0.0.1 随机端口
含 callbackUn+工具清单
registerTool（）注册全部工具
* mopsok
External MCP Servers
HTTP Callback
openclaw.json
POST /mcp/execute + secret
plugins.mcp-bridge.config
stdio
SSE HTTP
运行时工兵调用回调
1 读取服务器
一③2连接＆发现工具
③ 启动HTTP Bridge
写入openclaw.json
注册 MCP工具
ReadyY
Main Process
OpenClaw
External
QCon
42
InfoQ 极客传媒
全球软件开发大会

## Page 043

设计实践-MCP 工具调用
MCP Tool Invocation Flow
Agent Request - Bridge Proxy - MCP Server — Response
® OpenClaw Runtime
• Main Process
• External MCP Servers
LLM 决策调用工具
Request
Agent选择调用 mcp_｛srv_｛tool｝
插件发起 HTTP 请求
3 验证 Secret
4
执行工具
5 执行& 返回
HTTP POST
MCPSDK
mcp-bridge POST /mcp/execute
McpBridgeServer
MicpServerManager.caliToo！（）
MCP Server 处理井返回结果
HTTP Response
—Response
LLM.洪策
箱件 POST
验证 Secret
③ callTooll）
③ MCP执行
结果返回 Agent，
OpenClaw
Main Procesg
External MCP
aCon
43
InfoQ极客传媒
全球软件开发大会

## Page 044

设计实践-IM会话同步
OpenClaw Gateway
LobsterAI Main Process
Channel Plugins
OpenClawRuntimeAdapter
10个IM平台插件
WebSocket
• pollChannelSessions（）
Telegram /Discord /Dinglalk....
WS://127.0.0.1
• ensureActiveTurn（
•prefetchChannelUserMessages（）
一流式事件
Chat Engine
• reconcileVVithHistory（）
chat delta /final
接收消息+调用 LLM
RPC 请求
History （isonl）
chat.history
ChannelSessionSync
chat.history AP］
sessions.list
会话映射：Gateway Key 本地 Session
权威数据源
SQLite
sessions + messages + mappings
UI 数据源
QCon
44
InfoQ 极客传媒
全球软件开发大会

## Page 045

•
设计实践-IM会话同步机制和局限性
流式事件
chat.history
sessions.list
WebSocket 传输
WebSocket 推送
RPC 请求
RPC请求
通信通道
• chat delta / final
•权威消息列表
•活跃会话列表
• Token Auth
• agent lifecycle
• limit=50 条
•limit=200 条
• Auto-reconnect
•tool events
•user +assistant
•10s轮询周期
• 心跳 60s
实时推送
权威数据
发现机制
传输通道
流式事件— 实时但可能丢失（WebSocket断连/重连）
chat.history— 权威但有延迟（limit=50 滑动窗口）
sessions. list —被动发现（10s 轮询，limit=200）
WebSocket 传输—自动重连2s 30s，可能中断
QCon
45
InfoQ 极客传媒
全球软件开发大会

## Page 046

设计实践-IM会话同步问题
用户消息丟失
模型消息丟失
顺序错误
•流式事件先到，SQLite 无用户消息
• chat state=final 不可靠
• 助手回复先于用户问题显示
• prefetch 时 Gateway 可能未写入
• Turn 卡在 running 永不完成
• 多轮消息时序交错
HIGH
HIGH
MED
消息重复
历史截断
•轮询多次发现同一会话
• Gateway 重启返回条目少于本地
• 断连重连后事件重放
• 盲目 replace 会永久丟失数据
MED
MED
Con
46
InfoQ 极客传媒
全球软件开发大会

## Page 047

设计实践-History-First 与对账算法
reconcileWithHistory 流程
两种数据来源对比
Guard 检查
非 Channel Session Skip
流式事件
chat.history
亨
（WebSocket 推送）
（API拉取）
x History
chat.history APl, limit=50
• 仅包含助手响应片段
• user + assistant 全量
补全+修正
• 无用户消息
•唯一获取用户消息的途径
•可能丟失 /不完整
•经清洗后事务写入
文本清洗
Discord / QQ / Feishu / POPO
不完整的一半
完整的真相
比较本地
position + content 逐条对比
亨
History-First 原则
三分支结果
chat.history =唯一真相源 （user + assistant）
一致一 Skip
更少 Skip
不同一写入
流式事件只有助手响应片段，没有用户消息。
chat.history 包含完整的 user + assistant 数据，
无需操作
保护本地数据
事务写入
对账=用 history 完整数据补全+修正本地 SQLite。
QCon
47
InfoQ 极客传媒
全球软件开发大会

## Page 048

设计实践-事件缓冲机制
Phase 1：缓冲
Phase 2：预取
Phase 3：回放
pendingUserSync = true
reconcileWithHistory（）
pendingUserSync = false
Gateway 推送 chat event
chat.history API 获取消息
按 seq 排序缓冲事件
ensureActiveTurnO
对比 Gateway vs 本地 SQLite
Chat + Agent payloads 有序回放
所有事件进入缓冲区
用户消息写入 SQLite
UI 实时更新（200ms 节流）
bufferedChatPayloads［］
emit（'message） UI通知
用户消息始终在
bufferedAgentPayloads［
助手消息之前
最多重试2次
按seq编号，保留到达顺序
保证消息顺序正确
缓冲：pendingUserSync=true 期间所有 chat/agent 事件进入
bufferedChatPayloads / bufferedAgentPayloads
预取：reconcileWithHistory 获取用户消息写入 SQLite（最多2次重试）
回放：pendingUserSync=false 后按 seq 排序合并回放，保证消息顺序正确
QCon
48
InfoQ 极客传媒
全球软件开发大会

## Page 049

设计实践-双路径完成机制
Path A： 正常完成
Path B： 备用完成
触发：chat state = final
触发：agent lifecycle phase =end
handleChatFinal（）
— setTimeout（3000ms） 等待 Path A
- resolveFinalTurnText（）
3s 后仍未完成？
reconcileWithHistory（
completeChannelTurnFallback（）
emit（complete）
- reconcileWithHistory（） emit
Double Guard（防重复完成）
active Turns.has（sessionld）—先到先得，后到者退出
Turn 完成 status='completed' IPC通知 UI
缓冲：pendingUserSync=true 期间所有 chat/agent 事件进入
bufferedChatPayloads / bufferedAgentPayloads
预取：reconcileWithHistory 获取用户消息写入 SQLite（最多2次重试）
回放：pendingUserSync=false 后按 seq 排序合并回放，保证消息顺序正确
QCon
49
InfoQ 极客传媒
全球软件开发大会

## Page 050

，设计实践-数据存储与设计决策
数据表
内存缓存
设计决策
History-First
cowork_sessions
activeTurns
chat.history 是唯一权威数据源
PK:id status|title
Mapssessionld, TurnState>
channel_session_key | metadata
唯一写入路径
2
1.N
bufferedChatPayloads
replaceConversationMessages（）
Array per Turn （seq ordered）
cowork_messages
3
防数据丢失
FK: session_id | type | content
bufferedAgentPayloads
Gateway <本地 Skip 对账
sequence | metadata
Array per Turn （seq ordered）
-T:N
④ 双路径完成
chatFinal + Fallback + Guard
channelSessionMap
im_session_mappings
Gateway Key local Session
3 事件缓沖
PK:im_conversation_id + platform
pendingUserSync+ seq回放
FK:cowork_session_id |agent_id
pendingUserSync
boolean per Turn
平台文本清洗
Discord / QQ / Feishu / POPO
im_config
key-value （JSON） per platform
QCon
50
InfoQ 极客传媒
全球软件开发大会

## Page 051

•
设计实践-IM会话同步数据流
IM 消息到达
Engine 处理+写入
3
WebSocket 推送
用户在IM平台发送消息
Chat Engine 调用 LLM
流式事件推送到 LobsterAI
Channel Plugin 接收并转发
响应写入 History （isonl）
chat delta / agent lifecycle
Telegram/ Discord / Ding lalk .n.
Gateway 拥有完整生命周期
事件可能丟失或乱序
事件缓冲＋预取
5回放+流式响应
6 对账＋完成
pendingUserSync = true
pendingUserSync = false
reconcileWithHistory（）
缓冲事件+ chat.history 预取
按 seq 排序回放缓冲事件
Gateway 权威数据覆盖预览
用户消息写入 SQLite
UI 实时更新（200ms 节流）
emit（'complete"） Ul最终更新
Con
51
InfoQ 极客传媒
全球软件开发大会

## Page 052

设计实践-配置同步与密钥安全
三层分离架构
User Settings
配置层
OpenClawConfigSync
OpenClawConfigSync
构建 openclawjson，所有密钥使用$［VAR｝
占位符替代
Provider Registry
Config Builder
AGENTS.md Sync
密钥层
Atomic Wrie
In-Memory
Secret Environment Variables
openclawjson中敏感信息使用环境变量保存
OpenClaw启动时动态注入
openclaw.json
secretEnv Vars
apiKey："$（PLACEHOLDER｝"
APIKEY："Sk-real.."
运行时层
fork/spawn
Gateway Process
OpenClaw Gateway Process
Gateway 启动时从环境变量解析占位符，获取
密钥永不落盘
S WAR/ - process.env VAR Real Key
真实密钥发起 API调用
aCon
52
InfoQ 极客传媒
全球软件开发大会

## Page 053

设计实践-密钥安全
用户输入 API Key
ConfigSync 分流：占位符vs真实密钥
openclaw.json（磁盘）
secretEnvVars（内存）
"apiKey”："S（LOBSTER_APIKEY_OPENAI
LOBSTER_APIKEY_OPENAl'sk-proj..
"token”"$（OPENCLAW_GATEWAY_TOKEN｝"
OPENCLAW_GATEWAY_TOKEN："a3f8c1.."
④
Gateway 进程启动•env =｛..secretEnvVars｝
Gateway 解析 $｛VAR｝ process.env［VAR］
真实密钥全程仅在进程内存中，密钥永不落盘
磁盘一仅占位符
內存一真实密钥
网络一TLS 保护
QCon
53
InfoQ 极客传媒
全球软件开发大会

## Page 054

设计实践-配置同步
配置同步流程
LLM Provider
IM Channels
Agents
MCP
Skills
Sandbox
触发时机
Build managedConfig
Read Existing
用户修改LLM供应商/IM 频道配置
Agent / Skill/ MCP 配置变更
工作目录变更/会话启动前
｛..existingGateway，..managedConfig｝
原子写入
YES
Changed？
NO
问题：写入中途崩溃writeFileSync写到一半崩溃
string equality
半截 JSON Gateway 启动失败
解法：tmp + rename
先写入，tmp-｛timestamp｝，再 fs.renameSync0
Atomic Write
Skip （Zero I/O）
覆盖。rename 是文件系统的原子操作一要么完
成，要么不发生
Post-sync: sessions.json•exec-approvals•AGENTS.md• Per-agent workspaces
return ｛ok,changed, bindingsChanged｝
QCon
54
InfoQ 极客传媒
全球软件开发大会

## Page 055

• 设计实践-AGENTS.md
AGENTS.md 受控注入
AGENTS.md
USER ZONE
用户自由编写，sync 不修改
用户内容与系统配置
# My Project
用 HTML 注释标记分区，让用户自由编写的内容与系
This is a React + TypeScnipt project...
统自动管理的策略安全共存。
## Build Commands
npm run devstart dev server
npm run build — production build
注入的策略
<l- LobsterAl managed: do not edit below this line->
System Prompt—用户在设置中配置的系统提示词
Web Search Policy一指导模型使用browser/web_fetch
MANAGED ZONE
每次 sync自动重建
Exec Safety Policy—删除操作前必须确认
Memory Policy—记忆持久化的 write-before-confirm
System Prompt
Web Search Policy
Exec Safety Policy
Scheduled Task Prompt一定时任务引擎指引
Memory Policy
Scheduled Task Engine Prompt
设计保证
Skill Overrides: qqbot-cron x feishu-cron-reminder x
幂等：內容相同时跳过写入，不改 mtime
原子：同样使用 tmp rename 模式
幕等：相同则跳过
原子：tmp rename
降级：bundled template 兇底
降级：无用户内容时加载 bundled 模板
QCon
55
InfoQ 极客传媒
全球软件开发大会

## Page 056

•
设计实践-变更检测与重启策略
重启策略
syncOpenClawConfig（）触发
无操作
collectSecretEnvVars（）
configSync.sync（）
配置和密钥均未变更-不重启、不写入、零开销
YES
needsHardRestart？
NO
热加载
secrels I bindings | explicil
仅 openclawjson 內容变更 一原子写入文件，
Gateway 文件监听自动加载
Active
Config
Sessions？
Changed？
硬重启
延迟重启
立即重启
热加载
无操作
轮询爷待会话锫束
stcp -setEnv-spawm
File watcher 感知
Zero 10
密钥变更/ IM 绑定变更/显式请求—停止进程 一注
入新 env 重新 spawn
密钥变更一硬重启 | 绑定变更一硬重启|配置变更一热加载|无变更一零开销|有活跃会话一延迟
aCon
56
InfoQ 极客传媒
全球软件开发大会

## Page 057

）4
Vibe Coding实践
QCon
57
InfoQ 极客传媒
全球软件开发大会

## Page 058

Vibe Coding 买践
有道龙虾：Vibe Coding
什么是Vibe Coding？
什么是 Vibe Coding？
由 Andrej Karpathy 提出：
由Andrej Karpathy 提出
编程不再是逐行编写代码，而是与 Al 协作的“对话式创作”
编程不再是逐行编写代码，而是与AI协作的“对
话式创作”
function（）..）
核心转变：
Al：好的，我来生成….
结果：运行成功！
从关注语法转向关注意图和结果
Code: Console.og（Hello Vibel）；
Vibe Coding目标
核心转变
有道龙虾
利用 vibe coding 快速验证商业想法
｛；=>
意图
利用Vibe Coding 快速验证产品想法
从关注语法转向
追求“极速迭代”而非“过度工程化”
class
！2
追求“极速迭代”而非“过度工程化”
探索vibe coding的能力边界
if/else
积累vibe coding的软件管理经验
for loop
关注意图和结果
探索 Vibe Coding 的能力边界
结果
error
耶：
积累 Vibe Coding 的软件管理经验
QCon
58
nroo
遵极客传婃
全球软件开发大会

## Page 059

AI能力开发等级
AI编程 vs自动驾驶：等级对照
AI Team
L5 Al开发团队：多Agent协作，无需人类干涉
L5 完全自动：无需方向盘，全自动
验收
L4 全自主Agent:Al到端完成，人类验收结果，无需干预
L4 高度自动：Al全程驾驶，特定场景无需人类
关 点
结果
冶醟瘙菅
L3
L3 半自主Agent（SDD>50%）：Al主导，人工盟督关健点和给果
L3有条件自动：AI主导驾驶，人类准备搂管
L2
2
L2结对开发：Al对话生成，人工检意
L2部分自动：AI控制方向和速度，人类监控
L1 代码补全：人写代码，AI辅助补全
L1辅助驾驶：人类驾驶，AI辅助
QCon
59
nroo
遵枚客传婃
全球软件开发大会

## Page 060

Vibe Coding 实践
AI编程成本
TOKEN COSTS ARE SIGNIFICANT - CANNOT IGNORE
Coding Plan
成本较低
限流，限速，限制产品
适合个人开发和小团队
Tokey
S
适合中小规模开发项目
©
Token
Tohen
企业端Token付费方案
Cost
（LLM）
成本较高
Token Cost
服务较为稳定
适合大团队中大规模的项目
未来开发
传统开发，成本优势
Al开发，效率优势
aCon
60
InfoQ 极客传媒
全球软件开发大会

## Page 061

Vibe Coding 实践
舒适期
舒适期
项目规模小，复杂度低
代码生成质量高
开发流程：需求->计划->执行->验证 循环
项目规模小，复杂度低
开发任务分配
类似工单系统，智
代码生成质量高＜
开发任务分配
”能派单，高效流转
类似工单系统，智能派单，高效流转
SMALL
APP
功能开发跟人无关
需求
功能开发跟人无关
代码合并
代码合并
验证
循环
计划
冲突较少，AI基本可以解决
MERGED：
冲突较少，ai基本可以解决
女
回归测试冲突少，
回归测试问题少，成本低
执行
成本低
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 062

Vibe Coding 实践
痛苦期
《痛苦期*
项目代规模大，复杂度高
无法按时交付软件
项目规模大，复杂度高
发版时，多个PR合并冲突多
Al倾向使用局部最优方案，忽略整体架构
拆东墻补西墙
头疼医头脚疼医脚
Al倾向使用局部最优方案，忽略整体架构
已有功能会被修改
拆东墻补西墻
无法按时交付软件
AI模型幻觉
头疼医头脚疼医脚
发版时，多个PR合并冲突多
分析代码时有概率产生错误信息
已有功能会被修改
Al模型幻觉
openclaw-runtime 出现”重试成功”时通常是用全新的 runtd（比如新用户消息触发的 run），复用同一
分析代码时有概率产生错误信息
runld 成功的情况极其罕见。
这句话有什么依据吗？
Thought for 7s 2
没有依据，我瞎说的。这是我在没有充分证据的情况下给出的安慰性结论，应该直接说“不确定”。
让我从日志里实际看看gateway重试时的行为
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 063

Vibe Coding 买践
项目管理经验
PILLARS OF SOFTWARE QUALITY: SPEC-DRIVEN, TEST-DRIVEN， & TECHNICAL REVIEWS
PELABSLPP
Spec-Driven Development
RELIABILITY
CLARITY
EFFICIENCY
ROBUSTNESS.
ROBUSTNESS
规范驱动开发，尤其是核心业务模块
SPEC-DRIVEN DEVELOPMENT （SDD）
TEST-DRIVEN DEVELOPMENT （TDD）
文档中包括功能，设计，测试，边缘用例等
min test c；
BEHAVIOR
return code •：：
X
Test-Driven Development
TEST
TDD
BEHAVIORS
PR时提前发现问题
单元测试和集成测试尽量覆盖
TECHNICAL REVIEWS
E2E测试，覆盖核心功能
Refactor
Principles
方案评审
开发需要对模型方案进行详细评审
Core Engineering
开发需要对项目架构层面有详细了解
重要模块需要设计评审
TECHNICAL REVIEWS
aCon
63
InfoQ 极客传媒
全球软件开发大会

## Page 064

75
未来规划
QCon
64
InfoQ 极客传媒
全球软件开发大会

## Page 065

从 Chatbot 到 Claw （Agent OS）
GAI产品正在经历三个阶段的演进
令
ChatBot
Agent
Claw （Agent OS）
AI能聊天，能查资料，但
AI干完活就走，无记忆，
常驻式个人 Agent，记得
本质上只是问答和信息检索
也没办法自己主动干活
你的习惯，能主动做事
REMEMBER
PROACTIVE
DATA
QCon
65
InfoQ 极客传媒
全球软件开发大会

## Page 066

Claw 类产品的新机遇
Agent 向各领域渗透
Skill 即服务
Skill Store
Package
SKI！
Skill
Skill
Package
Package
Package
Package
鉛62包图
2026年 Agent 正在快速向各领战进
行渗透。真正的价信在于端到端执行
丸
声明式 Skil框架让非开发者也能定
Success
义AI能力，健生了 Skill 市场和生态，
复张任务態，而不仅是对话。
类似 App Store機式。
开源生态共建
AI工作流
Agen
众300K+
OpenClaw
Al Agent
Orchestrator
OpenClaw 正在构建一个开的 Agent
未来的工作方式可能不是人使用AI 工
生态，
Github star 数起过300K，且迭
具，而是 Agent饿调各种工具为人服
代速度非帛抉。
务，人只需表达意图。
QCon
66
InfoQ 极客传媒
全球软件开发大会

## Page 067

Q&A
欢迎 Star & Contribute & 试用
Github 仓库
https://github.com/netease-youdao/LobsterA
有道龙虾官网
https://lobsterai.youdao.com
QCon
67
InfoQ 极客传媒
全球软件开发大会

## Page 068

InfoQ 极客传媒
QCon
全球软件开发大会
THANKS
大模型正在重新定义软件
Large Language Model Is Redefining The
Software

## Page 069

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
