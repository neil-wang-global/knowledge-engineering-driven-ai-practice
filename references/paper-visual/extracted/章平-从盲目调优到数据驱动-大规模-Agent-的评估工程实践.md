# 章平-从盲目调优到数据驱动-大规模-Agent-的评估工程实践

说明：以下为按页从渲染图片进行的可见信息提取；保留页码并尽量逐行转录页面文字、标题、标签与数字。

## Page 001

InfoQ 极客传
QCon
全球软件开发大会
从"盲目调优"到"数据驱动"
大规模 Agent 的评估工程实践
章平|亚马逊云科技

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
01
真实案例：旅游搜索Agent的7周质量隐形降级
02
Agent评估的挑战
03
Agent 评估工程的方法论
目录
4
三个完整案例（旅游，代码，客服）：从问题到解决
05
工程实践与落地路径
06
总结

## Page 004

0T
从"盲目调优"到"数据驱动"
真实案例：旅游搜索Agent的7周质量隐形降
级
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 005

旅游平台Agent
Agent工具
问题：用户询问：从纽约到巴塞罗那7天行程，包括机票，$3000是否足够？
期望正确行力
实际回答：
调用”计算旅行预算”工具，提供专业建议
从网页搜索通用的巴塞罗那旅行信息
###美组约•巴塞罗那：7天•预算$3,000
以下是一些关于巴塞罗那旅行的参考信息：
| 项目|预估费用！
0"2026巴墨罗那终极旅行指南“-TravelBlog.com
往返机票（JFK+BCN）
1 $550
$750 1
巴塞罗那是西班牙最受欢迎的旅游城市之一，拥有高迪建筑、美食和海滩••
1住宿（7晚，中档酒店）
1$700
$980|
| 餐饮（每日 $40-$60）
1 $280
- $420 |
| 当地交通（地铁＋尔出租）
1 $80
$120
0“巴塞罗那旅行要花多少钱？"-BudgetTraveler.com
1景点门票（圣家堂、米拉之家等）
| $100-$150
一般来说，巴塞罗那每天的花费大约在$100-$200 之间，具体取决于您的旅行风格
一 其他（购物、小费、杂项）
1 $150 -$250 |
|合计 | $1,860 - $2,670 |
0"纽约飞巴塞罗那的廉价机票攻略"- FLyDeals.net
结论：$3,000 足够
淡李机票可低至$300 往返，旺季可能高达 $800+.…
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 006

• 旅游搜索业务：7周隐形降级
-15%
+23
正常
正常
用户参与度
无效反馈
响应时间
错误率
持续下降但未被察觉
用户抱怨趕狹增加
4周
3周
发现时间
修复时间
依赖人工反馈分析
日志分析+Prompt调试
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 007

02
Agent 评估的挑战
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 008

• 传统监控的盲区：技术指标vS 用户体验
X
技术监控（运维视角）
用户体验（评估视角）
响应时间（P95）
x
用户参与度
“心碎，算了，不用了”
1.2s 1.1s个改善
下降 15%
“隔壁家好像更聪明”
错误率
x
无效反馈
“这个回答没有帮助”
0.3% -0.2%降低
增加 23%
“我要跟人工客服说话”
工H具激活成功率
x
工具选择准确性
998.5% 稳定
92% - 67% 大幅下降
API延迟
X
响应有用性
无异常
0.85 0.52 严重降级
所有技术指标：系统健康/运维团队毫不知情
用户体验持续恶化总结7周
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 009

• 根本原因：缺乏系统化的评估体系
Prompt修改失误
检测时间过长
删除了"ALWAYS use calculate_trip_budget"
传统监控无法发现
改为模糊的'全面信息收集"
依赖用户反馈累积：4周
失去专业的预算计算能力
基于通用知识给出模糊的范围估算
诊断时间过长
自动化评估价值
检测：4周 2小时
pass@k 指标异常
日志分析＋人工调试
诊断：3周一1天
多维度分析定位
定位根因需要：3周
总计：7周一1天
98% 的时间节省
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 010

02
Agent 评估工程的方法论
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 011

• 根据使用场景定制质量评估
1：定义业务标准
2：
3：选择评估模型
4：配置采样
•分析对话，判断准确的购买意图
示例：“购买意图识别”
• 根据任务选择价格合适
100% vs10%
• 考虑显示声明，以及有关价格支付
的模型
平衡成本与全面性
问题，明显信号
• Temparature
• 基于评价量规的评分
Top K
• 0.0：无购买意图
• 0.5：
•1.0：清晰购买意图
• 依次分析原因再评分（Reasoning）
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 012

v select evaluators K selected
评估架构体系：从可观测性到评估
Response qualitu evaluators （1/8）
corecress
Haofuiness
口 conostness
Agent Runtime
Agent评估
nstuction tcllcwing
• Task completion evaluators （1）
Goal Suxsess Flate
Agent
User
• component-level cvaluators （1/2）
让LLM判断每个指标
配置
Framework
ADOT
• Safety cvaluators （1/2）
四2 Hamtulress
Foloale wecthoto rconwcoetom tmnsotcot
• custom evaluators0
输出判断结果
Sclect an wistinacustom cvzluator sroatea new.custom mealuatar t
Al Agent Telemetry
On-demand
Agent观测性平台（LangFuse, etc）
=IntentRasolution
6：
Av：- score （-5toS
观测性控制面板
1.3
countK
监控和访问
ot atan. /5 -sot gsnoally 12/s - Neutal/Msed B/5） Gexplyyes （4/5） -115/5
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 013

• 评估的两种范式：1. Ground Truth
退款示例
Ground Truth（基于预定义答案）
用户输入：“我三天前买的耳机有杂音，订单号 ORD-20260312，我要退款"
核心：无需大模型，Agent 行为拆解成可验证的检查点，逐一比对
优势：快速（<10ms）、便宜（$0）、可复现
预定义正确答案
局限：脆弱、无法评估主观质量。如果 Agent 返回“reason”：“尺
寸问题”而非“尺码不对”，严格匹配就会判定失败，即使语义相
-应调用的工具：process_refund
同。
-必须提取的参数：订单号= ORD-20260312， 退款原因= 商品质量问题
-应执行的前置步骤：先调用 query-order 查询订单状态，确认订单存在且在
预定义测试流程
退款期内
Agent实际输出和期
构建测试对（输
望输出对比
返回结果：
评估流程
入和期望输出
精确匹配、包含检
成功/失败
查、正则等）
1.检查 Agent是否先查询了订单一是
/否
适用场景
2. 检查 Agent 是否调用了 process_refund 而非其他工具（如
exchange_product） 匹配
/不匹配
3. 检查传入的订单号是否 ORD-20260312一匹配
/不匹配
- 工具调用是否正确（调了哪个函数、传了什么参数）
4. 三项全部通过 该用例 Pass：任一失败一 Fail
实体提取（从用户输入中提取日期、金额等）
路由/分类（意图识别是否正确）
流程是否按预期步骤执行
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 014

• 评估的两种范式：2.LLM-as-Jude准
你是一个客服质量评估专家。请根据以下标准对客服回复打分（1-5分）：
LLM-as-Judge（使用LLM评估）
评分标准：
-共情（1-5） 是否理解用户情绪，表达关心
- 有用性（1-5）：是否解决了用户的问题
适用：有用性、相关性、语气、创造性
-准确性（1-5）：信息是否正确，有无编造
-语气（1-5）：是否专业、礼貌
优势：灵活、可扩展、捕捉细微差别
用户输入：｛user_input｝
局限：调用大模型成本较高，时间长，判断标准需校准
客服回复：｛agent_response）
请以 JSON 格式返回评分和理由。
大模型评估流程
示例评估
用户输入、
Judge LLM根据评
Agent输出、
分标准给出分数或
低分进一步归
user_input =“我等了两周还没收到货，太气人了！”
评估标准发给
判断
因分析
agent_response
=“您的订单正在配送中，请耐心等待。”
Judge LLM
Judge LLM 可能返回
“共情"：2.
# 没有回应用户的愤怒情绪
"有用性”：
3，
#给了状态但没有具体信息
主观判断
”准确性”：4，
＃ 信息基本正确
"语气"：3
＃礼貌但略显冷淡
“理由”：“回复缺乏共情，未对用户等待两周表示歉意，也未提供具体的配
客服回复是否礼貌、是否共情？
送时间或补偿方案"
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 015

混合评估
旅游Agent混合评估
70% Ground Truth +30% LLM-as-Juage
混合方案
Ground Truth：工具选择是否正确
用户输入：“帮我搜一下4月1号到4月5号巴黎的酒店，预算每晚 1000元以内”
•客观判断，做对事，调对工具、传对参数）
预定义正确答案：
优先用 Ground Truth，便宜、快、稳定
-应调用的工具：search_hotels
• 主观质量相关，例如用户体验（语气、个性化、创意）：
-不应调用的工具：search_flights、book_hotel（用户只是搜索，还没有要求预订）
LLM-as-Judge
评估流程：
• 平衡成本与质量
1. 检查 Agent 调用的工具是否为
search_hotels 一 匹配
/不匹配
2. 检查 Agent 是否误调用了 book_hotel（用户没说要订） 未误调
/误调了
3. 两项全部通过 一 Pass
成本对比
LLM Judge：推荐理由是否有说服力
•Ground Truth：$O/次
•LLM-as-Judge： $0.01-0.05/次
用户偏好：喜欢博物馆和美食，预算 5000元
•10万次/月：$1.800-4,500
Agent 实际输出：
|“推荐您入住 Hotel Le Marais，位于玛黑区中心，步行5 分钟可达蓬皮杜艺术中心，
检查点|类型|结果| 权至 1
楼下就是知名的L'As du Fallafel 餐厅。四晚含早价格3800元，为您留出1200元的餐
饮和门票预算。”
1 GT-1 工具选择
1 Ground Truth|
Z Pass I 占总分 23.3% |
GT-2 參数提取
Ground Truth|
Pass 1 占总分23.3%|
1 GT-3 流程顺序
I Ground Truth |
Z Pass I 占总分 23.3% |
评估方式：将用户输入、用户偏好、Agent 输出一起发给 Judge LLM，附上评分标准：
1LJ-1 推荐说服力
I LLM-as-Judge 1 5/5| 占总分 10%||
评分标准（1-5分）：
1LJ-2 自然流畅
I LLM-as-Judge | 5/5 | 占总分10%|
1 LJ-3 偏好覆盖
| LLM-as-Judge | 5/5 | 占总分10%|
-1分：推荐理由泛泛而谈，如"这家酒店很好”
-3分：提到了位置或价格，但没有和用户偏好关联
最终得分：
- Ground Truth 部分
（70% 权車）：3/3 全部通过-0.7
- 5分：明确将推荐理由与用户的具体偏好（博物馆、美食、预算）挂钩
- LLM-as-Judge 部分
（30%权重）：15/15 满分-0.3
Judge 评估结果：5分
推荐理由同时关联了博物馆（蓬皮杜）、美食（L'Asdu
综合得分：0.7+0.3=1.0（ 分）
Fallafel）和预算分配，非常具体
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 016

•评估指标的三个层次
Output Level
Trace Level轨迹层
• Session Level会话
（Span）
在一次完整交互中的整体表现
单次动作是否正确？
多轮对话
评估：工具选择、参数提取
评估：有用性、相关性、正确性
评估：一致性、上下文理解
评估器：ToolSelectionAccuracy
评估器：Helpfulness，
评估器：Custom Consistency
ResponseRelevance, Correctness
工具是否正确调用？
整个对话质量如何？
查询时是否参考之前信息？
1 轮次| 用户| Agent|
用户：“巴黎4 月份天气怎样？带什么衣服？”
用户：“帮我算一下去巴黎5 天的预算，两个
Agent 回复：〝4 月巴黎平均气温8-16°C，早晚
第1轮|”我想去巴黎，预算8000元”|”好
人，住四星酒店”
偏凉。建议带一件轻薄外套和一把折叠伞，4月降
的，帮您按8000元预算规划"！
雨较多。白天阳光好的时候穿长袖即可。
第2轮|“酒店别太贵，省钱吃好的”！”明白。
逐项检查：
酒店控制在3000元内，留5000元给餐饮和活动
- Agent 是否调用了 calculate_trip_budget？-
- Helpfulness：
回答了天气和穿衣建议 4/5
是
/否
- ResponseRelevance： 没有跑题去推荐景点一
|第3轮|"我的预算是多少来着？"|？|
- 参数 destination
是否为 Paris？一 匹配
5/5
- 参数 duration 是否5？一匹配
- Correctness：巴黎4月气温数据准确，降雨描述
评估检查点：
- 参数 travelers 是否力2？一匹配
合理 5/5
- Agent 在第3 轮是否回答8000元？一记住了
-参数 hotel_rating 是否为 4？一匹配
反面回答
/ 忘了
Agent 回复：〝巴黎是法国首都，有埃菲尔铁塔
- Agent在第2 轮的预算分配（3000+5000）是否
和卢浮宫，非常值得一去。”
等于第1 轮的总预算 8000？ 一致
/ 矛盾
- 如果用户在第 5 轮又问“酒店预算多少”，Agent
QCon
是否仍然回答3000元nfo商 极含语媒
全球软件开发大会

## Page 017

•
考虑Agent评估非确定性
pass@k
pass^k
1
ALL
pass@k：在k 次尝试中获得至少一次正确解的概
所有k 次尝试都成功的概率。随着k的增加，pass^k会下降，
率。随着k的增加，至少成功一次的概率就越高。
更多试验中保持一致性难度更大。如果每次试验的成功率为
50% 的pass@1：在评估任务中首次尝试就成功完成
75%，进行3次试验，那么三次全部成功的概率为（0.75）~
一半任务
42%
The Difference Between Pass@k and Pass^k
100
—〇
pass@k
75
"At least one of k trials succeeds"
As k increases, pass@k rises toward 100%.
两个指标在多轮会话之后差异巨大
With 3 trials, this agent hits 97% pass@3.
pass@3: 97% vs pass^3:39%
Success Rate （%）
50
pass^k
*'All k trials must succeed"
As kincreases, pass^k drops towards 0%.
With 3 trials, this agent falls to 39% pass^3，
25
-• pass@k （≥1success）
pass^k （all succeed）
10
Number of trials （k）
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 018

评估体系的三阶段演进
⑧-⑧
问题："Agent能做什么？"
问题："功能是否还正常？"
方法：在线评估＋采样（5-
特点：初始通过率低（20%-
10%）
• 特点：目标通过率 ~100%
50%）
效果：7周一2小时发现
•
案例：prompt修改后
案例：pass@l 从 20% 一
pass@I 从 95% -20%
• 工具：监控告警＋可观测性
80%
•
目标：防止改动破坏现有功能
•
目标：持续监控生产质量
•
目标：快速迭代，提升核心
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 019

04
三个完整案例：从问题到解决
旅游，代码，客服
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 020

• 案例1：旅游Agent-工具选择失效
问题
用户询问：从纽约到巴塞罗那7天行程，包括机票，$3000是否足够？
Agent 回应：从网页搜索通用的巴塞罗那旅行信息
：OK
12%
4
：OK
18%
3
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 021

旅游Agent业务问题处理
选择Agent
配置评估器
③配置采样
30
/OTEL
平衡成本和覆盖
5
率
LangGraph
kubernetes
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 022

• 几小时内质量问题浮上水面
# Toolselection accuracy
Assiaceuragy
0.3
Count （K）
l.l.alli
0.91
0.30
0.90
0.86
0.80
0.68
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 023

•
案例1：旅游Agent - 修复前后对比
提示词（修改前）
提示词（修改后）
Prompt（Broken）
Prompt （Fixed）
"'Focus on comprehensive information gathering.."
"CRITICAL: When user provides origin, destination, duration，
budget
没有明确工具选择指导
- ALWAYS use calculate_trip_budget"
明确的工具选择规则
Agent响应
Agent响应
"Yes， $3,000 is generally enough...
"Yes， $3,000 is more than enough！
Flight：$400-800（估算范围）
Flights：$600（精确）
Daily： $80-250/day"
Accommodation： $560
未调用任何工具
Total： $1,790 Remaining： $1,210"
基于通用知识•范围估算不精确
调用 calculate_trip_budget•数据驱动•精确
评估结果
评估结果
Tool评估器：
'no results"
Tool评估器：1.00
（无法评估缺失的工具调用）
（所有3个工具评估器完美）
Trace评估器：1.00/
Trace评估器：1.00
（响应全面，但无法检测缺失工具）
（所有6个评估器一致认可）
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 024

•案例1：旅游Agent - 评估对比
Too
Trace
• ToolSelectionAccuracy — 是否选择了正确的工具？
• Helpfulness -响应是否有用？
• ToolParameterAccuracy - 是否提取了正确的参数？
• Responseflelevance — 响应是否相关？
• Custom Budget Tool Evaluator - Budget 专用评估器
• Correctness—信息是否正确？
问题版本评估结果
修复版本评估结果
Tool Level：
- ToolSelectionAcouracy： **"no results"**
Tool Level：
- ToolParameterAccuracy： **"no results"**
无工具调用
- CustomBudgetE valuator：**'no results" *
- ToolSelectionAccuracy：
**1.00**
Trace Level：
- Helpfulness：
**1.00**
- ToolParameterAccuracy：
一Correctness：**1.00**
一 ResponseRelevance： **1.00**
**1.00**
LLM-as-Judge 看到的是：
- CustomBudgetEvaluator：
-响应结构完整（有标题、列表、建议）
**1.00**
- 信息看起来合理（价格范围正常）
- 回答了用户的问题
为什么Trace都是满分？
却无法检测：
没有调用专业工具
Trace Level：
- X数据来自通用知识，非权威来源
- X 范围估算 vs精确值
- Helpfulness： **1.00**
一X 不同查询可能不一致
- Correctness： **1.00**
QCon
- ResponseRelevance： *1.00* InfoQ 极客传媒
全球软件开发大会

## Page 025

• 案例1：旅游Agent - LLM-as-Judge解释分析
• ToolSelectionAccuracy评估器一评
• CustomBudgetEvaluator -评分：
分：1.00
1.00
"用户问题：Is $3,000 enough for 7 days in Barcelona from
“Agent表现出色。用户查询明确包含所有四个必需元素；
New York？
出发地（New York）、目的地（Barcelona）、时长（7天）和预
这明确是一个预算可行性问题，涉及特定行程。
算（$3,000）。
Agent调用了'calculate_trip_budget工具，参数为；
Agent正确选择了'calculate_trip_budget工具，这是
origin="New York, destination='Barcelona'，
处理预算相关旅行查询的合适工具。所有必需参数都被
duration_days=7,budget=3000
准确提取。Agent没有使用web_search或其他不适当的工具，
这些参数直接映射自用户问题中的信息。
而是直接调用了正确的专业工具。“
工具返回了完整的预算分解：航班$600、住宿$560.
餐饮$350.活动$280，总计$1,790，剩余$1,210，
并确认预算可行。
此行为与用户意图完美对齐。”
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 026

pass@k和pass^k验证：多轮不同版本对比测试
模糊的提示词
修复后明确提示词
You are a helpful travel planning assistant.
You are a helpful travel planning assistant.
Tool Selection Guidelines：
Focus on
comprehensive
information gathering to provide the best possible answers.
- When user provides origin, destination，
duration, and budget -> Always use calculate_trip_budget
Use available tools to research and compile detailed responses.
- For flight-specific queries 一> Use search_flight_info
Available tools: search_flight_info, calculate_trip_budget, web_search, get_climate_data，
- For weather information -> Use get_climate_data
convert_currency.calculator
- For currency questions
Use convert_currency
- Only use web_search for general travel intormation not covered by specific tools
Extract parameters accurately and provide specific, actionable information.
Available tools: search_flight_into. calculate_trip_budget, web_search. get_climate_data.
convert_currency. calculator
pass_k_evaluator：多轮一致性
多轮对比测试：
基准 vs broken vs fixed
'instructions"： "Evaluate the agent's consistency acrossmultiple trials of the
AGENT VERSION COMPARISON
same query. \nlnContext： ｛context｝\nTool Used： ｛tool_turn｝\nAvailable Tools：
［available_tools｝\nynConsistency Evaluation Criteria：\n\n1. **Tool Selection
consistency*n- Does the agent use the same tool across trials？\n
Metric
V1_baseline
v2_broken
v3_fixed
tools are used,1s there a valid reason7\n\n2： **Parameter Extract1on Consistency**n
Success Rate
80.0%
0.0%
100.0%
- Are the same parameters extracted from identical queries7\n
- Do parameter values
bass@1
0.0%
0.0%
100.0%
match across trialsunin3. **Result Consistency*\n
- Do calculations produce the
bass@10
100.0%
0.0%
100.0%
same resuLts?n
- Are recommendations consistent？\n\n4.**Response Format
bassA1
①.0%
①.0%
100.0%
Consisteney**/n
- Is the response structure similar across trials？\n
- Are key
bass^10
0.0%
0.0%
100.0%
information elements always present？\nl iScoring Guidelinest \n- 1,0（Perfect）：
Identical tool, parameters. and results across all trials\n- 0.75（Good）： Same tool
Evaluator Scores
v1_baseline
vZ_broken.
V3_fixed
and parameters,minor formatting variations\n- 0.5 （Moderate）： Correct tool but some
parameter variations\n- 0.25 （Poor）： Inconsistent tool selection or significant result
Tool SelectionAccuracy
0.84
0.20
1.00
varlations\n- 0.0（Inconsistent）： CompLetely different approaches or
ToolParameterAccuracy
0.80
0.00
1.00
tooLs\nlnProvide：\n- Score （0.0to 1.0/In- Label （Perfect
Helpfulness
0.74
0.45
0.85
correctness
0.92
0.55
1.00
Consistency/Good/Moderate/Poor/Inconsistent）\n- Explanation of consistency Level\n-
CustomBudgetEvaluator
0.86
0.20
1.00
Specific examples of variations if any""
Qcon
InfoO
极客传媒
全球软件开发大会

## Page 027

•案例1：旅游Agent - 评估指标对比
67% -92%
0.52 1.00
工具选择准确性
响应有用性
Broken Fixed
极大提升
4周 2小时
3周 1天
检测时间
修复时间
98.5%提升
96%提升
传统监控盲区
多层次评估
提示词重要性
• Tool Level：检测工具使用（发现
“全面信息收集”（模糊） 失败
•技术指标正常（响应时间、错误
问题根源）
• "ALWAYS use tool when...
”（明
率、工具激活率）
• Trace Level：评估响应质量（发
确）一成功
• 工具使用模式变化 一 质量降级
现用户体验影响）
•具体、可执行的工具选择规则
QCon
InfoO极客传媒
全球软件开发大会

## Page 028

• 案例2：代码生成 Agent - 质量与安全问题
发现的问题（无评估时）
CLAUDE
1. 安全漏洞：
CODE
#
危险的代码：SOL注入风险
- SQL注入风险（未参数化查询）：12%代
query = f'SELECT * FROM uSers WHERE
userame="/username/|
企业级代码生成助手
码
cursor.executelquery）
硬编码密徜
APL_KEY = "sk-1234567890abedef"
• 帮助开发者生成 代码
-硬编码密钥：8%代码
db_password = "admin123"
• 需要确保代码质量和安全性
- 缺少输入验证：25%代码
没有异常处理
2. 质量问题：
data = requests.get（url）.json（）
问题：AI生成的代码质量不稳定
result = datallitems ||O|| value"l
-缺少错误处理：35%代码
# 无类型信息，调用者只能猪
• 单元测试：
通过（功能正常）
def process_order（order, user, discount）：
- 没有类型注解：60%代码
total = order［"price"］*order［"qty"］
return ｛"total"：total： （1 - discount），"user"： user）
• 集成测试通过（接口正常）
- 缺少文档字符串：45%代码
嵌套循环 O（n^m），逐个查找
def find_common（list_a, list_b）：
• 安全和质量问题需要人工 Code
result=
3. 性能问题：
for a in list a：
Review 才能发现，每个PR 30-60分
for b in list b：
钟
ffa==b：
- 未优化的循环：18%代码
result.append（a）
return result
修复每个漏洞平均2-4小时
- 重复的数据库查询：15%代码
QCon
InfoQ极客传媒
全球软件开发大会

## Page 029

案例2：代码生成 Agent 评估架构
Claude Code OTEL Integration - Evaluation
Local Environment
Cloud
• Claude Code Hook触发
Developer
Tocl calls
Claude Code
i Observability Logs
二LLM
LLM-as-udge
Agent事件日志
• OTEL格式（Span,Trace，
Session）
hooy evants
•
写入可观测性平台
（JSON stdin）
PutLogEvents
Read Traces
InvckeModel
• 評估器结合大模型处理
• 评估指标打分
contig.json
OTEL Hook
• OTEL Formatting
ctauae aode otel hook.py
Generate Spana
Spans + Events，
Evaluation
& Events
Scores & Metnics
oplional
OTEL Fialds:spanldtraceld: 6assion.id
~Evaluation Results
Scope:strands.teemetry.tracer
GoalSuccesshate
Attra: service.name tool.name
Hepfulness Acouracy
Langtuse
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 030

案例2：代码生成Agent- 评估前后对比
问题示例：“实现用户登录API” 生成代码
评估前
评估后
def login！
username：
str，
password：
Str
def login（username, password）：
SQL注入风险
1> Dictlstr, str！
参数化查询（防SQL注入）
query = f"SELECT *FROM
明文密码对比
m验证用户登录
密码哈希验证
Returns；｛status"：
''success/failW
users
无错误处理
try：
异常处理
WHERE
query = "SELECT * FROM users
name='［username｝"
无类型注解
WHERE name =？"
类型注解
result = db.execute（query.
（username. 1）
result = db.execute（query）
无文档
文档字符串
if result and
check_password_hash（
if result and result［0］［2］==
result［Oll password_hash］.
password：
password）：
return f'status"：
"'success"
自动评估发现（秒级）：
return ｛'status"："success"｝
except Exception as e：
logger:error（f"Login error： ｛e/"）
return ｛'status"：
"fail
LLM-as-Judge: 0.35-0.95
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 031

• 案例2：代码生成- 评估指标改进
12% -> 95%
0.58 -0.92
安全问题检出率
代码质量评分
SQL注入，硬编码等
LLM-as-Judge平均分
30min - 5min
85% - 98%
人工Review时间
pass@5（能力）
自动化预检
生成正确代码概率
增强提示词
自动化评估
|持续监控
添加安全检查清单
每次生成后立即运行6个评估器
• 采样10%生成代码进行深度评估
明确要求参数化查询、异常处理
发现问题自动重新生成（最多3次）
• 每周生成安全报告
提供安全代码示例
记录所有问题用于持续改进
• 发现新模式立即更新评估器
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 032

•案例3：客服Agent- 用户满意度下降
发现的问题（无评估时）
场景：电商售后客服
1. 同理心缺失（28%对话）：
• 平台：处理退款、换货、投诉
用户：“我很生气，等了两周货还没
到！"
• 规模：日均5000+对话
Agent；“请提供订单号以便查询。“
。
目标：解决问题+保持用户满意度
直接要信息，没有表达理解
2.重复询问（35%对话）：
业务影响
用户在第2轮已提供订单号
◎
Hey: Howcan lassist
today？
Agent在第5轮又问“请提供订单号"
need help with my
用户满意度（CSAT）下降：4.2 3.6（5分
xecount
制）
◎
Mll resolve that for you！：
缺少会话记忆
Thanks tor the support！
。
转人工比例增加：15% 28%
3. 解决方案不清晰（42%对话）：
平均对话轮数增加：6 9.5（效率降低〉
用户：“什么时候能到账？"
Agent："已为您处理退款。“
缺少关键信息（时间、金额、方式）
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 033

• 案例3：客服Agent - 通过评估找到问题
评估设置（多轮对话评估）
Trace Level （LLM-as-Judge）
Session Level（Custom）
• Empathy Score：共情分数（0-1）
• Context Retention：是否记住之前说的话
• Information Completeness：
信息完整性
•Efficiency：对话轮次（越少越好）
• Clarity Score： 清晰度分数
•
Resolution Quality：问题解决质量
提示词优化
多轮评估
实时反馈
• 添加”从用户消息中提取所有关键信息”
指令
•不只评估单次响应，评估整个对话
•对话结束后自动运行评估
• 检测是否重复询问已提供的信息
•低分对话标记给质量团队审查
• 要求始终包含具体数字（金额、时间）
• 添加共情话术模板
• 评估最终是否真正解决问题
•每周生成改进建议
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 034

•
案例3：客服Agent- 评估前后对话质量
评估前
评估后
用户：“我要退款，订单#12345"
用户：“我要退款，订单#12345"
评估结果对比
Agent："好的，我可以帮您处理退款。
Agent："理解您的需求。让我为您
查询订单#12345的退款情况。"
评估前
评估后
请提供订单号。”
直接使用用户提供的订单号
Empathy（同理心）
0.3
0.95
用户已提供订单号，还要再问
［调用 verify_order, fetch_policy，
Clarity（清晰度）
0.4
1.0
用户：“我刚说了，#12345！“
process_refund 工具］
Efficiency（效率）
0.5
0.95
Agent："抱歉。订单#12345已处理
Agent“已为您处理退款：
用户满意度
2.8
4.6
退款，请等待。”
•订单金额：¥299
对话轮数
8
3
没有说明退款时间和金额
•退款金额：¥299
升级至人工
Y
N
用户：“什么时候到账？多少钱？"
•退款方式：原路返回支付宝
•预计到账：3-5个工作日
Agent："请查看订单详情。”
退款确认邮件已发送至您的邮箱。
没有直接回答问题
还有其他需要帮助的吗？”
信息完整、清晰
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 035

•案例3：客服对话 - 评估指标改进
3.6 4.6
9.5轮—4.2轮
用户满意度（CSAT）
平均对话轮数
5分制，提升28%
效率提升56%
28% ->12%
62% -> 94%
升级至人工率
pass^10（可靠性）
降低57%
一致性大幅提升
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 036

05
工程实践与落地路径
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 037

构建评估体系：8周路线图
基础设施搭建
评估器配置与校准
•选择Agent框架
• 配置内置评估器
•集成可观测性
Tool/Trace Level
CloudWatch/Langfuse
•开发1-2个自定义评估器
• 配置trace收集和存储
•校准LLM-as-Judge
（>90%）
W1-2
W3-4
W5-6
W7-8
评估任务设计
自动化与集成
• 提取20-50个任务
•在线评估（5-10%采
从生产失败中提取
样）
•定义Ground Truth标准
关键场景100%
•两位专家验证（一致率
• 配置日志告警
>90%）.
•集成CI/CD pipeline
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 038

，三个案例的评估方案总结
对比维度
旅游Agent
代码生成
客服对话
核心问题
工具选择失效
安全＋质量
同理心＋清晰度
评估框架
AgentCore
Langfuse
Langfuse
Ground Truth
70%
40%
30%
LLM-as-Judge
30%
60%
70%
关键指标
ToolSelection
安全检出率
CSAT满意度
改进效果
67% -92%
12% - 95%
3.6- 4.6
检测时间
4周 2小时
Review时 秒级
用户投诉一实时
ROI
>100:1
>50:1
>80:1
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 039

评估常见问题
5个常见问题 ＆ 解决方案
问题1 任务设计质量差
两人独立评估，一致率>90%
问题2过度依赖LLM-as-Judge.成本过高（$0.02-0.05/次）
推荐：70% GT +30% LLM 混合方案
问题3忽略非确定性
pass@k（能力）vs pass^k（可靠性）多轮评估
问题4评估与开发脱节
C/CD集成＋自动告警＋PR门控
问题 5 采样策略不当
5-10%常规采样.100%关键场景
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 040

评估成本分析
成本分析（三个案例）
假设10万次/天 Agent 调用
-每天 10万次Agent调用
旅游Agent
-每月300万次调用
$300/月（AgentCore+CloudWatch）
- 每次评估 =1次LLM 调用（Judge 模型对 Agent 输出打
+$150/月（评估执行5%采样）=$450/月
分）
代码生成
单次 LLM-as-Judge 的成本：
$100-500/月（Langfuse+LLM, 10%采样）
-评估 Prompt（评分标准、指令）：约 500-800 tokens
-被评估的 Agent 输入＋输出：约500-2000 tokens
- Judge 模型的输出（评分＋解释）：约 200-500 tokens
客服对话
$500-1500/月（多轮评估，10%采样）
单次评估大约1200-3300 tokens （input + output）
Claude Opus/GPT-4： 单次评估 $0.02-0.05
评估方案
月成本
说明
ROl计算（旅游Agent示例）
无评估
问题检测需要4-7周
成本：$450/月
100% Ground Truth
快但只能评估确定性任务
收益：节省＄20K工程时间＋避免$50K+用户流失
+ 15%质量持续提升（持续价值）
100% LLM-as一Judge
$60,000-150,000
太贵
10% 采样＋混合方
$1,800-4,500
推荐方案
ROl：>100:1第一个月即回本
案（30%GT +70%
LLM）|
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 041

0の
总结
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 042

• 核心要点：三个案例的启示
评估是Agent生产化的必要条
方法论：Ground Truth+ LLM-
不同侧重评估方向
件
as-Judge
旅游：7周一1天（98.5%时间节省）
三个层次：Output, Trace, Session
旅游：工具选择（Tool Level重点）
代码生成：30min人工review 5min（自动化预
三个阶段：能力评估 —回归评估一生产监控
代码生成：质量评估（40% GT+60%
检）
LLM）
处理非确定性：pass@k（能力）vs pass^k（可靠
客服对话：用户满意度3.6-4.6（28%提升）
性）
客服对话：交互质量（70% LLM + Session
Level+
• 识别关键场景（20-50个任务）
• 配置基础评估器（内置＋自定义）
立即行动
评估不是成本，是投资
• 从5-10%采样开始
' ACTION
设置CloudWatch告警
8周即可建立完整评估体系
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 043

InfoQ 极客传媒
QCon
全球软件开发大会
THANKS
大模型正在重新定义软件
Large Language Model Is Redefining The
Software

## Page 044

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
