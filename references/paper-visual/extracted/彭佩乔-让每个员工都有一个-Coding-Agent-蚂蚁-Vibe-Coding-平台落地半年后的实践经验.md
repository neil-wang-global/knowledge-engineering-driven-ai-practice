# 彭佩乔-让每个员工都有一个-Coding-Agent-蚂蚁-Vibe-Coding-平台落地半年后的实践经验

> Page-by-page visual information extraction from rendered slide/page images. Text is OCR-assisted and preserves visible page order; diagrams/tables are represented by their visible labels and relationships as line-by-line text.

## Page 001

nfoQ 极客传媒
QCon
全球软件开发大会
让每个员工都有一个 Coding Agent
蚂蚁集团 Vibe Coding 平台落地半年后的实践经验
彭佩乔（乔杨）
技术专家
蚂蚁集团 - 支付宝- 体验技术部

## Page 002

极客邦科技 2026 年会议规划
促进软件开发及相关领域知识与创新的传播
06月？上海
RR 1000人
08月9深圳
81000人
AiCon
•Al Infra 系统工程
AiCon
•Agentic Al
-多 Agent 协作与实践
•轻量化与高效推理
全球人工智能开发与应用大会
•多模态融合
•多模态应用
全球人工智能开发与应用大会
-模型训练与推理创新
-Al + IoT 场景实践
会议时间：6月26-27日
•数据平台与特征服务
会议时间：8月21-22日
•AI工业化落地
010月9上海
RR 1200人
012月9北京
R 1000人
•Al Agent
QCon
•Vibe Coding
AiCon
•大模型架构创新
•智能可观測
•多模态 AI 产业融合
全球软件开发大会
•推理基建
全球人工智能开发与应用大会
•具身智能
•模型攻防
• Al for Science
会议时间：10月22-24日
•AI x 创造力
会议时间：12月18-19日
•大模型安全

## Page 003

InfoQ 极客传媒
QCon
全球软件开发大会
01
我们做了一个什么样的平台
02
我们落地过程中遇到了什么样的挑战
03
我们选择的解决方案和实际效果
目录
04
基于真实用户业务推动的架构升级
05
一些行业趋势与判断
06
经验与心得分享

## Page 004

前端纯静态页面
01
一句话介绍
快速搭建展示型网页，即刻预览
用自然语言对话，生成前后端
一体的网站，
前端＋自有接口
02
灵活接入已有后端，实现数据交互
用户群体
前后端一体化
03
自动生成数据库与API，全栈闭环
面向集团内部员工，不需要任
何技术背景
智能体 AI应用
04
结合 Al Agent，制作创新形态交互
acon
InfoQ 极客传媒
全球软件开发大会

## Page 005

像聊天一样开发
所见即所得
自然语言对话，实时预览网站效果
可视化拖拽编辑交
SIL
聰天
Experience the next generation of digital aesthetics. A
关注
发现
附近
Q
乔柄
pulsating holographic universe built with React and
给我做一个演示用的“小红书"App的 demo
Framer Motion.
亡
T
舀
Geminl 3 Flash 2026-01-09 13336
NITIALIZE SYSTEM
我将为您打造一个充满活力、祝觉精美的“小红书“网格社交应用
員分享
大北加行攻。1洱海边的
色背美和圆湖的卡片设计。
•核心布局：实现标志性的瀑布流（Masonry Layout）首页，让
点遮编辑
功能规划
分享协作
1. 首页瀑布流：展示发现页的内容卡片。
多人 Vibe 协同、实时分享预
>日穿搭1早秋必备的室
周未去 儿1報在市中心
Al Gemini 3 Fiesh v o
②帮助+ @预览 ◎设置
重新发布
添加协作
协化名可姿者利修改剑作内容
Q 输入工号或花名搜索
曰 数据管理
s入？添加图片Q
2025.7 发布，上线半年，内部MAU过万，其中一半是非技术背景的用户，平均对话12轮可以发布一个网站
Qcon
InfoQ 极客传媒
全球软件开发大会

## Page 006

一位PMO 同事 Vibe 了一个专属 战役管理平台
纯自然语言对话了 2000+轮，烧了6亿 tokens，最终 vibe 出一个生产级的重磅平台。
01
ENCOUNTERED ISSUE
Tokens 消耗极快
重度用户一个月花了¥5000，成本压力巨大。
acon
InfoQ 极客传媒
全球软件开发大会

## Page 007

ik
System Prompt
Stable
aaa
abb
2k
Tools Schema
Stable
Before
10k
Repo Map
Stable
Agent
Afte
5k
Open file
Stable
aaa
abb
200
User Message
Change
精准化 Search / Replace
AI Coding 场景Cache命中率可以做到很高
~80% Tokens Off
200/18,200 ~1%
Qcon
InfoQ 极客传媒
全球软件开发大会

## Page 008

一位 PMO 同事 Vibe 了一个专属战役管理平台
纯自然语言对话了 2000+轮，烧了6亿tokens，最终 vibe 出一个生产级的重磅平台。
02
超长轮次变傻
百轮对话后，Agent 出现健忘和逻辑混乱。
acon
InfoQ 极客传媒
全球软件开发大会

## Page 009

/tool_results/
•/search.json
./data.json
./analyze.json
•1.
1 Memory
Memory.md
+UserMessage
/skills/
./supabase.md
••••
Index
./tailwind.md
./shadcn.md
•1
通用型压缩方案，意图保留不稳定
不一定适配垂类平台
最近用户消息＋意图＋项目总结＋索引
/code_indexing/
.1.
acon
InfoQ 极客传媒
全球软件开发大会

## Page 010

一位 PMO 同事 Vibe 了一个专属 战役管理平台
纯自然语言对话了 2000+轮，烧了6 亿 tokens，最终 vibe 出一个生产级的重磅平台。
Q3
ENCOUNTERED ISSUE
巨型项目卡顿
文件数量庞大，Agent 响应变慢还改的不准
acon
InfoQ 极客传媒
全球软件开发大会

## Page 011

a.ts
/tool_results/
Tool Call
./search.json
./data.json
./analyze.json
./⋯
index
import a，
import b；
ToolA？？
Tool A
Tool_A_Result.json
Results
⋯⋯..
通过构建 file graph 提高 Agent分析查找效率
在简单易撞关键词场景 ref 效率远高于 grep
Agent 可以从上下文中主动加载/卸载外部信息
Tool / MCP 等体积较大的执行结果不再占用宝贵的上下文
acon
InfoQ 极客传媒
全球软件开发大会

## Page 012

一位 PMO 同事 Vibe 了一个专属战役管理平台
纯自然语言对话了 2000+轮，烧了6亿 tokens，最终 vibe 出一个生产级的重磅平台。
Q4
ENCOUNTEREDISSUE
数据库门槛高
业务人员无法用精确的技术语言描述表结构。
acon
InfoQ 极客传媒
全球软件开发大会

## Page 013

// DDL.sql
DataBase Snapshot V1
CREATE TABLE xxx
需要数据持久化
DataBase Snapshot v2
// DDL.sql
CREATE TABLE XXX
我要做个投票
ALTER TABLE yyy
DataBase Snapshot V3
需要数据持久化
我要做个投票
数据库建表
-1!1！！！ ！
User / Options / Votes
// service.ts
CRUD API
api.CRUDC）；
/vlew.tsx
DataBase Snapshot V..
根据意图全自动完成SQL/CRUD 设计，每个版本均有快照可以回滚
确保用户的意图可以准确的变成对应的持久化设计
acon
InfoQ 极客传媒
全球软件开发大会

## Page 014

一位PMO 同事 Vibe 了一个专属 战役管理平台
纯自然语言对话了 2000+轮，烧了6亿 tokens，最终 vibe 出一个生产级的重磅平台。
用户的项目顺利上生产，开始服务真实业务。随着在 Muse 平台上复杂的大型项目越
来越多，我们也逐渐将服务这个场景的经验升级成了项目中新的 Agent架构。
一-- 新架的上线阶段数指表现（2月一次年期）
+109%
+60%
-23%
Tokens 账单
人均消耗
acon
InfoQ 极客传媒
全球软件开发大会

## Page 015

Agent
Memory
Context
Agent架构跃迁
文件即记忆
超大工程管理
去 workflow
自主決策
Skills化
自动卸载
记忆召回
内置脚手架
最佳实践
工程索引
随着基模能力越来越强的一些经验：不用再
让 Al自行决策记忆的加载与卸载。消费后释
预置前端 Al场景最佳实践。建立全局代码索
教 AI 做事，可以完全打破传统工作流模式。
放以节省上下文，保留语义化索引，确保随
引让 Al 照着规范复用，确保超大规模的项目
赋予工具让其自主决策，极致释放模型灵活
时可以精准唤起。
代码依然可迭代。
性、自主性，真正才有“智能”的感觉。
由真实用户大型项目推动的 底层技术升级
acon
InfoQ 极客传媒
全球软件开发大会

## Page 016

一群HR 同事开始自助搭建 内部流程＆管理平台
从一场面向 HR 的AI 工具培训开始，Ta 们也开始陆陆续续成了 AI 加持下的“超级个体”
自助将知识 skills 化
C Files
Q Search
G SKILL.md ./connect-ai-service
G SKILL.md
Q1
v connect-ai-service
- **ID：**500001
- **Name：** muse-buc-service
G SKILL.md
- **NickName：** BUC
v muse-buc-service
- **Description：** 本技能提供了页面获取
- **Version：** 1200001
G SKILL.md
v muse-employee-service
AI 听不懂黑话
＃ 系统当前登录用户信息获取
G SKILL.md
大量蚂蚁内部私有知识库和特定缩写，模型无法理解。
v muse-file-upload
## 技能概述
G SKILL.md
本技能提供了获取系统中当前登录用户花名以及！
Vsrc
v components
15
##使用场景
- 表单自动填充花名，工号（报名表、申请表、
accordion.tsx
- 用户信息展示（个人中心、用户卡片、评论区
- 权限判断（基于用户工号的权限控制）
安 alert-dialog.tsx
20
- 数据提交（记录操作人信息）
& alert tsy
21
- 用户行为追踪（记录用户操作日志）
參 aspect-ratio.tsx
22
个性化展示（根据用户信息定制内容）
23
焙 gco6c+-L9f.orex
-人务陬l（故蔬旺丁佈破悅区侞）
- 旺可论尚蹊（洛峡旺蘇希瓶）
路 2161-9510a cex
- 教蔬萌仪（尚联蘇衔Y而酸）
w:gccOLqIourfex
- 该品丝彩（椰上医开H吡老故敏斯照）
acon
InfoQ 极客传媒
全球软件开发大会

## Page 017

一群HR 同事开始自助搭建 内部流程&管理平台
从一场面向 HR 的AI 工具培训开始，Ta 们也开始陆陆续续成了 AI加持下的“超级个体”
预置 组件与技能、AI可以自由发挥
Q2
彭佩乔 乔杨
员工信息不通
HR系统需要频繁调取和验证员工组织架构数据。
acon
InfoQ 极客传媒
全球软件开发大会

## Page 018

一群HR 同事开始自助搭建 内部流程&管理平台
从一场面向 HR 的AI工具培训开始，Ta 们也开始陆陆续续成了 AI加持下的“超级个体”
数据环境隔离、独立数据权限角色
Q3
ENCOUNTERED ISSUE
添加数据管理员
敏感数据保障
只有数据管理员可以查看和操作生产数据库
HR 许多系统需要高敏感数据安全保障
Q 输入工号或花名搜索
当前是测试数据，在预览或应用编辑
状态下提交的数据，只用于体验功
能，你可以随时删除，清空也不会影
响发布后的作品效果。
〇 查看正式数据
acon
InfoQ 极客传媒
全球软件开发大会

## Page 019

一群HR 同事开始自助搭建 内部流程&管理平台
从一场面向 HR 的AI工具培训开始，Ta 们也开始陆陆续续成了 AI 加持下的“超级个体”
一站式 内部文档打通/钉钉打通/搜索/⋯
Al Kimi K2.5v使用蚂蚁内部模型创作，请放心使用
Q4
•乔杨-D2分享大網
更新于 02-0318:45
基于文档帮我做一个可视化展示页面
6 Muse消息通知
【年会拼车】 加入了你的拼车单！目前剩余位
子：1。
内部生态割裂
查看详情
业务流程无法与日常办公协同软件打通。
01月29日10:10
s.&
输窗
2026新春团队全家福
您已成功预约「品美轻团建|全家福拍摄：2月2日
11:00-11:10，杭州-【A空间】
，如
有变化请及时释放。
查看详情
恤秘务遍以時辦授。
acon
InfoQ 极客传媒
全球软件开发大会

## Page 020

靠对话“说”上线的 营销活动
没有研发资源的运营，抱着试试看的态度对接，最终全程 Vibe Coding 完成了 C 端活动。
D2C
设计稿.sketch
设计稿.png
1
--！-！-！
Before
高保真还原难
随着多模态基模发展
已具备 Coding Agent能力
C端营销活动对视觉和动效还原度要求极高。
After
设计稿.png
acon
InfoQ 极客传媒
全球软件开发大会

## Page 021

靠对话“说”上线的营销活动
没有研发资源的运营，抱着试试看的态度对接，最终全程 Vibe Coding 完成了C端活动。
Q2
ENCOUNTERED ISSUE
预置 脚手架 自带移动端网关调用示例
客户端适配
示例自带注释 索引到外部 LLMs.txt文档库
移动端布局、客户端环境适配、移动网关与用户体系。
Qcon
InfoQ 极客传媒
全球软件开发大会

## Page 022

靠对话“说”上线的 营销活动
没有研发资源的运营，抱着试试看的态度对接，最终全程 Vibe Coding 完成了 C 端活动。
Q3
写的快
大流量高并发
提供企业级的高性能基础设施，轻松抗住大流量并发。
发的快
高性能
AI Coding时代的敏捷迭代
Qcon
InfoQ 极客传媒
全球软件开发大会

## Page 023

靠对话“说”上线的营销活动
没有研发资源的运营，抱着试试看的态度对接，最终全程 Vibe Coding 完成了C 端活动。
自动构建期测试、运行时异常监控、离线任务扫描、自动修复
写的快
挂的快
发的快
高性能
但是，AI 永远替代不了真正的程序员
AI Coding时代的敏捷迭代
AI Coding时代，高级程序员的价值只会更高
Qcon
InfoQ 极客传媒
全球软件开发大会

## Page 024

AI 产品，就是要让AI 可以 更低门槛的被更多人使用
用更普惠的方式，让非技术群体也可以获得AI平权，可以助力更多的工作岗位的同事成为超级个体
最近30天企业内部，使用本产品数据
5000
）创作者
600亿 tokens
acon
InfoQ 极客传媒
全球软件开发大会

## Page 025

从「垂类」走向「全能」
用户永远不会跟着你的想法来使用产品，用户只在乎这个 AI 产品用的顺不顺手
花器人服务员：职业苔代还定.
司拌每2026。创作中
‹代码
⑦梨助 ②
万」让体里杀统地厂释区一没中，我万你有与了一还1
口 大
职能进化？8。
尽的深息分析折告。二《机器人路务品：阳中参付会作
一员：职业替代还是职能进化？
通用型 Web 应用创作
•视觉主体：背景通过 Al 生成了迷雾笼罩下的未
在这份报告中，我从以下盟个维度讲有了打解：
至表
烹感器技术的奕破，餐饮业正在经历一场前所未有的自动化变革。从最初的“送
QCon
序，配合巴大的全总 Coding Agent没，宫廷
、绘济新水，近比，人类与利器在放衣、效婆
0 分栏
蚤语音交互、智能避障甚至迎宾功能的类人助手，机器人在服务业的渗透率正
出龙大三市有儿仇邻感的天水士每市
工时上的核心差异（机器人通常12-18 个月即可
@ 关联内容
文档
创作 巴 团建投票。创作中
• 國建投票/
2026
•极简主义：采用非对和构图，将大量留白
，北这进这去印这这区数后，人必公情会住向期
分析了为什么在后疫惜时代，人们
品0 高亮块
（空气感）留给背景的宏大叙事。
卧机菇人服劳员•我业育…
找已技说 nuse-puc-servace 时仅能效池，1曼」片
• 字依设计
：使用阿里巴巴普惠体，井为标
TEAM ESCAPE
题添加了轻微的“放障艺术（Clitch
3肥业刘验评信：明雅冶出呷此岗位向临沿车邻
食间，人失的 旧体 以都花歌1。
—分割线
佛 对机器人抢走工作的恐.
K服务员这个职业，而是会引友就业么
OTING PLATFORM
+ 进入管理后台
Efect）”动画效果，授拟未来显示屏的质
纯传菜员），而哪些岗位将因技术介入而变得更加
修复核心；
曲 服务机器人行业市场规…
4.未来图景：提出了*机器人负责底层汤辑（效
•替代区：高重每 麦当劳尝试用机器人当….
专菜、收残、举啦清洁）。
•正确获取全局变量：现在应用会严格遵循获取优
2026.04 BEIJING
• 层级元明：项部资出 Rcon 2026 与北泉
先级，首先尝试从
站中心兴售Codinc Aaent取动的饼友
华，人尖员员业连現（佰的肉口保工
•保留区：高杉④ 研报三：服务扒器人一…
七推荐〔如高级领位、点餐建议、投说
window. TERN,user.clientuser 救興必肉
新范式”校心专题，底部通过细线分割出专
你可以在文档库中查看这份完整的报告。希望能为你提
口中提取系统级用户信息。
向往的
业的技术大会信息。
•新增区：机器人运营、人机协同管理、智能设备维护。
• 子段以别刀有
校心信息呈现
•使用 userId作为唯一的身份 识
• 专題聚焦：将“Coding Agent 驱动的研发新范
Coding Agent 驱动
二，作为视见干心强的人死协作的沱起。
•使用 nickName作为显示的姓名，并将其
•安实正址，仕底部信总仨你注」画可条构那匀拉
桃春人服务员：短现荟…
创建文裆
一、市场驱动力：效率与成本的经济账
付人1湖数结车十。
远方
的研发新范式
术负断人的定位。
•环境兼容性：保留了对
• 促于avatarirt状时头内示统头体。
•品感背书：保管Infod 与极各郑科技的主办
Lcgo 标识。
方信忌，并设计了一个极简的 QCon 2026
ahConfia 的舆底诺辑。福保在不同容我刊
维受
人大服劳贝
不当导致的主流程卡死问题。
境下都能稳定识别工号，彻底解决了因获取方式
页面已适配移动端，可直接预览。
② 请捕述你的需求或想法，部刻开启创作之旅，输c
工作时长
需排班，受体力及法定工时限制
投票选出你最心仪的团建目的地。每个伙伴拥有一票权重，支持
现在系统可以准确识别当前登录人的真文姓名、工号和
头像，为后续的投票和权限校验提供了坚实的数据基
随时修改。当前已有 4］位伙伴参与投票。
材入-我芝街端二公负间，负宫贺
口本問期
侍姿文占
Gemini 3 Flash
服务一致性
受情绪、疲劳影响，存在波动
校搞取和听报，于国商用服劳机奋人巾场拟体住2020年关饭12001元，具中食以容
AlChitecis & Techl Ledds
Qcon 2.
文档、表格、PPT类创作
心清猫运你的需求女檬法，期匆升后创作之服，箱修
旷野回响•川西秘境
艺术之旅•阿那亚
入公/38+- 可换行
海报、创意、营销类制作
DEPARTURE:2026-08-20
F DEPARTURE: 2026-07-08
仰望雪山，俯瞰草原。在旷野的呼唤中，
孤独图书馆、礼堂与大海。在艺术氛围中
食Gemini 3 Flash
里作囚队取创到夺选。
激发灵感，探讨无限可能。
≥©100%④
Qcon
InfoQ 极客传媒
全球软件开发大会

## Page 026

从「垂类」走向「全能」
用户永远不会跟着你的想法来使用产品，用户只在乎这个 AI产品用的顺不顺手
1、信息在Agent间传递
代码
图片
知识
文档
Workspace
2、一个通用型 Agent 直接操作所有内容
Agent
Session
Session
Session
User A
User B
User C
不同项目之间
如何多人实时协同？
如何跨场景、跨模态的信息互通？
Qcon
InfoQ 极客传媒
全球软件开发大会

## Page 027

从「垂类」走向「全能」
用户永远不会跟着你的想法来使用产品，用户只在乎这个 AI产品用的顺不顺手
z 一切内容都是文件
AI 时代的软件设计哲学：
② 一切文件都用 Git管理
一 流程都围绕AL 友好来设计”
3 一切会话都在 WorkTree 中发生
利用成熟的软件体系，快速、简单、健壮 的解决了刚刚的2个问题
AI 原生掌握的技能，才是未来的一等公民
acon
InfoQ 极客传媒
全球软件开发大会

## Page 028

未来的基建必须 天生 AI 友好
基础设施的受众正在发生根本性转移：从面向 Developer 转向面向 Agent。
Interface
Docs
ENCOUNTERED ISSUE
保障 AI 会写
保障 AI 会用
AI没学过的语法，未来推广将寸步难行。编程界面和知识库必
文档的第一读者从人类变成了机器。基础能力必须laC化，
须对齐业界流行方案，降低 Al 的学习与生成门槛。
提供结构化的 API和机器可读的接入指南。
IIms.txt
CLI
ENCOUNTERED ISSUE
流量入口 Token化
不可被AI 驱动=淘汰
未来平台的关键不再是GUI,GUI 甚至可以腐化，但 Ilms.txt
未来不支持 CLI、无法被 Agent 调用的软件可能天生就低人一
或 readme_for_agents.md 将成为最核心维护的资产。
等，不能融入AI自动化工作流的产品将加速被淘汰。
acon
InfoQ 极客传媒
全球软件开发大会

## Page 029

AI 时代的用户，不在意过程 只在意结果
从拿 AI 当工具，到拿 AI 当队友，Al Native 时代=信任Al，放手让它干
Product
Infra
ENCOUNTERED ISSUE
ENCOUNTERED ISSUE
交付才是核心
Token 就是未来的电
没人在意程序底层是 Code执行还是LLM 执行，智能化和
Coding 过程越来越不重要。能让用户舒服地用起来，能真正
“懒人化”是不可逆的趋势。
拿来落地业务需求，产品才算有价值。平台的核心壁垒将从
“如何将需求变成代码”转移到“如何保障用户需求交付”。
“用 Claude Code 的程序员，现在连git push 都懒得自己敲了。”
acon
InfoQ 极客传媒
全球软件开发大会

## Page 030

一些额外的 经验与思考 分享
关于 Agent 工程的发展，关于让 AI执行确定下任务的约束方法论
AI时代的架构师，第一设计优先级是：面向变化
任何事情都有可能在3个月之后发生巨大的变化”
acon
InfoQ 极客传媒
全球软件开发大会

## Page 031

一些额外的 经验与思考 分享
关于 Agent 工程的发展，关于让 AI执行确定下任务的约束方法论
Vibe Coding
LLM 永远倾向尽快结束对话
从 Agentic 开始
释放LLM 的潜力
让 Agent在 真实环境 中长时间运行，
Spec Driven？
约束
利用验证-反债-修复 闭环，
Test Driven？
可执行约束
持续达成 用户预期的目标交付，
Harness Driven？
解放范式
才是工程的最终追求。
Model + Harness =Agent
con
InfoQ 极客传媒
全球软件开发大会

## Page 032

一些额外的 近期AI圈技术热点 的想法
关于知识管理、关于自进化的 Agent体系
Karpathy
Karpathy
Karpathy-Inspired
HermesAgent
AutoResearch
LLM Wiki
Claude Code Guidelines
91k
73k
46k
HermesAgent
泛知识管理
Coding Agent
VS
Train-> Keep / Revert
PlainText+Bash
行沩优化
OpenClaw
Wiki 式哲学
自学习、自进化
释放原生AI 潜力＋驾驭AI 行，永恒的双轨话题
acon
InfoQ 极客传媒
全球软件开发大会

## Page 033

nfoQ极客传媒
QCon
全球软件开发大会
THANKS
大模型正在重新定义软件
Large Language Model Is Redefining The Software

## Page 034

上
探索 AI 应用边界
AiCon
QCon
海
Explore the limits of Al applications
站
全球人工智能开发与应用大会
2026年6月26-27日/上海张江科学会堂
专题：世界模型与多模态智能突破
专题：Agent 系统架构与工程化实践
专题出品人：未政
专题出品人：鲁洁楠
极佳视界 / 联合创始人& 首席科学家
OPPO /大模型算法员责人
专题：AI 原生数据工程
专题：Agent 安全、评测与可信治理
专题出品人：王彦辉
专题出品人：马传雷（岳立）
火山引擎/数智平台产品总监
支付宝 /业务风险技术部负责人
专题：Agent 数据、记忆与运行时
专题：企业级研发体系的重构
基础设施
专题出品人：沈浪
专题出品人：邓亚峰
快手/ 研发效能员责人
EverMind / CEO
