# 黄兆嵩-把-UI-生成接进流水线-基于半监督评测体系的-UI-自动化生产实践

> Page-by-page visual information extraction from rendered page images. Text below preserves the visible text recognized on each page; pages with diagrams include every OCR-readable label captured from the image.

## Page 001

InfoQ 极客传媒

QCon

全球软件开发大会

当UI生成接进流水线：

基于半监督评测体系的

UI自动化生产与投放实践

黄兆嵩

蚂蚁集团

## Page 002

极客邦科技 2026年会议规划

促进软件开发及相关领域知识与创新的传播

◎6月 ？上海

2 1000人

◎ 8月9深圳

8 1000人

AiCon

•Al Infra 系統工程

AiCon

•Agentic Al

•多 Agent 协作与实践

•秷罼化与高效推理

全球人工智能开发与应用大会

*多桢态融合

*多模态应用

全球人工智能开发与应用大会

*模型训练与推理创新

•Al + IoT 场景实践

（会议时间：6月26-27日

•数据平台与祷征服务

会议时间：8月21-22日

•AI 工业化落地

010月9上海

81200人

012月？北京

R8 1000人

•Al Agent

Qcon

•Vibe Coding

AiCon

•大模型架构创新

•智能可观測

*多模态 AI产业融合

全球软件开发大会

•推理基珊

全球人工智能开发与应用大会

*具身智能

。模型攻防

•Al for Science

会议时间：10月22-24日

•AIx 创造力

会议时间：12月18-19日

•大模型安全

## Page 003

InfoQ 极客传媒

QCon

全球软件开发大会

01

序章：新时代体验技术面临的变革

02

第一章：如何生成高质量UI

03

第二章：如何在LUI中应用AI生成

目录

04

第三章：如何实现有效的监督& 迭代优化

05

总结与展望

支

## Page 004

支

新时代体验技术面临的变革

aCon

InfoQ 极客传媒

全球软件开发大会

## Page 005

第1阶段

部分主流Chat APP

「不同需求」

UI 仍处于「以文本为主的初级阶段」

超 郊|年粒（1小号，

第2阶段

：2美园象戏北2器：是花穿井严驾店，太京

「不同数据」

WINKHAIS.B2R28，

③0

CLAUDE CMD

Caude SHE wti0

第3阶段

中美

系忪

「不同用户」

不档

來族必習 消公主理家真雀。

1.GU供给无法满足需求，CLI用户体验受损

acon

InfoQ 极客传媒

全球软件开发大会

## Page 006

UMT.CO.WNT

产品POC

「需求」ToUI

生产上-“不会用、完不成、不通过”

迭代上—“效果怎么优化？效果优化了吗？”

自动生产

「Data」To UI

@

前端实现

「Design」 To UI

2. From 传统的预研发模式 To 自动生成的几个典型场景&仍然面临的挑战

QCon

Infoo极客传媒

全球软件开发大会

## Page 007

第一章

如何生成高质量UI

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 008

WORKBENCH

「Prompt 工作台」

You are an expert At assistant and exceptional senior software

deve loper with vast knowledge across and multiple programming

Lanquages （React、 TypeScript）， frameworks, and best practices.

to

“我服了，每次改prompt像在写短篇小说”

smessage_formatting_1nfo2

- You can use the following HTL elements to optinize message

# AI 热行策略（预级设计师思维链路）

.spre>，sstrong~，

E to

池tc.

- 每个prompt上千字

## 1.深度设计决带 （Chain of Thought》

file

- 版本管理

# 祝觉风格：Cyber-Industrial•Hacker Temninal

Ln="'anonymous"

a# 1. 设计 Token 系统

- 多人合作写一个prompt

名生成的星

### 1.1 色彩休系（极高河比度）

风格。相

ice］

- 改动牵一发而动全身

- 主色（Phosphor Green）x：'#33ft00”（经典终端绿），

云疗”还是

- 强调色（Amber/0rangc）**：#ffbe0a（用于警告，总结或点强调）。

内稳健性。

•cn/retrieve_image！

- 背景色（Terninal Black）**：#0a0a8a（深黑色，允许添加微弱的 CRT 扫描线

retrieve inaget

织理）。

- 墨告色（System Error）**门#1f3333（明亮的系统级警告红）。

1行？哪

### 1.2 字体与字号

三切换时产

- 字体族 （Monospace Suprenacy）**

-核心要求：必須使用等點字体。'JetBrains Nono, Fira Code, Courier New，

2遮批.

- 严禁使用任何比例字体 （Proportional Fonts），

；调盩层圾

- 特保处理

觉呼吸

一被地金碳後用文季事今 本繳加械購路tex-shaJow: 0 0 Sox rGba（31，

- 核心金额：使用大号字号，井添加微弱的

关馄数抵

255,0,8.5）模积累光屏光晕。

###1.3 图角、边难与纹理

- 国角策路***绝网直角【ercm）料。产禁使用图角。

1造30晨

- 边框傳系**：

-Lpx 实线或虚线边性，額色使用主色（#331T&0”）或请 后的绿色（#11521 ）。

-使用 ASCEI 字符进行边框装饰（如“十十拐角）。

- *CRT 料效x*：使用一个半透明覆盖层，带有细密的水平扫描线坟理。

3.为了构建流水线，痛苦的Prompt研发过程

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 009

支

WORKBENCH

「Prompt 工作台」

•备虎-公用测试Prompt工作台 逗用U生成-最简单版本

•当我草猪保存于2026-03-17 18:50:13

纣出模式

版本记录

挹交新版漆

缇排

评双买验

榕销Prompt

配置 四

桤型选捏

试运行冫生威结果

生表

v 全併服示

＞生成回答

乡 全閣感井

它 封制原有prampl

数据逃指 巴谈带2条奴坛

选泽奴据素

受量定义 （um

AI一留生成受量

P user

角芭定义

C 变堂生成規則

动

资源规范

requaranent

• 定变量

花入受盤或点示「A生成受量內間」

用户筘入

白

十 凉加擬小润码安

E

4.定义/调试「UI生成链路」的工作台

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 010

WORKBENCH

「Prompt 工作台」

任务

对比模式

版本记录

投交新版本

用户正在生成一份 prompt中的变量的具体内容

试运行丿生战结果

请根据prompt和变量生成规则，生成变量及其对应的mock值的具体数据。

共1个蘋果

全部

全屏展示

＞生晟回答

输出格式为json结构，每个属性代表一个变量的变量名及其对应的字符串的

口 鹅綁

浩择数涡樂

史斯配園

设置敪湛

数值。输出不要包含多余解释内容。

1定

AI一鍵生成变量

＆釐生戍报翾

示例

4 活配裝素：

•培景 -决定语义化分区

（beader/main/sectian/tceter）

prompt：请以（theme）为核心主题，创作一首符合（style）风格的诗歌.

曼众 码定字体大小、请气（正式/活该/面）

•好-料断學需使用表格、列表、表惜、陶片等元素

imrer已保從d42jchas

variableNames:theme,style

5 一欢性：关健河需与后续自动配图描述，配為主也、按

忸文爽保持間义餃射

vestag0g

评分

rule：提示模板总结：该模板的主要目标是指导AI创作一首以指定核心主题

theme为中心、符合特定风格style的诗歌，关键元素包括核心主题theme、

講定

风格style。

正在酸釀逛行

变量考虑因素：theme作为核心主题，典型示例为具有情感或意象支撑的具

配手机和桌低端，頭

其雕，一89调试预览“

体日常场景、自然现象或人文事物（如巷口老槐树），长度简短，功能是作为

包含产品场景團片、功倍列表、行动号召按钮和助

表单

从精选的高海拨阿拉比卡豆，到每一次穎

诗歌创作的核心围绕点；style作为诗歌风格，典型示例为文学流派或传统创

•数据属性绑定

准的萃B，

我们正在禅次淋量试运行

气与阳光的温暱角落.

作风格（如田园抒情），需明确诗歌的语言表现手法与情感基调，符合该风格

- 自动生成Mock

相配地不及 -和牛感鑄暴可视化

的特征。

•自定义数据格式

酸教司宇恒顾与对比

输出：｛"theme"："巷口的老槐树巷口的老槐树”，"Style"："田园抒情田园抒情”｝

5.辅助编辑、辅助Mock、辅助调试

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 011

支

WORKBENCH

「Prompt 工作台」

Chat 工作合

单个UI生成/精修

生产流水线

批量生产

USTTL,UNF

E）

◎

6. UI生产线

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 012

PROMPT OPTIMIZER

战的账单E幼026

Todo List

「需求改写」

999

Add a now tack..

“这个是快速验证的项目，没有产品文档”

Complete project documentatior图

Schedule meeting with team

-一句话需求、没有产品、交互设计

Revlew oonding pull requests

- 界面布局和交互凌乱

Prepare presentation slices

- 功能不全

- 只能说刚刚达到用户需求（及格分）

个税汁算器

计算结贤

7.高产量流水线上通常不会有人工精心编写的产品设计文档

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 013

角色

PROMPT OPTIMIZER

＜ 张单详作

你现在是一位拥有104年经验的资深广品经开（PD），莺在頂级科技公司机资多款成功广品的设计与上经。你精通帶

求分析、用户体验优化和产品规划，并能将报息需欢转化为清重的产品文栏。

「需求改写」

999

202390月3还（元）《

分析其田用升发需来，井结合历史免象中的期户编好相设计员格买果，补克 以产品鸡设计

需求说明，以便能够君此生成葛质量的UI没计，

700.00

请便用专业的Markdown格式输出一份结构完絡的文档，避免榜關摇迷，条止输出markdown。最多300个罕目

含以下烧心部分

“根据数据生成一个账单页面”

立即还廠

输出内容结构

带知识库

果户没有朗础产品意幽或

的

“suggestContentid"：1，

1需求概迟

Agent

“userlntent”“查询当前及未来账单详情，

¥700

¥299

核心问赠降速 明保指出用户個临的关事点与那决方茶

包括待还金额、消费明细、未入账交易和退

日网第：3023:08-90=2053-16-03

主要功能需求 列出主婴功縮模炸

2. 枝心功能及表

款状态”

•用户角色与场累：详送不同用户带色及其长用场腰

"suggestService”

•用产流程图：关键流保的步州分簡粗决策点

•功脆授块详細说明：每个功陪的具体措丞，用例和边罪鲜并

•交监设计原期：用户交互模代、动效要来

•信惠架构：内容坦织和民級挡树

•响应式/白适应设计要求：在

•内容帝略：女率風格流玉（

霄淋矿写。

前

后

3.其他关证考量

账单管理页面产品需求文档

•100

•可幼间住要求：确保广品对？

•品牌一致性指南：产品如何

1. 需求概述

210.00

核心问题陈述：用户需要清晰掌握

注意事项

当前应还金额、历史消费分布及未来待入账金额，解

决”还款金额不明确“和“消费不透明”的痛点。

• 为设计师提供明 的约束系f

•预见井等决潜在的设计冲突！

主要功能需求：账单总览卡片、消费趋势圍表、未入账预警、分期还款入口

拉物8务 辽海东学业业烧对路基特2由

•使用行业标准术差。但過保：

2. 核心功能列表

•登个火档最多300个字

用户角色与场景：

用户宜询本期账单（10月），了解700元待还款项、299元未入账金额及

一周消费波动

功佗模炔详细说明：

炒焖识氐

•顶部状态卡：突出是示待还金额700元、还款日10-15倒计时、一键还救按钮

•消费分析图：柱状图展示周一至周日消费分布（最高210元/周二），支持点击童看单日明细

团市延利

• 三栏数据面板：已还800/总額1500/未入账299，用色彩区分状态（ /灰/橙）

•账準岡期栃签：显示09-05至10-04入 問期。关联”什么计入本期”的tooltip说明

交互设计原则：

• 金额采用大字号加箱，还款日期红色高亮

8. 需求改写 -更缜密的业务逻辑 -和合理的页面布局

acon

InfoQ 极客传媒

全球软件开发大会

## Page 014

“帮我做一个中老年用户运动步数统计展示页”

Claude 4.5

PROMPT OPTIMIZER

「需求改写」

“帮我做一个To-Do List”

Gemini 3

L供製了！地块給準！

早安，开始高效的一天！

我的待办

6,580

专日亮旗帘

+都一个新肉任南。

33%

罰 今日涉潋

8,563

投交工作申请

目标8,000选

66

100%

已达标山

嶺写文拶

工P

谁 交岡平埃

• 耗热量

乍癸成讲覆

交付产品被计

前

33%以am

8,109

343

后

前

后

本周运动记录

D00 7202

G,411歩

300

300

塑康小贴士

Thesecrtod attne eindh

蚁胃龄人平均

委加新任务..

工作

荔优先級

粒止日期

5,800步

9.需求改写。更多案例

acon

InfoQ 极客传媒

全球软件开发大会

## Page 015

COMPONENT DETECTOR

「组件检测」

设计稿还原-“细节上有偏差”

- 布局不对

- 位置有偏差

- 视觉走差容易遗漏

推荐入杀篮理

茂3X珍路商

游庄体肉历大

授荐規™

推荐入会管理

口 卡包合员卡退款

出 C领终活动管理

美宜佳会员卡

份 G天路江世臀理

我品活边

xXXXX:QKXX

广苏系業行以公元

xxco08

ieae

雷 大物日达动管理

吗 按然入会修理

拰禅规則谅嚣

拉荐羽间

扫荐人群

推荐市

拄折识先汲

10.设计稿还原总得修改

acon

InfoQ 极客传媒

全球软件开发大会

## Page 016

COMPONENT DETECTOR

「组件检测」

Claude 4.5

2 20260318152044.jrg 文件上传成功

組 識别

自动识别图中组件类照、坐标、内容和拌式。多级单张图片购应速度；误葱小于5pixel。

组件检测

哉的慾度

芝麻名片

前

目标分割

倍岸卡

法兌持

上传护

芝麻粒炼𠈔

免拇根

芝麻粒烤金：河提坪

芝麻粒

我的额度

芝麻名片

框架识别

消息助手 发宝物脂纸柜•都隆的柜望勞已守約 08-25）

芝麻校炼金：可復班

免押租1綠驗试舞所生迷

OCR

缘绥泮毁炼金炉

图

在側閑片上传完成后，点击下方「真即檢测」

可在出窗口查看算法识别的 UI JSON 結梅

规则匹配

生成链路

◎ 立即控測

11. 基于2W+UIN标注数据集训练「组件检测」模块，还原位置、布局更加精准

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 017

支

设计稿

COMPONENT DETECTOR

「组件检测」

凯旋门

推𦱾人会體理

英宜佳会员卡

合员活动

狌荐荫則

凯旋门

刧換貕涵

撫莊入參箸阻

美宜佛会品卡

推荐入会管理

日 卡包含灸卡运酒

卤 商2筱日

XXXKNXXXYXX

英宜佳会员卡

。北翠中

活爻仡坦

邸 s天路江世官结

KKxXXXXX

田 大淇日忠动管瑾

前

公费法动

4推奇人金限理

推荐規剽设笠

后

石动时间

后动纵忑

拄存时湖

含局奴路

止：21-0827258

步戊侦见片会员凝烘筛动

8:1021-L8-300000

陈荐城而

己选将20个地区 洋情

陰释仪咒级

推荐规财

摈菛先朱绘

KimiK2

12.UI检测+无多模态能力模型。执行设计稿还原效果

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 018

COMPONENT DETECTOR

「组件检测」

UI還原度比對

自动识别设计预与真机之间的差异。秒级张图片哈应速度：误差小于5pixel

制JSCN致発

9:41

749

LercrentR umfietn

设计稿

线上酸图

單安裂符信用卡办理 肇核癸數

招简银行信用卡办理 审核失财

ElcncntIcon

水平方肉迎离差异：設计務中距商为 970P市山图中迎里为10=3

小 竖直方可 离差养 益计基中党商为2南U图中堂商为

Eementcog

Comtianentorebutton

Ehmcnicoggg

台精最行灣用卡办理

co0rd: 120.0. 329.2270.3041 cont:47.4

coord: 124,755. 191. W71 cont: 55.2

③ 水学方肉範廣差异 過计稿中路商为？7苏山国中部町为124

娱產方有距离茶异，记计中距商为，200 有U看限中距限为55

CanponontCLodeBucton

cocrd: 12328, 350, 2440y 57L1 cont1 99.51

0 水平万同距两茶异：温计積中單商为 2150 而U低国中原腐为2127

双消订牟

显邯 理

資角养异： border raclis dlff basefaol.to camperec（esc）

异常检测

consseordNssciaTeinu6

CampanentTees

352100329237

质量走查

coord: 2596 20902 23962 106J cont2 86.4

辅助标注

13. 基于组件检测的 还原度比对功能

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 019

支

STYLE RETRIEVER

「风格召回」

“你这个上不了线啊”

- Mac 表情包

- 不符合预期的圆角、阴影

-字体、大小

- 蓝紫色渐变

- 五颜六色的ICON

欢注回来，开启您的数字化湖业之旅

实吋庤行授

$$

灵感变现实巅峰挑战

旗向企业贺部创意人才利師发精天的跟級A技场

在这里，每一个想法都可能改尖世界

125,000

8,950

23,456

¥1,256780.0

疯狂赚钱设置

准备好聚富了吗？尚泰面

红鼓中客

$月工资（元）-越多越爽！

输入你的工资，不要害墓！

刨新驱动

快速落她

史燒作式翅作。从要製信火司

少上班时间-开始雞钱！

13.AI生成的页面难以达到业务产品的视觉质量要求

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 020

支

STYLE RETRIEVER

「风格召回」

风格仑库

+ 新增民格席

Muse歌认风格

③ 如何消物

＋新增员硌換版

共：个空问

lucide-react图极屋

B220

默认风搔

沲报场景知识厍

UI参考知识库

云垸白描

已发布

柔光璃韵

暗夜科技

以纯白为基底，搔配低饱和子色授块，扁平插

以白薰淡黄渐爽富道温眠光晕，揸配半透明白

深退的眾色基底映合毛玻璃的聯眼光愛，

呵迩

商风轻量化呈现数招。留白聚焦信息层梁，封

色毛玻璃卡片，轻激悬浮于背景之上，梁也文…

补秘而现代的视览层次。供资的磨砂贾感搭配.-

8306人

日 2025-06 0110-22

前2025-08-011020

8 神秘人

RAG+生成链路

14.管理业务设计风格的仓库与自动录入

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 021

STYLE RETRIEVER

「风格召回」

Active Tosks

700.00

“根据数据生成一个账单页面”

700.00

¥700.0

3

洲劑蒜好

张鹉阴娟

税的涨单

！.：！！

◎

父易期堡

7000

深鸡出厅-城午

Wekomein,Nixto

•100

：205

-299.0

-45.4.

交通品门-海凑出仃

¥786.08

15. 风格应用效果

嚴近亥易

-5∞06

acon

InfoQ 极客传媒

全球软件开发大会

## Page 022

支

STYLE RETRIEVER

「风格召回」

RAG & 重排序

》帮我生成一个个人简介的UI界面，数据可以mock

•我来帮你生成一个个人简介的UI界面。首先让我调用风格狂暴技能来获取高质量的UI设计参考。

“帮我设计一个

• SkilL（style-fury）

L Successfully Loaded skill : 2 tools allowed

•我来帮你搜索个人简介页面的UI设计参考。

asuS

• Bash（curl _location https://）

'Content-lype：

application/json ）

% Total

% Received % Xferd

Average Speed

Time

Time

Time

Current

upload

Total

Soent

Left

spced

②

w +17 Lines （ctrL+o to expand）

“扁平化、移

•已获取到设计参考。现在让我获取参考图片视觉内容，然后为你生成个人简介页面。

• Read 2 files （ctrl+o to expand）

• 根据搜索到的设计规范，我来为你生成一个现代简约风格的个人简介页面。

设计规范摘要

-设计风格：极简丰必、留白型设计

- 布局类型：卡片布局。

居中对齐，

自适应

的牛失期橡脱分

二體粹爽鹽：醬備藥青。线促醬鳥

中性色调，

单色系配色

長一級感与劑皮料

一 组件类型：圆角卡片，

无衬线字

体

-目标平台移动端优先，响应式设计

现在让我生成页面代码。

* wibblinga （345%• + 824 tokens）

¥899

約0110602

16. 风格狂暴- 提供千张优质UI风格模版库

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 023

第二章

如何在LUI中应用AI生成

acon

InfoQ 极客传媒

全球软件开发大会

## Page 024

STREAM RENDER

「流式渲染方案」

LUI Chat App

GPU USAGE

CPU LOAD

老板！显卡（卡）不够了！

98%

100%

生成这些复杂的 UI 资源

消耗太大，卡爆了！

d.d

“怎么这么慢”

Generating UI..

mlall运

边输出边渲染/减少输出内容

增加复用率

17.UI生成在AI应用落地的双重挑战

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 025

支

STREAM RENDER

「流式渲染方案」

HTML代码输出

用户

s tont-sans select-none">

｛ 卡片容器：同定尺寸470x400 /｝

<div

className="relative bg-white rounded-2x］ shadow-xl overflow-hidden flex

LUI 界面

「lex- ol！

style=ff width：'470px".height：：480px/3｝

背张装 +/｝

sdiv clasSate="abisolute top-Qright-0 w-64 h-64 bg-gradlent-to-br from-

oranae-50 to-transparent rounded-b1-fult poincer-events-none opacity-60"2/div

业务智能体

渲染引擎

｛ 部区城（Helght ~60px）

<div classvame="flex justity-between Ltems-center px-6 pt-5 pb-2 2-10">

cciv className="flex items-center gap-2">

<div className-"bg-orange-180 p-1,5 rounded-lg text-orange-686">

<lucide-jcon namc="sparkles" size="18"/</lucide-jcons

<h1 classtiames"text-lg font-bold text-gray-800 tracking-tight">｛dat

UI生成

a.1itle｝e/hi

eciv className="text-gray-400 cursor-pointer hover;text-gray-680">

<lucide-icon nane="more-horizontal" Size="20"×/lucide-icons

</div>

｛ 、主要内容区性（Flex Grow）w/｝

<div ClasealerTlexL oAo cekTwexwcow2un

｛/* 信思文 * ｝

ediv className="nt-1 mb-2">

sdiv classNene="fLex 1tems-bosclinc oop-2 mb-1"2

cspan classhlame="text-2x1 font-extrabold text-gray-900 font-

nono tracking-tighter">7:/spans

ssDan classHame="1ext-sm font-Seaibold text-arey-700'5fdato.

能不能减少输出内容？

18.等待智能体输出&UI生成输出

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 026

支

STREAM RENDER

边输出边渲染 /减少输出内容

流式生成渲染效果

「流式渲染方案」

17:137

用户

＜ 支付宝AI搜

终端方案的流式输出协议

LUI 界面

sicon src="https://XXKX" /> 16周岁以下少年儿至按照自原則

！ 茗料| 要必！

Hello！

童户口本| 户主页及本人页|

| 号份证| 监护人凉件|

我可以帮你答笼、快達信息检索、总结海量内容 在”支

业务智能体

• 组件引用

| 出生证明| 证明盗护美系|

付宝->消息“找到“A搜”、随时召唤我～

渲染引擎

• 动态渲染

11 -sxui-bullet Lcon='check'title="地点2

12

户籍所在地派出所/政务服务中心公安窗口。最近地址：西湖区西溪派出所 古墩路699号

x/xui-bulietx

如何申请社保杰

14-sxui-DuLlet icon='check'title="时间”>

周一至周五（法定节假日除分，上午8:30 12:08.下午14:00—17:30.郎分地区提供周六延时服袋

Skill

◎ 習能调度、

流式输出协议

17- sxui-DuLlet icon'check'title"甩话

18-

sa href="https://www.elipey.com/"style="text-decoration:none;color：#1677ff; fon

t-weight:normal；"s

19

0571-88665555

密码 怎么 可以 里面 激活 拍×

</a>

e/sui-bullets

22

@#

ABC

DEF

23

ciconsrc-"check"/ **办理费用*

24

GHI

JKL

MNO

换行

25 • cxui-co Lumnss

sKui-co unn titlc-"百次申波'>免册s/xui-column~

PQRS

TUV

WXYZ

发送

123

中

19. 实时生成UI-流式输出协议

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 027

支

STREAM RENDER

边输出边渲染 /减少输出内容

「流式渲染方案」

渲染逻辑

用户

class StreamingUIRenderert

private state: RendererStatc：

private readonly BUFFER_THRESHOLD: number；

1/ 触发处理的鼓小token 数

private readonly RESOURCE_END_MARKER: string; // 资源区块结束标记

LUI 界面

cons tructor（config: RendererConfig） ｛ /* 初始化 state， 设置值 */｝

外部入口：接收流式 token

onToken｛token: string）： void｛

this.state,buffer+= token：

业务智能体

渲染引擎

if（this.bufferExceedsThreshold（））

this.processBuffer（）；

设置缓冲区

｝

｝

Skill

流式输出协议

onStreamComplete（）： void｛

this.flushBuffer（）；

1/ 父理剩余缓冲内資 最后执行script

this.executescripts（）；

激法所有交互 本

｝

//— 核心缓冲区处理

private processBuffer（）： void｛

1f （！this.state.resourcesReady）｛

this.hand leResourcePhase!l；

this.handleRenderPhase（）：

｝

｝

20.实时生成U！一流式解析输出，最后添加逻辑

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 028

STREAM RENDER

第一阶段 加载资源/初始化

边输出边渲染 /减少输出内容

「流式渲染方案」

1 — 阶段一：资源加载阶段（f1ag = false）

private handlekesourcePhasef）： void t

1/ 1. 持视累积，怕测资源区块是否已输出完毕

if （！this.isRescurceBLockComp Letefthis,state.buffer）） retum；

用户

1/ 2.解行份凉声期（CSS/5/字体/依欢特）

const resources = this.parseResourceDec Larations（this.state.ouffen；

1/ 3.一次性并行加製所有资源

await this.loadA11Resources（resources）：

LUI 界面

V4、初始化空白页面容器

this.initiali2cPage（）：

115.将 buffer 中资迎区决之后的内容保留，进入道染阶股

this.state.buffer = this.extractPostResourceContent｛this.state.buffer）；

业务智能体

th1s.state.resourcesReady = true：

渲染引擎

第二阶段 流式渲染

Skill

—阶段二：增量溫染阶段（flag = true）

流式输出协议

private handLeRenderPhasel）： void. f

1Y 1. 补金残缺结构：盐试闭合不完整的JSON/HTML 标盛

const comoietocstrueture = fhas comnicscPorsaolseruemurehhs Siate outsen：

11 2. 解析为标准 UINGde 网

const currcntTrcc-this.parscToUINodeTrccfconLctcaStructurc）；

核心缓冲区处理

11 3.与快照做 di+f，计算最小受更集

private processBuffer（）： void｛

const patches = this.diffTrees（this.statc.snapshot,currentTree），

if （！this.state.resourcesReady）｛

this.handleResourcePhase（）：

114．将安更集納码为帶重消感办议

const messages: PatchHessagel］ IJ = this.encodePatchMessages（patches）；

｝els

this.handLeRenderPhase（）；

1/ 5. 推送增量消息拾前端渲染后

this.dispatchToRcndercr［mcssagcs）；

1/ 6.更 快张

vnis.sidwe.shagsnor cuntewtee

21. 实时生成UI-先加载资源、然后开始渲染

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 029

STREAM RENDER

边输出边渲染丿减少输出内容

「流式渲染方案」

用户

增量协议

•补全web结构

- Diff+增量协议传输

LUI 界面

-解析渲染

const op1= ［｛

"'op"："add"，"path"："/o"，

业务智能体

"value"：｛'name"；"markdown"，"'params"：｛"text"："我们来分析一下"｝，"unitId"："markdown-@"，"hasNext"：true｝

渲染引擎

const op2 = ［｛'op"；"replace"，"path"："/@/params/text"，"value"："我们来分析一下用户的需求"｝

const op3 = ［

｛"op"："'replace"，"'path"："/0/hasNext"，"value" ： false｝，

Skill

流式输出协议

｛'op"："add"，'path”："/1"，"value"：｛"name"："columns"，"params"：仔，"unitId"："columns-1"，"hasNext"：true｝｝

const 0p4= R

"'op"："add"，"path"："/1/children/0"，

"value"：｛"name"："image"，"params"：｛'src"："..."'｝，"unitId"："image-2"，"hasNext"：false｝

｝

22.后端往前端传递的消息协议

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 030

支

STREAM RENDER

边输出边渲染/减少输出内容

「流式渲染方案」

用户

HTML代码的改进方案

LUI 界面

业务智能体

渲染引擎

S331HONT,4CIMT3323

檢心指隊

Skill

流式输出协议

2osiw.ornorl'Serorl, ono

w wX- wes tonpse

sonst

this-getNttrituto！

corak ieeilds- 1ucise.Leora lieethioml || tueide.icons（nesl：

cwee:fleeteClcnan：（Lcomhcoal：

23.实时生成UI- HTML or React 代码生成方案

acon

InfoQ 极客传媒

全球软件开发大会

## Page 031

STREAM RENDER

边输出边渲染/减少输出内容

「流式渲染方案」

终端DSL方案「账单」

Web DSL方案

HTML / React万系

用户

：！！5Gk

2023-10

＜ 花呗账单

此刻 对话 灵期

LUI 界面

下午好

下午天气阴，温度9°C，一小时后有小雨，记得带伞

找。

业务智能体

渲染引擎

现在家？空府

Skill

流式输出协议

小时后參 取

探一下

G 张单分析

# 记个苹儿

醫 签日怢

有什么问题尽管问我

24.实时生成UI-更多产物类型的例子

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 032

支

RUNTIME RENDER

增加复用率

「TOC 运行时渲染方案」

如何给 不同的用户 在不同场景下 购买同一个商品时，展示不同的页面

产品数据库

B Sarah （25）

Alex （32）

曲 Designer

Developer

系 Travel

一 Gaming

电子产品

耳机

蹶狡

Sarah （25）

Alex（32）

（壁号，属佳）

《墾号，

厲住）

（尺品，顾色）

（尺码，嘴色）（尺码，顏色）

由 Designer

E Developer

aTravel

P Gaming

（尺劣，前色）

服装

运称

材盒

榨装

圭标

（天码）

（選也）

｛共過）

（註點】

服装

2 John （20）

2 Sarah （25）

（图节、本）

€ Sports

PSports

产品目录与信息

相似的人 买相似的产品，可以用同一组页面

25.UI生成-召回方案 存量数据都有

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 033

RUNTIME RENDER

增加复用率

「TOC 运行时渲染方案」

如何给 不同的用户 在不同场景下 购买同一个商品时，展示不同的页面

DIFFERENT CONSUMER PROFILES

SAME PRODUCT：

数据冷启动

SNEAKERS

YOUNG MALE

YOUNG FEMALE

ELDERLY PERSON

Ai 2 Ecguus

SUPPORT &

CUSHION

- 用户特征

•商品数据结构

WORKDAY

-日期特征

•业务特征

ADVENTURES

WEEKEND

GET THE LOOK

ALKINC

EAS

DIFFERENT DATES

WEEKEND

用户

UI召回

EESTVE

DEALS

SPECIAL

THOUGHTFUL

HOLIDAY

26. U生成-召回方案 借助U仓库，实现秒级响应、一人N面

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 034

支

RUNTIME RENDER

「TOC运行时渲染方案」

边输出边渲染丿减少输出内容

增加复用率

UI 仓库

- 组件引用

业务智能体

渲染引擎

-动态渲染

数据冷启动

此刻双语 灵鞋

Skill

流式输出协议

下午好

下午天气雨，這服8公，一小村后公小两运海那中

相似性过低

离线生成

UI 召回

9°

27. 解決方案总结

术 为什么问阳风管问我

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 035

第三章

如何实现有效的监督&迭代优化

aCon

InfoQ 极客传媒

全球软件开发大会

## Page 036

支

UI QUALITY ASSESSMENT

「UI评估」

“这个生成完，让我们产品把把关”

28.质量监督是UI生产到上线的关键关卡。

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 037

UI QUALITY ASSESSME

共2阜复期

搜素規则名称

官方-UI视 规則集 UI運估

「UI评估」

＋新建规则

创肆人

创羸时侧

Rule Key

2026-01-21 09:57

test_rule_key_5

停止生成

宫方-UI 視觉规则集

U！ 评估

描还备注

8 编辑

设置数据

宫方定义的U堂规菇，用士许估是古有UI 樱公销误

方定义的UI视觉规范，用于评估是否有UI 视觉错误

支付宝业务设计规苑

0！评估

支付宝客户嫩产品没计欢花婉则

详情内容

② 编辑

poor_visual_hierarchy（视觉展级差）

说明：UI元素必須遇过大小、颜色、间距和位置来建立清晰的重要性

层级。

规则：如果让重要元案不够突出，或制造多个相互竞争的视觉焦点，

“个人旅行万

会使用户感到困惑。

inconsistent_spacing（何距不一致）

说明：UI元素在整个界面中必须保持一致的问距硕式。

规则：否则会造成视觉混乱，并降低界面的专业感和可用性，

misaligned_elements（元素未对齐）

说明：UI 组件必须正确对齐，以建立视觉秩序和一致性。

规则：否则会”坏视觉流动，使界面最得杂乱且不专业。

inappropriate_grid_system（网格系统不合理）

说明：界雨布局必须遵循合理的网格系统，以确保经构一致.

规则：香则会导致布局混乱，难以浏览和导航。

color_blind_unfriendly（对色宜用户不友好）

说明：配色方案必须能破色觉缺陷用户区分。

规则：否则会让色盲用户无法理解依校颇色编码传达的信息。

overuse_of_colors（赖色使用过度）

28.质量监督是UI生产到上线的关键关卡。

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 038

吃 云游记

UI QUALITY ASSESSMENT

「UI评估」

行者无疆，心随景动

记杀每一次出发的楼动，分享旅逾中适

规则录入

见的山川湖漤与人问烟火，

动评价

报告输出

2075-09-

渔逐欧者拉：冰岛环岛自鸡日

#D

RULE NAME

最新游记

记

评分审核

总体得分

Poor Visual Hierarchy

Crpenized elements with clearimporanceleves usings

在世界尽头的冷番仙境，感曼冰川与火

山的失舞，即使在要度中守候了三个小

•2. Inccnsistent Spacing

Wain:nin ocnsistent spacing patterns throughouttre

时，当承抹妹光在天际舉动时，一…

總构忮砓份

E Misaligned Elements

Prcperly aligned compenents fer visual order..dison

闼设金女味

布局逻辙*

S Color-Blind Untricndly

Schemes must be cistnguishablc for vision issues...

Violating Brand Cuidelines

Achere to esteblished visual identity （colors, fonts..

sueS

Potential Issues

细节缺陷

涍审桢

Megible Text

Readable with acpropriate size, weight. Ine spacing

Confusing Navigation

Intuitiyc struclure folloving Ulcomventions.prcre：

7 2023-11-

或清晰

可能因上下文或受

详细诨价

Unresponsive Interactions

放都红叶狩：千年古都的秋日

根本上

众而异的因素。

私语

问题

Poor Form Yalidation

Clear error messages and validation reedback.. use

纷行在岚山的打精小径，程足于清水的

部发生了严重的物谋车叔（製发 Rule A.1）。日期（如

Non-Responsive Design

Interlaces adap:to diffarent scrgen sizes...content

異台之上。当秋风杂红了两山的报叶，

（e.g.，误导性的

*15.021 和地点《如“部，克”因容器宽度不足发生换

这座古名的哎中伯供在传声诉说着干，

4 2023-06-

！希照，圣托出

式不

颜色编码、伪造

行，直接与下方燃悲发生了文字里塑碰说。这种基础的容

器溢出控制失识，属于前竭验收的死刑。［视必细节|元素

岡濃全文

發琴海的蓝「迷失在圣托里尼

数据）

之间不仅是”拉贴險：、简直是：驗也脱是驗（触发 Rule

的白墒间

C3】，又字最无算片地所在一起，完全疲环了可该性

这里在世界上最天股日浴，也有最烧带

（iloginlo_toxt）•［布局］这种由于換行导致的垂直的律

官方提供规则

业务录入规则

的菸白配魚。在Oia小題的最慮法路一

破碎，让整个卡片头部品得摇掘称坠，絲毫没有专业度可

曰

T

杯如球，看君夕阳惯摄酸入景翠海

对济

遮挡 层级架构

主题色 文案风格

阅读全文＋

29. 规则体系

QCon

Das A K, Mueller K. Misvisfix: An interactive dashboard for detecting, explaining, and correcting misleading visualizations

InfoQ 极客传媒

using large language models［JJ. IEEE Transactions on Visualization and Computer Graphics,2025.

全球软件开发大会

## Page 039

支

UI QUALITY ASSESSMENT

「UI评估」

UI 质量评价

标注榄式

时比模式

山站米岩出

山上他JSONL文件

效掂列表

鱨构性硬伤

19 321a1103-d1o2-4394-0ec4-17，

每节觖陷

详细许价

12929.00

视览呈镜涵可，但选不过没报過迫症的审视。！而局1你然北了亲要性原則的禁意|触发Rue D.2）。别表为容抱园紧贴上方，市CTA技徒孔學響北落在度B，中润留出了一玫尴您的完效空论（触发 Rue 8.31、这停空做分配证

模宽此在网资光强单后户生断屈，内容与现作的天玩发戒物理距离希释了，虽然没有发生你但碰撞，但这种您放的壬真的津真’朝致"还爱得远，

图片标注

标注列去（0）

AI 账单新变化

Q

有新的未入账消费待确认

廿死狋住

已为你聚合大额待确认支出

iPhone15

2025-10-28• 数码电器

5999.00元

MacBook Pro

2025-09-28，数码电岩

12999.00元

•人审重合率：68.57%

查看全部

-人审通过重合率：43.75%

•人审拒绝重合率：100%

30.UI自动化评估 ＆ 人工标注

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 040

UI QUALITY ASSESSMENT

「UI评估」

自动迭代优化链路

1-清按照用户需求，生成HTL页面，要求如下：

1+请根据以下「分层式内容规范」直接输出完整且符合要求的 HTML 页面代

+码.

3-# 臺础要求

2+需水：$（requirenent）

4- 使用HTNL5标准语法

3+

触发

5 - 包含完聚的文档结构 （DOCTYPE、html、head.body标然）

层级化内容规范（务必逐条热行）

6-设置合适的页面标题和meta信臮

7- 确保代码格式规范、缩进清晰

6+A. 文案优先级与字号

7+P1（导航/主标跑）：32px /2ren1P2（副标題）：24px /1.

9-米内容更求

+5 rem

10— 页面内容需要紧扣用户需求

8+P3（段落主题）：18px / 1.125 ren |P4（正文/辅助）。

11- 包含标、段落、适当的结均化内容

+16pX/1rem

细节缺陷食會*

未通过

刚刚

12-- 如果主题适合，可以添加列表、圈片占位符或其他相关元素

9+P5（最小可读）：14px /0.875 ren 1［不得在同级元素中出现两种字

13-- 内容要有一定的完整性和可读性

+号！

文本内容样式不规范

14-

144.

上线下线、审核

31. 生成链路自动迭代流程

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 041

支

总结与展望

用户 &LUI应用 交互场景

业务Agent

运行时渲染召回方案

流式渲染方案

召回

生产

生产平台

UI管理平台

支撑

生成式U链路调试平台

UI流水线生产平台

仓库

UI评測

UI标注

U审核

优化

工具集

流式渲染引擎

Skill 能力输出

×风格化 X组件检测 × 需求改写

日 页面声明协议一》图 增量消息协议—＞三 动态渲染器

基建

多模态知识库

窈，大模型

数据库

视觉/评测模型

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 042

几个想法

CLI？

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 043

总结与展望

READY

提高生成质量

应用到LUI

「链路调试工作台」＆「工具」

「流式渲染方案」＆「UI召回」

质量监督

Claude Code

「半监督质量评估」&「规则体系」&「自动迭代」

Skill 集成

TO BE SOON

平台：

Claude Code 深度集成&产品个性化资源管理/知识库

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 044

InfoQ 极客传媒

QCon

全球软件开发大会

THANKS

黄兆嵩 山糕

蚂蚁集团

## Page 045

上

探索 AI 应用边界

AiCon

河

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
