# CLI for AI Agents

- Source PDF: `references/papers/CLI_for_AI_Agents.pdf`
- Visual pages: `references/paper-visual/images/CLI-for-AI-Agents/`
- Extraction mode: visual page-by-page information extraction
- Page count: 11

## Page 001

为AI智能体重新设计你的CLI
为什么面向人类的终端工具在
AI时代注定失效，以及如何构
｛
建下一代架构。
"action"： "process_logs"，
"source"："logs/"，
"filter"：｛
"contains"："error"
｝
"output_format"："json"，
"destination"： "output_stream"
grep-r'error'logs/
｝
grep-r'error'logs/
"action"： "list_files"，
"path"；
"."
Is-la--human-readable soutput.txt
"options"；｛
"all"：true，
sed's/otd/new/g'file.config
"human_readable"： true
Yhormat"：nstructured_data"
awk "print $1｝' data.csv
｝
"'action"'："transforn_data"，
"source"："data.csv"，
"operatlon"；｛
"type""："extract_column"，
"Index"： 1
！output-schema”： t
"fields"：［"1d"］
S NotebookLM

## Page 002

核心冲突：人类体验 vS. 智能体体验
简单的改造并不能解决问题。两者在设计假设上存在根本分歧。
人类体验
智能体体验
•优化发现性与容错性
•优化可预测性与纵深防御
agent"： "alpha"，
"task"：｛
“Id：“T-181"，
"type"：
"execute'
"parameters"：f
“precision"： "high”，
"predictability"： "strict"
"'security"！｛
"Layer1"： “validate"，
"Layer2"：
"encrypt"
万NotebookLM

## Page 003

法则一：原生JSON载荷优于定制化参数
扁平参数导致信息丢失；原生JSON无缝映射API架构，消除翻译损耗。同时
保留两种方式：人类使用快捷参数，智能体使用-json。
信息损耗/UI层
my-cli spreadsheet create --title'Q1 Budget'--locale 'en_US'--timezone 'America/Denver'
--sheet-title 'January'--sheet-type GRID --frozen-rows 1 --frozen-cols 2 --row-count 100
--col-count 10 --hidden false
零翻译损耗
gws sheets spreadsheets create --json'｛
"'properties"： ｛"title"： "Q1 Budget"
••｝
｝'
S NotebookLM

## Page 004

法则二：用运行时架构自省取代静态文档
静态API文档不仅浪费大量Token，且容易过时。CLI本身必须成为可被动态查询的“单一事实来
源”
。
gws schema
极高的Token消耗
drive.files.list
｛
"params"： ｛ …•｝，
动态解析机器可读架构
"'response_types"：｛ ••｝
5 NotebookLM

## Page 005

法则三：严格管控上下文窗口
智能体按Token付费。巨大的API返回包会摧毁其推理能力。必须在指令层强制缩减返回体积。
｛"data"：［｛id"："123"
"'name"："Alice"，"details"：
TOKEN BUDGET
｛...｝，"history"：..），。
Chame"：
"Teal"），
｛'history"：...），
Eipenaste"："Inana"），
｛"data"：［（"id'"
123"
'name"："Alice"
"details"：
！123"
"'name'：'Alice"'
"details"：
｛..），
"history"：...），
..1｝，Kuage""｝，
0%
丧失推理能力
｛'data''： ［｛"id"："123"
（name" ： 'Alice"
"details"：
，"history"：..），_.1）2，
CTameEY"："1ST8S'D，
｛'data"： ［｛"id"："123"
，（name"："Alice"，"details"；
｛'data"：［｛"id"："123"
"haue"："ALice"
"details"：
｛，"dataitts"，
"details"：｛..F，"history"：..｝，-1
TOKEN BUDGET
字段掩码
（Field Masks）
维持高效推理
NDJSON 分页
S NotebookLM

## Page 006

法则四：针对AI幻觉强化输入防御
人类会拼写错误，智能体会产生幻觉。CLI必须作为抵御错误输入的最后一道防线。
人类错误（罕见）
智能体幻觉（常见）
意外输入.•1../.ssh
混淆生成的路径片段
非法嵌入查询参数
ID拼写错误
（fileId?fields=name）
明文输入
双重编码（%2e%2e）
智能体并非受信任的操作员。
绝不能盲目信任其输入。
A NotebookLM

## Page 007

法则五：分发智能体技能，而不仅仅是命令
智能体不看--help。它们依赖于对话开启前注入的上下文。通过结构化的
SKILL.md 传递那些无法被直觉推断的硬性规则。
-
name:gws-drive-upload
L REPOSITORY
description: Uploads a file to Google
Workspace Drive with specific controls.
src
--
agents
• Always use -dry-run for
D
mutating operations
D
SKILL.md
• Add --fields to every list
上下文注入
call
S NotebookLM

## Page 008

法则六：单一信源，多终端架构
优秀的CLI应基于同一个核心二进制文件，为不同框架的智能体提供服务。
Discovery Doc
（单一信源）
Core Binary
（gws）
CLI
MCP
Gemini Extension
Env Vars
（人类交互终端）
（stdio JSON-RPC）
（原生智能体能力）
（无头凭证注入）
A NotebookLM

## Page 009

法则七：部署终极安全护栏
构建闭环安全机制，防止破坏性变异操作与来自第三方数据的提示词注入攻击。
--dry-run
--sanitize
Sandboxed
Inspection
｛
Ignore previous
"action"："delete"，
instruetsons...
"'target"："user_data"
DROP TABLE users
Safe AI
Processing
Injection Attempt
Blocked
5 NotebookLM

## Page 010

实施路径：渐进式改造指南
无需推翻重来。按照优先级逐步为现有CLI增加智能体支持。
暴露 MCP 接口
分发
（消除Shel1转义）
CONTEXT.md/
技能文件
（注入规则）
7
引入
--dry-run
（变异操作安全）
6
支持字段掩码/
--fields
（保护Token）
5
增加--describe
/架构查询
（支持自省）
4
严格校验所有输入
（防御幻觉）
3
添加 --output
json
（基础门槛）
2
1
S NotebookLM

## Page 011

智能体并非受信任的操作员，
请以此为基准进行构建
人类体验与智能体体验并不对立，而是正交的。保留人类的便捷操作，但在底层，
必须构建智能体所需的原生载荷、架构自省、输入强化和安全护栏。
F NotebookLM
