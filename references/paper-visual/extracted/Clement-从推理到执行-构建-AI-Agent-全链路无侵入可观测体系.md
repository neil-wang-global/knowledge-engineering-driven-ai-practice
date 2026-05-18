# 从推理到执行：构建 AI Agent 全链路无侵入可观测体系

- Source PDF: `references/papers/Clement-从推理到执行：构建 AI Agent 全链路无侵入可观测体系.pdf`
- Visual pages: `references/paper-visual/images/Clement-从推理到执行-构建-AI-Agent-全链路无侵入可观测体系/`
- Extraction mode: visual page-by-page information extraction
- Page count: 39

## Page 001

InfoQ 极客传媒
QCon
全球软件开发大会
从推理到执行：构建 AI Agent 全链路
无侵入可观测体系
Clement
阶跃星辰

## Page 002

极客邦科技2026 年会议规划
促进软件开发及相关领域知识与创新的传播
06月？上海
R 1000人
08月9深圳
28 1000人
AiCon
•Al Infra 系统工程
AiCon
•Agentic AI
•多 Agent 协作与实践
•轻量化与高效推理
全球人工智能开发与应用大会
•多模态融合
•多模态应用
全球人工智能开发与应用大会
•模型训练与推理创新
•Al + IoT 场景实践
会议时间：6月26-27日
•数据平台与特征服务
会议时间：8月21-22日
•AI工业化落地
010月？上海
RR 1200人
012月？北京
81000人
•Al Agent
QCon
•Vibe Coding
AiCon
•大模型架构创新
•智能可观测
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
Agent 观测新挑战
02
深度行 感知
目录
03
全链路追踪
04
数据标准与交付
05
总结与展望

## Page 004

•
Agent 响应从3秒变成 120秒，问题在哪？
Agent 执行记录
Pod 监控
tooL_call:bash -l 成功/
CPU 8%，内存 340MB，网络正常
只知道调了 bash，不知道为什么慢
看不出问题
LLM 指标
容器日志
TTFT 210ms, token 正常
无输出
跟LLM没关系
bash 初始化不写日志，一片空白
口我们知道 Agent调了bash-l。但bash 起来之后容器里发生了什么？
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 005

•
容器里实际发生了什么
最终 exec进去逐一排查，根因其实很简单—
一沙箱镜像的.bashrc 配了大量初始化脚本，每次 bash-I要跑将近91秒。
bash -I （PID 4521, total： ~91s）
/opt/conda/bin/conda shell.posix activate base ~58s
-/opt/conda/bin/python （import site-packages） ~55s 镜像层 1/O 阻塞
（大量 pyc / metadata 文件按需加载）
nvm use default
~12S
-nvm_resolve_alias default
~1.2s
nvm_Is v18.20.0
~3.5s 目录遍历触发1/0
nvm_change_path + rehash
~7s
eval “$（pyenv init-）”
~9s
pyenv init --path
~2s
pyenv rehash（shims 重建）
~7s
个 /opt/pyenv/shims/扫描
source bash-completion
~8S
source kubecti-completion
~3S
- （bash ready）
~0.1s
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 006

Agent 观测新挑战
为什么 Agent 需要一种全新的可观测方案
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 007

•
Al Agent 的执行模式
应用层
*LLM推理驱动指令解析
平台层
Tool Call：选择工具并传参
核层
•沙箱执行并返回最终结果
传统微服务
Al Agent
确定性：相同输入 -＞相同路径
非确定性：同 Prompt ->不同 Tool Call
静态路径：调用链在代码中静态定义
动态路径：LLM 实时决定调哪个工具、传什么参数
日志审计：审计调用日志即可
决策审计：需回溯"为什么 Agent 认为该执行这条命令"
口 Agent 的执行链路跨越三个技术域，行为不可预测、路径动态、决策需审计一这与传统微服务的可观测性需求有本质区别。
Qcon
InfoO极客传媒
全球软件开发大会

## Page 008

• 现有可观测体系的盲区
盲区① 网络安全（CNI/ Firewall）
］
能看到：IP 到IP 的连接
看不到：Agent传输的 Prompt 语义、MCP 协议中的工具调用参数
盲区②审计日志（K8s Audit）
2
能看到：控制平面的"意图”——谁请求了 Exec
看不到：数据平面的"实况"——容器内部实际执行了什么命令
盲区③应用性能监控（APM）
3
能看到：HTTP 延迟与错误率
看不到：Agent 思维链（CoT） 与实际副作用（Side Effects）的关联
口 Agent 的决策逻辑（LLM） 执行行为 （Tool）-运行结果（Sandbox）的完整因果链采集需要新方案。
acon
InfoO 极客传媒
全球软件开发大会

## Page 009

Agent 执行链路的四层上下文断裂
1
LLM 推理层（OpenAI, Claude⋯）
Agent 编排层 （LangChain, AutoGen•）
2
断裂①：HTTPS/TLS加密，Trace Context 缺失，Prompt 内容不可见
平台调度层（kubectl exec / execd / CRl exec）
3
断裂②：ExecRequest 不携带 user / source / trace 身份信息
4
沙箱运行时层（容器内进程）
口 核心问题—怎么把四层断裂的上下文串起来？
QCon
InfoO极客传媒
全球软件开发大会

## Page 010

•
• 我们需要什么—从盲区倒推需求
现有盲区
需要补齐的能力
TLS加密导致LLM 流量黑盒
穿透 TLS— 不改代码的前提下看到 Prompt/Token
容器隔离导致运行时不可见
穿透容器 —看到沙箱内每个进程的命令、输出、退出码
各层数据互相独立无法串联
跨层关联一 把 LLM 对话和内核进程事件绑定到同一链路
工具调用通过Stdio/MCP 走进程管道
Stdio 感知一捕获进程间管道通信（覆盖 MCP stdio 场景）
Agent 自身不知道命令是否真正成功
执行反馈—Agent 能查询退出码/stderr/资源消耗，自主判断和排查
现实中 Agent运行环境和类型千差万别：有SDK 集成的 Agent、无 SDK 的自研 Agent、平台托管 Agent、Coding Agent
环境有：容器沙箱、虚拟机沙箱、MCP场景等
我们需要一个不依赖业务代码、不绑定特定框架、能穿透容器和 TLS 的底层采集方案，和现有的 SDK/平台方案形成互补。
acon
InfoQ极客传媒
全球软件开发大会

## Page 011

•
现有 Agent 可观测方案全景
方案A:SDK 侵入式
方案 B：平台侧采集
方案 C:Proxy 代理式
代表：LangSmith、LangFuse
代表：百炼、Dify、Coze
代表：LiteLLM Proxy、Portkey
优势：零额外接入成本，编排拓扑完
优势：语义信息最丰富：完整
整
优势：框架无关，接入简单
Prompt、 Token、Chain-of-
局限：平台锁定，运行时层依然是
局限：只能看 Agrnt 到大模型 链
Thought
黑盒
路，工具调用和沙箱执行完全看不见
局限：框架绑定、需改代码、运行时
层完全无感
缺失的能力：运行时层＋跨层关联—没有任何现有方案能回答：容器里实际执行了什么进程？每个进程的
stdout/stderr 是什么？这些进程和上层LLM 对话有什么关系？
QCon
InfoO极客传媒
全球软件开发大会

## Page 012

•
为什么是 eBPF— 与现有方案共存
思路
做法
判断
给SDK 加运行时采集
在 LangSmith/LangFuse 里集成进程监控 依赖框架集成，覆盖不了无 SDK 的 Agent；看不到
容器内子进程
给 APM加 Agent 语义 Datadog/Jaeger 增加 LLM trace
TLS 加密后仍是黑盒；不理解 MCP/Stdio 语义
Sidecar 容器
每 Pod 注入采集容器
资源开销随 Pod 数线性增长；需 admission
webhook 改 Pod spec
eBPFV
DaemonSet 部署，内核级采集
零侵入＋性能可控＋穿透 TLS+穿透容器
运行时层可见性
跨层关联能力
执行反馈闭环
穿透容器隔离，看到沙箱内每个进程的命
把运行时进程事件与LLM对话、K8s审
Agent 通过API 查询退出码、stderr、资
令行、stdout/stderr、退出码
计日志串联，填补上文提到的层级断裂
源消耗，自主判断执行效果
最佳实践：SDK 做上层语义增强，eBPF 做底层运行时采集。两者互补，不是替代。
QCon
InfoO极客传媒
全球软件开发大会

## Page 013

12
深度行沩感知
如何构建 Agent 执行的“全息画像”
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 014

整体架构图
Edge Collector
Hub Server
K8s 审计日志
eBPF 内核态
分析引擎
进程探针
Stdio 探针
五层关联引擎
执行生命周期
LLM 处理
TLS 解密
网络探针
资产+IAM
风险评分
Trace 管理
Redis
Kafka
异步写入缓冲•Batch Flush• Session 预聚合
Perf Ring Buffer
ClickHouse
对外接口
RL 信号
用户态处理
rl_sessions
协议解析
K8s富化
Prometheus
Query API
Outcome
Efficiency
rl_exec_records
进程树
Trace 注入
WebSocket
OTLP
Fidelity
Safety
rl exec stdio
QCon
InfoO极客传媒
全球软件开发大会

## Page 015

•
Agent 链路全景— 四条通信链路的传感器布局
链路
场景
采集点
获取的数据
A2L
Agent - LLM API
uprobe TLS 解密+HTTP 解析
Prompt、Token、模型名、TTFT、延
迟
A2T
Agent >沙箱执行
tracepoint（进程）+ kprobe（stdio）
命令行、退出码、stdout/stderr、
CPU/RSS
A2A
Agent - Agent
socket filter + Trace Context
调用关系、延迟
MCP
Agent MCP
kprobe vfs_write + JSON-RPC 解析
method、工具名、参数、结果
Tool （stdio pipe）
口 四条链路、三种探针类型（tracepoint / kprobe / uprobe），覆盖 Agent 的全部外部交互。
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 016

eBPF 采集点全景图
Agent 交互协议
A2L
A2T 命令
A2T 网络
MCP Stdio
A2A
Agent LLM
Agent Sandbox
Agent -Tool
Agent t MCP Server
复用网络探针
Prompt•Response:Token
exec:fork，exit stdio
HTTP•gRPC• SQL
JSON-RPC over Pipe
识别 traceparent
•内核态•eBPF 探针
TLS 透明解密
进程全生命周期
网络协议识别
管道 1O 监控
uprobe
tracepoint
socket filter
kprobe
SSL_write / SSL_read
sys_enter/exit_execve
网络报文过滤
vfs read /vfs_write
OpenSSL/BoringSSL
命令•参数•返回码
HTTP•gRPC•SQL自动识别
Pipe FD 过 一>字节流
uprobe
tracepoint
kprobe
JSON-RPC tools/call
Go crypto/tls Write/Read
sched_process_fork
tcp_connect / accept
扫描 RET 指令偏移
父子关系—进程树
连接五元组•目标发现
* 流量不经网卡
eBPF 是唯一捕获途径
明文 HTTP Payload
kprobe
URL•Method•SQL
do_exit
退出码•CPU•RSS
tracepoint
sys_enter write （fd=1/2）
stdout /stderr 捕获
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 017

• 进程生命周期— 三个 Tracepoint
—
2
sched_process_exec
sched_process_fork
sched_process_exit
PID, PPID，命令行（comm+args），可执
父子 PID 关系
退出码，CPU 时间，RSS，页面错误
行文件路径，工作目录
不管 Agent 通过 kubectl exec、execd 还是 CRI调用进入沙箱，tracepoint都能捕获。回到开始的问题，如果有进程树，一目了然：
bash -I （PID 4521,exit=0， ~91s）
- /etc/profile.d/conda.sh （PID 1235, exit=0，~1.2s）
/opt/conda/bin/conda shell. posix activate base （PID 1236, exit=0， ~58s） 根因
— /opt/conda/bin/python （PID 1237,exit=0，~55s）
镜像层1/O 阻塞
nvm.sn （sourced）
nvm use default （PID 1238, exit=0，~12s）
— nvm_Is v18.20.0 （PID 1239,exit=0，~3.5s）
＜ 目录遍历1/0
pyenv init- （PID 1240,exit=0，~9s）
一 pyenv rehash（PID 1241, exit=0， ~7s）
个 shims 扫描1/0
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 018

•
Stdio 捕获与 MCP 协议解析
命令行 Stdio 采集
MCP Stdio 协议解析
kprobe 挂载 vfs_write / vfs_writev， 过滤 fd=1（stdout）/
MCP stdio 传输模式：Agent 和 Tool（子进程）通过
fd=2（stderr）
stdin/stdout 管道通信，传输 JSON-RPC 2.0消息。
Agent 调用：Agent 任务：“迁移前备份数据库”
kprobe vfs_write 捕获
Agent 汇报：
"Database backed up to
- MCPParser 解析
$3://backups/db.sql.gz"
提取：
method=tools/call
我们采集到的 stderr：
tool_name=read_ file
arguments=｛path：".."7
Step 1: pg_dump production | gzip > /tmp/db.sql.gz
stderr: FATAL: password authentication failed
exit code: 2
＜ dump 失败，gzip 输出 0字节
采集链路：
① eBPF kprobe 捕获 stdout pipe 写入
Step 2: aws s3 cp /tmp/db.sql.gz s3://backups/
stdout:upload： ..db.sql.gz-s3://backups/db.sql.gz
内核态 detect_jsonrpc（） 快速识别
exit code:O
＜ Agent 只看到这个
③ 用户态 MCPParser 解析
实际：备份文件 0字节，迁移后无法回滚
method/tool_name/arguments/result
QCon
InfoO极客传媒
全球软件开发大会

## Page 019

•
TLS 解密 —Agent 到 LLM 链路怎么打通
Agent - LLM 全走 HTTPS。不解密，就看不到 Prompt、Token、模型名。
uprobe 挂载
解析＆ 识别
Agent 进程
HTTP 解析
OpenSSL / BoringSSL
OpenSSL uprobe
汇聚
请求/响应/ Streaming
进程
SSL_write /SSL_read
模型/Token /TTFT
Python / Node / cURL 等
明文截取
完整 A2L 可观测数据
加密前/解密后拿到原始数据
LLM API 识别
17 个提供商 URL 匹配
Go crypto/tls 进程
Go TLS uprobe
Go Agent / MCP Server
tls.Conn.Write / Read
加密库
状态
备注
OpenSSL/BoringSSL
支持
覆盖 Python/Node/curl 等大部分场景
Go crypto/tls
支持
goroutine 栈迁移、Register ABl、itable 变更
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 020

• Agent 场景下的内核态设计
能力 1：Agent 进程发现
进程树遍历
三模式 PID Filter（解决冷启动）
exec 事件
is_descendant_of_monitored（）
DISABLED
BOOTSTRAP
ENABLED
sched_process_exec 触发
向上遍历进程树（最深8层）
全量采集
进程放行，1O 过滤
严格过滤
匹配容器祖先
Bootstrap 模式：启动阶段放行所有 exec事件
标记为 Agent 进程
runc/ containerd-shim
仅过滤IO 事件，确保不遗漏新进程
能力2：内核态流量分类
13 种协议推断链
HTTP
HTTP2
gRPC
」， websocket
SSE
JSONRPC Y MCP
流量自动分类为5种 Agent 通信类型
A2L
A2T
A2A
MCP
INTERNAL
Agent -LLM
Agent 一Tool
Agent -Agent
MCP 协议
内部通信
acon
InfoQ 极客传媒
全球软件开发大会

## Page 021

Agent 资产发现与行为风险
Agent 特有风险检测
资产自动发现
Reward Hacking
總酵雲理裂产酱需理声明。从网络流通中自动盘点 Agent生
Agent 报告成功，但实际未完成一内核证据vs Agent声明
权限越权
Agent
Tool
实际访问超出 RBAC 声明范围 >行为vS 声明偏移检测
频繁调用 LLM端点的工
Agent 调用的下游服务：
作负载，按
T-Infra /T-Data/F-
Namespace/Label/
SaaS
无限重试
ServiceAccount 聚合
进程树显示相同命令循环执行 ->fork 链模式识别
资源滥用
RSS/CPU 持续增长无收敛 —》进程级资源追踪
LLM Source
传统安全工具检测syscall 异常，但缺少 Agent请
DNS/SNI + API路径+响应特征：M-Public / M-Private
一不知道
“这个 curl 是 Agent 的正常工具调用
还是数据外泄”。eBPF + Agent 意图识别解决这个
问题。
acon
InfoO极客传媒
全球软件开发大会

## Page 022

后端 Agent 语义处理
能力1 | Trace关联
PodName
数据处理
TracelD
确定性，零存储，无 Redis
my-agent-a3t8b2c1...
UUID 一确定性映射
能力2| LLM流量聚合
SSE chunk
StreamAggregator
SSE chunk
完整 Response
OpenAl: data： ［DONE］
IImBodyScore（）匹配 Req Resp
Token 统计 +TTFT
多 Provider 完成检测
Anthropic: message_stop
SSE chunk
能力3 | Session 预聚合
90K events/s
內存 Map 折叠
3K writes/s
30x 压缩
3000 sessions x 30 evt/s
按 session_id 聚合 upsert
•（sessions） flush
O（events）- O（sessions）
QCon
InfoO 极客传媒
全球软件开发大会

## Page 023

）2
全链路追踪
构建从 LLM 对话到内核 Syscall 的完整视图
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 024

• 断裂问题 — 五条数据流，零条关联线
我们已经有五层采集能力：LLM流量、Agent 资产、K8s 审计、运行时事件、进程链。但现在它们是五条独立的数据流。
1
2
3
L1 LLM 层
L2 Agent 层
L3 沙箱平台层
"我知道有一个 GPT-4 请求"
"我知道这个 Pod 是 Agent"
"审计日志发现执行了沙箱命令"
4
5
L4 运行时层
L5 进程链层
"'eBPF 捕获到一个 bash 进程"
"这个 PID 有三个子进程"
LLM 到 Agent
Agent 到沙箱
进程链断裂
Agent 框架不注入 W3C traceparent，
CRI 不透传身份信息，审计日志和 eBPF
进程 fork 后缺少 trace 继承机制，子进程
LLM 请求无法溯源到具体 Agent
事件互不相识
变成孤儿事件
QCon
InfoO 极客传媒
全球软件开发大会

## Page 025

•
LLM 层—Agent 关联— 节点级透明 Trace 注入
问题：绝大多数 Agent框架不注入W3C traceparent， LLM 请求到达 API时没有调用者标识。
Edge Collector （DaemonSet）
① LLM 请求
② 携带 traceparent
（无 traceparent）
① eBPF sockops 拦截出站TCP
Agent Pod
LLM API
② 透明代理识别源 Pod
Go / Python / Node.js
③ 注入 traceparent
语言无关
无 Sidecar
幂等安全
性能影响小
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 026

• 沙箱平台层 一运行时关联：沙箱入口 ×运行时事件
Kubectl exec
execd
CRl exec
有 Audit Log
gRPC/ HTTP
无审计日志
eBPF tracepoint 统一捕获
--时空关联算法---一----
滑动窗口缓冲区
Audit Log 到达
Pending Session
Redis 时间桶索引
eBPF 事件到达
eBPF 先到 一>缓冲等待
Audit 先到一桶内等待
K8S API Server
Audit
eXeC
Kafka消费
一水印线：过期数据自动清理
窗口 +30s
时间 +30s
三元组
命令分级匹配
匹配
P PodUID
QCon
关联成功一继承至整棵子进程树
InfoQ 极客传媒
全球软件开发大会

## Page 027

• 运行时-，进程链层关联：进程树构建与 Trace继承
每个进程节点采集的信息
进程树（trace:abc-123 全树继承）
阶段
采集内容
bash -c "run.sh" / PID 1001
exec（启动）
命令行 argv、可执行文件路
］
根节点，fork+exec 派生子进程
径、启动时间
运行中
stdout/stderr、CPU time、
python train.py / PID 1002
RSS peak
2
子节点 - pip install numpy / PID 1003
exit（退出）
退出码、信号、执行时长、资源
消耗汇总
curl callback / PID 1004
3
一次沙箱执行触发的整棵进程树，从根到叶都在同一个
并行子节点，同一trace 上下文
trace 下。
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 028

•
完整 Span树
- Coding Agent 修复单测
trace: f7a2c1d8•5层•13 Span•9.4s
0s
3s
6s
12S
LLM Request
1.8s
Claude Sonnet•3400 tokens • TTFT 220ms
L2
coding-agent
sandbox-prod•SA: agent-sa
L3
Kubectl exec
audit_id:aud-3亿7•审计关联/
L4
bash -c "fix_and_test.sh"
9.4s
PID 5012 exit 0•9.4s
L5 子进程链
① cat src/utils.py
exit 0•0.2s
grep -rn "def calculate" tests/
exit 0•0.3s
git diff HEAD~1 src/utils.py
exit 0•0.4s
sed -i's/x *y/x + y/' src/utils.py
exit 0-0.1s
python -m pytest tests/ -v
exit 1•3.8s•FAILED
FAIL3 8S
stderr - Query API 调整策略
0 Agent 读 stderr 一自我纠错
exit 0•0.1s
cat tests/test_utils.py
exit 0•0.1s
sed -i's/== 15/== 8/"test_utils.py
8
python -m pytest tests/ -v
exit 0•3.6s•5 passed
PASS 3.6S
git commit -m "fix: correct calculate"
exit 0-0.8s
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 029

落地与应用
标准化输出与业务赋能
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 030

• 可观测指标体系 — 四大类结构化指标
原始事件经过关联和聚合后，沉淀为四大类结构化指标，覆盖 Agent全生命周期。所有指标通过标准 Prometheus / Metrics
端点暴露，支持 ServiceMonitor 自动发现。
LLM 交互指标
执行层指标
• 请求量与错误率（按模型/Provider）
事件量（exec/fork/exit 总数）
• Token 消耗分布（prompt/completion）
执行时长与退出码分布
• 延迟分布（端到端＋TTFT）
• 沙箱执行入口检测分类
•传完成/已完感/超时计数
• 吞吐量（RPM/TPM 滑动窗口）
• 完整的 trace 信息
eBPF 健康指标
关联与处理指标
• eBPF 程序运行次数与耗时
• 事件处理量与处理耗时
CPU 占用百分比
•审计-执行关联成功率/失败率
• 已加载程序/Map 数量
• Session/Trace 去重计数
•JIT 编译大小与 Map 内存
• 消息队列消费延迟与错误率
Qcon
InfoQ 极客传媒
全球软件开发大会

## Page 031

• 查询 API— 从 audit_id 到完整执行档案
把五层关联后的数据，通过一个统一的查询 API 暴露出来。输入一个标识符，返回完整的、跨层关联后的执行档案。
By batch_id
By trace_id
By session
评测效果对比：成功/失败分布、退
链路追踪：从 LLM 请求追踪到沙箱
会话回放：查看一个 Agent 会话的全
出码统计、资源消耗汇总
执行。返回 LLM Span + Agent 资
部行为。返回时间排序的完整事件流
产＋所有 exec 事件
API 调用示例
存储架构（ClickHouse）
POST /api/vl/rl/query
rl_sessions
-会话元数据（audit_id +K8s身份）
"method"："get_trace_by_audit_id"，
rl_exec_records
"'params"：｛
执行记录（命令/退出码/时长）
"'audit_id"："2b4a9d2b-8c1f-.."
rl_exec_stdio
Stdio内容（TTL自动过期）
｝
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 032

•多实例架构— 分布式状态管理
Hub 需要水平扩展，但关联引擎依赖有状态上下文。怎么在多实例间保持一致？
共享层（跨实例一致）
本地层（实例内缓存）
写入层（异步批量）
RedisTrace ID 缓存（TTL24h）、
进程生命周期追踪器（64 分片锁，纯
Channel 缓冲 + 多 Worker /
Rendezvous 会合点（TTL
内存）、SSE 流式聚合器（按连接分
Session 预聚合
2min）、Exec 去重计数器、跨实例
桶）、事件环形缓冲区/TTL 去重集
背压策略：满载时非阻塞丢弃＋计数
Pub/Sub
合
器追踪
2
共享层：Redis 优先，内存
本地层：亲和性路由消除分
3
写入层：异步批量＋背压保
回退
布式协调
护
Redis 不可用时自动降级为进程内
Kafka partition key =
满载丢弃，确保采集链路不被下游
存—功能不中断，跨实例一致性
hash（PodUID:PID），，同一进程所有
存储拖慢
变为 best-effort
事件落在同— Hub 实例
QCon
InfoO极客传媒
全球软件开发大会

## Page 033

• 观测闭环 — 从观测数据到 Agent能力评估
Outcome
退出码/stderr
人：离线评估
Efficiency
CPU/时长/ RSS
Reward /Batch 对比/ 归因
eBPF 内核采集
+ Query API
Fidelity
声明vs实际执行
Agent： 实时反馈
Safety
权限偏移/敏感操作
查退出码一>自主重试
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 034

Agent 性能评估与选代—观测数据的工程落地
场景 1：
场景2：评测间对比
场景 3:Agent 自
场景 4:Reward
benchmark归因
主消费
信号
从只有结果到具体原因
版本回归定位
实时执行反馈
多维量化评估
将 pass/fail 拆解为进程
跨批次对比成功率与执行
Agent 直接查询执行结
将 Outcome、
级失败分类，区分环境、
时长，借助 Exec Trace
果，自主判断失败原因并
Efficiency、Fidelity、
策略与资源问题，让评估
定位性能劣化根因。
调整策略，形成闭环自我
Safety 合成统一
结果真正可操作。
修正能力。
Reward， 驱动 RL 训练
与行为优化。
QCon
InfoO 极客传媒
全球软件开发大会

## Page 035

05
总结与展望
Qcon
InfoQ 极客传媒
全球软件开发大会

## Page 036

• 边界
eBPF 看不到 Agent 框架内部的决策
VM沙箱暂无完美的零侵入方案
逻辑
Firecracker/Kata 等 VM 沙箱场景仍有覆盖盲区，
Chain-of-Thought 推理过程对内核层不可见
需要单独部署
TLS 库版本追踪需要持续投入
SSE 流式重组在极端并发下可能丢
chunk
OpenSSL/BoringSSL/Go 版本差异需要持续
维护
高并发场景下流式数据完整性存在丢失可能
口最佳实践：分层组合—eBPF 做底层安全网+SDK 做上层语义增强。两者互补，而非替代。
acon
InfoQ极客传媒
全球软件开发大会

## Page 037

• 结论
观测数据的价值不只是
Agent 生态迭代太
“人看见”
Agent 可观测的核心
快，无侵入方案一次建
实时闭环：Agent 查退出码
问题是跨层关联，不是
设、持续覆盖
/stderr，自主调整策略。
单层采集
百花齐放的 Agent 生态下的
长期闭环：内核级证据生成
APM、K8s 监控、安全工具
较优解。无侵入方案是唯一
Reward 信号，训练出更强
各有专长，但跨层串联需要
能让可观测能力"一次建设、
的下一代 Agent。观测
新方案。
持续覆盖"的架构选择
量化一反馈—进化。
acon
InfoO极客传媒
全球软件开发大会

## Page 038

InfoQ 极客传媒
QCon
全球软件开发大会
THANKS
大模型正在重新定义软件
Large Language Model Is Redefining The
Software

## Page 039

上
探索 AI 应用边界
AiCon
Explore the limits of Al applications
站
全球人工智能开发与应用大会
2026年6月26-27日/上海张江科学会堂
专题：世界模型与多模态智能突破
专题：Agent 系统架构与工程化实践
专题出品人：朱政
专题出品人：鲁洁楠
极佳视界/联合创始人 &首席科学家
OPPO /大模型算法员责人
专题：AI 原生数据工程
专题：Agent 安全、评测与可信治理
专题出品人：王彦辉
专题出品人：马传雷（岳立）
火山引擎 /数智平台产品总
支付宝 /业务风险技术部员责人
专题：Agent 数据、记忆与运行时
专题：企业级研发体系的重构
基础设施
专题出品人：沈浪
专题出品人：邓亚峰
快手/研发效能员责人
EverMind / CEO
