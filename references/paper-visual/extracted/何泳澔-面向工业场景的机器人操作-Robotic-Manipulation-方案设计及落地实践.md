# 面向工业场景的机器人操作（Robotic Manipulation）方案设计及落地实践

- Source PDF: `references/papers/何泳澔-面向工业场景的机器人操作（Robotic Manipulation）方案设计及落地实践.pdf`
- Visual pages: `references/paper-visual/images/何泳澔-面向工业场景的机器人操作-Robotic-Manipulation-方案设计及落地实践/`
- Extraction mode: visual page-by-page information extraction
- Page count: 44

## Page 001

地瓜机器人
InfoQ 极客传媒
QCon
全球软件开发大会
泛工业场景中机器人操作方案设计与落地
Design and Implementation of Robotic Manipulation Solutions in
General Industrial Scenarios
何泳澔 博士
地瓜机器人-具身智能负责人

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

具身的战略聚焦
具身智能的两大应用场景
1
具身智能技术的应用场景主要可以划分为两大领域：一是面向日常生活的服务场景，如家庭服务、
医疗护理等（To C）；二是面向生产制造的泛工业场景，涵盖仓储物流、装配智造等（To B）
首要任务：解放泛工业场景生产力
2
在我们看来，具身智能技术当前最核心、最紧迫的任务，是聚焦并解放泛工业场景中被束缚的生
产力。这是目前具身智能的当务之急，应对未来的人口老龄化危机，更是核心价值的重要体现
坚定的战略选择
3
坚定地瞄准泛工业场景，解放生产力。我们致力于构建一套从硬件选型、算法优化到数据采集
的完整解决方案，以应对泛工业场景的复杂性和多样性。
QCon
地瓜机器人
InfoQ 极客传媒
全球软件开发大会

## Page 004

地瓜机器人
InfoQ 极客传媒
QCon
全球软件开发大会
01
问题定义
02
硬件方案
目录
03
算法方案
04
数采方案

## Page 005

问题定义
更加深刻理解场景和任务
QCon
地瓜机器人
InfoQ 极客传媒
全球软件开发大会

## Page 006

泛工业场景介绍
泛工业场景并非完全的无结构环境，其布
许多泛工业场景，如铸造车间、矿山、化
泛工业场景中大量存在着搬运、装卸、装
局和任务流程往往具有一定的规律性和重
工环境等，普遍存在高温、高湿、高噪
配等重体力劳动，这些工作不仅效率低
复性，存在一定的动态变化和不确定性。
音、粉尘、有毒气体等恶劣条件。这些环
下，而且容易导致工人受伤。引入机器人
这种“半结构化”的特性使得我们可以相
境对人类工人的身心健康构成威胁，而机
可以有效替代人类完成这些繁重的体力工
器人则可以在这些环境中稳定、持续地工
作，将工人从重复性的体力劳动中解放出
对容易切入和进行方案设计。
作。
来。
半结构化，复杂度可控
声/光/气污染，条件恶劣
重体力劳动
QCon
地瓜机器人
InfoQ 极客传媒
全球软件开发大会

## Page 007

• 泛工业场景中的任务分类
操作任务的精度要求
任务感知复杂度
2
3
厘米级，毫米级，亚毫米级
视觉，力觉，触觉
1
4
操作对象的物理可预测性
任务执行效率要求
刚体，铰接刚体，柔体，软体，流
分钟级，秒级，毫秒级
体等
维度划分
QCon
地瓜机器人
InfoQ 极客传媒
全球软件开发大会

## Page 008

典型任务—物流仓储中的箱体码垛与搬运
J
物理可预测性
感知复杂度
刚体，形状相对固定
视觉为主，无需力、触
觉
精度要求
执行效率
厘米级，容错误差大
秒级为主，吞吐量适中
QCon
地瓜机器人
InfoQ 极客传媒
全球软件开发大会

## Page 009

典型任务-
零部件装配与螺丝拧紧
J
物理可预测性
感知复杂度
刚体，或者铰接刚体
视觉与力觉
精度要求
执行效率
毫米级
秒级到分钟级
QCon
地瓜机器人
InfoQ 极客传媒
全球软件开发大会

## Page 010

典型任务—
-精密装配与线缆插接
J
物理可预测性
感知复杂度
刚体，但是元件小
视觉，力觉和触觉
精度要求
执行效率
亚毫米级
秒级，如果是流水线，
可能要求吞吐量较高
QCon
地瓜机器人
InfoQ 极客传媒
全球软件开发大会

## Page 011

• 具身智能方案 vS 工业自动化
更好的场景适应性
更优的成本边际效应
• 对结构化的依赖降低
• 标准硬件本体结构
• 跨任务的泛化能力
• 软件定义
•动态异常处理和自主纠错
•RaaS （Robot as a Service）
为什么更需要具身智能方案
ROI
QCon
地瓜机器人
InfoQ 极客传媒
全球软件开发大会

## Page 012

任务难度分级框架
5
四个维度所有要求全覆盖
4
高节拍操作
秒级和毫秒级TT，动态物体
3
自适应高精度操作
柔性/高精度/多模态占两项以上
2
感知增强操作
引入力觉和触觉
视觉引导操作
刚性对象+粗定位＋单一感知
QCon
地瓜机器人 InfoQ 极客传媒
全球软件开发大会

## Page 013

• 当前关注的任务类型
操作精度覆盖厘米级
操作物体为刚体类
到毫米级
本方案关注的
任务类型
感知能力覆盖视觉与
操作效率覆盖分钟级
力觉，触觉待定
和秒级
QCon
地瓜机器人 InfoQ 极客传媒
全球软件开发大会

## Page 014

02
硬件选型
各种硬件本体与场景的适应性
QCon
地瓜机器人
InfoQ 枚客传媒
全球软件开发大会

## Page 015

硬件本体
移动底盘
轮式
足式
轮足
履带式
速度
快
慢
快
中等
越障
低
高
高
中等
效能
高
低
中等
中等
控制难度
低
高
高
中等
室内物流/送餐/巡检
复杂地形/抢险
典型场景
户外探索/军事/农业
QCon
地瓜机器人
InfoQ 极客传媒
全球软件开发大会

## Page 016

•
硬件本体
一上半身（躯干）
外部垂直导轨
集成伸缩柱
折叠式
机械刚性
高
运动灵活
低
环境密封
差
中
空间占用
大
变动
QCon
地瓜机器人
InfoQ 极客传媒
全球软件开发大会

## Page 017

•硬件本体——上半身（臂）
工业协作臂
仿生机械臂
核心特点
追求安全和高协作性
追求仿生结构，自由灵活
性能优势
运动稳定丝滑，重复精度高
柔顺，更易遥操
局限性
可达空间受限，体积和重量较大
控制相对复杂，承重较弱，稳定性可能欠佳
aCon
地瓜机器人
InfoQ 极客传媒
全球软件开发大会

## Page 018

硬件本体-
一上半身（末端执行器）
2指（夹爪）
3指
4指
5指（仿生灵巧手）
核心特点
平行或角度开合
三点围合，常呈120°布局
冗余设计，多为2对2或3+1布局
仿生人手结构
结构最简单、成本低
具备自对中能力，抓取球形
接触面积大，对大型，柔软物体
灵巧度最高，完全适配人类
性能优势
可靠性极高、控制逻辑成熟
物体极其稳定，性价比高
的压力分布更均匀，稳定性极佳
设计的工具，具有极强的普适性
灵巧度极低，难以处理球形
复杂度高于2指，
结构最复杂、驱动电机
处于3指与5指的中间态
局限性
或不规则物体，
在狭窄空间内的适应性略逊
数量多、成本最高、
商业化成熟度略低于工业级3指
无法实现"手内操作”
于精细灵巧手低
算法控制难度极大
典型应用
工业搬运/结构化零件抓取
高实验室研究/圆筒类容器抓取
柔软包装、大型易碎品搬运
高端人形机器人/精细服务场景
目前，执行末端集成了最丰富的多模态感知能力：视觉，力觉，触觉
QCon
地瓜机器人
InfoQ 极客传媒
全球软件开发大会

## Page 019

硬件本体
传感器
双目深度相机
结构光深度相机
iToF深度相机
面阵dToF相机
激光雷达LiDAR
红外 结梅光
测距原理
双目视觉（被动三角法）
结构光（编码图案+三角法）
iToF（间接飞行时间 测相位）dToF（直接飞行时间•测脉冲）
dToF + 扫描机构
室内适配性
中
高
高
高
高
室外适配性
高
极低
低
中
极高（抗雨雾/强光）
测距范围
0.3~20m
0.05~5m
0.1~10m
0.3~20m
0.5~200m+
成本等级
低
中
中低
中
高
适用场景室外机器人/自动驾驶视觉，工业精密检测/机械臂抓取
体感交互/扫地机器人
室内建模/近距机器人避障
自动驾驶/工业测绘
QCon
地瓜机器人
InfoQ 极客传媒
全球软件开发大会

## Page 020

02
算法方案
高潜的方案路径
QCon
地瓜机器人
InfoQ 极客传媒
全球软件开发大会

## Page 021

• 为什么VA比VLA更适配泛工业场景
VLA（Vision-Language-Action Model） vs VA（Vision-Action Mode
• 语言模态的价值在泛工业场景的价值几乎没有。相对标准化的流程，可拆分，任务执
行推进完全无需语言，程序化流程即可。语言的最核心的价值在于提供人机交互的媒
介，更适合通用场景。
• 语言模态的加入，势必引入Language Encoder或者完整的VLM （Vision-
Language Models），会使得模型变得庞大，导致推理效率很低。
• 在引入VLM的前提下，需要训练的数据量也会增多，可能还需要大规模的预训练。
当前的数据形式对于语言的利用也是极其低效的。
• VLA更像是一个纯学术研究方向，应该以探索人机交互的有效性为重点
• VA更多是直面控制问题，解决在观测引导下的合理轨迹动作生成
我们要以目标为导向去构建方案，不需要提前“站队”属于哪个路线，现在不存在一条清晰
的路径
QCon
地瓜机器人 InfoQ 极客传媒
全球软件开发大会

## Page 022

高潜的VA模型技术路线
阶段4
感知模态：
阶段3
视觉（多目第三视角，腕部视角
等等）
力觉（关节力矩，腕部六维力）
感知模态：
触觉（未端执行器指端）
阶段2
视觉（多目第三视角，腕部视角
等等）
时序：
阶段1
力觉（关节力矩，腕部六维力）
感知模态；
Transformer Fuser with KV
触觉（未端执行器指端）
cache
视觉（多目第三视角，腕部视角等
感知模态：
等）
时序：
视觉（单目第三视角）
动作预测：
单帧静态
DiT+FlowMatching
时序：
时序：
单帧静态
动作预测：
单帧静态
DiT +FlowMatching
动作预测：
DiT+FlowMatching
动作预测：
CNN +DDPM
世界模型：一种自监督（即预测未来状态）的多模态表示学习框架
主要价值在于预训练阶段，让多模态特征能够在隐空间中进行对齐
QCon
地瓜机器人
InfoQ 极客传媒
全球软件开发大会

## Page 023

高潜的VA模型技术路线
阶段1
VO-DP （Vision-Only Diffusion Policy）
单目VA方案
纯视觉方案性能超过RGB-D方案\泛化性和鲁棒性超过当前的VLA
• 3D-Aware预训练可明显提升任务的成功率
Noise Action
VGGT Heads
Propr.
000
Inputs
Conditioning
Policy Head
Semantic-
Images
Spatial
VGGT Encoder
Geometric
Inputs
Fuser
Conpression
Predicted Action
VGGT Encoder
Semantic-Geometric Fuser
Spatial Compression
000000
CNN Residual Block
K/V
stride:2
stride:1
reshape
conv
conv
Alternating-
Avg.
DINO
O
3×3
3×3
Avg.
Attention
Pool
V2
Cross-
Network
1D
⑦
FFN
O
Pool
Attention
2D
ConV
1×1
stride:2
semantic-aware tokens
geometry-aware tokens
LX
QCon
地瓜机器人
InfoQ 极客传媒
全球软件开发大会

## Page 024

高潜力的VA模型技术路线
阶段1
VO-DP： 单目VA方案
Pick&Place
TABLE II: RoboTwin Benchmark Results. DP: Diffusion policy/9］， DP3:3D diffusion policy ［LI, VO-DP: T= 3, VO-DP-I：
T=1
Big Cube
Method
Block Hammer Beat
Block Handover
Botlle Adjust
Container Place
Empty Cup Place
DP
0.7+0.9
77.7‡4.5
39.3+0.5
14.0+6.9
69.3+2.5
DP3
79.3士1.2
97.7‡1.2
85.3‡0.5
83.7+1.7
88.7+1.7
Cover Cubes
VO-DP
85.0+1.4
89.7+0.5
63.3+12
43.0+3.7
82.0+2.2
TABLE V: Real-world Performance. In the four real-world
VO-DP-1
78.7+5.2
94.7 0.5
69.3+2.5
31.3+2.6
17.3+1.7
Method
Pick Apple Messy
Put Apple Cabinet
Dual Bottles Pick（Easy）
Dual Bottle Pick （Hard）
Diverse Bottles Pick
tasks, it can be observed that VO-DP significantly outper-
DP
31.0+0.8
63.6‡1.9
73.7+1.2
63.3+0.5
7.3+1.2
DP3
18.7+2.9
84.7+0.5
83.3+0.5
64.0+0.8
60.7+0.5
forms the other two methods.
VO-DP
80.00.8
94.3‡2.3
88.3‡0.9
67.3‡3.3
32.33.3
VO-DP-1
81.7+0.9
98.00.8
86.3+0.5
60.3+1.2
31.3+1.7
Method
PPSC
PPBC
CC
SC
AVG.（f）
Method
Shoe Place
Dual Shoes Place
Tool Adjust
Blocks Stack （Easy）
AVG.（）
DP
19.3+1.2
4.7+0.5
20.0+2.9
3.7+1.2
34.8
DP
23.3
16.7
3.3
1.7
11.2£9.1
DP3
56.3+1.7
13.7+1.7
58.3‡0.5
22.0+2.2
64.0
DP3
73.3
68.3
75.0
53.3
67.5‡8.5
VO-DP
43.0+0.8
17.0=0.8
58.3+3.9
52.3+2.5
63.9
VO-DP-1
520+0.8
1933+0.9
55.3+26
693‡2.5
04.6
VO-DP-1
96.7
91.7
93.3
70.0
87.9 10.5
真机实验
仿真实验
aCon
地瓜机器人
InfoQ 极客传媒
全球软件开发大会

## Page 025

高潜力的VA模型技术路线
阶段1
VO-DP： 单目VA方案
Stack Cubes
Cover Cuboid
Pick&Place
Pick&Place
Big Cube
Small Cube
VODP
TABLE VIL: Appearance Robustness. Train: n cubes; Test：
cubes.
AVG.
• upesd
85.0
50.0
40.0
90.0
66.3+21.6
DP
TABLE IX: Background Robustness. Train: desktop surface；
Test: desktop surtace， .
andm surtace.
DP3
desktop surface
AVG.
85.0
90.0
80.0
95.0
87.5+5.6
dxapsed
TABLE VI: Size Robustness. Train: 3.0 cm cubes; Test: 2.5
cm, 3.0 cm and 5 cm cubes.
Robustness test
Robustness test
Robustness test
Robustness test
3.0 cm
2.5 cm
5.0cm
AVG.
Zero-shot on
Zero-shot on
Zero-shot on
Zero-shot on
85.0
60.0
50.0.
65.0+14.7
blinking light
blue background
big cube
green cube
VODP
TABLE
VIL: Illummation Robustness.
Train：
Nommal，
Test:Nomal, Light Switch, Blinking.
Normal
Light Switch
Blinking
AVG.
85.0
80.0
85.0
83.3+2.4
Pi0.5
4z apesd
+xspced
4x speed
鲁棒性实验
QCon
D
地瓜机器人
InfoQ 极客传媒
全球软件开发大会

## Page 026

• 高潜力的VA模型技术路线
-阶段2
VO-DP+ （Vision-Only Diffusion Policy）
-多视角VA方案
• 从单一第三视角，提升为多视角，可以多个第三视角或者腕部视角；视觉编码器优化
使用 DiT+FlowMatching 的Policy Head，便于融合多视角特征
加噪动作
视角1
DiT 策略头 （Policy Head）
DiT Block（重复N次）
图像特征 Tokens
注意力
（Self-Attention）
00OO
共导图像
视角 2
编码器
DO00
作为眾件行人
交叉注总力
（CNN / ViT）
Cross-Attention
Shared Weights
全连接层
（MLP）
视角3
去噪动作
QCon
地瓜机器人
InfoQ 极客传媒
全球软件开发大会

## Page 027

•高潜力的VA模型技术路线
阶段2
VO-DP+ （Vision-Only Diffusion Policy）
多视角VA方案
Policy Head
Observation
Encoder
Param
Adjust Bottle（%）
Beat Block Hammer（%）
Click Alarmclock（%）
Click Bell（%）
single-view
VGGT
1B
99
88
55
79
DINOv3
Dil
840M.
99
94
72
92
（ViT-H+）
DINOv3
DiT
300M
99
94
59
87
CFM
（ViT-L）
multi-view
DINOV3
DiT
86M
99
96
68
100
（ViT-B）
DINOv3
CNN
198M
100
93
68
92
（CNN-L）
QCon
• 地瓜机器人 InfoQ 极客传媒
全球软件开发大会

## Page 028

• 高潜力的VA模型技术路线
阶段3
MMA （Multi-Modal Action Model）
多模态动作模型
• 多视角视觉感知
加噪动作
• 力觉和触觉
视角1
图像特征 Tokens
DiT 策略头（Policy Head）
@
0COO
共享图像
DiT Block（重复N次）
视角2
编码器
口000
（CNN / VIT）
口000
自注意力
（Self-Attention）
多模态交叉注意力
（Cross-Attention）
视角3
全连授层
（MLP）
力觉编码器
力觉 Tokens
力觉 （Force）
（MLP）
触觉编码器
触觉 Tokens
去噪动作
触觉（Tactile）
（CNN）
00口口
QCon
地瓜机器人
InfoQ 极客传媒
全球软件开发大会

## Page 029

• 高潜力的VA模型技术路线
阶段4
Context-aware MMA （Multi-Modal Action Model）
长上下文的多模态动作模型
• 多视角视觉感知
• 力觉和触觉
• 长上下文支持
加噪动作
视角 1
图像特征 Tokens
上下文 Transformer
DiT 策略头 （Policy Head）
口00D
（Context-aware / Causal）
共享图像
DiT Block（重复N次）
视角2
编码器
00O@
（CNN/ VI）
口U口图
自注 力
Masked Attention
（Self-Attention）
｛时序奄码）
上下文交叉注意力
@
KV Cache 积累
（Cross-Attention）
视角3
〈累积历史上下文）
全连接层
（MLP）
全连接层
（MLP）
上
力觉编码器
力觉 Tokens
力觉（Force）
（MLP）
上下文融合特征
（Updated Tokens）
#
触觉编码器
触觉 Tokens
去噪动作
触觉 （Tactile）
（CNN）
COCC
Q。
QCon
地瓜机器人
InfoQ 极客传媒
全球软件开发大会

## Page 030

高潜力的VA模型技术路线-
—世界模型的预训练
世界模型下的预训练框架
隐空间预测损失 （Predictive Loss）
模态 A
预测器
编码器A
（5p
（Projector）
留
编码器A
模态 A
（EMA）.
世界模型特征椎演
Z 1
模态 B
编码器 B
660
呵
：89
［sg
编码器B
模态 B
（5）
（EMA）
2+1
tt1
模态C
编码器C
品0
：品9+
sg
编码器 C
模态C
（5）
（EMA）
（Sta
t+1
隐空间联合约束
动作模态
DiT
预测动作
（a）
（下一动作预测）
QCon
• 地瓜机器人 InfoQ 极客传媒
全球软件开发大会

## Page 031

02
数采方案
多种数采方案的优劣和具体实现
QCon
地瓜机器人
InfoQ 枚客传媒
全球软件开发大会

## Page 032

操作数据的格式介绍
一图读懂操作数据格式，以单个Episode为例。
多模态数据定义
多模态数据帧率展示
语言与任务（Language）
描述：全局指令或单步任务语义
全局指令：“将红色的方块放入蓝色的碗中“
示例：”将红色的方块放入蓝色的碗中“
视觉轨（~10Hz）
视觉帧（Vision）
率：~10Hz-30H2（併颁基准）
Frame 1
Frame 2
Frame 3
Frame4
Frame 5
包含：多视角 RGB 图像流
动作轨（~50Hz）
动作与本体（Action）
|||
频率：~50Hz-500H2（中高频）
包含：关节角、速度、末端 6D•位姿
知轨（力
触觉（Tactile）
频率：～50Hz-100Hz（中频）
包含：夹爪指尖阵列或视触觉传感器数据
对齐策略（Alignment Strategy）
力觉（Force）
以最低频的视觉时间戳为基准，向高频流扒取最近邻数据（或酒值）
率：～1000Hz+（极高 连续流）
时间（Time）T=0-TEN
包含：F/T六维力矩传感羅反馈
aCon
地瓜机器人
InfoQ 极客传媒
全球软件开发大会

## Page 033

•当前主流的数采方案——遥操作（Teleoperation）
同构臂遥操
主臂与从臂在运动学结构上一致，通常采用关节级一一映射
进行遥操。
优势
• 高保真：无需复杂IK 映射，可直接采集与目标机器人一
致的关节轨迹。
• 力控友好：若支持力反馈，可提升接触任务的稳定性与可
操作性。
S NERTI
劣势
sharpa
I MiR| TERADYNE Robotics
• 通用性差：往往需针对目标机器人单独设计主臂。
Train. Deploy. Scale.
Onan industrial
• 易疲劳：物理回拖或长时间操作的人机负担较重。
Al platform.
人机工效受限：部分布局下会出现遮挡、操作空间受限等
问题。
适用场景
高精度、强接触、双臂协同任务，如装配、叠衣服、打包；
如装配、
常用于采集高质量专家示教数据做微调。这个是泛工业场景
数据获取的主要手段。
QCon
D
地瓜机器人
InfoQ 极客传媒
全球软件开发大会

## Page 034

•当前主流的数采方案——遥操作
（Teleoperation）
VR遥操
操作员通过VR / XR/ 动捕设备输入头手或全身位姿，系
统经运动重定向与实时控制求解，驱动机器人跟随。
优势
•轻便省力，适合长时操作
• 结合vr沉浸式第一人称视角利于全身协同控制
劣势
• 力觉通常不足，接触密集任务难
• 人机骨骼差异会带来映射误差与动作失真
适用场景
人形机器人全身数采；低力控要求、强视觉依赖的遥操与示
教：常用于采集专家演示数据做微调。
QCon
2 地瓜机器人
InfoQ 极客传媒
全球软件开发大会

## Page 035

•当前主流的数采方案—UMI
UMI （Universal Manipulation Interface）
操作员手持带腕部相机的独立夹爪，系统记录末端 6D位姿
与夹爪开合状态，同步采集局部交互视频。
优势
•轻便低成本，适合真实环境的大规模采集
• 同一类策略接口较易迁移到不同机械臂平台
劣势
• 位姿估计精度受视觉重建影响
• 局部视角容易遮挡、缺少全局信息
•人类示教与机器人执行之间存在embodiment gap
适用场景
更适合大规模预训练和泛化学习；高精度接触任务通常还需
更高保真数据补充微调。
QCon
】
地瓜机器人
InfoQ 极客传媒
全球软件开发大会

## Page 036

•当前主流的数采方案——Ego-Centric
Ego-Centric 采集
操作员佩戴头戴/胸戴/腕戴等第一人称设备执行任务，记录
视觉、手部/腕部运动，以及可选的触觉或受力信息。
优势
• 适合在真实场景中大规模采集
• 视角贴近人类操作
• 若结合手部动捕，可覆盖精细操作与接触过程
劣势
• 手部高精追踪难、易遮挡
• 人类动作迁移到机器人仍需额外对齐
适用场景
大规模预训练；人形机器人全身协同学习
QCon
• 地瓜机器人
InfoQ 极客传媒
全球软件开发大会

## Page 037

• 关键数据获取的方法
-Dagger （Dataset Aggregation）
DAgger （Dataset Aggregation）是“让机器人在自己会犯错的地方继续学习” 的方法。它不是只学专家一开始做对的
轨迹，而是让机器人先自己执行，再让专家告诉它：如果你走偏了，这时候应该怎么改回来。本质上是一种 Human-in-the-
Loop 的 corner case 的收集策略。
DAgger 原理示意图
让机器人在自己会犯错的地方继续学习（Dataset Aggregation）
传统模仿学习（BC）的问题
DAgger 核心流程（选代）
效果：学会纠正偏差
训练数据分布
① 初始化
•• 专家轨迹
用专家示范数据
— DAgger 策略轨迹
训练初始策略 To
专家演示轨迹（干净）
偏离后能被拉回
② 策略执行
让当前策略nt
2测试/部署时
自主执行任务
走偏/进入
未见逑的状态
3 专家纠正
专家纠正动作a*
在策略真实到达的状态st
策略执行轨迹（走偏）
请专家给出正确动作a*
DAgger 的价值
只见过“顺利状态”
数据聚合+再训练
覆盖“偏移状态”的数据分布
进入偏移状态 没学过
将 （St,a*）加入数据集
学会在走偏后如何纠正
错误不断累积—任务失败
用聚合数据重新训练 +1
减少错误累积，提高任务成功率
QCon
地瓜机器人 InfoQ 极客传媒
全球软件开发大会

## Page 038

• 不可或缺的数据源—
仿真
仿真在机器人操作中的核心价值：操作数据生成和闭环测试
3D数字资产生
大规模场景生成
成
传感器和机器本体仿真
基于任务目标的轨迹数据自动生成
QCon
2 地瓜机器人 InfoQ 极客传媒
全球软件开发大会

## Page 039

不可或缺的数据源-
仿真场景生成工作TabletopGen
TabletopGen：一个完全自动化的agent框架，
给定图像生成各种类型的3D桌面场景。
Generative Instance Extraction
Interactive Simulation
"'A hobby desk with some
Scene Assembly
model cars and tools."
Segmentation
Image-to-3D&
Task: place the cucumber into the bowl, and subsequently move the
& Completion
Z-up Canonicalization
carrot and salt shaker onto the cutting board.
Input
Task: Put the magnifying glass into the box.
Pose and Scale Alignment
Differentiable
Renderer
ri
（ri,t,S）
Est. Init
Top-view for tez S：
Viewpoint
Csil, Cedges Camp
- Stacking Prior
for ti
Synthetic Data：
DRO Module
TSA Module
｛Task; RGB; Joint states; Actions；...｝
QCon
地瓜机器人
InfoQ 极客传媒
全球软件开发大会

## Page 040

不可或缺的数据源
仿真场景生成工作MarketGen
MarketGen：一个完全自动化的agent框架，通过PCG的方式生成规模化的超市场景
Text
Reference Image
（b） Handcraft: time-consuming
/eomman
conivenience
store Exhibiting
efficiert /avout.
The styie ofis.
Collected reterencing Real World
（c） Tabletop：
simple layout
Diverse assets wlth Physiral properties
Spatial Layout
d Household
Asset Retrieval
IsaOC Sim
（1） Rule-based
Asset Adiustment
（2）LLM-based
PCG
Limited Input
Soatiol Uncontrollable
Auto-Gen Simulation Platform
Auto-Gen
Structured Complex Layout
Commercial Scenario
（a）Ours
QCon
地瓜机器人
InfoQ 极客传媒
全球软件开发大会

## Page 041

• 简单有效的数据预处理策略
-ISR
ISR（Information-Standardized Resampling）优化episode采样流程，使得采样后的数
据更加标准化，分布更加一致，从而使得模型学习更容易，能够得到更高的操作成功率
• 从黎曼流形视角重新定义轨迹上的“距离”
人类遥操作轨迹存在速度
1
• 用统一度量表征轨迹的运动学与动力学特征
波动、停顿和冗余采样
• 在压缩冗余动作的同时保留关键操作阶段
固定3倍降采样无法区分无
2
效停顿与关键操作阶段
剔除冗余停顿点
均匀轨迹速度
需要一种面向信息分布的
平滑过渡
3
轨迹标准化方法
保留加速或减速的操作意图
原始数据
重采样数据
QCon
地瓜机器人
InfoQ 极客传媒
全球软件开发大会

## Page 042

简单有效的数据预处理策略
-ISR
更少数据，更高成功率
多人采集数据，ISR显著提升成功率
Method
Place&Cover
Place&Stack
Push-T
AVG.（个）
3×+T0.5
45.8（33.3）
48.6（33.3）
48.9（33.3）
47.8
80
36
ISR+T0.5
72.2（28.9）
72.2（28.2）
71.1（40.2）
71.8
33.3
：60
32
3×+ VO-DP
56.9（33.3）
66.7（33.3）
64.4（33.3）
62.7
ISR + VO-DP
77.8（28.9）
91.6（28.2）
71.1（40.2）
80.2
Success Rate （%）
40
28.2
28
Sampling Rate （%）
72.2
48.6
0
20
time-uniform 3x
ISR
Place&Stack from Single Operator
36
33.3
-•32.9
32
Success Rate （%）
28
Sampling Rate （%）
45.8
24
22.2
0
20
time-uniform 3x
ISR
Place& Stack fromThree Operators
QCon
地瓜机器人
InfoQ 极客传媒
全球软件开发大会

## Page 043

InfoO 极客传媒
QCon
全球软件开发大会
THANKS
数字世界和物理世界的AGI正在发
生

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
