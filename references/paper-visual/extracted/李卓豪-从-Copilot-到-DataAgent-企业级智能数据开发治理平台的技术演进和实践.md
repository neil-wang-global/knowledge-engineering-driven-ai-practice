# 李卓豪-从-Copilot-到-DataAgent-企业级智能数据开发治理平台的技术演进和实践

来源PDF：`references/papers/李卓豪-从 Copilot 到 DataAgent：企业级智能数据开发治理平台的技术演进和实践.pdf`
页面图像目录：`references/paper-visual/images/李卓豪-从-Copilot-到-DataAgent-企业级智能数据开发治理平台的技术演进和实践/`

说明：以下为按页信息提取，尽量保留页面可见文字、标题、列表、表格与图示标签。
## Page 001

```text
InfoQ 极客传媒
QCon
全球软件开发大会
从Copilot 到 DataAgent：
企业级智能
数据开发治理平台的技术演进和实践
李卓豪
网易智企.数帆数据开发治理平台技术负责人
```

## Page 002

```text
极客邦科技 2026 年会议规划
促进软件开发及相关领域知识与创新的传播
06月？上海
21000人
◎ 8月9深圳
R 1000人
AiCon
•Al Infra 系统工程
AiCon
•Agentic Al
•多 Agent 协作与实践
•轻量化与高效推理
全球人工智能开发与应用大会
•多模态融合
模型训练与推理创新
全球人工智能开发与应用大会
•多模态应用
•Al+ IoT 场景实践
会议时间：6月26-27日
•数据平台与特征服务
会议时间：8月21-22日
•AI 工业化落地
•10月9上海
881200人
012月？北京
8 1000人
QCon
AlAgent
•Vibe Coding
AiCon
•大模型架构创新
。智能可观测
•多模态 AI 产业融合
全球软件开发大会
。推理基建
全球人工智能开发与应用大会
具身智能
•模型攻防
•Al for Science
会议时间：10月22-24日
•Al X 创造力
会议时间12月18-19日
；大模型安全
```

## Page 003

```text
          背景与演进历程：从Copilot到
     01
          DataAgent

     02   核心技术架构实现


     03   关键能力的技术实现

目录   04   落地挑战与评估体系


     05   未来展望


     06
```

## Page 004

```text
背景与演进历程
从Copilot到DataAgent
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 005

```text
数据开发治理平台在数据价值链路中的定位和业务痛点

                    数据应用产品：ChatBI、智能问数


                    Cli、Skills   指标、表、模型映射


                    数据开发治理：EasyData


                                 集群任务诊断


                    NDH：Hadoop & AI 支撑底座
```

## Page 006

```text
AI浪潮下需求痛点


新项目实施，数据建设初   对于持续稳定发展的业    存储计算资源不断消耗，   新人如何快速的熟悉数据
始化效率有不断提升的需   务，基线不断地添加新任   每年都需要运动式的治    架构、安全可靠地工作；
求：企业存量数据标准词   务，如何高效的保障基线   理，上任务容易下任务难   如何专注数据设计自身，
典挖掘、批量数据入仓、   产出，系统性降低风险是                 而不是数据存储、计算引
              核心业务关注，能否智能
核心字段发现等                                   擎特性
              重构数仓


 初始化效率低        数仓基线优化        资源持续优化        研发效率提升
```

## Page 007

```text
Copilot探索：提升开发效率


                                      自然语言实现短链路典型单一场
        1    ChatAPI                  景，比如具体表权限申请、数据
                                      服务API创建

                                       通过模型微调实现数据开发、
        2        SQL提示补全               自助分析取数SQL补全，提升
                                       研发效率

                                        进一步开发提效，SQL生
        3              Copilot          成、优化、纠错、数据质量
                                        任务、词典提取、找表


                                          模版业务场景数仓智能
        4                   AutoETL
                                          化一键构建
```

## Page 008

```text
Agent技术爆发：从"开发"到"全场景"的范式跃迁

                        P
OpenAPI &MCP                         场景Skills
业务自建Ai应用                             面向解决具体问题
                                   用户自定义的工作流程

                       全场景
                   A   端到端
                             D
Cli Tools                        内嵌DataAgent
数据开发的vibe coding                 更好的产品体验 、企业安全
数据开发的sdd                              端到端场景需求


                        C
```

## Page 009

```text
核心技术架构实现
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 010

```text
 Copilot 架构
应用层   离线开发      自助分析           任务运维       数据地图   数据质量     数据标准                            前端交互


接入层             OpenAPI                          SDK                                      WebAPI


                Copilot（辅助开发）                     Agent（自主决策）                 知识库管理                     LLM管理
                      SQL Copilot                                           业务数据
                                                  智能数据集成与调度              任务数据   表数据                供应商           模型
      代码生成      代码纠错             代码补全     代码解释                           标签数据  函数数据
         治理 Copilot               元数据 Copilot                                                           安全管理
                                                  智能质量监控与修复
业务层                                                                           知识库              访问审计             访问控制
      质量规则       Copilot架构
                标准分词    智能找数              生成补全                                系统知识
         安全 Copilot                 运维 Copilot    智能数据治理与审计                 业务、行业知识                     监控分析
      敏感识别      分类分级             失败诊断     任务优化                                                 反馈收集             埋点统计
                                                  智能数据查询与分析                 评价体系
                          Dify                                           用户评价  召回评价            配额控制             行为分析


                      LLM 插件                                 AI APP 插件
基建层                                                                                                MCP Client
      云厂商 LLM     OpenAI LLM          网易有灵 LLM     Dify       Coze         CoreAgent


数据层     RDS               ES               PG          接入层           ED库          Kafka      OpenAPI            MCP
```

## Page 011

```text
    Copilot能力跃进：从通用LLM到企业知识增强
                             知识增强跃迁                    ✓
        !


     LLM 的局限               知识增强 Copilot             知识库核心价值

     幻觉风险                           用户查询输入           记忆沉淀
?                                               M
     生成不存在的字段、SQL语                                   历史SQL、最佳实践复
     法错误                                             用

     语境缺失                           意图理解解析
                                                     语境感知
!                                               C
     不懂内部术语、表关                                       表关系、业务术语理解
     系、业务规则
                     知识库           知识检索 (RAG)
     知识滞后                                            规范统一
T                                               R
     无法感知最新业务变更                                      标准定义、口径一致性
     和数据                           LLM 增强生成

     输出随机                                            效率提升
X                                               S
     相同问题每次答案不一                    企业级精准回答           秒级响应、降低重复工
     样                                               作
```

## Page 012

```text
知识库架构
                                    知识库                                         知识库管理
                                                                                            向量化
                        业务知识库                                                       知识评价           向量
                                                                 行业知识库
SQL模                                                                                              数据库
        SQL片段    多表关系   计算逻辑    内部术语       业务规则       时间参数     专业术语 业务流程            用户评价
 板
                                系统知识库                                               命中评价
                       加工数据                                       登记数据
                                                                                相似度检测                ES
SQL片段     SQL块     多表关系  表元数据             UDF         指标       系统函数  系统常量
                                                                                    知识召回

                                                                                    知识存储           Easy
                 数仓加工                                      Dify加工                                 Copilot
                                                                                    知识加工


                                                      业务数据

                        代码                                                    表数据
 离线开发            自助分析        点赞代码               UDF           元数据      样例数据         分区信息        数据源

                                                       标签
  主题域             分层           指标               维度             度量       主键          治理标签        备注


         离线开发                                          UDF                                 ES
```

## Page 013

```text
   AutoETL架构
标准化的业务场景模版抽象，

       新数据源系统


根据数据源实际情况进行AI改写模版


       模版引擎生效


适配新环境的标准化业务数仓构建
```

## Page 014

```text
    从 Copilot 到 Agent：可控的自主化演进
� Copilot 阶段：确定性辅助   � 能力跃迁："执行者"到"决策者"     � 分层解耦：通用 + 垂直

✅ 已解决：知识沉淀、语境感知、      Copilot       Agent   ▸ 通用 Agent 底座
生成质量                                        意图理解 | 任务规划 | 反思纠错

                      单步响应      →   多步规划
✅ 模式：人主导决策、AI辅助执行
                                            ▸ 垂直 Sub Agent 插件
                      即时生成      →   持续迭代    数据开发 | 任务运维 | 数据治理
⚠️局限：

 • 需要人工触发、单步响应
                      人类触发      →   目标驱动
                                            ▸ 垂直 Tool、Skill
 • 被动执行，无法自主规划        辅助工具      →   数字员工    SQL执行 | 智能运维 | 质量校验


�演进策略：通用Agent承载不确定性，垂直组件处理确定性，实现可控的自主化
```

## Page 015

```text
    DataAgent
                                                             客户端层

                 多租户                                          多会话                                   流式展示

                                                              接入层

                  SSE                                       WebSocket                               事件总线

      安全层                                                    编排层                                           记忆层

    提示词安全                           主Agent (ReAct)                        SubAgent (配置接入)                  短期记忆
                                                                        数据开发          任务运维
                             意图拆解      动态规划            调度
     数据安全                                                                Agent         Agent               长期记忆
                                                                        元数据           数据治理
                             结果评估      反思纠错            仲裁
     Tool权限                                                             Agent          Agent               领域知识

                             执行层                                                            反馈层

数据开发 Tool        数据运维 Tool     数据治理 Tool          知识库 Tool               评估                    反馈            纠错

                                                              模型层

        OpenAI                             Anthorpic                       DeepSeek                   本地模型

                                                             可观测性

            日志                               追踪                                 监控                     审计
```

## Page 016

```text
DataAgent关键模块
用户请求（自然语言）
任务管理模块
大谐言模型（LLM模型）
知识检索模块
• 理解用户意图
支撑模块
• 规划任务步骤
安全控制模块
• 选择合适工具
理解规划模块
异常处理模块
DataAgent
核心能力模块
决策推理模块
工具调用层（CLi、MCP、Function Calling）
• read_file / edit_file
数据处理篌块
• get_table_metadata / execute_code
• edit_sCheduler_config
文件操作模块
对话管理模块
• 等其他工具.•
调度管理模块
功能模块
代码生成模块
EasyData 平台API
• 任务管理 API
工作流编排模块
• 元数据查询 API
• 调度系统 API
• 代码执行 API
aCon
InfoQ极客传媒
全球软件开发大会
```

## Page 017

```text
    DataAgent Case：智能运维
          � 用户                                          Agent 工具调用链路
基线报警：任务 dws_xxx 实例 95021 失败
已阻塞下游 3 个任务
                         � Agent                        � 提取实例ID
           收到，正在排查实例 95021 失败原因...     报警信息 → 实例ID: 95021
           ① 调取调度系统执行日志
           ② 调取 Spark on Yarn 运行日志
                     � Agent                               � 调度日志
            诊断完成：OOM（内存溢出）             调用 EasyTaskOps CLI 获取任务执行日志
            当前运行内存：4G
            根因：数据量增长导致 Executor 内存不足
            建议：调整内存至 6G 后重跑
                                                             ⚡ Yarn日志
                                       调用 Spark History API 获取 Executor 运行日志
          � 用户
确认，调整到 6G 重跑
                                                         � OOM诊断
                       � Agent         模型识别: OutOfMemoryError 当前内存 4G → 建议 6G
            正在执行重跑... 监控中
            实例 95021 重跑成功 ✅
            基线恢复正常 ✅                                  ✅ 执行重跑
            下游 3 个任务已自动恢复调度            调用重跑 API，检查状态 SUCCESS，检查基线恢复
```

## Page 018

```text
关键能力的技术实现
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 019

```text
   为什么需要 SQL 片段提取？

      ❌ 通用LLM的真实表现                 ✅ SQL片段提取：企业知识资产化
"造假"——编造不存在的表名和字段名             终结"造假"
  模型不知道你有哪些表，它会猜                  基于真实SQL，表名、字段100%准确

"漏条件"——遗漏 is_deleted=0 等业务规则   捕获"漏条件"
  隐性知识，新人也不一定知道                   自动沉淀业务规则，is_deleted=0 内置

"凭感觉"——没有历史范例可参考               告别"凭感觉"
  每次从零生成，准确率低                     历史范例即插即用，准确率大幅提升

"写冗长 Prompt"——用户需手动补全上下文       简化"Prompt"
  提示词复杂度 > 直接手写 SQL               片段即结构上下文，Agent直接召回


� SQL片段不是文档，是给 Agent 召回的结构化上下文，是 RAG 的精准知识
```

## Page 020

```text
 SQL片段提取
               � SQL片段 = 带业务注释的 SQL+ 语义描述
采集   线上真实SQL

                         片段提取     关联数据            结构化输出

     只保留SELECT，
拆解                        保留              原始片段   表注释
     JOIN <= 2           SELECT
                                  字段元数据
                                                          代码片段
                                                  常量
                                          字段注释
                                                 变量化
                         控制表数量
     关联元数据（表、                     表元数据
匹配                任务代码
     字段、血缘）                                               片段标题
                         限制库表
                                           表名    业务线

                                  字段枚举值
     补充描述、场景、                                             使用粒度
富化                       保留备注
     注释
                                          代码片段   业务规则

                         结构化输出    业务规则                    使用场景
     向量存储，支持语
入库
     义检索
```

## Page 021

```text
     SQL 片段抽取
           ① 获取真实代码                                                     ② 片段提取             ③ 获取关联元数据                                     ④ 结构化输出
            业务RDS → 完整SQL                                         保留SELECT核心逻辑                表DDL + 字段信息                               综述·粒度·场景·SQL


                         输入：业务计算回调比率特征的真实SQL
WITH tmp AS (                                                                                                             结构化输出
 SELECT material, AVG(video_callback), ...
  FROM (
    SELECT flight_id... FROM iad_dwb_prod.dwb...di WHERE d = '...' AND exposure > 0 ) ta   【综述】通过dwb_evt_iad_ctrfeature_di表关联ad_material素材表，按素
 JOIN (
                                                                                           材×投放计划粒度聚合广告回调指标，构造交叉比率特征。
    SELECT mal_id FROM adman.ad_material WHERE d = '...' AND ... GROUP BY mal) tb ON
ta.material = tb.material_id GROUP BY material, flight_id)
                                                                                           【粒度】以素材ID×投放计划ID为粒度主体，每行代表一个素材在某个投放计
INSERT TABLE iad_algorithm_prod.link_send_feature PARTITION(d=...)
SELECT ceil(vid_score*100), vid_sum, ... exp_sum, material, flight_id                      划下的回调指标聚合值及其交叉比率特征。
FROM tmp
                                                                                           【场景】构建广告投放链路中的发送特征，通过视频回调等指标的交叉比率，
                                  片段及关联的元数据                                                刻画素材×计划维度的投放效果，支撑广告投放模型的特征输入与效果预估。

"表名": "iad_dwb_prod.dwb_evt_iad_ctrfeature_di",                                            【SQL】 SELECT material,                                -- 素材ID
adman_adcore_db_ods_prod.ad_material                                                                         flight_id,                          -- 投放计划ID
"字段": "material , video_callback, flight_id, content_show_type, ..."                                         AVG(video_callback)    vid_score,    -- 视频回调均值
"过滤条件": "d, content_show_type",                                                                              SUM(video_callback)    vid_sum,     -- 视频回调总和
"SQL片段(去CTE，保留SELECT核心)":                                                                                    ...                                 -- 其余比率特征
SELECT material, flight_id, AVG(video_callback) vid_score ...                              FROM iad_dwb_prod.dwb_evt_iad...di      -- CTR特征明细表
FROM iad_dwb_prod.dwb_evt_iad...di                                                         JOIN adman_...prod.ad_material       -- 素材维表
JOIN adman...prod.ad_material                                                              ON material = material_id
ON material = material_idWHERE d = '...' AND exposure > 0                                  WHERE d = '...' AND exposure > 0            -- 指定日期且有曝光
GROUP BY material, flight_id                                                               GROUP BY material, flight_id
```

## Page 022

```text
  如何实现高质量 SQL 生成？

      常见 ChatBI 方案               数据开发方案

 面向业务用户，依赖预定义指标体系，灵活性受限   面向数据开发 / 分析师，无需预定义指标，灵活可
                          变

          自然语言                     自然语言


         指标/标签                  SQL片段等知识召回


           SQL                      SQL


�SQL片段是代码生成的精准知识基础，对代码生成质量至关重要！
```

## Page 023

```text
       SQL代码生成

   自然语言                  结构化                      精准知识                        SQL


       问题明确&改写                    知识召回                   代码生成                 代码纠错


                                                                        生成
   业务知识   用户问题            改写问题            表识别                   改写问题    SQL


                                                  召回知识
                                  知识召回                                 语法纠错          元数据
                  意图反问
                                （语义检索、关键字检索）
改写模板      明确&改写                                                 代码生成
                                                                       基于语法
                                                  SQL模                  树纠错
                         表元数据      多表关系    计算公式    板

                         SQL片                                   输出      输出
   行业知识   改写问题                     业务规则    系统知识
                          段                                     SQL     SQL
```

## Page 024

```text
 SQL 代码生成
             ① 问题改写                                    ② 知识召回                                      ③ 代码生成
          自然语言 → 结构化JSON                             表DDL + 字段元数据                             改写问题+知识+模板→SQL


            用户原始问题                                         召回：表元数据                                        生成SQL
                                      dwd.dwd_iad_adx_click_di                     SELECT DISTINCT ta.user_id
我要查询唯品会的合约人群包，两部分人取并集，第一部分是30          murs (user_id), material_id, dt             FROM (
                                                                                     -- Part1: 30天内点击唯品会/淘宝/京东素材
天内点击过唯品会/淘宝/京东素材的（点击表和素材标签表关
                                      iad_preformat.dspmaterial...tags_dd            SELECT t1.user_id
联），第二部分是美妆兴趣标签等级 ≥ 2 ，                 material_id, sponsor_group_name, d            FROM (SELECT dt, murs AS user_id, material_id
然后这些人还得是装了唯品会 App                                                                      FROM dwd.dwd_iad_adx_click_di
                                      iad_preformat.dmp_adx_rank..level_dd             WHERE dt >= date_sub(...,30)
                                       murs (user_id), tag_name, cpm_level             GROUP BY 1,2,3) t1
                                                                                     JOIN (SELECT d, material_id
                                      iad_dwb_prod.dwb_app_install...dd                FROM iad_preformat.dspmaterial_...
          改写后结构化JSON                   user_id, app_list                               WHERE sponsor_group_name
                                                                                        LIKE '%唯品会%' OR '%淘宝%' OR '%京东%'
                                                                                       GROUP BY 1,2) t2
"问题类型": "数据查询",                                        召回：代码片段                       ON t1.material_id=t2.material_id AND t1.dt=t2.d
                                                                                     UNION
"问题改写": "(1)近30天点击过唯品会/淘宝/京东素材用户；     SELECT t1.user_id FROM                         -- Part2: 美妆兴趣标签等级≥2
  (2)美妆兴趣标签等级≥2的用户。                   (SELECT dt, murs AS user_id, material_id       SELECT murs AS user_id
  (1)并集(2) 再 交集 安装唯品会App的用户",          FROM dwd.dwd_iad_adx_click_di                 FROM iad_preformat.dmp_adx_rank_...
 "过滤条件":                               WHERE dt >= date_sub(..., 30)                 WHERE tag_name LIKE '%美妆%'
                                       GROUP BY 1,2,3) t1                              AND cpm_level >= 2
   sponsor_group_name : "唯品会/淘宝/京东"   JOIN                                         ) AS ta
   tag_name : "美妆"                    (SELECT d, material_id                       JOIN (
   cpm_level :"≥2"                     FROM iad_preformat.dspmaterial_...            -- Part3: 安装唯品会 App
   app_list :"唯品会"                     WHERE sponsor_group_name                      SELECT user_id
                                        LIKE '%唯品会%' OR ... '%淘宝%' OR ... '%京东%'     FROM iad_dwb_prod.dwb_app_install_...
"假设性回复": 假设查询将从广告素材点击行为和美妆兴趣标
                                       GROUP BY 1,2) t2                              WHERE array_contains(app_list,'唯品会')
签两个维度筛选用户取并集，再与唯品会App安装用户取交           ON t1.material_id = t2.material_id           ) AS tb
集，返回去重后的user_id                         AND t1.dt = t2.d                           ON ta.user_id = tb.user_id
```

## Page 025

```text
  Data Agent 如何调用工具？

    ❌ 传统方式：GUI 自动化          ✅ CLI 天然适合 Agent


截图识别 → 脆弱，UI 变更即失效     结构化输入输出 → JSON 直接解析

每步都需要 LLM 推理 → 慢且贵     零 LLM 运行时成本 → 确定性执行

无法批量编排 → 缺乏可组合性        管道机制可组合 → 多命令串联编排

无结构化输出 → Agent 难以解析    对人类可见可调试 → 复现 Agent 行为


�CLI 不仅是 Agent 的交互方式，更是 Token 效率的最优解
```

## Page 026

```text
  CLI vs MCP 的核心差距
            MCP 方案                               CLI 方案

MCP 把知识放在了运行时的上下文窗口里                 CLI 把知识放在了模型的训练数据里

Schema 注入        ~28,000 tokens      Schema 注入                 0 tokens
工具选择                 ~3,200 tokens   命令组合                  ~800 tokens
50台设备总计         ~145,000 tokens      50台设备总计              ~4,150 tokens


                       Token 效率差距：35 倍


�业界验证：钉钉、飞书、企业微信 72 小时内争相开源 CLI
```

## Page 027

```text
  我们的选择：为 Agent 设计的 CLI
① 默认非交互             ⑤ 渐进式发现
Agent 无法处理交互式提示     --help 让 Agent 按需获取


② 结构化输出             ⑥ 可组合
--format json 是标配   输出格式一致，管道串联


③ 快速失败              ⑦ 有界响应
错误告诉 Agent 怎么修      限制输出量，高信噪比


④ 安全重试
幂等操作 + dry-run 预览
```

## Page 028

```text
EasyData Cli & Skill
                                    EasyData CLI                                   EasyData Cli Skill

                                      三层命令
                                                                                       配置管理
       Shortcuts                  Service Commands            Web API
   (高频快捷命令，手工封装)                    (1:1 映射OpenAPI)            (前端 API)

                                                                                       命令缓存


       Schema管理                  全局命令 & Flags                 安全认证                     工作流程

构建嵌入    定时刷新        实时刷新       全局命令         全局Flags   AK/SK               OAuth2
                                                                                      公共Flags


                       存储                                      帮助                      错误处理

                                Command Schema 存
   配置存储            Token加密存储                          帮助命令                 内省
                                       储                                               重要规则


                                                                                       使用示例

                               GateWay（HTTP/MCP）
                                                                                      子产品说明
```

## Page 029

```text
                                                                     GateWay
      EasyData GateWay
                                                          MCP/OpenAPI                                                 Web API

                                                          EasyOpenAPI                                       单点系统
GateWay 将子产品的 OpenAPI 元数据
                                                              协议
转换为 MCP Schema，再通过 CLI 层暴
                                             MCP                        HTTP（OpenAPI、CLI）
露为命令行能力，实现一套架构统一对外
                                     MCP Schema            安全认证                      安全认证

                                                            AK/SK             OAuth2                         Cookie
            � 一个服务                       合法性校验             (个人/客户端)         (Device/客户端)       前端
 OpenAPI                                                                                       接口             管理
            GateWay 作为统一入口                                 权限校验              Scope权限           认证
                                   内存        定      主     (个人/项目/项目组)       (资源域:资源:操作)
                                             时      动
                                                                           Proxy
                                             更      推
                                   数据库       新      送     请求转发            传递上下文            解析包装

            � 两项协议
 MCP Tool
            HTTP + MCP                                                  子产品
                                          EasyDev                     EasyDMap                        EasyTaskOps

                                  OpenAPI         MCP                        MCP            OpenAPI
                                                              OpenAPI                                     MCP Schema
                                                 Schema                     Schema
   CLI      ⚡ 三种能力
 Command                          task        schedule       table         lineage         instance        baseline
            OpenAPI + MCP + CLI
```

## Page 030

```text
）4
落地挑战与评估体系
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 031

```text
    数据准备


SQL的筛选                                      SQL去重
•   锚定业务场景，离线开发、自分析           2    3        •
                                            •
                                                所有sql 按照时间顺序从小到大排序、遍历；
                                                每条新时间戳的sql ，对比其前两小时内的其他sql
•   基于sql行数
                                            •   如果2小时内存在一条sql 和当前sql 的 篇幅大小增
•   基于用户sql文件数
                                                加或减小范围小于 1/2 并且 编辑距离小于
•   识别同一个任务在不同开发环境下的版本                          avg_word_len * max(3, sql_word_num/10),则
•   识别用户之间copy修改                                认为是相似的。


                         1              4   •   删除前两小时内的相似sql，最大时间戳内的相似sql
                                                替换该删除的相似sql。


SQL预先处理                                     SQL拆解
• 转义、中文编码、变量宏定义还原                           •   基于引擎AST做数据切割
• 辅助信息：业务小组、表、任务负责人、引                       •   正常训练
  擎类型                                       •   分段训练 + 语法完整性校验
• 超长SQL处理：构建大宽表
                             微调训练数据准备       •
                                            •
                                                拆解为子查询单元
                                                分层生成：先 CTE 定义，后主查询
```

## Page 032

```text
从细节优化模型效果

            关联现象
            • 生成和上文风格不一致的错误语句
            • 和上文的信息似乎存在严重割裂
            • 不懂得从上文推测出补全类型是span补全，写
              了一个功能独立的行。
            • 重复了与下文重复的sql语句


            其他细节-潜在埋点建议
            • 用户临近时间的点击操作序列，以时间戳为顺序
              组织
            • 用户的SQL代码历史书写记录，用于微调
            • 用户对这个SQL补全的评价（赞或踩）、修改意
              见反馈入口
```

## Page 033

```text
    Text-to-SQL评估体系


评测系统目标                            高质量评测集
• 统一评分标准：评估维度清晰、兼顾单个sql 和         •   用户提供，即人工整理
  整体能力                            •   从线上新sql任务提取
• 支持规模自动化：能对数百上千条评测样本做全           •   sql自动复杂度打标
  量回归，支撑版本对比与长期演进                 •   sql数据整理：sql真实跑通，sql有下游依赖
• 支持结果分析：测试过程trace关键链路信息、         •   sql扩展：主要是做算子变异：select、join、
  给哪些维度、复杂度表现不佳                       where、聚合、order


评估指标                              成熟度分级

•   EX：核心指标，是否完全正确                • 维度设计：表、字段、条件、聚合、加工
•   Intent Match Score，衡量查询意图匹配   • 权重与综合得分
•   静态结构对比：SQL结构对比                • L1-L6成熟度等级
•   动态结果验证：结果等价判断
```

## Page 034

```text
Text-to-SQL评估系统
用例层
基线测试集
补充测试集
外部实体
Test Case Management
Baseline Test Suite
Supplementary Test Suite
执行层
代码生成执行逻辑
Execution Control
代码生成Agent
大模型 API服务
LLM API Service
收集层
Data Collection
眼
评估数据采集
执行日志收集
日志数据库
评分层
基于代码评分
基于执行结果评估
Scoring Layer
模型基本信息
效果评估维度
性能评估维度
成本评估维度
指标层
模蜑茗称
模型广商
来型广商
（Single）
◎ 三次汁佑
> 蜜体指标
单次指标
（Overall）
（Single）
（3味指标
楔翌价格
单次指标
（Pass）
（Overall）
（Price）
（Single）
鹽体指标
（Overall）
算度
SQL屈动
Pass:2
正棠结粜率
苗宇菠送
平均 过
頃存/作優存
SQL正娟
Pass"3
Pass"4
装東正歸率
生蹤时长
透用时长
平均速胺
输入竿价
Token
平均成本
成本
Pass@5
调永时长
输出单价
本论節素
是舌可本
墨香圍内
復登厂商
Pass@5
Token效藏
报告层
生成测试报告
测试数据写入引擎
Reporting & Persistence
敥据库
BI 图表展示
（同时是BI工具）
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 035

```text
产品AI Native化
AI开发态
Azkaban 运行态
开发者/ Claude Code
引擎直接解析执行
project.info
build.py
project.Zip
oroject.properties
schedule.into
读取
1. validate
sources.into
DAG•文件，参数•测试
flow.properties
profiles.info
extract@节点名.job
2.compile
CONVENTIONS.md
transform@节点名.job
解析 ref（）•合井参数
load@节点名.job
flow.info
DAG +参数＋测试契约
输出
3.package
lineage.info
生成.job•打包 zip
nodes/*.sal
*.sh/*.py/*.sql
nodes*.py
禁止手动修改
nodes/*.sh
版本管理•git
Azkaban 零改动
Con
InfoQ 极客传媒
全球软件开发大会
```

## Page 036

```text
05
未来展望
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 037

```text
• 场景化Skill
EasyData 全景 SKILL 架构
基于 CLI + 基础SKILL 构建的大数据开发治理平台智能能力矩阵
貓 AI Agent /用户
自然语吉施图 - SKILL 发现—CL向令调用一结构化捨出
全紧 SKILL 矩阵
沿 数据开发
双 数据地图
9 数据资产
溫数据安全
SOL开发讲式
任多编择 DAG
表搜索发现
Schema 查询
资产目泶编目
成本分谢校算
权限申清审批
脱鉉規则配置
代們年盗 Reviev
血缘影响分析
元效製管理
效砺血城ㄠ诺
质量说估报告
生命用期管理
飯惑数据扫描
合规市计日忠
密順补全生成
调度配置管理
标签分类体系
热度分析统汁
价值評估打分
浴理建议推送
分级分类标注
汸向凤隆顿器
智能运维
智能冷断
自助取数
更多 SKILL
任务运行监控
异芥自动恢复
逐SQL分析
数据倾斜谂断
NL25QL 資询
指标口径查询
数湣顾量巡检
模型设计轴助
SLA 基线告酸
资灣水佼分析
任务失敗归因
资涤瓶颈定位
报淡快速生成
数据导出下哉
数指入湖入仓
跨繳数据何步
技参表后效！
排队等待分析
遂蟭汲告生成
依敉链絡分析
智篼烙芟建议
石玫数接查询
指林异常检測
效拼合同管理
（无限扩展）
| 基础 SKILL 层
EasyData CLI基础SKILL
陇i管狸
命分暖行
工作流程
公共 Flags
桃误处狸
安全规则
使用示例
子市帚说明
Schena 网价
Help不統
EasyData CLl
Shortcuts 快捷命冷
Service commands 服务命令，
Web ARI
全局始令& Flaos
Schema
無格受系：Sehems 原种 AKSK + DAUIZ安至证新台存花
EasyOpenAPI 統一网关
MCP 动议
HTFTP （OpenAPI/CLD！
Schema 管理&校验
安全认证（AKISKOAuth2 Scope 权限）
Proxy 优理转发
QCon
|子产品（EasyDev•EasyDMap • EasyTaskops•...）
InfoQ 极客传媒
全球软件开发大会
```

## Page 038

```text
InfoQ 极客传媒
QCon
全球软件开发大会
THANKS
大模型正在重新定义软件
Large Language Model Is Redefining The
Software
```

## Page 039

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
