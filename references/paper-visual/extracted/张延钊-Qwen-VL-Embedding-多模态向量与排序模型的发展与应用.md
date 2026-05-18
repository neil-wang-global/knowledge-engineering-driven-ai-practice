# 张延钊-Qwen-VL-Embedding-多模态向量与排序模型的发展与应用

> Page-by-page visual information extraction from rendered slide/page images. Text is OCR-assisted and preserves visible page order; diagrams/tables are represented by their visible labels and relationships as line-by-line text.

## Page 001

InfoO 极客传媒
QCon
全球软件开发大会
Qwen3-VL-
Embedding：统一多
模态表征与排序
张延钊
通义实验室算法工程师

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
背景介绍：什么是表征与排序模型
02
方法介绍：模型、数据、训练与算法
目录
03
结果介绍：评估与使用

## Page 004

背景介绍-Embedding模型是什么
将文本，图片等对象映射为向量，应用于检索、分类和聚类等NLP核心任务
Object 1
0.5
0.3
0.1
Object 2
Embedding Model
0.8
0.5
0.3
….
Object 3
0.9
0.4
0.2
Objects
Vectors
检索
聚类
从大规模数据中找到最相关
根据文本相似度进行聚类，分
根据文本和标签的向量相似
（，口）X
的文本
析
度进行分类
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 005

• 背景介绍- Embedding Model 历史
①
词袋模型：早期统计方法，稀疏向量表示
TF-IDF / BM25
word2vec：分布式词向量，捕捉语义关
②
系
Skip-gram/CBoW
③）
预训练模型：上下文感知的深度表示学习
BERT / Sentence-BERT
Qwen3-VL-
4
大语言模型：统一多模态表征与排序
Embedding, Gemini-
Embedding
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 006

背景介绍-Embedding Model 训练过程
对比学习：拉近正样本距离，推远负样本距离
-1.1
Query
北医三院
4
cos（f（z），f（ ）
Positive
北京大学第三医院
f（z）
f（z'
Negative
北京大学医学部
4
4
pooling
pooling
4
Negative
Anchor
LEARNING
BERT
BERT
Negative
Anchor
Sentence
Sentence c'
Positive
Positive
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 007

• 背景介绍-RAG范式下的Embedding与Rerank
Embedding检索 Rerank重排序-LLM生成
Embedding
Query
Model
Corpus
Embedding
Vector
Retrieved
LLM
Mode
DB
contexts
Response
Query
QP
Retrieved
Index
Ranking
contexts
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 008

• 背景介绍-Rerank 模型介绍
Cross-Encoder架构：Query和Document联合编码，捕捉深层交互关系
Embedding
p（yes"|｛i, q,d｝）
Hidden State
4
LM head-
Qwen3
Qwen3
凵U
••.
口L
口
｛Instruction｝+｛Query｝ /｛Doc｝
［EOS］
｛Instruction｝
｛Query｝
｛Doc｝ Assistant：
（1） Embedding
（2） Reranking
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 009

• 背景介绍-Qwen3-Embedding/Reranker
支持多种类型文本数据
代码
记忆
Qwen3
法律条款
网页
Embedding/Reranker
工具描述
本地知识库
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 010

背景介绍-多模态Embedding
CLIP VS VLLM Based Embedding
CLIP model
MLLM model
LLM
Projectot
MLLM
Image Encoder
这台车的售价？
这台车的售价？
单独处理文本/图片，无法建模混合模态输入关系
接受任意模态输入，直接输出向量
From sctatch训练Image encoder，需要大量图文对数据
基于MLIM continue train，数据量需求更低
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 011

背景介绍-Qwen3-VL-Embedding/Reranker
支持将文本、图像、视频的对象表征为向量，提供基于向量的相似度计算能力
TEXT
IMAGE
VISUALDOCUMENT
VIDEO
• urbanarchitecture
• user interface design
• expressive movement
Qwen3 YL Embedding
urban architccture
expressive movement
Text Representation
Unified Multimodal
Image Representation
Representation Space
VisDoc Representation
Video Representation
user interface design
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 012

方法-模型架构
Embedding Model
Reranking Model
［Instruction」
［Query/Doc］
［PAD］
（Instruction］
［Query］
［Dod］
［ASSISTANT！
Vision Encoder
Qwen3 LM Dense Decoder
Embedding of ［Query/Doc：
Reranking Score: P（"yes"）1
LM Head
口 Texh Tokens
口 Vision Tokens
1 Model Weights
Last Hidden States
Qwen3-VL-Embedding
Qwen3-VL-Reranker
• 双塔模型
• Cross Encoder
• 基座：Qwen3 VL Dense 模型
• 基座：Qwen3 VL Dense 模型
• 表征获取方法：Last Pooling
• 分数获取方法：下一词预测为 yes 的概率
• 指令遵循
• 指令遵循
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 013

方法-训练数据组成
总量3亿：文本1亿、代码1500万、图片1亿、视觉文档3000万、视频5000万
• 总数据量：3亿
• 数据构成：
Video
• 文本数据：1亿
• 代码数据：1500万
Document
visual
• 图片数据：1亿
Training
Data
• 视觉文档数据：3000万
• 数据来源
Image
• 开源数据
• 内部数据
• 合成数据
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 014

方法-数据合成
粗粒度质量过滤—细粒度类别标注一类别均衡采样
1. 粗粒度质量过滤：过低分辩率、异常
宽高比、静态场景、损坏片段
2． 细粒度类别标注：
A. 使用VLM标注图像、视频类别
B. 过滤低置信度、低文本图像相关
性数据
C. 类别均衡采样
QCon
InfoQ极客传媒
全球软件开发大会

## Page 015

方法-数据合成
图像（分类/间答/检索）＋视频（检索/分类/问答/片段）＋数据挖掘（召回/过滤/难负样本）
多任务数据合成
图像分类
图像问答
图像检索
视频分类
视频问答
视频检索
片段检索
数据挖掘
• 召回：基于 embedding 模型，重新用合成数据的 query 召回 candidate
• 过滤：
• 正样本过滤：过滤召回相关度低的正样本
• 负样本挖掘：基于正样本相关性分数选择难负样本
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 016

方法-训练策略-对比式预训练
一阶段：完全基于合成数据，使用开源模型进行初步过滤，优化目标：对比学习
Supervised Fine-Tuning
Qwen3-VL-Reranker
Collected Data: 4M
Synthesized
Synthesized/Collected
Data: 300M.
Data: 40M
Distillation
Qwen3-VL-Instruct
Qwen3-VL-Embedding:s2
Contrastive
Multi-Task
Pre-training
Contrastive Learning
Model Merging
Qwen3-VL
Qwen3-VL-
Qwen3-VL-
Embedding: sO
Embedding: s1
Embedding: s3
Data
Method
Model
Model Training
Data Mining
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 017

方法-训练策略-多任务对比学习
二阶段：Embedding： 多任务对比学习|Reranking：监督微调 | 高质量＋合成数据
+ Qwen3-VL-Reranker
Supervised Fine-Tuning
Collected Data: 4M
Synthesized
Synthesized/Collected
Data: 300M
Data: 40M
Distillation
Qwen3-VL-Instruct
Qwen3-VL-Embedding:s2
Contrastive
Multi-Task
Pre-training
Contrastive Learning
Model Merging
Qwen3-VL-
Qwen3-VL-
Qwen3-VL-
Embedding:sO
Embedding:s1
Embedding:s3
Data
Method
［
Model
一 Model Training
DataMining
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 018

方法-训练策略-（模型蒸馏+融合）
三阶段：Reranker标注相关性-模型蒸馏—＞模型融合提升未蒸馏任务性能
Qwen3-VL-Reranker
Supervised Fine-Tuning
Collected Data: 4M
Synthesized
Synthesized/Collected
Data: 300M
Data: 40M
Distillation
Qwen3-VL-Instruct
Qwen3-VL-Embedding: s2］
Contrastive
Mulfi-Task
Pre-training
Contrastive Learning
Model Merging
Qwen3-VL-
Qwen3-VL-
Qwen3-VL-
Embedding: sO
Embedding: s1
Embedding： $3
Data
Method
Model
一 Model Training
— Data Mining
Con
InfoQ 极客传媒
全球软件开发大会

## Page 019

方法-优化目标
多种负样本策略对比学习：批次内/难负样本/跨查询文档负样本＋假负样本过滤
1
N
e（s（gid）/T）
Cretrieval
Zlog
N
Emuesandiy/）+ Zmye daa）/e）+ Zmpeslt a）/e）+ Zmye danda）/rt）
• 多种负样本：
「0，
ifsig>s（gid）+0.1or j二時，
mij=
• 批次内其他文档作力负样本
（1，
otherwise，
• 查询白身的难负样本
• 对于分类任务：只使用难负样本
• 查询与其他查询作负样本
• 对于高质量多模态数据：只使用批次内负样本与难负样本
• 文档与其他文档作为负样本
• 假负样本过滤
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 020

•
方法-优化目标
CoSent：细粒度相关性 | Distillation：学习reranker | SFT： 生成式微调
CoSent Loss
Cot8 =10% 1+
乙
exp
S（ai,t；）>5（gm.dna）
• 对InfoNCE 的推广，适用于相关性标注更细粒度的时候
Distillation Loss
Cdistill = -
Preranker（di l q） log Pembedding （dil 9），
• 基于交叉熵，让 embedding 模型学习 reranker 的相似度评估
SFT LosS
Creranking =-10gP（LL,9,a.），
• 基于生成式模型的监督微调优化目标训练 reranker
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 021

评估-多模态
MMEB-V2平均性能SOTA；图像检索、视频检索、视觉文档检索均SOTA
Model
Image
Video
VisDoc
All
CLS QA RET GD Overall CLS QA RET MRET Overall VDRv1 VDRv2 VR OOD Overall
#of Datasets
10
10
12
4
36
5
5
5
3
18
10
4
6
4
24
78
Open-Source Models
VLM2Vec （iang et al.，2025）
2B
58.7 49.3
65
72.9
59.7
33.4 30.520.6
30.7
28.6
49.8
13.5
51.8
48.2
44
47.7
VLM2Vec-V2 （Meng et al.，2025）
2B
62.9
56.3
69.5 77.3
64.9
39.3 34.3 28.8
36.8
34.6
75.5
44.9
79.4
62.2
69.2
59.2
GME （Zhang et al.， 2025b）
2B
54.4
29.9
66.9 55.5
51.9
34.9
42.0
25.6
31.1
33.6
86.1
54.0
82.5
67.5
76.8
55.3
Ops-MIM-embedding-v1*
2B
68.1
65.1
69.280.9
69.0
53.6 55.6 41.8
33.7
47.6
76.4
53.2
77.6
64.2
70.8
64.6
RzenEmbed （ian et al.，2025）
2B
68.5
66.3
74.5 90.3
72.3
50.4
49.7
46.6
38.9
47.3
87.1
55.1
87.2
43.4
74.5
67.2
VLM2Vec （iang et al.， 2025）
8B
62.7
56.9
69.4
82.2
65.5
39.1
30.0
29.0
38.9
33.7
56.9
9.4
59.1
54.0
49.1
53.1
GMVIE （Zhang et al.， 2025b）
8B
57.7 34.7
71.2
59.3
56.0
37.4 50.4 28.4
37.0
38.4
89.4
55.6
85.0
68.3
79.3
59.1
Ops-MM-embedding-v1*
8B
69.7
69.6
73.1
87.2
72.7
59.7
62.2
45.7
43.2
53.8
80.1
59.6
79.3
67.8
74.4
68.9
RzenEmbed （ian et al.， 2025）
8B
70.6 71.7
78.5 92.1
75.9
58.8
63.5 51.0
45.5
55.7
89.7
60.7
88.7
69.9
81.3
72.9
Closed-Source Models
IFM-TTE*
8B
76.7 78.5 74.6 89.3
77.9
60.5
67.9 51.7
54.9
59.2
85.2
71.5
92.7
53.3
79.5
74.1
Seed-1.6-embedding-0615*
76.1 74.0 77.9 91.3
77.8
55.0 60.8 51.3
53.5
55.3
85.3
56.6
84.7
68.6
77.7
72.6
Seed-1.6-embedding-1215t
75.0 74.9 79.3
89.0
78.0
85.2 66.7 59.1
54.8
67.7
90.0
60.3
90.0
70.7
82.2
76.9
Qwen3 VL Embedding Models
Qwen3-VL-Embedding-2B
2B
70.3 74.3 74.8
88.5
75.0
71.9 64.9 53.9
53.3
61.9
84.4
65.3
86.4
69.4
79.2
73.2
Qwen3-VL-Embedding-8B
8B
74.2 81.1 80.2 92.3
80.1
78.4 71.0 58.7
56.1
671
87.2
69.9
88.7
73.3
82.4
77.8
aCon
InfoQ 极客传媒
全球软件开发大会

## Page 022

评估- MMTEB
通用文本表征评估：MMTEB Qwen3-Embedding SOTA
Mean
Model
Size
Mean
Bitext
Class-
Clus-
Inst.
Multilabel
Pair
（Task）
（Type）
Mining
ification
Retrieval
Class.
Class.
Rerank
Ketrieval
STS
tering
Source Models
KaLM-Embedding-Cemma3-12B-2511 （Zhao et al.， 2025）
12B
723
83.8
77.9
55.8
5.5
33.0
84.7
67.3
75.7
79.0
1ama-embed-nemotron-8b（Babakhin et al.，2025）
8B
69.5
81.7
73.2
54.4
10.8
29.9
84.0
67.8
68.7
79.4
NV-Embed-v2 Lee et al. （2024）
7B
56.3
57.8
57.3
40.8
1.0
18.6
78.9
63.8
56.7
71.1
GritLM-7B （Muennighoff et al.， 2024）
7B
60.9
70.5
61.8
49.8
3.5
22.8
80.9
63.8
58.3
73.3
BGE-M3 （Chen et al, 2024）
0.6B
59.6
79.1
60.4
40.9
-3.1
20.1
80.8
62.8
54.6
74.1
multilingual-e5-large-instruct （Wang et al.， 2024a）
0.6B
63.2
80.1
64.9
50.8
-0.4
22.9
80.9
62.6
57.1
76.8
gte-Qwen2-1.5B-instruct （Li et al.， 2023）
1.5B
59.5
62.5
58.3
52.1
0.74
24.0
81.6
62.6
60.8
71.6
gte-Qwen2-7b-instruct （Li et al, 2023）
7B
62.5
73.9
61.6
52.8
4.9
25.5
85.1
65.6
60.1
74.0
Qwen3-Embedding-0.6B （Zhang et al.， 2025c）
0.6B
64.3
72.2
66.8
52.3
5.1
24.6
80.8
61.4
64.6
76.2
Qwen3-Embedding-48 （Zhang et al.， 2025c）
4B
69.5
79.4
72.3
57.2
11.6
26.8
85.1
65.1
69.6
80.9
Qwen3-Embedding-8B （Zhang et al, 2025c）
8B
70.6
80.9
74.0
577
10.1
28.7
86.4
65.6
70.9
81.1
text-embedding-3-large
58.9
51.4
62.2
60.3
46.9
-2.7
22.0
79.2
63.9
59.3
71.7
Cohere-embed-multilingual-v3.0t
61.1
53.2
70.5
63.0
46.9
-1.9
22.7
79.9
64.1
59.2
74.8
Gemini Embedding （Lee et al.， 2025）
68.4
59.6
79.3
71.8
54.6
5.2
29.2
83.6
65.6
67.7
79.4
Seed-1.6-embedding-1215*
70.3
61.3
78.7
76.8
56.8
-0.0
46.2
85.5
66.2
66.1
75.9
Qwen3
Qwen3-VL-Embeddnig-2B
2B
63.9
55.8
69.5
65.9
52.5
3.9
26.1
78.5
64.8
67.1
74.3
Qwen3-VL-Embeddnig-8B
8B
67.9
58.9
77.5
72.0
55.8
4.5
28.6
81.1
65.7
69.4
75.4
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 023

• 评估 - Reranker多模态检索
相较于Embedding模型进一步提升检索能力
MMEB-v2（Retrieval）
Model
Size
-MMTEB（Retrieval）JinaVDR ViDoke（v3）
Avg Image Video VisDoc
Qwen3-VL-Embedding-2B
2B
73.4
74.8
53.6
79.2
68.1
71.0
52.9
jina-reranker-mo*
2B
-
68.2
-
85.2
-
82.2
57.8
Qwen3-VL-Reranker-2B
2B
75.1
73.8
52.1
83.4
70.0
80.9
60.8
Qwen3-VL-Reranker-8B
8B
79.2
80.7
55.8
86.3
74.9
83.6
66.7
Con
InfoQ 极客传媒
全球软件开发大会

## Page 024

评估-视觉文档检索任务
Reranker在视觉文档任务上平均性能取得SOTA
Model
Size VisRAG VisDocOOD Vidore-v1 Vidore-v2 Vidore-v3 JinaVDR Avg
1lama-nemoretriever-colembed-1b-v1（Xu et al.，2025）
1B
82.4
65.6
90.5
62.1
55.5
66.4
70.4
1lama-nemoretriever-colembed-3b-v1 （Xul et al, 2025）
3B
85.5
69.7
91.0
55.5
57.1
67.8
71.1
colnomic-embed-multimodal-3b （Team, 2025）
3B
86.8
71.0
89.7
63.5
56.4
77.6
74.2
co.gwen2.5-v0.2 （Faysse et aL.， 2025）
3B
86.6
70.9
89.5
59.3
52.4
75.6
72.4
tomoro-colqwen3-embed-4b （Huang &Tan, 2025）
4B
89.0
75.9
90.6
66.0
60.2
76.2
76.5
colnomic-embed-multimodal-7b （Team, 2025）
7B
88.7
75.6
90.0
62.0
57.6
78.9
75.5
tomoro-colqwen.3-embed-8b （Huang &Tan,2025）
8B
90.2
76.8
90.8
67.7
61.6
79.2
77.7
Qwen3 VL Embedding Models
Qwen3-VL-Embedding-2B
2B
86.3
74.3
84.4
65.3
52.9
71.0
72.2
Qwen3-VL-Embedding-8B
8B
88.8
78.3
87.2
69.9
59.0
76.9
76.7
Qwen3 VL Reranking Models
Qwen3-VL-Ranker-2B
2B
89.7
77.5
90.3
62.5
60.8
80.9
77.0
Qwen3-VL-Ranker-8B
8B
91.1
80.4
91.7
71.3
66.7
83.6
80.8
QCon
nroo
遵枚客传婃
全球软件开发大会

## Page 025

评估-模型特性- 维度截断与表征量化
支持截取维度与量化降低存储与计算开销（4-16倍存储成本降低）
MS MARCO
VL3-Syn
（3.87ms, 7812ME
0.497
0.5
0.3
（0.9ems,1053NBY
0.4
（45ms, 32539MIB）
0.3
MRR@10
（solms,123MB）
0.0-
32
256
512
768
64
256
512
768
1024
Embedding Dimension （log scale）
Embedding Dimension （log scale）
• 模型性能随截取的维度下降而下降，但在最开始的时候下降平缓；
• 可以通过截取维度与表征量化来降低部署时的存储与计算开销
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 026

评估-模型特性 - 输入视觉粒度
模型性能随输入视觉粒度提高呈上升趋势，但存在边际效应
Image （Scaling Tokens）
Visual Document （Scaling Tokens）
Video （Scaling Tokens）
Video （Scaling Frames）
53.0卡
58-
77.5•
57.5
75.0
52.5-
561
$5.01
54
72.5
52.5
52.0-
$2
50.0-
51.5-
50-
47.5
67.5
48-
$1.0-
65.0
46-
45.0-
62.5
30.5
44
42.5-
42-
40.0
200
400
600
800
1000
1200.
500
1000
1500
2000
2500
3000
1000
2000
3000
4000
5000
6000.
10
-20
30
40
-50
60
Tokens
Tokens
Tokens
Frames
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 027

• 使用样例 - 文本类型任务
文本分类任务 / 文本检索任务
• 任务描述：将一篇新闻文章自动归类到预定义的主题类别中，如体育、科
• 文本分类任务
技、财经、娱乐等。
• 输入：“昨日NBA总决赛迎来抢七大战，湖人队最终夺冠。”
• 标签：体育
• 文本检索任务 •用户查询（Query）：“身份证到期了怎么办理换证”
• 候选文本片段：
• 身份证换领指南：本人携带旧身份证、户口本到户籍所在地派出所申请…
• 如何补办丢失的学生证？需携带本人身份证到学校教务处填写申请表⋯•
• 护照有效期不足6个月怎么办？建议尽快申请换发新护照（需携带身份证）•
•TOp1：
文本1：“身份证换领指南：本人携带旧身份证、户口本到户籍所在地派出所申请换证，可
提前3个月办理。”
CvOn
InfoQ 极客传媒
全球软件开发大会

## Page 028

• 使用样例- 图像类型任务
图像分类任务/ 图像检索任务
Doc1：猫10.95）
• 图像类任务
Instruct：对给定的动物图片进行分类
Doc2：狗（0.05）
• 图像检索任务
Instruct：寻找符合给定描述的图片
Query：
一个戴着红色帽子的人在
泥泞的道路上骑车
0.7
0.2
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 029

• 使用样例- 视频类型任务
视频分类任务/视频检索任务
• 视频分类任务
Doc1：体育赛事（0.8）
Instruct：对给定的电视节目进行分类
Doc2：新闻报道 （0.1）
• 视频检索任务
Instruct：寻找符合给定描述的视频
Query：棒球手击中了棒球
0.9
0.1
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 030

使用样例- 视觉文档检索
视觉文档检索任务（OCR Free，更好的图像理解能力）
Query：美国第三季度营收
Top1：
CEO点评—2023年年度业绩摘要
2023年第一李度
2023年第二委度
2023年第三李度
20心期
4%
22e表
9%1
二2亿锅元
8%/
6.0Temn 3%
6.52t米元
12%
6.29aw 13%f
2023年第四季度
22亿美元
8%
美国市场
10.05税
1%
11.65c米
7%）
11.74/kmn
8%
5.69亿美元
6%
美国以外（国際）市場
美国以外（国际）市
美国以外（国际）市场
9.78ek
10%0
9.95效米示
11%0
9.56gkx
8%
黑业务的顺长譯商市農个重置产部舒货
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 031

垂域多模态检索
短视频/电商/ 安防 等垂直领域应用
•电商
• 短视频
•安防
Query：北欧极简风格的浅灰色
Query：右下角的白猫
Query：厨师在锅中翻炒的烹饪过程片段
布艺客厅沙发
1 英食京任-∞00K
2025-07-08 10:33 11
现代沙发-客厅
现代沙发-客厅
现代沙友。画面展现了省厅，室
现代沙发，画面展现了密厅，长
素，时长19B9
内设计，东具。灯等元素。梅圆
报.内部的，实尚养无素，构国
黄食coukitchen
精戣白彩亦器
精致色彩沣幽
64.7%
53.4%
2025-07-08 10:33 11
现代沙发-客厅
现代沙发-卧室
现代沙发，画山爱现了签厅，裕
现付诊发，画幽嚴现了卧至树
品 社拉代列，Padaontn,coakng kitchen
子、沙我，长榄笋元索，枚圆積
拒床、房问婆死聚，协图順款
cooxhouse马元素，阳长仿秒
或色彩半器
色移牛盆
如食onioncoeklna
52.6%
46.6% 0
aCon
InfoQ 极客传媒
全球软件开发大会

## Page 032

如何使用
ModelScope / HuggingFace / GitHub / API
mnodelScope
Hugging Face
© GitHub-
$Qwan3-WL-Enbedehng-and-Rerank
Qwen3-VL-Reranker
Owen/Owen3-VL-Reranker-2B
2 Imageto-Text•.t2B•Updated 4days...•34k:071
夕 Owen/Owen3-VL-Reranker-8B
2 Image to-Text89B•Updated 4day... • 21.86k - 060
Qwen3:VLEmbedding
Qwen/Qwen3-VL-Embedding-28
P Image-to-Text•t:2BUpdated 4day.... 止23k，©177
Owen3 Vl.Embedding
Qwen3.VLReranker
$ Qwen/Owen3-VL-Embedding-8B
Qwen3-VL-Embedding & Qwen3-VL-Reranker
R Imageto-Text•#8B•Updated 4 da. • ≥23.2k• 0196
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 033

• 总结
统一多模态表征与排序：架构、数据、训练、性能、开源
01 统一多模态架构
基于 Qwen3-VL 构建 Embedding 与 Reranker，支持文本、图像、视频、视觉文档
02 大规模多模态训练
3亿多模态数据，三阶段渐进式训练：对比预训练—多任务联合学习- 蒸馏与融合
03 全面 SOTA 性能
MIMEB-V2、MMTEB 等多项评估均取得最佳性能，视觉文档检索优势显著
04 开源可用
ModelScope / HuggingFace / GitHub / API 多渠道发布，支持维度截断与量化降低部署成本
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 034

未来规划
统一多模态表征与排序
01 全模态统一：文本，图像，视频，音频
02 效果/效率持续优化
03更多领域覆盖：自动驾驶，医疗图像，多模态记忆，…
04为人类检索场景服务->为Agent 场景服务
QCon
InfoQ 极客传媒
全球软件开发大会

## Page 035

InfoQ 极客传媒
QCon
全球软件开发大会
THANKS
感谢聆听

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
