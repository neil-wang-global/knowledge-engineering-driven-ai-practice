# 林瑞虹-生成式-UI-AI-交互新模式探索

来源PDF：`references/papers/林瑞虹-生成式 UI ：AI 交互新模式探索.pdf`
页面图像目录：`references/paper-visual/images/林瑞虹-生成式-UI-AI-交互新模式探索/`

说明：以下为按页信息提取，尽量保留页面可见文字、标题、列表、表格与图示标签。
## Page 001

```text
InfoO 极客传媒
QCon
全球软件开发大会
生成式UI：AI交互新模式探索
林瑞虹
云软件体验技术团队（华为）/高级开发工程师
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
InfoQ 极客传媒
QCon
全球软件开发大会
生成式UI——开启AI交互新模式
02
生成式UI 原理与基于场景落地扩展
目录
03
协议对比与标准化争论
```

## Page 004

```text
生成式UI
-开启AI交互新模式
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 005

```text
改善文本对话体验，可视化直观清晰
传统AI交互多为高密度长文本流，理解成本高。生成式UI能自动将文本转化为柱状图、饼图等可视化图表，大幅提升信息获取效率。


                                               信息降维
                                               将复杂数据转化为视觉语言


                                               直观高效
                                               一眼识别关键趋势与结论


                                               自动生成
                                               无需手动操作，AI 实时渲染


    Markdown效果               使用生成式UI
```

## Page 006

```text
 优化多轮信息交互， 贴合业务降低门槛
在多轮对话中，用户需要反复输入指令来确认选项，过程繁琐。生成式UI可以直接生成可视化的选择界面，用户通过点击即可完成操作，
大大简化了交互流程，降低了用户的使用门槛，让AI交互更贴合实际业务场景


                                文本交互                    可视化UI
                                繁琐指令输入                  一键点击操作
```

## Page 007

```text
 千人千面实时渲染，告别“预制”轻松调整
生成式UI打破传统“预制”限制，基于用户偏好实时渲染内容。无论是严谨的专业报告，还是活泼的演示文稿，只需简单指令即可一键
切换文案、配色与布局，实现真正的个性化体验。


                       严谨专业                             活泼生动
```

## Page 008

```text
OpenTiny GenUI SDK 多轮对话案例


官网： https://opentiny.design/genui-sdk
Github： https://github.com/opentiny/genui-sdk
```

## Page 009

```text
原理与场景落地
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 010

```text
原理与场景落地
】 生成式UI实现原理
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 011

```text
UI是如何生成的？


                            组件库


                                                  UI的生成过程

     用户输入      大模型处理       渲染器解析        生成用户界面


                                                 生成式UI核心组件
               系统提示词：             流式渲染器：
            引导到模型分析用户意图，     解析大模型输出内容进行动态渲染，
              以特定格式回复           映射声明到对应组件
```

## Page 012

```text
核心原理机制解析


   结构化输出              流式增量渲染            缓冲保护区

大模型输出结构化的UI描述信息，   前端接收到部分结构信息后即可开   建立数据校验机制，过滤掉不完整
而非纯文本，为前端渲染提供清晰    始渲染，无需等待完整数据，大幅   或错误的信息，确保界面渲染的稳
指令。                提升用户体验。           定性和正确性。
```

## Page 013

```text
    原理：始于结构化输出
     大模型结构化输出三种形式                                          基于JSON的声明式UI

                                                         低代码平台                       页面协议
                  Chat Request （OpenAI）:
                   {…, response_format: {
          指定格式       type: ‘json_schema’,                                      {
                                                                                   "componentName": "Page",
                     json_schema: { schema: { xxx }}
                  }}                                                               "state": {},
                                                                                   "children": [
                                                                                     {
                                                                                        "componentName": ”div",
                                                                                        "props”: {
                                                                                         }
                                                                                         // …
                   Chat Request:
                                                                                     },
                   {…, tools: [{ …, parameters: {                                    //…
          工具调用        type: ‘object’,
                                                           TinyEngine低代码引擎     }
                                                                                   ]
                      properties: { xxx }
                   }}, …]}


                  System prompt:
         系统提示词
✅                 You are a helpful assistant. …
                                                                    +
           约束     Please response in following format:
                    xxx
                                                           渲染器               UI描述协议

     相同点：可以使用 JSON Schema 描述结构化输出                                 生成式UI


         采用低代码协议，通过声明式UI的结构化输出和渲染，实现AI自主展示UI界面
```

## Page 014

```text
      原理：流式增量渲染
                大模型输出特点：流式                                     实现局部增量渲染
                                                                                            全量渲染
{                                                 前序
    "componentName": "Page",
    "children": [                                 Text               Text                   Text
      {
                            ”Text",
         "componentName": "Text",                                                           Text
         "props”: {                               当前
            “text”:"Hello,
            “text": ”Hello, World!”
                           World!”
          }                                        Text，Text
    ]
      },                                    ❌
}
                                      渲染器
                                                                                            增量渲染
        完整的JSON
       不完整的JSON                                   前序             已有 = 前序

                                                  Text           Text               Text      Text
{
    "componentName": "Page",                                      = 当前 – 已有；diff              Text
    "children": [                                 当前             已有 = 已有 + ;patch
      {
        "componentName": "Text",                   Text，Text     Text，Text
        "props" : {

        }
           “text”: ”Hello, ”
                                            ✅
      }
    ]                                 渲染器                通过diff-patch实现仅追加变更集，维持内存稳定
}


    通过fixJson闭合JSON
                                                减少内存占用           避免全量重绘                    复杂场景高性能
```

## Page 015

```text
     原理：缓冲保护区
                                              无缓冲渲染场景
  输入              缓冲过滤池             输出
                                              1   信息展示型字符串 ✅
       Δ1                         Δ1              {"componentName": "Text", "props": { "text": "Hello World" }}
                非最后更新元素，通过               Δ’   2   枚举类型字符串            ❌
 Δ     Δ2                         Δ2
                                                  {"componentName": "TinyButton"}

       Δ3      输出未完成且匹配到规则，拦截                 3   资源地址 ❌
                （等下一轮或者输出完成）
                                                  {"componentName": "img", "props": { "src":
                                                  "http://example.com/foobar.png" }}
     缓冲保护区简化原理图：削减不完整信息引起的错误与不必要的渲染
                                              4   表达式/函数声明 ❌
                                                  {"type": "JSFunction", "value": "function()
缓冲保护区核心机制：                                        { console.log('foo') }"}
从 Delta 变化集中获取当前最后一个变化中的值，
                                              缓冲规则示例
• 如果该值匹配到了缓冲规则，则拦截从 Delta 变化集删除该变化不体现，仅推送其他
 非最后的更新；
                                              1    componentName

• 被删除的变化需要等待下一轮更新，当全部更新完毕或者变化值不是最后一条变化值       2    [componentName=img] > props > src
 时，可以推送该更新。
                                              3    [type=JSFunction] >
                                                   value
     拦截异常信息 · 保障渲染稳定 · 降低系统开销                 采用JSON路径的selector语法，类似CSS selector语法
```

## Page 016

```text
原理与场景落地
2 场地落地扩展
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 017

```text
场景落地述求下的扩展


  物料可定制扩展            交互上下文扩展           生成式 MiniApp

支持品牌自定义组件和样式，让生    能够理解并融合业务上下文信息，   突破单一组件限制，从生成UI片段
成的UI更符合品牌形象，实现个性   提供更智能的交互逻辑，提升用户   扩展到生成完整的小程序应用，覆
化视觉表达。             操作的连贯性。           盖全链路场景。
```

## Page 018

```text
物料可定制扩展：更懂品牌与业务
企业可以将自己的品牌组件库接入系统，AI在生成UI时会优先使用这些品牌物料，确保视觉风格的统一性，让每一次生
成都符合品牌规范。通过定制业务物料，解决复杂场景问题。

       品牌调性                          业务场景
 华为云          内部系统            拓扑图            员工接口搜索框


                 物料可定制可扩展，多技术栈支持
```

## Page 019

```text
         物料可定制扩展实现

             Server                  Web            Before 内置
                                                                         组件集合

                                                                          渲染器
                                 <genui-renderer
Before       Prompt
                                 content=“…”                               协议
                                 >

                        运行时动态化                                       多技术栈多物料支持
                                                    After 解耦开放

         genPrompt( {         <genui-renderer                                                     ……
                                                      TinyVue物料包    Element物料包   TinyNg物料包
                               :content=“…”
After    customComponent       :customComponents=                                    Angular渲染器        ……
         s,                   “…”                               Vue渲染器
            customSnipets,    >
            customExamples,                                                 协议
         })

                      支持运行时动态追加组件                               将协议、渲染器、物料包实现分层解耦
```

## Page 020

```text
  交互上下文扩展：跳出对话框，融合业务


  对话框内交互             对话框与对话框外的交互                 无对话框的交互
支持通过卡片交互自动触发对话   支持在对话助手中的卡片交互触发页面的其他模块的功能   支持生成式内容与非生成式内容进行交互
```

## Page 021

```text
交互上下文扩展实现
初版实现：专门为表单提交场景触                   通用化实现：抽取Action，继续对话仅为其中一种Action
发继续对话设计的方案

    提交                 提交         Actions
 TinyButton        ActionButton             继续对话            保存状态         ……


  对话组件
         provide(对话服务，……)
                                  系统提示词                            渲染器
                                  当前系统有以下Action可以调用，参数
                                  说明为：
                                                                   <genui-renderer
      ActionButton                 ….                               :content=“…”
         inject(对话服务，……)                                            :customActions=“…”
                                  规则：
                                  - 表单提交场景请使用 继续对话Action;
                                                                   >
         onClick = 对话服务.Chat
                                  示例：
                                  -
                                  this.callAction(‘continueCha
                                  t’,….)
提供一个特殊的按钮组件，点击的时候自动               提供一个通用Action上下文工具，通过系统提示词告诉大模型有哪些
触发上下文的继续对话函数调用                    Action，参数是什么，如何调用，并在渲染器完成调用
```

## Page 022

```text
延长线：生成式 MiniApp， 共享对话生成应用


  AI 应用平台与生成式小程序          对话生成应用


       AI 驱动生成     即时可用     一键分享协作
```

## Page 023

```text
生成式MiniApp构建器
                                                       规划与畅想
 对话生成应用         当前进度           深度讨论规格生成应用                  生成AI接管的原生应用
  Vibe Coding                  Spec-driven Coding              AI Native MiniApp


        支持局部修改的操作协议        ✅          多轮对话收集需求，意图追问                   AI 编写Action，完成交
                                                                          互与API调用

        支持局部选中修改       ✅               根据需求拆解生成规格文档
                                                                       API 正常数据直接展示

       API/工具/Mock访问与对接                根据规格生成MiniApp
                                                                      API 异常数据由AI接管，
                                                                           AI决策下一步
       应用分享与API工具授权                    增量需求和手动修改文档

                                                                       将已有的小程序作为模
        数据隔离与持久化                      Sub-Agent并发执行                     版，实时内嵌调用


        版本管理    ✅                     支持多页嵌套与路由

                                                               AI原生应用平台与调度Agent
   可视化氛围编程Agent                     规格驱动编程Agent
```

## Page 024

```text
 生成式MiniApp构建器 操作协议的优化分享（树状结构适用）

JSON Diff Patch Delta 协议              RFC 6902 JSON Patch 协议                 RFC 6902变体&强制ID索引
协议简化描述                                 协议简化描述                               协议简化描述

 增：path: [ newValue ]                 增：{ op:”add”, path:””,value: ””}      增：{ op:”add”, id:””,
 删：_path: [ originValue, 0, 0]        删：{ op:”remove”, path:””}             path:””,value: ””}
 改：path: [newValue, originValue]      改：{ op:”replace”, path:””,value:””}   删：{ op:”remove”, id:””,path:””}
 移：path: ['', newIndex, oldIndex]     移：{ op:”move”, from: “”,path:””}      改：{ op:”replace”, id: “”,
                                                                            path:””,value:””}
                                                                            移：{ op:”move”, id: “”, pisitionId:””,
协议优势： 表达唯一                             协议优势： 简单易懂                           position:
                                                                            协议优势：     通过增加id减少path长
                                                                            “before”|”after”|”append”}
                                                                            度，且比较容易转换成RFC6902
生成效果问题：                                生成效果问题：
                                                                            生成效果改善：
 1.     Path中数组下标识别糟糕                  1.   Path中数组下标识别糟糕
                                                                            1.   由于不依赖数组下标，生成效果有
      比如： children: { 3: [xxx]}, 长数     比如： {op: ‘remove’, path:
      组经常下标错误导致无法操作
                                                                                 较大幅度改善，但是需要手动计算
                                        ‘/children/0/children/2/children/
                                        3’}
                                                                            遗留问题：
 2.     删除操作经常无法写对                      长数组经常下标错误导致无法操作, l并
                                        且路径越长，下标就越多出错                       1.   大模型理解不正确的情况仍存在，需
  比如： children: { _2: [xxx, 0,
  0]}, 经常会写成 children: { 2:
                                       2.   连续操作后对下标影响难以修正                       要使用更简单的表述
  [xxx, 0, 0]}, 导致不能正确删除                比如：先删除数组第一个元素(index                      比如： 交换位置1和位置3元素， 不如告诉
                                        0)再操作第三个元素（index 2 -                     到模型吧1移动到2后面，把3移动到2前面
                                        >1），输出为2导致连续操作失败
```

## Page 025

```text
原理与场景落地
度量指标与局限性
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 026

```text
 AI 生成内容难保证，何时投放商用？

用户声音

   大模型生成内容不稳定，有时候会输出不正确的内容，导致无法使用。       内容正确性


   简短小卡片输出速度还可以，稍微长一点的内容生成很慢。        用户使用体验


   这个系统提示词很费token，有没有办法优化？   经济与效益


   为什么这个模型输出的时候好好的，换了另一家模型，这个输出就不对了。          大模型差异
```

## Page 027

```text
生成式UI的度量指标：性能指标体系探索


   核心思路：借鉴大模型成熟的 TTFT/TPOT 指标体系，构建生成式UI的用户体验性能衡量标准。


   关键指标一：首屏反馈时间                     关键指标二：渐进式渲染效率

定义：用户从提交请求到看到第一个有效可视化反馈的时间。      定义：首个元素出现后，后续UI组件逐步呈现的节奏与间隔。
意义：替代传统“三秒原则”，决定用户体验的第一印象。       意义：衡量生成流畅度，类似大模型的Token流式输出体验。


优化策略
1. 尽可能优先输出有效的可视化的元素，或者引入一些骨架，让问答专注输出
2. 尽可能简化组件的使用配置项，把常用配置项作为默认值无需配置，增强局部片段引用等
3. 压缩系统提示（渐进式披露），压缩上下文对话（总结），保持上下文使用率中健康的空间
```

## Page 028

```text
生成式UI的度量指标：信息表达能力


   指标一：UI 的可用度                    指标二：Token效率
核心定义：评估生成的UI界面是否具备完成目标任务的      核心定义：衡量生成UI消耗的计算资源(Token)与其传递
实际能力。                          信息价值的比率。

评估维度：                          评估维度：
• 完整性：界面元素完整，无缺失或错误组件          • 信息密度：对比纯文本，Token消耗是否合理
• 功能性：交互逻辑正常，按钮表单响应正确          • Token构成：区分排版Token与核心内容Token的比例
• 信息充分性：提供完成任务所需的全部关键信息
                               核心意义：追求最经济的Token成本与最高效的信息传
核心意义：确保UI不仅“像”，更要“能用”，是业务      达，平衡体验与消耗。
价值实现的基础。


可用度兜底策略                        Token消耗优化策略
1. Zod校验确保UI可用，使用回落文本回复等方式兜底   1. 通过渐进式披露和搜索策略展示组件信息和示例
2. 信息收集场景通过二次确认，确保信息无误再执行      2. 提供一些快速美观排版组件减少大模型在样式token消耗
                               3. 避免长数据大模型复述
```

## Page 029

```text
应用场景局限性


   长数据列表展示               超复杂应用界面              重复生成场景

局限性：大模型逐行输出效率低，导      局限性：逻辑复杂难以一次生成，上     局限性：重复生成浪费Token，且难
致用户体验极差。              下文限制导致无法单次完成。        以保证连续场景的一致性。


解法：                   解法：                  解法：
• 内置法：直接推送数据，避免复述     • 复杂度前移：任务拆分与多轮迭代    • 预生成：存储常见UI，叠加修改
• 编程法：定义API，初始化自行调用   • 片段引用：引用已有片段，压缩输出   • 前序引用：引用局部UI，追加微调
```

## Page 030

```text
协议对比与标准化争论
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 031

```text
协议对比与标准化争论
】协议对比
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 032

```text
 生成式UI的范畴与技术流派

   ？
         目前有很多“生成式UI （Generative UI）” 框架，相似又有许多不同。
         那么到底什么是生成式UI ？这些框架又有什么区别呢？应该如何选择？


 范畴思考：HTML/Markdown是否属于生成式UI？符合“声明式描述”与“流式渲染”特征。
 广义定义：任何由AI生成、用于描述和渲染用户界面的结构化信息，均可纳入生成式UI范畴。


    源码生成渲染型                    声明式UI                      数据驱动UI更新

                                                       代表：agui
代表：灵光闪应用
                           代表：TinyGenUI, a2ui, cosui   模式：UI界面预定义，模型仅推送状态变更数
特点：大模型直接生成前端源码（如
                           特点：生成JSON等声明式描述，由特定渲染       据。
HTML、Vue、React），后端/浏览器端动
                           器解析。                        特点：模型仅负责数据逻辑，不直接控制界面
态构建，最终在浏览器端渲染。
                           分析：组件与配置受限，可控性强；流式渲染        结构。
分析：发挥空间大但UI难约束；多不支持流
                           依赖解析器能力。                    分析：灵活性低，但安全性高；UI变化被限制
式渲染，需等待完整编译。
                                                       在预设范围内。
```

## Page 033

```text
声明式协议对比

                                           生成式UI 声明式协议对比
对比维度                   Tiny GenUI                             A2UI                 Cosui
          通过树状数据结构嵌套；                           通过索引实现UI嵌套；          树状嵌套；
UI 描述能力   仅支持深度优先先后渲染；                          渲染顺序可以自定义            具备局部刷新能力
          需要补充局部刷新操作协议                          具备局部刷新能力
          { type: JSExpression,                 /foo/bar (scope)     {{foo.bar}}
数据绑定形式     value: this.state.foo || scope.foo
          }
          JS方法 + 运行时自定义Action                   仅通过Action与大模型对话      compile阶段传入自定义Action
事件通信模式

          JS方法灵活度高，可能引入安全风险 后端接收用户操作行为描述，缺少及时 通过Action约束，较为安全，灵活度
安全约束                        反馈行为，需要通过大模型更新界面， 较低

          支持现有组件库（Vue、Angular）                  需要继承渲染器，需改造适配，存在一 支持San框架的组件库
物料扩展能力                                          定的耦合
```

## Page 034

```text
        协议转换： A2UI协议 转 TinyGenUI协议
[                                            {                                               {
    {                                                   "id": "simple-button",                  "componentName": "Page",
      "beginRendering": {                               "component": {                          "props": {                                   {
         "surfaceId": "simple-input-                       "Button": {                             "className": "simple-input-                            "id": "simple-button",
button-surface",                                             "child": "button-               button-surface-page"                                         "componentName": "TinyButton",
         "root": "simple-row",              text",                                              },                                                        "props": {
         "styles": {                                            "primary": false,   UI声明转换      "css": ".simple-input-button-
                                                                                             surface-page {\n                      font:
                                                                                                                                                             "onClick": {
            "font": "system-ui, -apple-                         "action": {                                                                                    "type": "JSFunction",
system, sans-serif",                                               "name":                   system-ui, -apple-system, sans-                                   "value": "function()
            "primaryColor": "#3b82f6"       "button_clicked",                                serif;\nprimaryColor:                          { this.callAction('continueChat', { message:
         }                                                       "context":                  #3b82f6;\n                    }",              'button_clicked' + JSON.stringify([['value',
      }                                     [ {"key": "value", "value": {"path":                "children": [                               this.state.inputValue]]) })}"
   },                                       "/inputValue"}}]                                       {                                                         }
   {                                                           }                                      "id": "simple-row",                                 },
      "surfaceUpdate": {                                     }                      物料转换              "componentName": "div",
                                                                                                      "props": {
                                                                                                                                                          "children": [
         "surfaceId": "simple-input-                      }                                                                                                  {
button-surface",                                       },                                                "style": "display: flex; flex-                        "id": "button-text",
         "components": [                               {                                     direction: row; gap: 8px; justify-                                "componentName": "Text",
            {                                             "id": "button-text",               content: start;align-items: center;"                              "props": {
               "id": "simple-row",                        "component": {"Text":                       },                                                          "text": "按钮"
               "component": {"Row":         {"text": {"literalString": "按钮                            "children": [                                            }
                                                                                                         {
{"children": {"explicitList": ["simple-
input","simple-button"]},"distribution":
                                            "},"usageHint": "body"}}
                                                       }
                                                                                    数据转换                    "id": "simple-input",                         ]
                                                                                                                                                             }

"start","alignment": "center"}}                     ]                                                       "componentName":                            }
            },                                    }                                          "TinyInput",                                             ]
            {                                  },                                                           "props": {                            }
               "id": "simple-input",           {                                                               "label": "输入",                  ],
               "component": {"TextField":         "dataModelUpdate": {                                         "placeholder": "输入",            "state": {
                                                                                                               "modelValue": {
{"label": {"literalString": "输入"},
"text": {"path": "/inputValue"},
                                                    "surfaceId": "simple-input-
                                            button-surface",
                                                                                    事件转换                          "type": "JSExpression",      },
                                                                                                                                                    "inputValue": ""

"textFieldType": "shortText"}                       "contents": [{"key":                                          "value":                  }
               }                            "inputValue","valueString": ""}                  "this.state.inputValue",
            },                                      ]                                                             "model": true
                                                  }                                                            }
                                               }                                                            }
                                            ]                                                            },
                    因TinyGenUI支持JS方法，A2UI协议抽象的方法定义和数据处理均可转换更底层JS函数处理。
```

## Page 035

```text
协议对比与标准化争论
2标准化争论
QCon
InfoQ 极客传媒
全球软件开发大会
```

## Page 036

```text
标准化争论焦点：是否只支持原生HTML元素？
                                           Generative UI 标准化，是否也要把
                                           UI组件定义标准化？ 然后映射到不同
                                           的OS开发框架的UI。
在生成式UI的标准化讨论中，一个核心的争论点是：标
准化的UI描述协议是否应该只支持浏览器原生的HTML                     以Google A2UI为例，预定义组件
元素/一个固定子集，还是应该允许扩展自定义的业务组                      是通过Catalog声明，A2UI中还是
                                               保留了自定义Catalog。
件。

                                           框架的作用是为了减少人类开发者的
                                           负担，但生成式UI当中已经不存在人
     核心矛盾：通用性 (HTML) 与 业务表达力 (自定义组件) 的权衡   类开发者这个角色，那么生成的结果
                                           为何要基于框架？


                                               前端框架的作用不仅仅减少人类开发
                                               者的负担，也能降低AI的负担，一个
                                               复杂交互功能的MiniApp，AI从零
                                               写，token消耗大，错误率也会大大
                                               提升。

                                           一旦支持定制，跨端跨系统就难适配
```

## Page 037

```text
标准化争论焦点：是否只支持原生HTML元素？


正方观点：拥抱原生，保持标准简洁                                                          反方观点：开放扩展，满足业务需求

  浏览器内核相关标准应该与框架无关                                                           协议应保持开放可扩展
  标准化应专注于底层能力，避免与特定前端框                                                       业务需求千变万化，需要协议具备足够的灵活
  架绑定，确保技术中立性。                                                               性来支持自定义组件，避免被标准束缚。
                                                   e Ne
  组件应当限制在通用范围                           a   ti v          ga                 业务侧有更多复杂诉求
                                                               ti v
  只支持原生HTML元素可以保证标准的通用性      f   i rm                                 e      复杂的业务场景需要专门的业务组件和上下文
  和稳定性，避免过度复杂导致的兼容问题。     Af                                                 支持，原生元素无法满足深度业务逻辑。


  标准化应围绕现有标准组件                                                               仅有原生HTML元素效果差
  基于现有的Web标准进行扩展，更容易被开                                                       仅使用原生HTML会导致AI生成速度慢、稳定
  发者广泛接受和浏览器厂商实现。                                                            性差，且难以满足严格的品牌视觉约束
```

## Page 038

```text
案例分析：业务高级搜索框


 高度复杂的交互逻辑
 包含多条件筛选、动态加载选项及联动交
 互，非简单静态页面。


 原生HTML构建的局限性
 AI难以一次性生成正确的结构与逻辑，不仅
 效率低，且难以满足品牌视觉规范。


 观点支撑
 此类复杂业务组件有力证明了“纯AI原生生
 成”在实际开发中存在显著短板。


                        业务高级搜索框 UI 界面
```

## Page 039

```text
总结


 生成式UI通过将AI的能力从文本生成扩展到界面生成，极大地提升了人机交互的效率
 和体验，是AI交互的重要演进方向。尽管在应用落地方面仍有挑战，但它的潜力巨
 大，值得我们持续探索和投入。


     Github: opentiny/genui-sdk   公众号: OpenTiny   欢迎star与关注
```

## Page 040

```text
InfoQ 极客传媒
QCon
全球软件开发大会
THANKS
大模型正在重新定义软件
Large Language Model Is Redefining The
Software
```

## Page 041

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
