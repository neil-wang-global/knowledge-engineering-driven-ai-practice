# 郭清沛-Ming-Flash-Omni-全模态统一大模型的关键技术与实践

> Page-by-page visual information extraction from rendered page images. Text below preserves the visible text recognized on each page; pages with diagrams include every OCR-readable label captured from the image.

## Page 001

InfoQ 极客传媒

QCon

全球软件开发大会

Ming-flash-omni：

全模态统一大模型的关键技术与实践

郭清沛

蚂蚁集团百灵多模态基础模型技术负责人

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

多模态大模型发展趋势：更多模态、理解生成一体化

模态

主要覆盖图像、视频

多模态生成

Gemini 3.0 （Google），

音频等两个及以上模态，

•生成视频&音频

GPT-4o/GPT-5

应用需求和技术发展将推动

例如：

Wan2.2-S2V（阿里通

（Open AI）

义）、

HunyuanVideo一

多模态模型走向全模态理解和生成统一架构

•Qwen一omni 系列

Foley（腾讯）

蚂蚁 Inclusion Al.

•紫东太初（中科院）

Ming系列

：开源领域

• Longcat一0mni（美团）

跨模态生成

首个全模态理解与生

从应用上看

•0mniHuman 1.5（字节）

成统一模型

•未来超级入口的需要，人的自然交互形式是“认知”（理解）与“表

达”（生成）的闭环全模态的交互是人类感知物理世界的主要方

•图文理解：Qwen VL

•图像生成：Qwen-

•语音U&G:Qwen-0mni

系列（阿里通义）、

Image（通义）、SD3.

（阿里通义）

式（除触觉外）。

Kimi2.5（Moonshot）

Midjourney

Baichuan-0mni（百

InternVL系列（上海AI

•视频生成：包括

川），MiniCPM-0（面

Lab）、Seed-VL系列

seeddance（字节），

壁）

Veo（Google）

从技术上看，统一的目标是”协同”

（字节）

•图像U&G:Janus一

keling（快手）

ProlDeepseek、Bage.

全模态统一大模型：

•语音生成：Qwen-

（字节）、MetaQuery

• 语音理解：Qwen一

ITS, Seed-IIS.

（Meta）

•模态统一：音，视、图，文 模态协同理解；

Audio系列（阿里通

VoiceBox（Meta）

•祝频U&G：

义）。

Whisper

•3D生成：

Genie 3

OmniVideol上海Al Lab）

•任务统一：理解和生成任务协同

（OpenAI）

（Google）

任务

理解

生成

理解生成统一

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 004

全模态统一大模型相关概念和定义

原生多模态、全模态大模型、理解与生成统一、全模态统一大模型

原生多模态

全模态大模型（Omni-MLLMs）

理解与生成统一

强调模态统一的方式

强调任务统一

强调模态统一

Language

Vision

Language

vision

数据流融合

［文本，图像，音频，视频］

LLM

Diffusion

LLM （AR）

文本

图像

统一预训练

Language

Vision

Language

Vision

全模态大模型

Omni-MLLM

Language

Vision

音频

视频

LLM （AR + Diffusion）

3D

Language

Vision

特点：从训练初期即引入多模态协同

特点：单一架构下的理解和任务解耦与融合

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 005

构建全模态统一大模型的核心挑战

挑战1：模态统一（基于统一架构 实現全模态协同理解）

挑战 2：任务统一（基于统一架构实现理解任务与生成任务的协同）

A1：桥接式方案

A2：原生统一方案

（基于现有LLM进行功能拓展）

（从底层构建统一表征架构）

B1：模型级统一

B2：表征级统一

多模态输入

（通过共享骨干网络支持多任务）

（建模统一的潜空间表征）

全模态统一大模型的每一项

Pretrained

特定编码器

LLM

模态扩充

输入数据

核心技术突破，都将引发行

统一多模态骨干网

业范式的深层变革

适配器/连接器

［理解 Head］

［生成 Head］

共享潜空间表征

模态扩充 during LLM Pretraining

（Unified Shared Space）

冻结的大语言模型

文本

像素/Token

＞模态统一-原生多模态

！

技术突破：视觉感知成

理解与生成协同建模

跨模态融合架构＋全模态协同训练

为LLM的标配，消除语

言模型与多模态模型之

间的界限；

棉战3： 數据异构性 和 模型异构性：細小全漢念大模型和LLMMFU gap，提升全模态训练效率

＞ 任务统一-统一表征范

数据异构性

模型异构性

（张量形状差异大，负载不均，显存碎片化）

（模态编码器计算不均、严亚流水线气泡）

式的突破：终结理解与

𢽴构菸𧰒

GPU 電行

Pipeline Parallelism

生成的长期割裂，实现

全模态能力的真正合一

GPU

SD videc

北水經代泡（坚润期脂）

aCon

InfoQ 极客传媒

全球软件开发大会

## Page 006

Ming-flash-omni 全模态统一大模型的解决方案

挑战 1：模态统一（基于统一架构 实现全模态协同理解）

A1：桥接式方案

A2：原生统一方案

（基于现有LLM进行功能拓展）

（从底层构建统一表征架构）

多模态输入

Pretrained

范式迁移

特定编码器

模态扩充

LLM

适配器/连接器

4

模态扩充 during LLM Pretraining

冻结的大语言模型

基础问题

跨模态融合架构＋全模态协同训练

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 007

Ming-flash-omni 全模态统一大模型的解决方案

挑战 1：模态统一（基于统一架构 实现全模态协同理解）

A1：桥接式方案

A2：原生统一方案

（基于现有LLM进行功能拓展）

（从底层构建统一表征架构）

多模态输入

Pretrained

范式迁移

特定编码器

模态扩充

LLM

适配器/连接器

模态扩充 during LLM Pretraining

冻结的大语言模型

基础问题

跨模态融合架构＋全模态协同训练

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 008

Ming-flash-omni模态统一：跨模态融合架构

基于MoE的跨模态融合架构：音、视、图、文协同训练

Add + Normalize

Imape token

效果对比：Multirouter v.s Single Router

FFN1FFN2

FFN3 FFN4

Router

MMStar

OCRbench

MMMU

A12D

MMB

Avg

Avg

Router Logits

T-Router

V-Router

A-Router

0=0.41

0.08

图文单油

48.21

57.9

42.22

69.95

721

57.89

similar expert distributions

for image and text

单独audio

561

Multi-Router［1；融合模态特征，兼顾模态差异

MoE Layers

baseline

4649

53.3

42.56

682

68.47

55.804

5.57

Layeri

Inage

Mutt-Router

45.74

57.7

4522

69.69

70.618

57.79

5.05

Kideo

Toemoale wartafa

vofien help npraml don

AnyExperts［2］：按需激活，每个token重要度不同，何必强制统一K？

［1］ Jing, L.， Gao, Y.， Wang, Z.， Y.， Wang, W.， .. & Guo, Q. （2025）. EvoMoE: Expert Evolution in Mixture of Experts for Multimodal Large Language Models. AAAI 2026

［2］ Gao, Y.， Lan, W.， Zhao, H.，， Liu, S.， & Guo, Q. （2025）. AnyExperts: On-Demand Expert Allocation for Multimodal Language Models with Mixture of Expert, CVPR 2026

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 009

Ming-flash-omni模态统一：跨模态融合架构

OCR

基于MoE的跨模态融合架构：音、视、图、文协同训练

AnyExperts［1］：按需激活，每个token重要度不同，何必强制统一K？

效果对比：

Dnamic（OrdMoE

TopK v.s

Input

6。

10g

Layeri

K （Experts per Token）

KAExperts per Token）

AnyExperts

Video

NLP

70 o

Dynarde （OriNoE）

Jynamic《OreiaE）

Teut

3095

6H。

K （Experts per Token）

Where is the man

个

：ABna

Qutdon

MOE FEN

RMSNorm

可视化

口口口口

重要token

mportance-aware Routin：

RMSNorm

TToken topK

口.

Muppar

口口口

Vision

Fstimution

Statistic

smnTEson

Encoder

［1］ Gao, Y.， Lan, W.， Zhao, H.，， Liu, S.， & Guo, Q. （2025）. AnyExperts: On-Demand Expert Allocation for Multimodal Language Models with Mixture of Expert, CVPR 2026

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 010

Ming-flash-omni 全模态统一大模型的解决方案

挑战 1：模态统一（基于统一架构 实现全模态协同理解）

A1：桥接式方案

A2：原生统一方案

（基于现有LLM进行功能拓展）

（从底层构建统一表征架构）

多模态输入

Pretrained

范式迁移

特定编码器

模态扩充

LLM

适配器/连接器

4

模态扩充 during LLM Pretraining

冻结的大语言模型

基础问题

跨模态融合架构＋

全模态协同训练

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 011

Ming-flash-omn模态统一：音、视、图、文模态协同训练

Pretrai.

4-感知能力

Image

Audio

Image

Yideo

Audio

全模态协同训练［

Vision

Audio

Vision

Audio

Encodcr

Text

Encoder

Encoder

Text

（Encoder

V

MLP

MLP

MLP

MEP

数据配比/训练阶段规划

Ming-0mni

Ming-0mni

＞ 各模态的数据量不同

Lun

Lun

≥ 任务复杂度不同，收

Stage-1：模态表征对齐

Stage-2：全模态对齐

+

敛速度不一致

PostTraining-指令理解+推理能力

Multi Nodal Multi-Task Balanced Training Strategy

Image

Audio

Image

Video

Audio

Toxt

Imago-Text

aD

Text

Updlave C

Forward

Modality

Vision

Audio

Vision

Audio

Image

Lz

xW2t weight

Encoder

Text

Encoder

Encoder

Text

Encoder

M2-

Video

ommi

Backward

x Wst

Vidco-Text

Audio-Text

MLP

MLP

MLP

MLP

03.¢2+D3t

Q4t十

Audio

x Wat

Ming-0mni

Ming-0mni

Historical validation losses

Lun

Lan

Stage-1： 图文指令跟随

Stage-2：全模态指令跟随+XPO

［1］ Guo, Q.，Song, K,Feng,Z.，Ma，

Q.， Gao, S.， ... & Zhou, J. （2025）. M2-omni: Advancing omni-mllm for comprehensive modality support with competitive performance.

QCon

InfoQ

极客传媒

全球软件开发大会

## Page 012

Ming-flash-omni 全模态统一大模型的解决方案

挑战 1：模态统一（基于统一架构 实现全模态协同理解）

A1：桥接式方案

A2：原生统一方案

（基于现有LLM进行功能拓展）

（从底层构建统一表征架构）

多模态输入

Pretrained

范式迁移

特定编码器

模态扩充

LLM

适配器/连接器

4

模态扩充 during LLM Pretraining

冻结的大语言模型

基础问题

跨模态融合架构＋全模态协同训练

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 013

模态统一训练范式迁移：原生统一方案

训练迭代次数

早期

中期

后期

早期多模态融合（即使在较低

LLM Pretrain阶段 （Language Model Base）

视觉 Token 比例下）能让模

型更自然地学习平衡的表示，

从而获得最佳的全模态性能。

早期视觉注入

中阴视觉法入

阪换员注入

20%

50%

80%

多模态敛据

引入时机

早期融合

中期融合

后期融合

（Early Injection）

（Mid Injection）

（Late Injection）

早期融合效果（最佳）

中期融合效果

后期融合效果（最差）

Vision Knowledge

Vision Knowlecge

Vision Knowiedge

Code

Vision Reasoning

Code

Code

Vision Reasoning

Vision Reasoning

［1Team, K.， Bal, T.， Bai, Y.，

Text Reasoning

OCR

Text Reasoning

OCR

OCR

Bao, Y.， Cal, S. H.， Cao, Y. •&

Text Reasoning

Shang, Z. （2026）. Kimi K2. 5：

Text knowiedge

Text Knowledge

Text Knowledge

Visual Agentic Intelligence.

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 014

构建全模态统一大模型的核心挑战

挑战1：模态统一（基于统一架构 实現全模态协同理解）

挑战 2：任务统一（基于统一架构实现理解任务与生成任务的协同）

A1：桥接式方案

A2：原生统一方案

（基于现有LLM进行功能拓展）

（从底层构建统一表征架构）

B1：模型级统一

B2：表征级统一

多模态输入

（通过共享骨干网络支持多任务）

（建模统一的潜空间表征）

Pretrained

特定编码器

LLM

模态扩充

输入数据

统一多模态骨干网

适配器/连接器

［理解 Head］

［生成 Head）

共享潜空间表征

模态扩充 during LLM Pretraining

（Unified Shared Space）

冻结的大语言模型

文本

像素/Token

理解与生成协同建模

跨模态融合架构＋全模态协同训练

搖战3：数据异构性 和 模型异构性：缩小全模态大模型 和LLM MFU gap，提升全模态训练效率

数据异构性

模型异构性

（张量形状差异大，负载不均、显存辟片化）

（模态编码器计算不均、严重流水线气泡）

𡜐构𦲀𧰒

GPU 昆存

Pipeline Paralletism

GPU

1有致針算（有效分写期：

滼水經代泡（壁闸W魁）

aCon

InfoQ 极客传媒

全球软件开发大会

## Page 015

Ming-flash-omni 全模态统一大模型的解决方案

挑战2：任务统一（实现理解任务与生成任务的协同）

B1：模型级统一

B2：表征级统一

（通过共享骨干网络支持多任务）

（建模统一的潜空间表征）

输入数据

统一多模态骨干网

共享潜空间表征

［理解 Head］

［生成 Head］

（Unified Shared Space）

文本

像素/Token

理解与生成协同建模

目标：基于统一架构实现理解与生成任务协同

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 016

Ming-flash-omni：全模态理解和图像/语音生成任务统一

分阶段训练：全模态理解侧训练＋生成侧训练

1）集成生成任务同时，保持理解效果 2）实现理解能力促进生成

Perception Troinin

wpongeBob scarefee spn：.

Vision Head

图像生成口：Meta-X架构，根据Context提取图像输出生成控制条件

Gereration Trainiig

DiT Bloaks

Text Token

口

wudio Token

Training

Denoising Objective e

Image@126px

Image@256px

Image@512px

Inference

Vision Token

'ad fcken

Detokenizer

Decoder

Multi-scale

Shared Experts

L

00

Kapresentation Alignment

DiT Blocks

DiT Blocks

DiT Blocks

Image@512px

Byc

00

00

FeEVAt isent

Response

DiT Block

Connector

DiT Block

1口回回-国

Multi modal Large Language Model

DiT Block

MoE FFN

V-Route

A-Router

RMSNorm

Ling-

mage tokens Text tokens

Multi-scale queries

Noisy inputs

XN

flash

Linear

语音合成［2］：thinker-talker架构，先思考（输出文本），再表达（合成语音）

Attention Layer

个vdeoRope

audio token

RMSNorm

flow matching

口口口

me！

AR decode

audio decoder （0.5B）

hifigan

Please answer the

bird perched..

Vision

Audio

Ming-0mni

style instruct

Encoder

Encoder

L1」

［2］

Infoo

极客传媒

全球软件开发大会

## Page 017

Ming-flash-omni：图像理解和生成任务统一存在的问题

Ming-flash-omni 基于Meta-Query方案的图像生成 获取的是高层语义，缺乏细粒度、结构及文字信息：

图像生成和编辑任务

图像编辑任务

文字生成

缺乏 参考图 结构化信

细粒度视觉知识（属性、空

语义->文字

息，ID难保持

间关系）无法有效传递至生

缺乏低层特征

成端。

缺乏ID保持及参考图

缺乏端细粒度感知

缺乏高保真文字生成能力

结构理解能力

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 018

Ming-flash-omni：图像理解和生成任务统一解决方案

核心思路

构造理解和生成的统一目标，

提升生成侧细粒度感知能力

图像生成和编辑任务

解决方案

细粒度视觉知识（属性、空

一种理解和生成的统一表达：生成式分割 即编辑

间关系）无法有效传递至生

成端。

6

饋确總難依赖|張勇維擬的倫糖業率。

准确编辑物体，必须先精确感知其边界——感知

精确感知

總掛零基提供理|生成威量真接反映理解精度，两者优化

缺乏端细粒度感知

解监督信号

目标自然统一。

餐使製細空间 |有效解决文本到图像生成中的组合性难

语义控制

QCon

InfoO极客传媒

全球软件开发大会

## Page 019

Ming-flash-omni：图像生成和理解任务的协同

一种理解和生成的统一表达：生成式分割 即编辑，分割任务->图着色任务（图像编辑任务）

千

变

的女人

原图

Qwen-Image-Edit

Nano-banana

Ming-lite-0mni1.5

原图

Qwen-Image-Edit

Nano-banana

Ming-lite-0mni1.5

指代分割任务

图像编辑任务

Type

Modcl

RcfCOCO （val）*

RefCOCO+ （val）^

RefCOCOg （val）t

Type

Model

GEdit-Bench-EN（Full set）个

GEdit-Bench-CN （Fulset）

GSC

G_PQ

GO

GSC

GPQ

GO

VLT

67.5

56.3

55.0

Vision.

CRIS

70.5

62.3

59.9

Instruct-Pix2Pix

3.58

5.49

3.68

LAVT

72.7

62.1

61.2

AnyEdit

3.18

5.82

3.21

PolyFormer-B

74.8

67.6

67.8

Edit.

MagicBrush

4.08

5.66

4.52

SteplX-Edit

7.09

6.76.

6.70

7.20

6.87

686

LISA-7B

74.1

62.4

66.4

Qwen-Image-Edit

8.00

7.86

7.56

7.82

7.79

7.52

SAM.

PixelLM-7B

73.0

66.3

69.3

Z-Imagc-Edil

8.11

7.72

7.57

8.03

7.80

7.54

OMG-LLAVA

75.6

65.6

70.7

UniWorld-vl

4.93

7.43

4.85

Q

Nano-banana*

15.7

13.9

14.9

OmniGcn

5.96

5.89

5.06

2012

788

Generalist.

0mniGen2

7.16

6.77

6.41

Uni.

Owen-Imuge-Edit*

BAGEL

传媒

全球软

Ming-Flash-Omni

¥2.1

65.2

65.4

Ming Flash-Omni

8.11

7.87

7.64

8.02

7.95

7.62

## Page 020

Ming-flash-omni：图像理解和生成任务统一解决方案

ID保持：双信息流设计

结构级信息流

图像编辑任务

参考图像一VAE编码一与噪

参考菵凑篓停晷搉

1

2

可登询 token

声潜变量拼接一自注意力增强

—全局语义编码 一提升编辑内

参考图结构和身份一致性

缺乏 参考图 结构化

容保真度与准确性

信息，ID难保持

缺乏ID保持及参考图

结构理解能力

解决方案

高保真文字生成：Glyph-ByT5路径

目

城市的温柔角落

Ming Flash Omni

文字生成

语义->文字

Ming

蚂蚁葉囷

InclusionAI

缺乏低层特征

Frompt提取

从用户Prompt提

Glyph特征

生成学形特征表示

牛成

取文字内谷

文竿

缺之高保真文字生成能

力

BYJ5编停

QCon

进行宇节级雏码

条件酵盒。

表示

token结合输入

InfoQ-校客传媒

全球软件开发大会

## Page 021

Ming-flash-omni：语音理解和生成任务统一解决方案

do

Sound

Spcech

Sound Speech

Music

becoser

Decoder

DIT Patch Head

Mimg-omni-tts

1d6d61

DiT Patch Head

DiT Patch Head

Large History Patch

Small Current Patch （noised）

Large Language Mode！

Aggregator

Continuous Audio Token

基于连续自回归的极简架构，实现在一句话音色克隆

Please synthesize this

Hello, this is Ming-

Text Token

sentence cheerfully：

omni-tts

中，对于方言、情绪、语速、语调、音量的细粒度控

Instruction

Spk Embedding

制，并且支持长播客生成，实现数学、化学公式的正确

tokenizer-12Hz

朗读

方言控制

情感控制

音色设计

一句话音色可控支持通过指令来控制音频

只需提供任意一句话即可克隆音

的喜怒哀乐

• 支持自然语言定义音色

色，说出地道的粤语和四川话

在CV3-Eval Emotional上的平均acc为

•

内置100+精品音色、以及经典角色音

•

在 WSYue-TTS-Eval 和 WSC-TTS-

78%，高于 CosyVoice3；

色，无需 prompt 音频，直接获得音色

Eval 上的粵语和四川话生成准确

矩阵

中性情感prompt音频生成带情感的音频效

率96%和86%

果突出

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 022

Put it all together: Ming系列能看、能听、能说、能画的全能AI

首个模态支持上全面对标GPT40的开源模型：输入音频、视频、图片、文本，输出文本、图片、语音

Image Editing

OMing-Omni

Ming-lite-omni x1.5Ming-lite-omni

aQwen2.5-0mni•Qwen2.5-VL

Visual Grounding

MetaQuery一XL

Janus-ProB

- Kimi Audio

GEditBench

RefcOCO（Gen）

Image Generation

GenEval

6.51

72.4

MMVet

Image

0.87

Understanding

Q: Where is the Shih Tzu in the image？

74.0

Answer in ［xO. yO. x1.yl］ format.

Make the sheep wear

tiny glasses

DPGBench

84.2

OCRBench

A：［0.

608,100.

923］

88.4

Image Generation

Audio Generation

GUl Understanding

1.69

72.0

SEED-TTS-zh-wer

MathVista

Q: In the given image. could

you find and tell me the

coordinates of search bar？

2.72

59.5

A photo of a

SEED-TTS-en-wer

LongVideoBench

A:clicklx=0.384.y=0.082）

A photo of a

toaster

cake

2.46

69.4

Image Style Transter

6.89

Audio

Aishell2-test-ios

6.89

MVBench

OCR

Video

Understanding

cy15-en

A pacaEva

Understanding

日期：2016-12-01

18:14

机号：039单号

Audio Chat

Video Chat

003056

收银员：0121

粤语：麻烦介绍一下杭州

Q：请描述视频内容言

货号 数量单价 金额

味全每日C胡萝卜疏果

杭州有着悠久的历史.如西湖、

原汁300ml

A：视频中一位女性

灵隐寺、雷峰塔等著名景点

146838 16.00 6.00

A cong e zou, C, zneng, C. Znou, C. Yan.C.. &He.Z. （2025）， Ming -Omni.A Unified Mulimadal Model tor pecepion and Gendabo

极客传媒

## Page 023

Put it all together: Ming系列能看、能听、能说、能画的全能AI

首个模态支持上全面对标GPT40的开源模型：输入音频、视频、图片、文本，输出文本、图片、语

This imagefideo capnires

Text loken

Shared Experts

SpongeBob s carefree spiri.

vision Token

Routing Experts

Model Scaling？

口 Audio Token

Detokenizer

是否随着模型尺寸增大，全模态

Pad Token

Generation Jraining

Muit-scale Dil Blocks

理解和生成效果提升？

Audio Decoder

connectol

MoE FFN

回国日日，

D00月 1000

Ling

XN

T-Router

V-Router A-Router

Attention Layer

二圈

GitHub: https://github.com/inclusionAL/Ming

Please answer the..

Generate a vivid

Multi-Scale Learnable Tokens

bird perched.

Hugging Face: https://huggingface.co/inclusionAI/Ming-

Vision

Audio

Encoder

Encoder

fash-omni-2.0

ModelScope: https://www.modelscope.cn/models/inclusionAL

/Ming-flash-omni-2.0

Ming-Omni

What story does thnis

mogeiideo teil？

Video

QCon

Infoo极客传媒

全球软件开发大会

## Page 024

Model Scaling: Ming-Flash-Omni

首个千亿参数规模的开源全模态统一大模型

Perceotion Iraining

Tiis inigehndeo captires

SpongeBob cavgfice spirit.

Vision Head

Generation Training

Omni

Specialist MLL M5

Ming

團 Adio Tcken

Audio

Ming-Flash-0mni-

Vision Token

網 Pad Token

DiT 8locks

Benchmark

2.0-1008-A6B

Gemini

LongCat-

2.5 Pro

Flash-Omni-

0mni-308-

VL/AudiO

5608-A278

A5B-Instruct

Image ceneration

Shared Experts

口

而口

町圍

00

MMStar

T090

88.50.

15.90*

Routing Experts

Audio Head

Vision Head

Rctincr

Byt

GeneralImage

MMBench EN_test11

87.50

88.80

Understanding

HallusionBench

63224

4

OO

MMvet

RetVAE iatent

AI2D

Unaerstanding

ChartOA

87.60

OCRBench

8490

MMMU

7070

MathVerse（Vision_Only）

STEM

MOE FFN

Blas

Bias

LogicVista

T.Router

Counting

FSC147（1）

RMSNorm

口口

Grounding

RefCOCO-aug

Ling-

WikiKnowledge

10000d

J00000

XN

flash

个

MVbench

Linear

Multi Image

CharadesSTA

MLVU

Attention Layer

Attention Interface

ibrispeech test-other（l）

401

个VdeoRope

AlpacaEval

98.80

RMSNorm

2MsNom

RMSNorm

Speech

ContextASR-Bench（J）

W5C-Eval-TT5-Avg-WER（J）

Linear|

LLinear

WSC-Eva/-TTS-Aug-ACC

Image

DPGBench

Generation

Geneval

ImageEditing

GEdit（EN/CN）-Overall

Image Segmentation

RefCOEO-val

Picase answer the.

Generate o wivid Multi-Scale Leornable Tokens

oird percllec.

Vision

Audio

Encoder

Encoder

Ming-0mni

Neties maitsd weh oninderine srenc.inthe orahnst.tedhnicsrecontetheswee obahed tyuswpuslcAn.crloaalcedo.mant.

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 025

Ming-flash-omni 全模态统一大模型的解决方案

挑战2：任务统一（实现理解任务与生成任务的协同）

B1：模型级统一

B2：表征级统一

（通过共享骨干网络支持多任务）

（建模统一的潜空间表征）

输入数据

统一多模态骨干网

共享潜空间表征

［理解 Head］

［生成 Head］

（Unified Shared Space）

文本

像素/Token

理解与生成协同建模

目标：基于统一架构实现理解与生成任务协同

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 026

任务统一：Ming在统一模态表征的探索

MingTok［］

语音和图像可以使用相同的

H/32xW/32+1

Semantics

泛式实现统一表征：

SABlock

Bi-directiona.

SABlock

Projection out

Proiection in

Uni-directional

SABlock

SA Block

Generation

VAE

Pixel Decoder

Low-level Encoder

Semantic Decoder

Pixel Decoder

Understanding

MLP

Image Latent 16d

Semantic Feature 1024d

Pretrained

Model

Feature

Pretrained

Masked

MingTok

Semantic Decoder

Unified MLLM

Model

-eatune

Latent tokens （d-32）

Clstoken

Unified MLLM

Pretrained features

Image Latent 32d

Generation

Semantic Feature 1024c

Low-level Encoder

Semantic

MingTok-Audio［2

Encoder

Understanding

SigLIP / QwenviT...

MLP

Self-attention block

Projection

Projection

Self-attention block

Projection

Self-attention block

Projection

ISTFI

≥ 用连续表征对理解和生成任务效果最好

＞ Latent 低维表征做自回归输出

xN

Frame

Acoustic

xN

latent

Semantic module

Unified

xN

1aMurO

Decoder

＞ Semantic高维表征做自回归输入

［1］ Huang, Z.， Zheng, D..• & Zhou, J. （2025）. Ming-UniVision: Joint Image Understanding and Generation with a Unified Continuous Tokenizer.

［2］ Yan, C.， Jin, H.， & Huang, Z. （2025）. Ming-UniAudio: Speech LLM for Joint Understanding, Generation and Editing with Unified Representation.

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 027

构建全模态统一大模型的核心挑战

挑战1：模态统一（基于统一架构 实現全模态协同理解）

挑战 2：任务统一（基于统一架构实现理解任务与生成任务的协同）

A1：桥接式方案

A2：原生统一方案

（基于现有LLM进行功能拓展）

（从底层构建统一表征架构）

B1：模型级统一

B2：表征级统一

多模态输入

（通过共享骨干网络支持多任务）

（建模统一的潜空间表征）

Pretrained

特定编码器

LLM

模态扩充

输入数据

统一多模态骨干网

几

适配器/连接器

［理解 Head］

［生成 Head］

共享潜空间表征

模态扩充 during LLM Pretraining

（Unified Shared Space）

冻结的大语言模型

文本

像素/Token

理解与生成协同建模

跨模态融合架构＋全模态协同训练

搖战3：数据异构性 和 模型异构性：缩小全模态大模型 和LLM MFU gap，提升全模态训练效率

数据异构性

模型异构性

（张量形状差异大，负载不均、显存碎片化）

（模态编码器计算不均、严重流水线气泡）

𡜐构𦲀𧰒

GPU 昆存

森鹽育华

Pipeline Paralletism

GPU

1有致針算（有效分写期：

滼水經代泡（壁闸W魁）

aCon

InfoQ 极客传媒

全球软件开发大会

## Page 028

Ming-flash-omni：训练优化-数据异构/模型异构

（a） Baseline Megatron-LM （Unoptimized）

（b） Ming-flash-omni （Our Optimized Infrastructure）

Data Heterogeneity Issue

Solution 1: Sequence Packing

Text

Text

（Short, len=128）

GPU Memory: Highly Fragmented

Fixedlength computational Batch

Short, len=128）

Image

Image

（Pixel=224^2）

Sequence

（Pixel=224^2）

Video

Packing

Gemory fragmentation

Video

（16-frames,224^2）

GPU Memory; High Utilization

（16-frames, 224^2）

Video

AUGIO

& Reduced Fragmentation

Audio

+ Timelne

GPU Memory: Load Imbalance

Solution 2: Flexible Parallelization

Rank0

Encoders

Heterrgeneous

Decoders

Model Heterogeneiity Issue

Rank 1

Encoders

DP/PP/TP---

Decoders

Modality-Specffic Pipeline Layout

Rank 2

Encoders

（LP）

Decoders

Encoder Stages

Decoder Stages

Rank 3

-Communication & Computation -•

Idle

Rank 0

Encoders （Busy）

Idle

Timeline

Minimized Pipeline Bubbles

Rank1

Encoders （Busy）

Busy

Idle

Solution 3: Custom Kernel Optimization

Rank 2

BuSy

Decoders （Busy）：ldle

Operator Level Optimization

Native LayerNorm

Results：

Throughput

Rank 3

Encoders（Busy）

Idle

Decoders （Busy）

Backward

Increase

28% MFU，

Custom CUDA Kernel

>4x Throughput

Pipeline Bubbles （Idle Cycles）

Step

（Ming-flash-omni）

0

80%

vs. Baseline

Bandwidth Utilization

Input Data：

口 Encoders：

Encoders：

L Decoders：

Computation: Solid -+ Communication Overlap：

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 029

Ming-flash-omni：训练优化-数据异构/模型异构

Audio

Vision

Encoder Backward

grad

Fncoder-B

（00000000000000）

针对非对称架构带来的流水线气泡，采用

灵活并行策略 （Flexible Parallelization）独

Sequences with diff-length

立配置组件参数，实现端到端训练效率

69.7%提升。

LUM

360g0u.PP:5 EP:8DP:9

Encoder-F

LLM

30 gpu, PP:3 DP:10

Encoder Forward

00000000000000000000

000000000000

Projector

Packed sequences

vision token

podding roken

sequence

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 030

百灵Ming系列开源后在社区受到了广泛关注

多模态大模型Ming-Omni 开源的多个版本在huggingface同类模型趋势榜单（any to any）位列榜首，

并入选huggingface热点论文榜。

Husging Foce

Hugging Face

aHodes

• Deastt 删Spaces

• comrunity m Docs Priang

Tass0 Lbnres Languge

Modes 1.4

• Filas bynome

Filles,searth

Ieence haleble

！Sotiredng

Nodeks 7,770

• Fuby osne

Fudtcd xerch

mnieona halabs

Hsort Tnrdre

m.snc.usiona./King-Lste-can-.s

rsnclu:1ocAI/M2:8-#1a2h-omp1-Prevtea

2 geseTaks

m inclusiorAI/Ning-flash-cmni-2.0

2 AnstoAny: Upsed sdayap:6olk-w2

c si0zon-3i/wi0rem.E1-1

中 Cneo/0n:n3-0mn）-388-453-Instnvet

• TetGenernon

MAnyto-dny

mgelofm

*Ats day•.355•Updasd 5ep22:2385c78

Insgt TtttoTos

n operbmb/Nin1CPY-0-4.5

CTecL Spokh

*Amto.ky： $98,Uptse5dapsa.154.9如

F102622-021DreaK-E2-FU：！

o Tettoide Tet-irSotechf

28

4282:00

openonb/hiniC81-0-2-6

© xgen-unaverse/ Capybara

MAnto-n:Upandabout2hounsar.08

pknen/beanz:s:cmoi-g0

mameeIS

中 Cwet/0an2.5:0mL-93

= operbab/Min:CPY- 0-4.5-gguf

• i1teistykh/Fa8e）-LR-501t

2 sitisns

君 Trrdftmssis

V KIN 9m0E 6 LG: DBXw

sospsosk-2:/3an.s.Pms-78

I NLXE

deepscek-o1/23eUs-Pro-7B

* OperHOSS-Tean /MOYA-728p

@50n-l:s0/830-88-8c

mArgt4ne.Vpdanefeb11a62t.23.50k

6 Pyioch f Fensoflow

或I

*tAnystotny upcakd ?daysagv 258k-013

k wnsc

inclus3onAL/Ni/g- Lite-cmi

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 031

Ming-flash-omni ：图像生成能力展示

Ming-lash-omni-2.0

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 032

Ming-flash-omni：语音合成能力展示

基于构造高质量方言生成数据集构建，

基于高质量audio caption指令数据，实现多样化的音色设计能

通过文本指令来生成地道的方言

力，从方言到情感、到角色，细粒度打造目标音色

跨语种方言生成

情感风格音色设计

方言音色设计

下面是我的原声

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 033

Ming-flash-omni Skill：让 OpenClaw能看、能听、能说、会画

赛博老管家測试-1

賽博老管家测试-1群～

# general

Search 赛博老管家測试-1群

Ce Events

Online-2

◎

Server Boosts

赛博龙虾小管家APF

阳光每一天

Text cnannes

# general

Offline-2

•#a-new-day

cafe3310

①

Voice channelsy

MichelleYang

•）

General

这是我的剪刀手语音说明！听听我有多可爱～

体验升维，具备活人味的

680.53 KB

victory_pose.wav

专属数字管家

0:07/8407

美【赛博龙虾老管家的小时报】（- 12:16 PM

过去一小时我主要在处理心跳任务，检查了系统中的定时任务状态。目前有两

One Skill is ALL you

个活跃的定时任务：

1.每2小时发送马年吉祥话语音到本频道

need

2.每2小时分享一个中文笑话

当前群内聊天比较安静，没有太多新消息。我随时待命，准备为大家提供帮

助！有什么需要我做的吗？

阳光每一天14:22

@赛博龙虾小管家 和大家打个招呼吧！

••1

赛博龙虾小管家ityping.

QCon

阳光每一天

Online

十 Message #general

全球软件开发大会

## Page 034

Ming-flash-omni 应用：给OpenClaw 装上眼耳嘴和身体

Ming一Omni API

User：在吗？发一张照片来

name: generate_my_photo

description: Generate photos of me（the

assistant） in various Locations using

my reference image （me.png） and the

Load Skil

image_text_to_image skill. Append a

voice message.

Image edit:image_text_to_image

text_to_speech

（语音）看，我在旅

游呢

O健接公生图、语音功能 APl: hutps：.//zenmux.a/ inelusionai/ming-（lash-omi-2.0

InfoQ 极客传媒

全球软件开发大会

## Page 035

Ming-flash-omni 应用：给 Claude code /OpenClaw装上眼耳嘴和身体

Showcase

*eAI相册美化一实际产出

© Ming-flash-omnl-2.0

华山 春节初一

下棋亭、西峰、南鮮、莲花柱

QCon

InfoQ 极客传媒

全球软件开发大会

## Page 036

InfoQ 极客传媒

QCon

全球软件开发大会

THANKS

统一全模态，不只是“把模态放在一起”

而是让架构、算法、训练、工程一起闭环

蚂蚁百灵 Ming 系列全模态模型

## Page 037

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
