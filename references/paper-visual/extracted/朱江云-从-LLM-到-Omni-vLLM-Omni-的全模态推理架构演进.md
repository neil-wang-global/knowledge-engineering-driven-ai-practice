# 朱江云-从-LLM-到-Omni-vLLM-Omni-的全模态推理架构演进

来源PDF：`references/papers/朱江云-从 LLM 到 Omni：vLLM-Omni 的全模态推理架构演进.pdf`
页面图像目录：`references/paper-visual/images/朱江云-从-LLM-到-Omni-vLLM-Omni-的全模态推理架构演进/`

说明：以下为按页信息提取，尽量保留页面可见文字、标题、列表、表格与图示标签。
## Page 001

```text
InfoO 极客传
QCon
全球软件开发大会
从 LLM 到 Omni：
VLLM-Omni 的全模态推理架构演进
朱江云
VLLM-Omni Commiter
```

## Page 002

```text
极客邦科技 2026年会议规划
促进软件开发及相关领域知识与创新的传播
06月？上海
28 1000人
08月9深圳
%， 1000人
AiCon
•Al Infra 系統工程
AiCon
•Agentic A！
多 Agent 协作与实露
•轻量化与高效推理
全球人工智能开发与应用大
•多模态融合
•多模态应用
•模型训练与推理创新
全球人工智能开发与应用大会
•Al + IoT 场景实践
会议时间：6月26-27日
•數据平台与犄征服务
会议时间：8月21-22日
•AI工业化落地
10月9上海
28 1200人
012月？北京
81000人
QCon
*Al Agent
、Vibe Coding
AiCon
•大模型絮构创新
•智能可观測
•多模态 AI 产业融合
全球软件开发大会
•維理基建
全球人工智能开发与应用大会
•具身智能
、模型攻防
•Al for Science
会议时间：10月22-24日
•AIX创造力
会议时间：12月18-19日
•大模型安全
```

## Page 003

```text
      About us


Roger Wang       Hongsheng Liu   Han Gao      Jiangyun Zhu
vLLM&vLLM-Omni     vLLM-Omni     vLLM-Omni    vLLM&vLLM-Omni
   Committer        Committer     Committer      Committer
```

## Page 004

```text
VLLM-Omni
Easy, Fast, and Cheap Omni-Modality Model Serving
THE SHIFT TO OMNI-MODALITY
TRADITIONAL SERVING（Text-only AR）
OMNI-MODALITY LANDSCAPE
EVOLVING
LLM
INFRASTRUCTURE
image
Heterogeneous
Outputs
AudIO
Video
OMNI-MODELS
（AR & NON-AR/DiT）
VLLM-OMNI ARCHITECTURE: RE-IMAGINED HETEROGENEOUS PIPELINE
MULTIMODAL INPUTS
-OmniStage Abstraction
RICH MEDIA OUTPUTS
MODALITY
Hidden States
LLM CORE
Hidden States
MODALITY
ENCODERS
（VLLM）
GENERATORS
ViT,Whisper, etc.
Tokens
AR Text & Hidden States Gen.
Tokens
DiT, Decoding Heads
KEY FEATURES & BENEFITS
PROVEN EFFICIENCY & FUTURE ROADMAP
SIMPLICITY
FLEXIBILITY
PERFORMANCE
PIPELINED STAGE EXECUTION
Expandod Model
Ditfusion
Suppor！
（Mcrc CmniciTl
（Paratel/Cacre/Guontzaton）
Stago
Full Disaggregation
scamless Integration
OmniStage Abstraction
［EicederfPrefilf
Hardware Suppon
supports various 0mni-Models
Overlapping computation for
0 uecose（6ni
（varius Ba:keds）
OpenAI API, Hugging Face Models）.
VLLM-Omni HF Transformers
Easy to Use if you krow vLLM.
（c.g, Qwen-Omni,Qwen-Image）.
High Throughput
Efficient Memory Management.
BENCHMARKED EFFICIENCY
ROADMAP & DEVELOPMENT
GET STARTED & JOIN THE COMMUNITY
Installation & Examples:github.com/vlm-project/vlm-omni
Slack： #sig=omni at slack.vllm.ai
Documentation: docs.vllm.ai/projects/vllm-omni/en/latest
Weekly Meeting:Wednesday 19:30 PDT
```

## Page 005

```text
Our Goal


    Build the fastest and
    easiest-to-use open-source
    Omni-Modality model inference &
    serving engine
```

## Page 006

```text
Omni-Modality models
Omni-modality: Text, image, video, and audio data processing
Non-autoregressive Architectures: extend the AR support of vLLM to Diffusion
Transformers (DiT) and other parallel generation models
Heterogeneous outputs: from traditional text generation to multimodal outputs
```

## Page 007

```text
        vLLM-mni API (1): Omni class

         A Python interface for offline batched inference for Qwen3-Omni/Qwen-Image


            from vllm_omni import Omni                        from vllm_omni import Omni

            # Example prompts.                                # Example prompts.
            inputs = {"prompt": prompt,                       inputs = "A cup of coffee on the table“
                       "multi_modal_data": {"video":
            video_frames, "audio": audio_data,},}
            # Create an omni with HF model name.              # Create an omni with HF model name.
            omni = Omni(model=“Qwen/Qwen3-                    omni = Omni(model="Qwen/Qwen-
            Omni-30B-A3B-Instruct")                           Image-2512")
            # Generate texts and audio from the multi-
                                                              # Generate image from multi-modality
            modality inputs.
                                                              inputs.
            outputs = omni.generate(inputs)
                                                              outputs = omni.generate(inputs)


https://docs.vllm.ai/projects/vllm-omni/en/latest/examples/
```

## Page 008

```text
vLLM-Omni API (2): OpenAI-compatible server

 A FastAPI-based server for online serving for Qwen3-Omni


 Server
$ vllm serve Qwen/Qwen3-Omni-30B-A3B-Instruct --omni --port 8091

  Client
$ curl -sS -X POST http://localhost:8091/v1/chat/completions\
    -H "Content-Type: application/json" \
    -d '{
        "model": "Qwen/Qwen3-Omni-30B-A3B-Instruct",
         "messages": "Why is this video funny? "
         "sampling_params_list": $sampling_params_list,
         }'
```

## Page 009

```text
vLLM-Omni API (2): OpenAI-compatible server

  A FastAPI-based server for online serving for Qwen-Image

  Server
$ vllm serve Qwen/Qwen-Image-2512 --omni --port 8091
  Client
$ curl -X POST http://localhost:8091/v1/images/generations \
  -H "Content-Type: application/json" \
  -d '{
    "prompt": "a dragon laying over the spine of the Green Mountains of
Vermont",
    "size": "1024x1024",
    "seed": 42
  }' | jq -r '.data[0].b64_json' | base64 -d > dragon.png
```

## Page 010

```text
      vLLM-Omni serving demo
 A Gradio demo for Qwen3-Omni online   ComfyUI Integration for low-code       vllm-playground: A web interface
 serving                               development                            for interacting with vLLM servers


https://docs.vllm.ai/projects/vllm-
omni/en/latest/user_guide/examples/    https://docs.vllm.ai/projects/vllm-   https://github.com/micytao/vllm-
online_serving/qwen3_omni/             omni/en/latest/features/comfyui/      playground
```

## Page 011

```text
                          Broad Model Support
vLLM-Omni supports 30+ popular omni and diffusion model architectures(growing rapidly)


                            Qwen-Omni      BAGEL       LongCat
                            Qwen-Image


                              Z-Image      Image/3D     SD3


                                Wan         MiMo        Flux


                              StepFun       GLM       Ovis-Image

                              …plus Many more
```

## Page 012

```text
 Contributors


Thanks to all the
contributors who
raised issues,
participated in
discussions, and
submitted PRs!


                    …
```

## Page 013

```text
vLLM Github Repo
         https://github.com/vllm-project/vllm-omni
         $ uv pip install vllm --torch-backend=auto

         $ uv pip install vllm-omni


                          4000+ Stars


               Official
               release
```

## Page 014

```text
InfoO 极客传媒
QCon
全球软件开发大会
VLLM-Omni System Walkthrough
•VLLM-Omni Team
```

## Page 015

```text
Goal of the walkthrough


  1. Understand how vLLM-Omni processes a multi-
     modal request and generates its multi-modal
     outputs.

  2. Learn where to modify if you would like to make a
  specific modification/contribution.
```

## Page 016

```text
Multi-modality models   Yin, Peiqi, et al. "vLLM-Omni: Fully Disaggregated Serving for Any-to-Any Multimodal
                        Models." arXiv preprint arXiv:2602.02204 (2026).


                                            Backbone: (multi) AR + DiT
                                            Models: Qwen-Omni/Ming-Omni
                                            Tasks: any-to-any


                                            Backbone: AR + DiT
                                            Models: Qwen-Image/GLM-Image
                                            Tasks: t2i, t2v, i2i...


                                            Backbone: AR + Spec. Gen.
                                            Models: BAGEL, Hunyuan Image 3.0
                                            Tasks: t2i, i2i, i2t...
```

## Page 017

```text
Multi-modality models: AR/DiT comparison

                                  AR                              DiT
  Use cases            Text generation           Multi-modelity generation
                       Token-by-token KV Cache
  Generation process                             Diffusion step
                       based
                       Prefill: compute bound
  Bottleneck                                     Compute bound
                       Decode: memory bound
  Seq length           varied                    Fixed

  Attention Mask       causal mask               Full mask

  parallelism          TP/DP/EP/PP/CP/SP         TP/EP/USP/CFG
```

## Page 018

```text
Main architecture of vLLM-Omni
                       vLLM-Omni                            Main component：
                         EntryPoints
APIServer           Omni/AsyncOmni           OmniStage
                                                            • Entrypoints: offline/online serving,
                                                              OmniStage abstraction for model stages(AR/
              AR                            Diffusion         DiT)
          LLMEngine                       DiffusionEngine   • AR module: inherited from vLLM(CB/PA/
                                                              Prefix Cache…) and adapted to the Omni-
Scheduler          Cache Engine             Scheduler         modality model
            Executor                          Worker        • Diffusion module: implemented natively
                                                              and optimized by acceleration components
 Worker            ModelRunner             ModelRunner
                                            /Pipeline       • Model/Layer/ops: parallelism,
                                                              quantization, attention…
                       Model/Layer/Ops
                                                            • OmniConnector: natively supports E/P/D/
              OmniConnector（E/P/D/G）                          G disaggregation


       imported                modified             new
```

## Page 019

```text
                                                                                                                PR #774
    Hardware Plugin System                                              plugin entry      hardware implementation


                                  vLLM-Omni                                             Multi-Hardware Coverage:
                                                                                        CUDA/ROCm/NPU/XPU
                                     EntryPoints
                                                                                        Composable Inheritance:
                                                                                        Reuses vLLM's native platform
                AR                           Diffusion         Hardware Platform
                                                                                        capabilities(for AR) via multiple
         LLMEngine                         DiffusionEngine     current_omni_platform
                                                                                        inheritance while adding Omni-
                                                                                        specific interfaces.
 Scheduler         Cache Engine              Scheduler
                                                                       (DiT/ViT)        Unified Abstract Interface:
             Executor                          Worker              Attention Selector   current_omni_platform

    Worker             ModelRunner         ModelRunner/
                     (GPU/NPU/XPU)           Pipeline              Worker Selector      Op Dispatch:
(GPU/NPU/XPU)
                                                                                        Attention backends and custom
                                                                                        ops are dispatched per-platform
                                                              Hardware-optimized        with hardware-optimized
                     Model/Layer/Ops                                                    implementations.
                                                                   kernel
     RotaryEmbedding
                                  DiffusionAttentionBackend             Sag
      AdaLayerNorm                                            FA                 SDPA
                                                                         e
```

## Page 020

```text
AutoRegressive(AR) Module Design
                   EngineCore                             imported           modified          new

                                                    1. Handles autoregressive generation stages:
  OmniARScheduler(vLLMScheduler)
                                                    • Text generation
   schedule()                    request            • Hidden embeddings
scheduler_output           additional_information   • multimodal latent tokens (e.g.: Talker in Qwen3-Omni)
OmniNewReques
tData                       prompt_embedding

                                                    2. Extends vLLM's core to support:
                   Executor                         • Multimodal inputs/outputs: Processing images,
       GPUARWorker(GPUWorker)
                                                      videos, and audio alongside text

GPUARModelRunner(GPUModelRunner)
                                                    • Prompt Embedding: Passing pre-computed prompt
                                                      embeddings between pipeline stages via serialized
  execute_model             additional_informati      payloads
                                on payload
  Pooler_output                                     • Additional information: Carrying per-request metadata
 extract_multimo            prompt_embedding          (tensors, lists) through the pipeline
 dal_output                      payload
```

## Page 021

```text
                                                                                                                  PR #215
    Natively Disaggregated Serving                                                                                   #979

                                                                              •   Standardized Unified Abstraction: A
                                                                                  generalized interface that handles
                     Omni(global scheduler)                                       heterogeneous data (Text, Image, Audio).

                                                                              •   Control & Data Plane Decoupling:
OmniStage-1                     OmniStage-2              OmniStage-K              Metadata travels via lightweight control
                                                                                  signals, while heavy payloads are
  Scheduler                       Scheduler                Scheduler
                                                                                  offloaded to high-performance data planes.
   Worker                           Worker                  Worker
                                                                              •   Hybrid Backend Support: Native support
                                                                                  for Shared Memory (SHM) and Mooncake
 ModelRunner                     ModelRunner              ModelRunner             for distributed transfers.
                                                     …
OmniConnector                   OmniConnector            OmniConnector        •   Disaggregated Multi-Modal Execution:
                                                                                  Enables seamless communication
               N_1                             N_2                      N_k       between decoupled stages.

                                 Memory Pool                                  •   Multi-Instance Scaling: Supports multiple
                                                                                  instances for each omni stage, enabling
                                Transfer engine                                   elastic deployment and efficient load
                                                                                  distribution across distributed clusters.
               Meta data flow          D2H2D flow          D2D flow
```

## Page 022

```text
When requests arrive

     Example: Qwen3-Omni


                   Code2Wav


        AR-decoder(Talker)


       AR-decoder(Thinker)


    Text        Visual        Audio
  Tokenizer    Encoder       Encoder
```

## Page 023

```text
                                                                       PR #367
Async Chunk & Audio Streaming Output                                      #727
                                                                          #951
                                                                          #1438


                                        • Pipeline Between Stages:
                                          Asynchronous chunked computation
                                          and communication across stages

                                        • Audio Streaming Output: The
                                          waveform is output immediately after
                                          Talker generates each token.

                                        • APIServer Support: OpenAI v1/chat/
                                          completions with “stream” argument


E2E generation   Streaming generation
```

## Page 024

```text
                       Async Chunk & Audio Streaming Output
     •     Qwen3-Omni


   1 / 10 concurrency: 12.4x / 8.2x improves                                1 / 10 concurrency: 1.1 x / 1.2 x improves

https://docs.vllm.ai/projects/vllm-omni/en/latest/design/feature/async_chunk_design/
```

## Page 025

```text
                                                                                    PR #939
Scaling Disaggregated Serving
  Example Multi-Node Deployment Diagram


                                          • Command Line Interface (CLI) Design (PR
                                            #939)

                                          • Distributed Deployment Structure
                                             a. Multiple APIServers (PR #939)
                                             b. DP based Scaling for OmniStage
                                             c. Coordinator for global management

                                          • Scheduling & Routing for load balancing
```

## Page 026

```text
  Omni-Modality models Acceleration Support


                    Output          Disaggregated
        Model                                           Streaming       Async chunk       CUDA graph       Gradio demo
                   Modalities        deployment
Qwen2.5-Omni    Text/Audio      ✅                   Only text       ❌                 ❌                ✅

Qwen3-Omni      Text/Audio      ✅                   ✅               ✅                 ✅                ✅

MiMo-Audio      Text/Audio      ✅                   ✅               ✅                 ✅                ❌

Qwen3-TTS       Audio           ✅                   ✅               ✅                 ✅                ⏳

Bagel           Text/Image      ✅                   Only text       N/A               Only AR          ✅

GLM-Image       Image           ✅                   N/A             N/A               ✅                ⏳
```

## Page 027

```text
                                                 Diffusion Module Design
                                                                                     vllm import            native             Third-party
                          DiffusionEngine
                               Scheduler
                                                                                               Diffusion Core
                                                                             •   Natively implemented and optimized by configuring
                           Diffusion Worker                                      the acceleration layer
                        Diffusion Model Runner
                                                                             •   Aligned with the AR arch with model_runner
                                                                                 abstraction
                           Diffusion Pipeline
                                                                             •   Support step-wise scheduler with continuous batch
                           N-step Sampling                                       for higher SLA
                embed                               latent
   Prompt                                                       VAE          •   Connect with AR module to speed up AR+DIT model
   Encode                          DiT                         Decode            inference with OmniConnector

                                                                                        Acceleration Features
                         Acceleration Features                               •   Cache backend: Cache-DiT, TeaCache…
Cache Backend                 Parallelism
                                                                             •   Parallelism: TP/HSDP/SP/CFG/VAE…
                    TP                                       Quantization    •   Attention: interface abstraction for third-party
  CacheDiT                                                   (FP8/GGUF)
                   HSDP       SP         CFG     VAE                             integration(FA/SAGE/MindIE-SD…)
  TeaCache                                                                   •   Quantization: FP8/GGUF…
                           Attention Backend                  CPU Offload    •   CPU Offload: module-wise/layer-wise
 Extensions                                                  (module-wise,   •   Extensions: LoRA
                    SDPA           FA          Sparse
    LoRA                                                       layerwise)
```

## Page 028

```text
    When requests arrive
  Request mm prompt:
  “Make it play guitar”
                                 Omni
                          vllm_omni/entrypoints/
                                 omni.py
generated image/
                                                         postprocess
     video
                          OmniDiffusion                DiffusionEngine                      DiffusionWorker
                          vllm_omni/diffusion/          vllm_omni/diffusion/               vllm_omni/diffusion/worker/
                            omni_diffusion.py           diffusion_engine.py                    diffusion_worker.py


              •    Convert user inputs into        •    Preprocess
                   OmniDiffusionRequest            •    Add to the scheduler’s
                                                        waiting queue                    Worker.model_runner
              •    Initialize DiffusionEngine                                               vllm_omni/diffusion/worker/
                                                                                                diffusion_runner.py

                                                          Scheduler
                                                        vllm_omni/diffusion/
                                                            schedule.py
                                                                                          ModelRunner.pipeline
                                                                                             vllm_omni/diffusion/models
                                                                                             pipeline_{model}_{task}.py
                                                                               ● Waiting request queue
                                                                               ● Running request queue
                                                                               ● FIFO
```

## Page 029

```text
          Diffusion modules with Acceleration Support
          •     X2I                  •⏳ = in progress (PR under review) •✅ = supported       •❌ = not yet supported

                                              SP (Ulysses &                                     CPU Offload
        Model         TeaCache   cache-DiT                    CFG-Parallel    Tensor-Parallel               VAE-Patch-Parallel FP8-Quantization
                                                  Ring)                                         (Layerwise)
Bagel                 ✅          ✅           ❌                ❌              ✅                  ❌            ❌                ❌
FLUX.1-dev            ⏳          ✅           ❌                ✅              ✅                  ❌            ❌                ❌
FLUX.2-klein          ⏳          ⏳           ⏳                ✅              ✅                  ❌            ❌                ❌
GLM-Image             ❌          ⏳           ❌                ❌              ❌                  ❌            ❌                ❌
LongCat-Image         ❌          ✅           ✅                ✅              ✅                  ❌            ❌                ❌
LongCat-Image-Edit    ❌          ✅           ✅                ✅              ✅                  ❌            ❌                ❌
Ovis-Image            ❌          ✅           ❌                ✅              ⏳                  ❌            ❌                ❌
Qwen-Image            ✅          ✅           ✅                ✅              ✅                  ✅            ❌                ✅
Qwen-Image-2512       ✅          ✅           ✅                ✅              ✅                  ✅            ❌                ✅
Qwen-Image-Edit       ✅          ✅           ✅                ✅              ✅                  ✅            ❌                ❌
Qwen-Image-
                      ✅          ✅           ✅                ✅              ✅                  ✅            ❌                ❌
Edit-2509
Qwen-Image-
                      ❌          ✅           ✅                ✅              ✅                  ✅            ❌                ❌
Layered
Stable-Diffusion3.5   ⏳          ✅           ⏳                ✅              ✅                  ❌            ❌                ❌
Z-Image               ✅          ✅           ✅                ❌              ✅ (TP=2 only)      ❌            ✅                ✅
```

## Page 030

```text
Summary


1. Support Omni-Modality model inference & serving
2. Consistent and unified API interface with vLLM

3. Native disaggregated deployment for different model stages

4. Pipeline async streaming for multiple stage engines

5. Native support for diffusion stage acceleration
```

## Page 031

```text
Latest Release and Schedule


                  •   RC version
                     Inherited new features from latest vLLM
                      Matched with vLLM formal release (e.g. v0.19.0rc1
                  released on Apr 04, 2026 for vLLM v0.19.0)

                  •   Formal version
                      New features with sufficient tests
                      Every 4 weeks (e.g. v0.18.0 released on Mar 28, 2026)
```

## Page 032

```text
InfoO 极客传
QCon
全球软件开发大会
VLLM-Omni Roadmap
•VLLM-Omni Team
```

## Page 033

```text
 Community collaboration

● Day-0 Support for xx
● Hardware support
● RL integration with veRL&veOmni
```

## Page 034

```text
     Future Roadmap (Overview)
https://github.com/vllm-project/vllm-omni/issues/2136

                                                        P0:
   •CI/CD: Performance monitoring
   •Streaming input and multi-turn
   •Large scale deployment
   •Full disaggregation(OmniConnector&OmniRouter…)
   •RL Integration

                                  P1:
   •Wider model support(Omni&DiT&World model…)
   •Diffusers backend support
   •ModelRunnerV2 support
   •Diffusion continuous batching
```

## Page 035

```text
vLLM-Omni Networking Hour!

   https://github.com/vllm-
   project/vllm-omni

   https://blog.vllm.ai/
   2025/11/30/vllm-omni.html

   https://github.com/vllm-
   project/vllm-omni/blob/
   main/docs/assets/WeChat.jpg
```

## Page 036

```text
InfoQ 极客传媒
QCon
全球软件开发大会
THANKS
大模型正在重新定义软件
Large Language Model Is Redefining The Software
```

## Page 037

```text
上
探索 AI 应用边界
AiCon
Explore the limits of Al applications
全球人工智能开发与应用大会
2026年6月26-27日/上海张江科学会堂
专题：世界模型与多模态智能突破
专题：Agent 系统架构与工程化实践
专题出品人：未政
专题出品人：鲁洁楠
极佳视界/联合创始人& 首席科学家
OPPO/大模型算法员责人
专题：AI 原生数据工程
专题：Agent 安全、评测与可信治理
专题出品人：王彦辉
专题出品人：马传雷（岳立）
火山引擎 /数智平台产品总脂
支付宝/业务风险技术部员责人
专题：Agent 数据、记忆与运行时
专题：企业级研发体系的重构
基础设施
专题出品人：沈浪
专题出品人：邓亚峰
快手/ 研发效能员责人
EverMind /CEO
```
