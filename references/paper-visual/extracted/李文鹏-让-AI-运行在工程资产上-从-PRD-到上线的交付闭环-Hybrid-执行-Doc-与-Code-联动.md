# 李文鹏-让-AI-运行在工程资产上-从-PRD-到上线的交付闭环-Hybrid-执行-Doc-与-Code-联动

来源PDF：`references/papers/李文鹏-让 AI 运行在工程资产上：从 PRD 到上线的交付闭环、Hybrid 执行、 Doc 与 Code 联动.pdf`
页面图像目录：`references/paper-visual/images/李文鹏-让-AI-运行在工程资产上-从-PRD-到上线的交付闭环-Hybrid-执行-Doc-与-Code-联动/`

说明：以下为按页信息提取，尽量保留页面可见文字、标题、列表、表格与图示标签。
## Page 001

```text
InfoQ 极客传媒
QCon
全球软件开发大会
让 AI 运行在工程资产上
从 PRD 到上线的交付闭环
李文鹏
好未来- 前端专家
```

## Page 002

```text
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
```

## Page 003

```text
     01   业内痛点、数据、趋势


     02   SOP 六阶段实践

目录   03   从多人协同 – 全栈小队的转变

     0
          Harness 高 ROI 全景
     4
```

## Page 004

```text
• 体感快了 20%，实测慢了 19%
METR 随机对照实验（RCT）
METR SWE-bench 实测
16 位资深开发者•平均5年项目经验 246个真实 Issue
Benchmark 通过*生产可用
-19%
+20%
38%
20%
仁
实测：完成时间增加
自评：觉得自己快了
功能测试通过
可直接合并到生产
能生成*能进生产
AI生成的代码，谁来Review？
它对齐的是谁的需求理解？
这个人请假了，谁能接住？
Review 成本≥自己写
PRD 歧义一AI自信地猜
上下文留在对话里=消失
用 AI 开发工具 个人提效
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 005

```text
现状与共鸣：AI 写代码已不是问题
哈佛 联合 美国效能公司（518 家企业 、11.4万工程师、2亿记录）   Thoughtworks 交付周期中编码时间占比 40%

          代码量 +8.5%
         任务耗时 -8.7%
       功能交付量 ≈ 0 增长

国内某万人研发的公司调研


      编码效率 +30% 到 40%

       需求交付效率基本不变


用 AI 开发工具 ≠ 个人提效 ≠ 组织提效，从 PRD 到上线，每一环都可能是断点。
```

## Page 006

```text
行业趋势


        Prompt Engineering → Context Engineering → Harness Engineering
概念层
        从优化提示词，到管理上下文，再到构建 Coding Agent 运行的完整工程体系


        OpenAI： 3~7 人团队、100 万行代码、5个月、零手写
顶级实践
        Stripe：每周 1000+ 可直接部署生产的 Agent PR


他们的共同点：资产完备 + 验证闭环 + 新项目
```

## Page 007

```text
• 从提示词到工程体系
Vibe Coding
Cursor Rules
SDD
全链路 SOP
想到哪写到哪
维护提示词文档
Spec 驱动开发
Skill 化+回写闭环
Prompt 即全部上下文
工具层优化天花板
需求 契约一代码
协同协议＋资产自动生长
碰壁：返工抵消收益
碰壁：协同断层、文档腐烂
碰壁：流程没闭环、资产不积累
今天展开讲这个
Q1
Q2
Q3
Q4
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 008

```text
SOP 就是资产生产线


      OnBoard                                   Release

  输入：项目代码                                   输入：代码变更 + Spec +
  输出：MVP 基座                                 Design
                                            输出：归档快照 + 基座回写

         Spec                                   Review
                                     基座闭环
  输入：PRD                                    输入：Diff + Spec
  输出：spec.md                                输出：Review 报告 + 测试建议


   Design & Plan                               Implement

  输入：Spec + 基座                              输入：Work Item
  输出：Design + OpenAPI + Work Items          输出：代码 + 测试
```

## Page 009

```text
• 解法：MVP 文档基座＋自然生长
冷启动
MVP 基座
债务扫描
项目总览
Runbook
架构约束
技术债
清单
结构扫描
自然增长
Spec回写
缺口补齐
Release 归档
迭代初期
迭代后期
半天冷启动
第1次送代
第N次选代
成本低->不改工作方式一团队顺手就用 自然进入 SOP 轨道
aCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 010

```text
解法：Spec 不是文档，是需求契约
流程改造：需求评审 → Spec Review（产研测共识 - 小时级）→ 技术评审（只聊技
术）

                                 用户故事      谁在什么场景下做什么事儿


                                 功能需求      系统必须具备哪些能力


                                 成功标准      做到什么程度算完


                                 待确认项      全暴露但只有阻塞级打断工作流


正排期迭代延期数量降低到 0
```

## Page 011

```text
•
从 Spec 到可执行设计
Design
design-
spec.md
数据模型
fe.md
分端
前端方案
Story 1
映射
API 契约 / JSON
Story 2
------
schema
L
公共组件设计
design-
Story 3
be.md
后端方案
巛
风险点/ 技术约束
旧：一份 design.md 混装 What + How
新：Spec 管 What, Design 管全局 Howv
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 012

```text
Work Item: Hybrid Execution 的前提
Work Item 1
Story
Work Item 2
Story
Work Item 3 Story
A 功能需求
功能需求
L 功能需求
User Story
验收场景
◎ 验收场景
◎ 验收场景
斋求+验收场景
技术方案
技术方案
技术方案
上下文依赖
口 上下文依赖
口 上下文依赖
Design
Work Item 4
公共
Work ltem 5
公共
全局设计+各模块设
日公共组件封装
数据库表结构
验收场景
⑦ 验收场景
技术方案
技术方案
上下文依赖
口 上下文依赖
工作项
任务描述
类型
执行者
Work Item 1
实现核心功能
Story
品 Agent
Work Item 2
优化用户交互
Story
3o人
Work Item 3
自动化测试
Story
品 Agent
Work Item 4
公共组件封装
公共
3人
Work item 5
数据库表结构搭建
公共
品Agent
没有清晰的交接包，就没法决策谁来做
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 013

```text
Hybrid Execution Protocol
Agent 总成本 = 准备成本 + 验证成本 + 返工风险


Hybrid 不是"AI 能用就用"，是一个有判断标准的协作协议
```

## Page 014

```text
• 缺口门禁：Agent 执行前的自检
缺口门禁
Work Item
接口
口翡求
图 验收
國 PASS|
Plan
① （code+ （vetiy
l字段
方案
上下文
杈限
最小交援包
國状态机
X
滋 边界
X FAIL
口缺口清单
验收
人工补齐
x 不自检
Agent 猜测实现
代码写完
Review 发现理解错
返工回
⑦ 自检
缺口晏露—＞ 人工补齐
一
Agent 完整实现
~〔一次做对区
METR: SWE-bench 功能通过率38%，人工评审后09 可直接合苏，平均潛26imin 修补
把"AI 乱写一通再人工返工"变成"先确认再动手"
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 015

```text
Review： 输入不只是 diff
传统 Review
升級后 Review
merge-request.diff
dift
spec：.md
design.md
八 基座交档
60 ~45,6 +45,18 0@
Story-1：用户同步权限
技术方案
项宪法
- const data = fetchuser（id）
Given： 窗理员角色
+ const data = swait getlser（td）|
when：点击同步
APl:/apl/sync-pems
双限模型：RBAC
Then 不空间亚新
Method: POST
同步樂路：最终一数
Auth: admin soken
钳误码 ERR_4XX
+ i （ldata） throw NotFound（）
return transfom（data）
Story-2： 异常处理
影晌面
缤岡规范
@ -18,3 +90,12 @@
vs
Given.网路中新
space-service, auth
async/avalt...
- syncPermissions （space）
\
+ avait syncPerms（space, opts）
Logger.info（'done'）
12 fles.changed
？需求是什么？
？测试够吗？
结构化对照
契约验证，非生观判断
Reviewer
只看代码 凭经验猪-容易漏
对照契约验证一结构化检查一不過漏
AI提的PR，审核时间是人提的4.6倍
aCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 016

```text
Review 输出：技术审查+测试补充建议
口 Review 报告一结构化输出
Spec 一致性检查
对汗 spec.md
传统输出：散落评论
升级后：结构化报告
VStory-1用户同步权限：GWT3/3 验收条件已实现
X Story-2 异常处理：缺少 Given”网络中断”的降级逻辑（spec 第42行）
-这里有问题，這议改一下
⑧ Spec 一致性
酱束3/4通过，1项偏商
上辛四
精确到 spec.md行号
技术风险点
姐济 design.md +基座
“这个写法不太好，但也行吧
！ 技术风险
A design 指定 cursor 分页，代码使用 offset 分页（design-fe.md第18行）
2
王五
2项架构违反，1项规范偏差
权限校验缺少基座约定的 RBAC中间件（base/auth.md第7行）
关联 design.md+基座文栏
不可追器
修复消单
亿 修复清单
可执行，可打公
3 项待修复，定位到文件：行号
sync.ts:45 -添加网络中断降级逻辑 （try-catch + fallback）
容易漏
改完打勾-全部递过即合并
perm.ts:12-替换 offset 为 cursor分页，与 design 一致
diff 驱动验证链路
吃 diff
口 变更文件
9影响面映射
nl 测试覆盖度
。补充建议
•必跑清单
代码变更入口
12 fles• 3 modules
模块 孩口：页面
已有用例 vs 影咽面
簌失用例会动生成
回浜＋新始鴻试
试不再"香心情決定路娜些" diff 驱动、影胸 决定
平均打回轮次：3-1.5，公共模块变更导致的线上bug数：0
Con
InfoQ 极客传媒
全球软件开发大会
```

## Page 017

```text
迭代归档：这次到底改了什么
•迭代归档报告
上线后 AI 目动生成，人确认5分管
代码合入
公共烩力形洲
驗证覆盖
厌险点
三个月后
上級完成
接障/新微求
⑧x
无归档
归档成本vs不归档成本
GitLab MR
群聯记录
Review 评论
NR.4471 3rmontthe aco
“些时好修改了权限澄相
这里有宁坑流意
MR 2418-2 momha 0go
‘心时方里，后换优化
归档成本
MR 0015-4.momite 0o0
22 6论已折免•
摊障半天
~5 min
A 目动生成＋人開认
笛次送代：append-only-參故护
信息散落 -三个月后找不到一同样的坑再踩一遍
不归档成本
~4 h
每次排踪羅 MR＋向人＋弱
◎ 有归档
河美候期及复以坑，知淣贯人州而发
• Release Archive 一v3.2.1 权限同歩面构
心.雯更换耍
1公共能力影路
取綠模憩路步汁年市
suth:4fles
SyicPers API 签名空班
［ 险证覆盖
燃觅险南
5分钟眾位
老格口装容期30天后下达（需通知下效）
下轮 Agent 可读
结构化快照一可追溯一人和 Agent 都受益
aCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 018

```text
基座回写：文档自然生长的闭环
合入前：一致性检查 基座回写 Release 记录
① 累积一致性检查
12
Design.md 蒸馏回写基座文档
Release 记录
Review 变单次交更，这里密所有变更疊加后的源移
选代沉淀的工釋的定，批量写回墨座
append-only•产品激进时间线
4. Review 反馈改了实现，未同步更新 spec
⑦ 接口定义
2 Bug 修复引入行为变更，spec 束炭段
公共約袋
、基座
-亚构权限限步为异步量模式
山. 技术妥协改变实现方案，design 未史新
一"本次临时兼容透辑”
仅归档
- spec: docs/spec/pern-sync.nd
-desion: docs/desianrperm-v3no
CI盤codo-.codo 这里验 codo•spnc—行业空白
-"UI 样式微選"
仅归档
#果V3.2.0- 空间模板系统
OnBoarding
Release
归档 圓与
Spec
亻
资产飞轮
Review
Design
Hybrid
OnBoarding 一 Spec ~ Design - Hybrid - Review. - Release 一 回写基座一下次迭代起点更高
在条流水线上自然长出来的文档资产
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 019

```text
• 越治理，越高效
技术债务分批清理驱动 AI效率正循环
每迭代分批清理
技术债务
腾出更多时间治理
"坏"代玛提示減少
正回
≤轮
Al 提效更明显
代码资产质量提升
债务越清-*AI 越准一，效率越高-，时间越多一清理越深...飞轮自转
每次选代都进化的文档资产和代码资产双飞轮
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 020

```text
飞轮效果/复利曲线
口径：PRD确认 迭代上线（全链路）
2个月 資产复利24%
•还在爬坡⋯.
50%
40%
20%
36%
15%
11%
25%
10%
8%
0%
0%
•
0%
Q1
Q2
Q3
Q4
复杂系统迭代
技术实现重写
CRUD 全链路
vibe coding
cursor rules
speckit 引入
全面维广
大规模•常规送伐
业务语义不变。框架迁移 Spec-Design-Coding-Review
且还在能坡
平台和工具会迭代，资产跟着团队走
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 021

```text
• 验证回路：Al 测试AI修复
测试层（独立 Agent/ 独立模型，基于 Spec 生成用例）
单元测试
接口自动化
压力测试
Agent 浏览器端到端
Agent产出代码
测试 Agent
通过 Review
独立模型执行
失败
自动生成修复任务
Agent 修复一重跑验证
AI测试 AI修复：避免"自己验自己”，Spec 驱动的自动化验证流水线
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 022

```text
背景：模型能力跃升
SWE-bench Pro: 30% - 77.8%
解題能力
两年内翻倍+，从”偶尔能帮忙"到“标准任务独立完成"
自主时长
METR 任务视野：分钟级
14 小时+
每4-7月翻倍 外推2027一个工作日 2028一周
标准任务不再需要复杂流程
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 023

```text
• 流程分级
Bug fix< 50行
零流程，直接委托
Anthropic 官方建议
标准 CRUD（50-500行）
-10 bullet+Skill
OpenAI Codex 团队
跨模块 feature（500-2k行）
中等 Spec
Kiro / Spec Kit
架构级变更（2000+行）
完整 SOP+人工监督
行业共识
流程的价值不在于存在，而在于匹配
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 024

```text
•前后端分工到全栈小队
创新项目燥发•天级迭代，需求随时变更•Deadline 紧张
多角色协同
全栈小队模式
前端 AI一前端一后端一后端 A！
• 送代拆多个 Spec，逐个执行防返工
× Spec 一次拆完 一 需求大量变更一返工
全栈负贵闭环模块，砍断长链路
X 接口对接仍靠人做媒介，效率瓶颈
单测＋接口测试＋压测 Skill 化
X 长链路信息同步去失/不一致
• E2E 测试 AI 输出人审侧重点
X 追求速度一代码质量恶化加剧
• 双端 Review：原前端 原后端互审设计+代码
5人日
3人日
2研发＋1产品•从零到一MVP上线
后续迭代平均每次上线周期
一前端一后端+AI = 加班地狱一全栈小队+AI = 天级交付
流程的价值不在于存在，而在于匹配
Qcon
InfoQ 极客传媒
全球软件开发大会
```

## Page 025

```text
Harness 全景
在一个模型能力和生成速度人人都有的世界里，真正的竞争力是你团队的流程、资产、和最终交付的产品本身


Velocity is dead. Long live delivery.
```

## Page 026

```text
InfoQ 极客传媒
QCon
全球软件开发大会
THANKS
大模型正在重新定义软件
Large Language Model Is Redefining The
Software
```

## Page 027

```text
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
```
