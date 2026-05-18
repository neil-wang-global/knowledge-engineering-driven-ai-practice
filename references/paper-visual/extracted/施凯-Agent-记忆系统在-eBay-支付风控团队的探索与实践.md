# 施凯-Agent-记忆系统在-eBay-支付风控团队的探索与实践

> Page-by-page visual information extraction from rendered slide/page images. Text is OCR-assisted and preserves visible page order; diagrams/tables are represented by their visible labels and relationships as line-by-line text.

## Page 001

InfoO 极客传媒
QCon
全球软件开发大会
Agent Memory in eBay Payment Risk：
Exploration & Practice
Name: Kai Shi
Title: Staff
Engineer

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
The Background Introduction
02
Initial Version of Agent Memory Practice
03
The Knowledge Graph in Agent memory
Agend
04
Memory Evolution
a
05
Memory Evaluation
06
Takeaways

## Page 004

Background
Build the Agent to help the EDP migration
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 005

Migrate Risk Checkpoints to ebay Decision Platform
Risk Checkpoin 1
Risk Checkpolnt 2
Risk Checkpoint1
Risk Checkpoint 2
Migrate
Ebay Decision Platfom
La
思
Lay
Decisions
Rules
Risk Business
Data
Models
Decisions
Rules
Risk Business
Objects
Models
Objects
• The eBay Decision Platform （EDP） is a managed platform for setting up and maintaining risk
checkpoints. lt is primarily a configuration driven solution that allows you to build checkpoints
without writing any code, supports flexible decision orchestration and enables complex decision
flows.
•
EDP Migration: Migrate diverse risk-control checkpoints into the eBay Decision Platform by
converting Java ousiness logic to YAML configurations, while preserving business functionality
and ensuring consistent risk-control decisions.
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 006

Agentic way for EDP Migration
Opportunities
Challenges
Logic-to-implementation conversion
Internal concept gap
Agents excel at understanding existing
LLMs lack precise understanding of interna！
implementation ogic and converting it into
enterprise concepts and a holistic view of
another form （e.g.， Java to Python） for public，
business processes
well-documented patterns
Efficient repetitive migrations
•
Limited business overview
Using Agents for tedious, repetitive migration
Limited global awareness of internal business
tasks can significantly improve efficiency and
context leads to errors and inconsistencies
reduce effort
The Agent Memory System is the key to implement the Agentic way for EDP migration.
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 007

Types of Agent Memory
In-Weights memory
In-Context Memory
2
3
Knowledge encoded in model
The active context window -
parameters during training. Always
conversation history, injected docs，
available, but immutable at
tool results. Flexible out token-
runtime.
limited and session scoped.
1
4
In-Cache Memory
External Memory
KV cache reuse across reauests
Persistent storage outside the
via prompt caching. Reduces
Engineering
model - vector DBs, knowledge
compute cost for fixed prefixes；
Perspective Memory
graphs, databases. Survives
not semantic memory.
sessions, scale without limit，
types
retrieved on demand.
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 008

• Requirements Identification: Agent Status at eBay
In-Weights
/ Claude Model itself （Sonnet / Opus）
eBay adopts Claude Code
Memory
Pre-trained weights
Code understanding, language, reasoning, tool use— bakea in
eBay engineers mainly use local
Immutable at runtime, fully transparent across all sessions
Claude Code in their daily work.Each
In-Context
department develops its own skillS，
/ ~190k token context window
vemory
most of which are built on the MCP
ctive context
Conversation history + CLAUDE.md + tool results all injectea
window
Vanishes when session ends, /compact extends lifespan
server provided by the core platform
team.。
In-Cache
Prompt Cache （infrastructure layer, invisible to
A user）
Memory
KV Cache reuse
Fixed prefixes like CLAUDE.md auto-cached, reduces APl cost
Not semantic memory, uncontrollable, very short lifespan
Developer
• CLAUDE.md （manually authored）
卜
global / project / directory hierarchy, auto-Injected at session
「Mcp Servers
start
External
Memory
A
Auto Memory （self-learning, v2.1.59+）
Local Claude
Claude auto-writes Markdown notes, still injected into context，
Code
Github
WIkI
200-line cap
Persistent cross-
00
sesSIOm
Vector search / Knowledge graph / Structured
retrlevable storage
×
DB
skills
Jira
Elastic Search
Not natively supported — requires MCP Server extension
—
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 009

02
Initial solution
Agentic RAG and Long-term memory
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 010

The Overview of the Agent Memory System
01
Initialization Phase
Memory Initialization Phase
Pre-defined graph traversal for known
tasks. Schema-aware generation + self-
validation tor unknown queries.
Chuking
Eorich
Al Agents
2hurking-
LLM
02
Growth Phase
Memory Storage-
SKills encode how to actcompleting
Opdate Event
the Eoisocic / Semantic/ Procecura
Memory Growth Phase
New
Embedding DR
Cbject Srorage
memory architecture.
Extraction
Update
03
Retrieval phase
Memory add
cummany
ADD
Deep
UPDATE
New
t0ol
thinking
~DELETE
Memcries
Messages
DNODP
Pre-defined graph traversal for known
Merory
Top similar
tasks. Schema-aware generation + self-
retrieve tool
memOrLeS
validation for unknown queries.
Fetch memory-
Memory Retneval Phase.
query
Fetch data
Rerank&
Validate
TopN
response
04
MCP server interface
reicn menow
Skills encode how to act — completing
the Eoisodic/ Semantic / Procedura
memory architecture.
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 011

The Memory Initialization Phase
Sources
Pre-chunk Cleaning
Chunking
Chunk Enrichment
Embedding & Store
Text
WOC
Embed
Merge
wiki
Understandi
Cleaning
the Chunk
Embeddings
google doc
Image
Read Chunk
Summarize
Build Vector
Process
Config
Chunk
Index
gitHub
Table
Embed
Persist to
Chunking
Conversion
Summary
VectorDB
git page
Index
Metadata
Metadata
Ingestion & Cleaning
Chunking & Enrichment
Embedding & Store *
We normalize content from wiki. Google Docs，
Documents are split into semantically coherent，
Final stage （completed in this project）：merge chunk
GitHub. and Git pages: clean and standardize text.
configurable chunks. Each chunk and its LLM summary
and summary embeddings, build the vector index.
tables, and images:then chunk so embeddings
are embedded, enabling exact and semantic retrleval.
persist all vectors, and index metadata （source，
capture clean, structured content.
position, tags） for filtered retrieval.
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 012

• The Memory Retrival Phase
• Multi - perspective query
Query Stan
Enhance
Muliple
Embed
Query
Queries
Quenies
enhancement: extract
entities/acronyms/time/app; favor
internal terminology and expansions
Embedding
• Hybrid retrieval and re - ranking：
the chunk
keywords + semantic; merge and
Plan Search
Searched
Rerank the
Strategy
Chunks
chunks
Filter Top N
dedupe; re - rank by evaluation score
Embedding
search from
• Hyperparameters: prompt，
the summary
strategy_mode, topN, evaluate_score，
necessary filters
• Accuracy first: raise threshold T，
Evaluate
Response
Query End
widen recall topN;accept higher
latency
Information
• Outputs: results + scores + filters +
Enough
brief expansion trace; log parameters
and confidence
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 013

• The Memory Growth Phase
• Non - personalized growth：
New extracted
excludes user preferences
memories
Extraction_-
Update
• Feedback - informed growth：
ADD
incorporates agent conversation
Summary
MTUPDATE
feedback
1. Input conversations
thinking
• DELETE
Messages
2.Summarize
IOOP
Memory add
• Prompt craftsmanship: creating
t00l
Top similar
memones
your own prompt is key to surfacing
information you’ re interested in
3. Query similar memories
New Memories
Embedding DB
5.Updating
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 014

Advantages of the solution
High accuracy for
Effectively assists with migration tasks, including error
specified queries
handling, concept Q&A, and operational guidance
By employing intelligent chunking and querying，
2
High Query Recall
we improved chunk semantic completeness and
query coverage
The implementation approach is clear and well-
Simple, straightforwarddefined an advanced Retrieval-Augmented
3
implementation
Generation （RAG） implementation that is highly
reusable.
aCon
InfoQ 极客传媒
全球软件开发大会

## Page 015

•
， The Limitations of the Solution
This memory system cannot provide higher autonomy to the
Agent
Unable to perform effective exploration
Strong memory search performance for specified queries, but
requires continuous user input and cannot provide the agent with
a global view to plan better exploration paths
Procedural memory conflicts
A centralized memory system aggregates user uploads.
Preferences and facts are easy to revise; some memories aren’t
simple substitutes and must coexist. Moreover, incorrect
procedural memories can persist in the system, providing the
agent with misleading information.
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 016

02
Knowledge Graph
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 017

• Why Knowledge Graph
1
2
3
！
Global Perspective
Multi-hop
Structured query
reasoning
Vector retrieval only finds
Some questions require
When the question is
locally Similar chunks.A
following a chain：'which
precise一"all
knowledge graph
variables flow into models
checkpoints in
captures the full system
used by rules in
environment X that
topology— how
checkpoint A？" Vector
depend on variable V"一
Checkpoints, rules，
search cannot traverse
fuzzy retrieval introduces
models, and varlables
edges. A knowledge graph
noise. Graph traversal
connect enabling
makes every hop explicit.
supports exact filtering，
questions no single chunk
path constraints,and
aggregation.
can answer.
Con
InfoQ 极客传媒
全球软件开发大会

## Page 018

• Hybrid Knowledge Graph Schema
WHAT
o1
Static Schema
Dynamic Schema
Predefined node types and relationships — Checkpoint, Rule，
No predefined types. Entities and relationships emerge
Model, Variable. Versioned and frozen after stabiization. Rebuilt
checkpol
automatically from written events — migrations, corrections, triage
only when the system structure changes.
decisions. The schema grows with the system.
WHY
Static alone is too rigid
01
Real systems have exceptions, history, and edge cases that don't fit a fixed schema. A
frozen graph cannot capture what happened— only what exists.
Dynamic alone is too loose
Without a structural backbone, queries lose precision. There is no stable anchor for
02
cross-layer Joins, versioning, or deterministic traversal.
Fyorid gives both
03
Deterministic traversal on the static layer. Contextual recall on the dynamic layer. The
two meet at shared entity_id— one query, two memory types.
acoQCon
InfoQ 极客传媒
全球软件金球软件开发大会

## Page 019

• Strategies to Build the Static Graph Schema
Use case - driven
Define the minimal core and necessary extensions based on key
query/inference scenarios.
Stability first
The core should converge on validated, general concepts, avoiding
the sinking of business-specific details into it.
Alignable
Design stable access nodes for core entities, and,as the graph
expands, ensure that through unified semantics or explicit
mapping rules, different subgraphs can recognize the entity as the
same object and participate in the same querying and merging
processes.
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 020

Claude code-Driven Knowledge Graph Extraction Workflow
Claude
Human
Claude
Claude
O1 Generate
02 Review
03 Execute
04 Validate
Explores codebase &
Edits extraction _logic，
Counts extracted vs
configs，
Strictly follows JSON
adjusts id_fleld
expected，
dratts JSON with
ruleS，
conventions，
flags orphan nodes，
extraction_ogic
pauses on ambiguity，
confirms or rejects
reports undeclared
for every entity &
never self-interprets
entity types
types
relationship
JSON Schema Contract
Why This Works
Alignable
Human owns the rules
anchor
"label*："Agent，
extraction_ogic Is plain language written by the
''source"："agents/*.py"，
Human
human. Claude executes, never interprets.
"id field*："'class_name"，
edits this
"extraction logic"：
◎
Stability-first by default
"Find classes inheriting BaseAgent，
JSON naturally encodes stable entities first.
use class name as node ID"，
Dynamic relationships added in later iterations.
properties：｛
"tools ："parse self.tools list"，
Alignable via id_field
"memory_type"："check memory= param"
A single id_field convention ensures static and
dynamic layers merge cleanly.
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 021

• Build a Agent Skill for KG construction
Building the Skill
What the Skill Looks Like
Describe Goal & Boundary
Natural language spec
01
name: kg-builder
Tell Claude Code: Data source（code/rules）， input （schema.json）， output
description: Build KG schema
（written nodes + validation report）， and constraints （label-scoped delete，
from codebase using JSON spec
MERGE not CREATE）.
tools：
- bash
-read_file
Claude Code Generates Skill File
Auto-generatea.ma
02
Claude drafts theclaude/agents/kg-builder.md with YAML front matter
# Pipeline
（tools, description） and a structured prompt encoding all 6 pipeline steps.
1.Install deps
2. Fetch source data
3.Load schema.json <-reviewed
Review & Embed schema.json Path
Human review gate
4.Clear by label
03
5.Extract & MERGE
6.Validate & report
Human reviews the skill file. Key edit: point the skill at the human-
approved schema.json so it never reads an unrevlewed file.
When It Runs
Run Once — Verify Output
Acceptance signal
Trigger: claude kg-builder in project root
04
• Input: schema.ison （human-approved）
Trigger the skill. Claude Code installs deps, fetches data, executes
• Output: node count diff + orphan report
extraction logic, writes to Neo4j, and prints a node-count diff as the
• Re-runnable: full rebuild each time
acceptance signal.
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 022

• Are Agent Skills also a form of Memory？
Procedural Memory
"I know how to do X"
in humans
In Agent system
How to perform tasks, skills，
Claude Code Skills
habits and automatic behaviors
Predefined queries + dynamic generation + verification of sufficiency and
necesSlty
^
calibrates via past
provides schema for generation
exoelience
Episodic Memory
"I remember X"
Semantic Memory
"1 know X"
in humans
In Agent system
in humans
In Agent system
Checkpoint / Rule /
Personal experiences，
Temporal events are
Factual knowledge，
Variable
conversation history，
persisted in graph form.
concepts,entities
structured entities and
temporal events
and their relations
relationships
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 023

Where Are We
Solved
What existing KG + Skills gave us
Still Open
What existing KG cannot handle
01
Knowledge Structure
Static KG
Knowledge Conflict
In development and migration, multiple versions of the same
Checkpoint - Rule Model - Variable dependencies
entity co-exist across environments. The graph has no
are explicit, queryable, and maintainable via schema.json
confidence mechanism to determine which version is the source
of truth.
dev rule R v2.1 vs prod rule R v2.0— which one does the query
02
Intelligent Query Routing
Query Skills
reflect？
Pre-defined graph traversal for known tasks. Schema-
aware generation + self-validation for unknown queries.
Structure vs. Semantics Gap
Graph traversal finds explicit edges. Vector search finds
semantic similarity. But real questions span both - and no
Procedural Memory
03
Memory Types
single query can bridge them today.
Skills encode how to act - completing the Episodic /
Semantic / Procedural memory architecture.
"Which rules with a history of issues depend on variable V？"
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 024

04
Memory
Evolution
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 025

•
Why Memory Must Evolve
01
Ambiguity & Entity Alignment
02］ Interaction Feedback Loop
The same concept carries different names across checkpoints.
User feedback during interaction is itself new knowledge -
When new knowledge is written in, there is no mechanism to
a correction, a judgment, a refined procedure. A static
recognize it as an existing entity.
graph has nowhere to put it.
Before
Feedback
User interacts
Gives feedback
risk score
riskScore
with Agent
or correction
pecomes
（checkpoint A）
（checkpoint B）
new memory
After entity resolution
New memory can take three forms：
rIsK score
（checkpoint A）
SAME_AS
「iskScore
Graph edge
Event node
Skill update
（checkpoint B）
structural update
episodic record
procedura memory
Without resolution, cross-checkpoint queries return incomplete
Each interaction is a learning opportunity. Ignored feedback
results
- the graph looks connected but has silent gaps.
is lost Knowledge.
A memory that cannot correct itself is just a snapshot. Knowledge evolves - so must memory.
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 026

• What is Graphiti
01
Bi-temporal Model
02
Entity Resolution
When it happened vs. when we knew
New knowledge finds its home
Every fact carries two timestamps: the time the event occurred
When a new node is written in, Graphiti checks whether it
and the time it was written into the graph. This lets the Agent
already exists under a different name or alias. If it does,it
reason about the past without being confused oy late-arriving or
creates a SAME_AS edge rather than a duplicate node
corrected information.
keeping the graph complete and connected.
Supports "what did we know at time T？" queries
Directly addresses the ambiguity problem
03
Conflict Resolution
04
Hyorid Retrieval
Contradictions are adjudicated, not overwritten
Graph traversal + semantic search in one query
When two facts contradict each other, Graphiti does not silently
A single query can combine structured graph traversal （follow
overwrite. It retains both versions with their validity windows，
explicit edges） with vector-based semantic search （find
and uses recency and source confidence to determine which is
conceptually related nodes）. The two modes complement each
currently authoritative.
other — closing the gap that Cypher alone cannot bridge.
No more sient MERGE overwrites
Resolves the Structure vs. Semantics Gap
QCon
InfoQ极客传媒
全球软件开发大会

## Page 027

How We Use It
Static KG holds structure — Graphiti holds what happened and what we learned
Checkpoin
Events•Decisions•Feedback• Learned
Static KG
+
t：Rule:Model•Variable: Business Logic
Graphiti
Benaviors
Structural Events
Interaction Events
Written during development & migration
Written during Agent interactions
Migration Record
User Correction
Agent suggested approach X for migrating checkpoint A. User
A checkpoint was migrated using approach X. Special handling
corrected: approach Yis required because of constraint B.This
applied to field Y due to legacy exception in environment Z.
judgment is now part of memory.
Exception Annotation
Triage Judgment|
Checkpoint C has a non-standard behavior:condition A triggers
Production issue traced to variable V returning null under
path B instead of default path D. Reason: downstream
condition C. Root cause confirmed. Resolution: add null guard at
dependency constraint.
rule R. Stored as episodic record.
Business Description
Skill Refinement
Update
After repeated corrections on checkpoint type X, a new
A new business rule was added to Checkpoint E: transactions
above threshold T now require secondary validation.
procedural rule is formed: always check dependency chain depth
before proposing migration order.
Example query spanning both layers： "Which checkpoints with past migration issues depend on variable V？.- graph traversal + episodic
recall, unified.
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 028

• Memory as an Organism
Memory is not a database. It's an organism — it grows, corrects itself, and gets smarter with every Interaction.
Semantic Memory
Static KG
Knows the structure
Checkpoint - Rule Model - Variable. The stable skeleton of the system.
Queryable, maintainable, rebuilt on demand.
Stable •Explicit • Structural
Corrects
conflicts resolved
by recency +
Episodic Memory
Graphiti
confidence
Knows what happened
Migration decisions, exceptions, user corrections, triage resolutions. Every event
is timestamped, resolved, and searchable.
Grows
Learns
TemporalEvolving:Contextual
new knowleage
feedback refines
from every event
proceduralskills
Procedural Memory
Skills
Knows now to act
Pre-defined queries for known tasks. Dynamic generation for unknown ones.
Refined over time by feedback from Episodic m Executable Adaptive• Learned
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 029

05
Memory
Evaluation
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 030

The Evaluation Targets
Retrieval
Answer
Regression
Agent retrieves the correct
Final response is faithful to
After any memory update （e.g.
memory （migration record，
retrieved content, traceable to a
KG version bump or new
exception, rule）. Measured by
real memory node, with no
Graphiti event）， previously
contextual recall and precision
hallucinated procedures or
correct answers remain correct；
against ground truth.
migration approaches.
validated via golden cases and
scheduled regression runs.
Correctness
Faithfulness
Safety
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 031

Single Query Evaluation with DeepEval
How It Works
ContextualRecallMetric
01
Coverage
Every Skill execution produces an evaluation triple: the
original question （input）， the memory nodes retrieved from KG
+ Graphiti （context）， and the Agent's final answer （output）.
How much of the relevant memory was actually retrieved? Catches the
case where a partial graph query misses critica nodes.
This triple is fed to DeepEval, which scores each metric
independently. Results are logged and aggregated into a per-
run report.
ContextualPrecisionMetric
Precision
02
Of everything retrieved, how much was actually relevant? High precision
means no noise — retrieved context stays on-topic.
Input
+ Retrieved Context
Output
-DeepEval
FaithfulnessMetric
No Hallucination
03
When It Runs
Weekly automated run— the baseline
Does the final answer stay grounded in what was retrieved? Any claim not
Scheduled
cadence
traceable to a memory node is a faithfulness violation.
Whenever a new version of the Static
KG Version Bump
KG is released
04
AnswerRelevancyMetric
On-Target
Manual
After a migration batch, or when
regression Is suspected
Did the Agent actually answer the question that was asked? Guards
against technically faithful but irrelevant responses.
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 032

Task Level Regression with Agent and Skills
What is a Golden Case？
Task
Expected
Actual
Migrate the variable x to EDP？"
The actual migrated variable by Human
The result of the migration by Agent
load_golden_cases Skill — Execution Flow
Load json golden cases. Each case must
Load
Read golden
Validate
cases file
format
have question, expected_answer，
expected_sources. Abort if schema invalid.
Execute
Run Agent
Capture
sor each case, poueke the heeeaver qyery
query
triple
antoe ee cf ateh tpg ved context/
Run all four metrics against each triple.
Score
Evaluation Skills
Compare vs
scoring
expected
Compare the actual result vs expected result.
Give each task a score.
Check each golden case's score and its
Aggregate
trend. For items with significant score drops，
Report
Score trend per case
report
use an Agent to analyze differences in search
strategies and resulting outputs.
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 033

0の
Takeaways
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 034

Think big, start small.
咩
Begin with real-world
Let industry
Favor small, focused
Never forget to
problems and define
developments propel
combinations over
assess and measure.
the question
your work,not
arge, all-in-one
precisely.
disrupt it.
platforms; defer
nonessential work.
EXecute
Evaluate
Start smart
Choose wisely
efficiently
rigorously
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 035

InfoQ 极客传媒
QCon
全球软件开发大会
THANKS
大模型正在重新定义软件
Large Language Model Is Redefining The
Software

## Page 036

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
