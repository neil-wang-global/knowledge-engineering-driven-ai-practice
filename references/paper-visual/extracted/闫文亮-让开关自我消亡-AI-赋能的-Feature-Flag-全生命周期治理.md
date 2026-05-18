# 闫文亮-让开关自我消亡-AI-赋能的-Feature-Flag-全生命周期治理

> Page-by-page visual information extraction from rendered page images. Text below preserves the visible text recognized on each page; pages with diagrams include every OCR-readable label captured from the image.

## Page 001

InfoQ极客传媒

QCon

全球软件开发大会

让开关自我消亡：

AI 赋能的 Feature Flag 全生命周期治理

闫文亮

快手 资深服务端架构师

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

InfoQ 极客传媒

QCon

全球软件开发大会

⑨

Feature Flag价值与隐形技术债

02

Al治理Agent：从Demo到工程落地

目录

03

安全护栏：三重校验＋双引擎架构

04

自进化：双Agent驱动系统自愈

05

总结与展望

## Page 004

Feature Flag价值与隐形技术债

从业务刚需到技术债陷阱

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 005

• 真实的故障

—〉

—>

APP启动

后端服务器

返回不兼容字段

APP崩溃

死循环：再次启动—>

后端已回滚，但崩溃太

APP崩动

再次崩溃

早，未拉到修复数据

Solution

唯一恢复方式：

—>

卸载重装

如果你是这个需求的研发，你的心情会怎么样？

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 006

•

什么是Feature Flag

无Feature Flag：全量发布

APP启动

—>

调用后端接口

返回不兼容字段

APP崩溃

死循环：再次启动一再次崩溃）

所有用户都受影响，只能卸载重装

外部用户 外部用户

有Feature Flag：内部灰度

APP启动

APP启动

调用新接口

走老接口

调用新接口

正常运行

走老接口

返回不兼容字段

（绿色对勾）

内部员工（灰度）

APP崩溃（橙色警告）

问题仅影响内部员工，外部用户零感知

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 007

Feature Flag的价值

（灰度放量- 安全阀门）

Feature Flag开关

灰度放量：先让1%用户试用，确认

无误后再全量

1% 10% 50% 100%

避免全量上线的风险

少量用户

大量用户

（快速回滚-降低损失）

Feature Flag

秒级关闭：发现问题立即关闭，无需

（秒级）

等待代码回滚

ON

快速回滚，降低损失

功能异常

OFF

服务恢复

（发布解耦- 核心对比）

（无FF

ON！

B

ONO

C

OFF

A

B

C

Vs

代码包A+B+C，B出问题全部回滚

A和C保持开启，只关闭B，各功能独立控制，互不

影响

是我们迭代路上的好帮手

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 008

Feature Flag的价值

AI

Feature Flag/保护

A 新功能发布风险增加

更需要谨慎发布

1%

10%

100%

AI生成代码，研发人员不熟悉

Feature Flag：安全发布的守护者

Al Coding时代，不熟悉代码更要谨慎，

Feature Flag是必备安全网

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 009

代码中几步之内必有开关

private boolean inject

onfig（

e type）：

iif （type

return faLse：

if CKswitchInstance.WEB_SERVER_POSTER.getBoolean（ key "anabls

tagloonV2"defauiyalue. false; KsFocts（））f

TagScope setTagTypeconfig（MAGTC_

FT6_V2.get（））：

perf namespace."sears

s9nFH9，

subtage"v2"）.1ogstashonly（）：

return Erue：

if （KSWitchInstance.WEBSERVER_POSTER.getBoolean（ kay "enabls

shTag当，

detaultvalue false, K5Focts（）））

TagScope.setTag Typeconfig （MAGIC_l

I6_MAP:getO.get Ctype.getTagType O.getValue（）

penf（ namespace: searg

eConTig".

isubteg."v1）.LogstashOnLy（：

return true；

perf（ pemespace： "seancha Config"lsubagr "default"）.Logstashonty©），

netuPn faLse/

pubLic static boolean enablm目

teParams（String bizName）f

KsFacts ksFacts = KsFacts.newBuilderCksFacts（））

.custom（"bizlame"bizName）

.buiLd@：

peturn KswitchInstance,WEB_SERVER_SEARCH.getBoolean（ koyenabl

AuteParams"，

defauitValue false, ksFacts）；

2usages

public static boolean

enable

T Rtimize（）

return Kswitches.WEB_SERVER_SEARCH.getBooLean（ key "en

ROatinize"e delulValues false）

10 usages s.hukui

pubLicestatic boolean enable

plit（）！

return KswitchInstance.LOCAL_LIFE_PLATFDRM.getScopeBooLean（key:Wenanlc Spltt，

defautVaiue false,KsFacts（））；

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 010

•

开关多带来的问题

代码维护成本飙升

浪费计算资源

新人接手项目，在一堆开关里梳理

每一次接口调用、每一次逻辑判

逻辑，分不清哪些有用、哪些没用

断，都要经过这些无用开关的校验

Al写代码后，我们都成了新人，对代码都不熟

日积月累就是不小的损耗

短视频服务，每秒会调用开关15亿次

浪费带宽资源

隐藏稳定性风险

客户端使用的开关需要通过接口

过期开关偶发拉不到推全的值，

进行下发

走到了旧的逻辑

每年开关下发的带宽成本就有xx万

引发意想不到的线上问题

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 011

• 过期开关没拉到推全的值

开关仍然存在，

但被认为“永远为true”

Old logic

deprecated

>排查困难

开关推全上线

开关遗忘

触发问题

异常发生

业务排查很久才定位

TODO：下线旧逻辑

TODO：

程序Bug：

走到I日逻辑，触发异常

问题根源：

（未执行）

开关未拉到推全值

旧逻辑已不再维护

几年前的过期开关

A 推全的开关也要及时清理，否则就是定时炸弹

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 012

治理困境

加开关-容易

清开关-困难

十

加开关

< 清开关

时间

2 1分钟

Z91小时+

if （flag.isOn（）） ｛.•｝

1. 梳理上下游逻辑

收益

2. 评估下线风险

解決上线风险

3. 修改代码

故障快速回滚

4.测试验证

发版解耦

5. 发布上线

门槛极低，收益极高，顺手就做

额外工作，无收益，担风险，没人愿意做

开关债务的根源：加法容易，減法困难

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 013

治理困境

创建人离职，项目交接

相信后人的智慧，反

正对我无收益，让后人治理吧

这个开关是干嘛的？

什么时候下线？有风险吗？

创建开关

跨部门合作，职责边界不清

自

下线开关可能影响

开关债务越滚越多

其他部门业务

债务累积

跨部门合作

不敢动，选择不动它

不敢动，选择不动它

不知道用途和风险，跨

不知道用途和风险，跨

部门影响太大，还是不动吧

选择不动-不敢动

离职交接

部门影响太大，还是不动吧

A 相信后人的智慧＋跨部门边界不清=债务死循环

QCon

Infoo极客传媒

全球软件开发大会

## Page 014

•

治理困境

～累计创建开关数

节

2019

2020

2021

2022

2023

2024

2025

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 015

AI时代加速技术债累积

Technical Debt Accumulates at Unprecedented

Scale

技术债以前所未有的规模累积

“What we're seeing is that Al code assistants excel at adding code

quickly, but they can cause 'Al-induced tech debt，” explained GitClear

founder Bill Harding. “This presents a significant challenge for DevOps

Armando Solar-Lezama, a professor at MlT specialising in program

teams that prioritise maintainability and long-term code health.”

synthesis, offered a colourful assessment in remarks widely cited across

“我们发现，AI代码助手在快速编写代码方面表现出色，但它们可能会造成“AI

the industry: Al represents a "brand new credit card here that is going to

引发的技术债务’，”GitClear 创始人比尔•哈丁解释道。“这对那些优先考虑可

allow us to accumulate technical debt in ways we were never able to do

维护性和长期代码健康的 DevOps 团队来说，是一项重大挑战。”

before."

麻省理工学院专注于程序合成的教授阿曼多•索拉尔-莱扎马在业内被广泛引用

的言论中给出了一番生动的评价：人工智能就像一张“全新的信用卡”，将让我

们以前所未有的方式累积技术债务。

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 016

传统治理方式的的局限

平台规范治理

设置过期时间、搭建审计看板

依赖业务自觉性，执行参差不齐

核心痛点

业务怕下线引发故障，

工程脚本治理

哪怕确认无用也不敢操作

自动化脚本扫描删除

灵活性不足，复杂场景易出错

想治 治不动

业务不停用

专项治理行动

开关越积越多

回到起点

定期组织清理专项

耗时耗力，“一周风”式，无法持续

治理速度远远跟不上开关新增速度

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 017

Al打破死循环

治理死循环

时机刚刚好

外部条件已成熟

夭武

1.大模型技术快速迭代

2.API调用成本降低

3.代码理解、修改能力成熟

Al打破死循环

内部条件已成熟

AI治理新时代

多

1. 开关治理痛点必须解决

2.业务迫切需要高效安全治理方式

3.公司AI基建不断投入

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 018

治理Agent的演进与工程落地

从Demo到工程落地

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 019

• 治理Agent的演进与工程落地

快手开关治理发展历程

2026

2025

AI Native开关治理（进行中）

不再是任用AI治理开关

2023

而是让开关自己驱动自己下线

Al开关治理

实现生命周期的智能化治理

2022

推出Al开关治理Agent

核心目标帮业务提效

运动式治理

減少人工介入

每个季度组织专项清理

治理消息推送

人工推动业务同学治理

培养业务自主下线开关意识

效率低，效果差，反弹快

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 020

AI治理开关初尝

正在开发需求…

开关A已经100%返回true，

开关治理消息：

帮我把这个全量开关下线掉

请清理名下无用开关

25年上半年

if （switchA.is0n（））｛

这么快就改完了！

AI能搞定单个开关.

｛.｝else｛oldLogicO；

能不能规模化

处理所有开关？

1/ 开关已下线

API

代码逻辑正确

格式规范

调用大模型Open

符合要求

符合要求

APl，实现自动化

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 021

治理Demo搭建

大模型

GiT

定位代码：开关key 一

读取源码：Git Open API

Al修改：Prompt+源码

提交MR:Git Open API

定位所有使用该开关的

将源代码读取到内存

传给大模型

提交代码 >

代码文件

返回修改后代码

自动生成MR

Bad Case

提示词调优

41

41

import com.goog le.common.util.concurrent.ListenableFuture；

5.**禁止修改非目标代码*料

42

42

import com.google.protobuf.ByteString；

*禁止修改其他开关调用**：即使使用相同的Facts对象，也不能修改其他开关的调用没辑

-**禁止简化共享的方法调用**：如ksFacts（）等被多处使用的方法调用，即使在目标开关中被优化掉，也不能！

43

- import

bStore；

-料禁止修改共享的变量构建料：如 KsFacts.newBullder（ksFacts（））等包含上下文信息的调用，不能简化：

44

- import

ekey：

4禁止删除仍被其他代码使用的importe：必須确认import在整个文件中完全不被使用才能明除

45

43

import

-ww~~-_Table；

6.

料逻辑等价性保证**

46

44

import

Lient；

-只有在确保不影响其他代码逻賴的前提下才能进行优化

保持所有非目标开关的原有行为不变

- 保持共享组件（Facts、Builder等）的原有语义

7.*渐进式安全优化

*第一优先级**：确保代码可编译，不出现语法错误

-**第二优先级**：确保逻辑等价性，不改变非目标代码行为

-**第三优先级**：在前两个条件满足的基础上进行代码优化

er.filterAtInCommentVisible（filteredComments, userId，

*出要水*

er.filterAtIncommentVisible（filteredComments, userId，

sthink>

｛｛思考的内容，think step by step｝｝

erv

</think

思维链 （Cot）

<code

｛｛完整的优化后Java代码，不包含任何markdown标识符、代码块标记或额外说明文字，确保输出为纯净的Java源代码｝｝

ervice..

userld）；

s/codex

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 022

逻辑错误引起足够重视

方法名与开关名一致

逻辑改反

开关名混淆

无关代码误改

大模型误将方法当成开关

“返回false时执行A”

开关A和B的Key相似，误

修改开关时，把相邻的“if

相关代码删除

误改成“返回true时执行A”

将B也下线

（a == 1）’改成'if（a==2）

整个功能模块失效

业务逻辑异常

误下线正常开关

莫名其妙改坏业务逻辑

完全信任大模型

建立安全护栏

=被动等待故障发生

拦截所有错误

不能指望大模型“永远不出错”

防止错误代码透出到线上

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 023

多轮对话

Andrej Karpathy 安德烈 卡帕西

@karpathy @ka

C 显示翻译

There's a new kind of coding I call "vibe coding'， where you fully give in to the vibes, embrace exponentials, and forget that the code

even exists. It's possible because the LLMs （e.g. Cursor Composer w Sonnet） are getting too good. Also ljust talk to Composer with

SuperWhisper so I barely even touch the keyboard. l ask for the dumbest things like "decrease the padding on the sidebar by half"

because I'm too lazy to find it. I"Accept All" always, I don't read the diffs anymore. When I get error messages ljust copy paste them

in with no comment, usually that fixes it. The code grows beyond my usual comprehension, I'd have to really read through it for a

while. Sometimes the LLMs can't fix a bug so ljust work around it or ask for random changes until it goes away. It's not too bad for

throwaway weekend projects, but still quite amusing. I'm buildinga project or webapp, but it's not really coding -ljust see stuff，

say stuff, run stuff, and copy paste stuff, and it mostly works.

我把一种全新的编程方式称为“氛围编程”，在这种模式下，你完全沉浸在编程的氛围里，拥抱指数级的效率提升，甚至忘了代码本身的

存在。之所以能做到这一点，是因为大语言模型（比如搭载 Sonnet 的 Cursor Composer）已经变得太过强大了。而且我只用

SuperWhisper和 Composer 交流，几乎都不用碰键盘。我会提一些特别简单的需求，比如“把側边栏的内边距减半”因为我懒自己

去找这个设置。我总是直接“全部接受”生成的代码，再也不看代码差异了。遇到报错信息时，我就直接复制粘贴进去，什么都不说，通

常这样就能解決问题。

写出来的代码已经超出了我以往的理解范围，得花时间仔细通读才能看懂。有时候大语言模型修不好某个漏洞，

我就换个方法绕过去，或者让它做一些随机的修改，直到漏洞消失。这种方式做一次性的周末小项目完全没问题，而且还挺有意思的。

我现在正在做一个项目或网页应用，但这已经算不上真正的编程了—我只是看看内容、说点指令、运行程序、复制粘贴内容，结果大

多都能正常运行。

上午7:17•2025年2月3日，

688.1万 查看

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 024

多轮对话

类比AI对话框

由

基于Session的多轮对话实现

我们平时使用AI对话框的时候，也经常发现大模型一次

后端

LLM

检測框架

性返回的内容不符合我们的预期，于是我们会采用追问

的方式，或者补充更多信息的方式进行多轮对话。

第一轮：原始代码+修改指令

返回修改后的代码

代码检测

快手翻译成英文

发现问题：XXX报错

多轮对话原理：带上历史对活一起发送

The transiation of"快手" into English is Kuaishou.

第二轮：历史对话+检测报错

If you are looking for the name of the app as it is marketed internationally, it is called Kwai.

4

根据上下文修复代码

再次检测

只给我输出结果就行，不用解释

检測通过

Kuaishou

后端

LLM

检測框架

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 025

• 校验模块强卡控

？

有了多轮对话，如何检测

大模型修改后强校验框架

Al修改是否有问题？

通过扩展检测插件，全方位检测，拦截各类Bad Case

S 逻辑检查插件

编译检查插件

• 是否下线了多余开关

。代码格式是否符合CheckStyle规范

•布尔逻辑表达式是否被改反

•是否存在语法错误

• 开关关联的业务逻辑是否完整

•流水线编译是否能通过

•是否误删非开关相关代码

检测通过— 进入下一轮 or 提交MR；检测失败-反馈错误给AI送代

Con

InfoQ 极客传媒

全球软件开发大会

## Page 026

• 第一道安全护栏 - 编译/逻辑错误拦截

检测失败，反馈错误信息

第一道安全护栏

阶段2：逻辑校验

阶段1：基础语法与风格校验

删除多余开关

校验插件

阶段3：编译构建校验

原始代码

大语言模型

（Checkstyle）

布尔逻辑表达式

输出

+修改指令

（LLM代码生成）

代码编译检查插件

校验插件

可交付代码

（流水线编译验证）

代码语法检测插件

其它插件

检测失败，反馈错误信息

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 027

•

•第二道安全护栏 - 人工拦截兜底

检测失败，反馈错误信息

第二道安全护栏-人工review

Al治理

原始代码

大语言模型

输出

第一道安全护栏

+修改指令

（LLM代码生成）

可交付代码

检测失败，反馈错误信息

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 028

大模型检查

评审模型

主模型：生成与修改

◎投票表決

评审模型独立推理

3个互不依赖的LLM分开判断，不共享上下文偏见

评审模型

个错误回传

投票胜出

评审模型

2个或2个以上通过，才通过

投票表決

模型级安全护栏

A 只要Review结果的确定性达不到100%，所有的修改结果还是需要100%的人工参与度

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 029

大模型检查

PAL: Program-aided Language Models

PAL.：程 辅助语言模型

Luyu Gao Aman Madaan Shuvan Zhou Uri Alon

Pengfei Liu？

Yiming Ying Joic Callin'Gratam Neabig/

｛-uyug,amdaan,shuyanzh,valon.p11u3.Yimins.ca_langneub1a］ecs.cmu.edu

Shryug.

amidaan, shuyanzh,ualor, plius.

系，callan gneubigkacs.cmu.edu.

Abstract

1.Introduction

摘变

1.引音

Taree languae models CPMs） have demon

stratcd an impressive ability to perfom arith-

Until as recently as three years ago. reasoning was consid-

大型语音模型《LLMs）在谢试时提供少最示

就在三年前，推理能力还被认为是大型爵音模型

meuc and symbolic reasonng tis. witen pro

crcu to be onc ol te mest seniicant clsallcnges Liat Jarge

例（郐

“少样本提示”）的情况下，已展现出

（L.I.Ms）尚未攻克的最重大挑战之一 （Marcus，

insuage mouels t.ews nad nocye overeome Camcus.

mrompting"）. Much of ihis success cin he it-

2018:2020:Garcez & Luamb,2020）. Recently. LLMs have

出色的算术和符号推理任务能力。这一成助

2018:2020:Garcez & Lamb,2020）。近年来，大型

很大程度上归功于“思维链”

奇提示方法，

語高校型情助少样本提示（Brownet a..2020）、在

of-tnoughs". which employ LLMs for bott wnder-

Fsks, inc luding commonsens： （Weiet al. 2021: Samh cs e.

这类方法利用 LLM 通过将间题分解为步聚来

各类推理任务中取得了令人瞩目的成果，这些任务包

Haring the problem deseription by decompusing

202.： Madaanc al.，2022.mathematica1l ewkawvezetal.

理解何题描述，并解決问的每一个步摄。

括常识推理 （Weiet al.，2021, Sanh et al.， 2021，

it into steps.as welt as solwing cich step of the

2022. Wuci al. 2022: Mishra cr al.， 2022）.and symbolic

尽管 LIMs 似乎擅长此类分步分解，但即便

al..2022; Wu et al.， 2022, Mishra et al.，2022） 以

Madaan etal.，2022）、效宁推理 CLewkowyczet

problem. White LLMs secm to be adcpi at this

rasonitig （YawcLaL.，2022: Ahneral.2022）. using tcw-snot

make logical and arithmetic misenkes in ihe sola-

soTLoi sict-by-sicp uccompostton. LLis oiten

prompung/Brown dal.，2020）.

问適分解正确，LLM 在求解环靠仍带出现返

及符号批理 （Yao et al. 2022, Ahn et al.. 2022）。

This process lisss been socceleraned by mesheds tbat ne-

掛和算术错误。本文提出了程序销助语音模

guire Clas to generale thesr cxpisen teasang sicms

型（PAL）：这是一种新颖的方法，利用LLM

通过要求大語言模型《LLMS）生成明确推理步骤的方

corectly. In tis paper. we present Program-

suech as "chain-of-thoughe"（Wei e nl, 2022）， *scrltch-

阅读自然语吉问题并生成程序作为中间维理

法，“思維胜”（Wei 等人，2022）、“草積水"（Nye

Aided Language models （PAL）：a novel approach

步飛，同时将求解步骤交由 Python 解择照

存人，2021a0 以及“从少到多”（Zhou等人，

Uw uses ute Lln o read natural anguape proa

2022） pruning In paricular, the widely used chair-of-

净运往时环谈处理。在 PAL 瓶果中，将自然

2022）提示法，进步加透了这一过程。具体而音，

Jens and penerie pyognas as the inermnediane

thoaratieot）methad presents the mnode with te exnlicst

应用广泛的思维链（COT）方法会向模数展示得出数

intcrmediate steps thut are reguired to reach thie fimal answer.

酒言何题分解外可执行步票仍是 LEM 的啡

终答案所需的明强中间步票。随后，

模聖露对实际测

runtime sucl as a Fytion interpreeer. With PAL，

Tlon, te nedlel is expected to spply a similar deconpesi-

学习任务，而求解则委托给解释器完成。我

試示例采用类似的分解方式，进而连续得出确的量

decomnesins the naturdl language nebiem into

runmsble steps remains the only leaming taxk for

accurite finad answer （Lingct al.2017: Amini ct aL.2019）.

们针对 BIG-Bench Hard 及其他数帮集的13

终资案（Ling 等人，2027;Amini 麥人，2019）。然

tbe LLM. whie solving is dclegated to the inter-

项效学、符号和算法推理任务，统证了神经

而，尽管大沿音模型销够将自然语合向题分解为多个

preser. we demonstrle tus synes:y nclwcen

peoblc ms into stcps und perform sinaple aridnetic opers-

LLM 号符号解释器之间的这种协同效区。在

步霖并完成简单算术运算，但在处理复杂算术

neural LI.M and a symbolic interpeer across:13

ticas. teir pertormance falis dramatically wen dealing

所有这些自悠语言推理任务中，利用LLM生

（Hendrycks 舒人，2021:Madaan &

Yazdunbakhsh, 2022） or lange nubers（Geva es al.， 2020

wth enlcx anlamettc（Hencrekselals cwel Macaane

成代码并通过 Python 解释習进行推理，所

Yazdanbakhsh,2022）或大数（Gieva 等人，

ing rusks from BIG-Bench Hau arf others. In

取祥的结果准毋率运痛干規棖大羿多的颇

2020;Nogueira 等人，2021;Qian 等人，2022）

all these natwvl Jergaige nasoning tasks.gcnce-

Python interpreter leads to more aocurate resuilis

g coc usng an LENand reasonag ustag：

fine-tuning a PL.M-based modl on 164B takens of explici

型。例如，采用 CODEX的PAL在GSM8K

时，其性能会急该下降。事实上，您报道，即便在基

数招集上实现了聂先进的少样本准疏率，超

于 PaLM 的模型上对1640亿个是式数学内容标记进

（Lewkowycz et al.， 2022）

roporicdly "incorscoticasoning" and"inoonces caleulation"

感了 Pal.M-540B 模型

CobEx achieves state-of-llve-art few-shat sccu-

nses chein-of-thought by absolutc 159top-1

In this puper we propose Program-Aided Languugs

在本文中，我们提出了程序雏助语合模聖（PAL）：这

moccl PAt:anovcl aoproach that uscs an LLw to read nat-

尼一和新親的方法，

利用大语音榄型（LIM）解谈自

utsl language prohlems and ganerae proyraim as teasning

steps.bit oflioadis the sofuion step toa Python intcrpreter.

*阳停贡破1爽卡肉基栩隆大学鸡宫技本研究所2美国灵

然语言向题井将排理步张生成为程序，同时将求解步

感认知公司。通讯作着：离路笔、阿商•马好、隔诗娇，邮

骤交由 Python解解器执行，

如图1所示。这种任务

that can decompos s natural Ianguage problem into pro-

節：<luyugamadaan,shuyamahl@es.cmu.edu>.

分说的方式依托于大语言模厚的能力

仑能格自然

snmnatc stcps which: is forlunatciy aviablc using con

沿音问题拆解为程序化步骤，

而这一点在当前最先进

temporary stuke-of- the-ar LL.Ns that are pre-（nined on both

第40 日国际根器学习大会会议论文果。美国夏成爽州百

2023 bu thee authards）

natural banguagc and programning languages （Browncr al..

山 PAILR 202, 2023年。版权所有©2023年者本人。

上 实现（Brown 人.2020;Chens

Code anadiuwhttp://eeawonw.chpa1.com.

工代码与数現见 http:/reaomwithgsl.com.

202la, Chowdiery 人， 2022a

尽管

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 030

AST引擎：用确定性的程序检测代替人工兜底复核

打造AST引擎，如果和AI引擎修改的结果一致，就不再人工复核

替换开关值

EntryRule

循环

表达式简化

布尔字面量清理

BoolSimplify

BooleanCleanup

规则

规则原子化，一个规则只做一件事情

语句清理

StatementCleanup（分发中心）

有向图

有向图驱动流程，级联触发规则

If清理

删除变量

删除字段

删除方法

删除赋值

Stream简化

标识符替换

移除嵌套块

删除布尔賦值

删除死代码

QCon

InfoQ极客传媒

全球软件开发大会

## Page 031

双引擎架构协作范式

LLM生成+AST校验

双引擎架构

LLM大模型：

AST校验：

处理模糊性，生成创新方案

程序规则确保零误判准入

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 032

治理Agent的整体流程

原始代码

+修改指令

通过

大语言模型

输出

第一道安全护栏

ASTReview

（LLM代码生成）

可交付代码

拒绝

检测失败，反馈错误信息

第二道安全护栏-- 人工review

Al治理

通过

输出

可交付代码

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 033

AST一定是正确的吗？

流水线测试兜底

原始代码

+修改指令

集成测试

流量录制回放diff

大语言模型

通过

（LLM代码生成）

第一道安全护栏

AST Review

输出

可交付代码

将治理压力由业务转向平台

拒绝

平台不是只提供提效工具，也要承担责任

检测失败，反馈错误信息

之前是业务有bug，改错了，业务自己负责

第二道安全护栏一人工review

现在是AST有bug，平台负责

Al治理

通过

输出

可交付代码

AST引擎和AI引擎同时改错的概率几乎为O

两者互补，且互相反哺

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 034

• 有AST引擎了，还需要AI引擎吗？

原始代码

+修改指令

大语言模型

通过

（LLM代码生成）

第一道安全护栏

AST Review

输出

可交付代码

拒绝

原始代码

AST 引擎

输出

VS

可交付代码

检测失败，反馈错误信息

第二道安全护栏一人工review

Al治理

通过

输出

可交付代码

AST不支持的代码一定会改错，到时候无法发现，那就还是需要人工100%的review

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 035

02

自我进化：人工到系统自升级

让治理系统具备自我迭代、自我修复、自我优化的能力

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 036

• 治理系统的进化刚需：规模一上来，人工维护就失效

规模增长 VS 人工维护能力

人工维护带来的三大困境

—治理需求—人工维护能力

效率低

1

人工Review排队，问题积压

人力成本浪费

2

AI大部分改的都是正确的，人力投入在无效review

滞后强

3

AST引擎和校验插件更新速度慢

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 037

• 评测体系：让优化有“据”可依

1、Al改代码

2、结果标注

基于trace存储AI的提示词和返回

Al修改的结果，需要人工进行review并标注

6、效果评测

3、看板搭建

评测体系

优化后跑评测case

讲标注的结果可视化

看优化的效果

5、针对优化

4、错误分析

针对标注结果进行针对性优化

錯误分析溯源

比如优化prompt，优化检测插件

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 038

•评测体系：让优化有“据”可依

原始代码

+修改指令

进入评测集

①

数据分析层

--Y

大语言模型

通过

（LLM代码生成）

≥第一道安全护栏

AST Review

输出

可交付代码

拒绝

②

评测执行层

检测失败，反馈错误信息

第二道安全护栏一人工review

Al治理

通过

输出

③

结果标注层

可交付代码

数据采集层

拒绝

进入评测集

进入评测集，并标记重要case

评测系统的技术架构

数据采集 ＋结果标注

aCon

InfoQ 极客传媒

全球软件开发大会

## Page 039

•让每一次人工复核，都变成治理系统进化的燃料

人工标注->系统自优化

人工对治理结果进行标注

评测通过->减少人工标注

持续迭代

正向飞轮

通过评测会使正确率提升

正确率提升会减少人工标注的量

优化完成->自动评测

系统自动进化

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 040

•让每一次人工复核，都变成治理系统进化的燃料

派 漏检：人工复核后Al是错的

◎ 误判：人工复核后Al是对的

本质 检测插件能力不足，有盲区

？

本质 AST规则僵化，误判率高

未覆盖（检测缺口），规则强度不足

误伤正确变更，识别不足

—》进化方向

如何进化

《 进化方向

把漏过的风险类型沉淀可复用的检测能力

把“正确但被推给人工”的案例沉淀为规则

发现是错误的，证明检验有问题

AlS|擎

未通过

大语言模型

AST引擎Review通过？

人工Review

（LLM生成代码）

编译/逻辑校验

改错

发现是正确的，证明AST有问题

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 041

双Agent专项升级

AST能力升级Agent

正确

解决：正确被推给人工（误判）

⑧ 人工标注结果

分析

自主修复

自动评测

产生报告

生产上线

定位原因

分流依据

优化AST规则

历史/新Case评测

汇总结论输出报告

评测通过直接上线

修改正确 or 修改错误

检测插件升级Agent

错误

解决：风险漏过（漏检）

自动判定并路由到专项Agent

定位

自动补齐

自动评测

产生报告

生产上线

发现盲区

新增风险识别

历史/新Case评测

汇总结论输出报告

评测通过直接上线

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 042

双Agent专项升级

编写测试用例

◎ 理解需求文档

编写技术方案

仓库：ks/kuaishou-kswitch

◎ 编写代码

② 评审代码

◎ 部署测试环境

AST 力升販（

②#发料

。 J万拉术为路

技太方案

双位出总道累与1C的第业。東欢沈饮化相发的内命。特就发汁三元会

反肉健：

conditinn

reture ainit 7K.1Y

P wExm

双K让次INOMO都建口奶粒，以及島理应或火干統法出对

2.3优化录程时产图

Zersieerstmpl

ZerafomersEngine

Dico lcanExpre3320n0ptin1zer

CoceAno lystsutils

＆ 更修汉拉：

ast6enecatedCode

narSe1cO2e

aCon

InfoQ 极客传媒

全球软件开发大会

## Page 043

•

整体流程

无需人工参与

流程结束

检测失败，反馈错误信息

通过

原始代码

大语言模型

校验插件

ASTReview

+修改指令

（LLM代码生成）

优化

拒绝

优化

校验插件优化

拒绝

通过

AST引I擎优化

人工review

Agent

Agent

人工复核变成系统进化燃料

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 044

整体架构

开关治理Agent整体架构

工具层

代码检索

源代码拉取

提交MR

流水线调用

检测层

编译检测

逻辑检测

AST检测

大模型检测

评测

结果标注

看板

回测

报告

Agent

AI基建

LLM

会话存储

多轮对话

模型切换

提示词

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 045

•

Al Native：全生命周期

之前工作的局限

之前做的所有工作，其实都集中在开关生命周期的最后一个环节—“删除”，这是很片面的

A 真正的AI Native开关治理，应该覆盖开关的全生命周期

智能创建

智能变更

智能删除

在需求研发阶段，就让AI参与进来

AI参与变更计划，变更巡检，变更阻断

基于创建时的上下文，自动删除

AI根据需求场景，判断是否需要使用开关

智能灰度放量：根据风险等级，自动分级

根据开关的预设条件

判断开关的作用（灰度放量、功能回滚等）

智能自动巡检，变更过程巡检系统/业务指标

V 根据业务迭代情況

给开关打上分类标签

V 异常自动回滚

根据用户使用数据

v 预设开关的下线时间和条件

动态调权与智能熔断

自动判断开关是否已经无用

•把脑子里的经验，沉淀下来作为AI的上下文

自 AI参与变更，避免人工忘记放量和巡检

无需人工介入，自动完成下线和代码清理

◎ 创建之初，就具备"可自动治理"的属性

⑦ 人工变更伙伴

◎ 实现开关的"自我消亡"

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 046

14

总结与展望

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 047

实践总结：Harness Engineering

（驾驭工程）

Stage 1

Stage 2

Stage 3

运动式治理

Al破局

双引擎架构

问题：治理死循环

突破：借助AI打破困局

核心：AI引擎＋AST引擎

AI引擎

双引擎协作

AST引擎

LLM

大模型

+

+

功能：强校验框架

+ 逻辑验证

功能：多轮对话+代码生成

双Agent自进化

意外收获

和Harness概念契合

目标：节省人力成本，安全治理开关

核心思想：用工程化手段约束Al、引导AI

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 048

•成果展示

AI累计下线1500+开关，删除代码60000+行

w 累计朗建开关数

现存开关个数 累计下线开关数

～ 里升长期使用开关个装

节

09

2019

2020

2021.

2022

2023

2024

2025

AI治理当前准确率在98%以上，AST引擎和AI引擎的拟合率在80%以上

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 049

，AI时代的工程治理新范式

传统人工管理

完美闭环系统

技术债A

完美固平衡

技术债B

“最好的治理，是治理本身被遗忘；最好的系统，是系统自己照顾自己”

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 050

InfoQ 极客传

QCon

全球软件开发大会

ywl

中国大陆

THANKS

大模型正在重新定义软件

Large Language Model Is Redefining The

Software

扫一扫上面的二维码图案，加我为朋友。

## Page 051

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
