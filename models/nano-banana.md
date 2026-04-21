# Nano Banana (Gemini 2.5 Flash Image) 深度档案

> 模型 ID：`gemini-2.5-flash-image`（稳定版，2025-10 升级至生产就绪）
> 上代号：Nano Banana | 原始发布：2025-08-26
> 升级版本：**Nano Banana Pro**（`gemini-3-pro-image-preview`）2025-11-20 发布
> 研发方：Google DeepMind / Google AI

## 1. 模型定位与技术归属

- **归属**：Google DeepMind，属于 Gemini 2.5 Flash 家族中的图像分支。[1][2]
- **发布时间**：2025 年 8 月 26 日，以 `gemini-2.5-flash-image-preview` 先行对外；2025 年 10 月进入生产就绪（GA），新增多档长宽比与更高分辨率上限。[1][2]
- **为什么叫 Nano Banana**：在 LMArena 匿名 Image Arena 测试阶段，该模型以"能把香蕉、各种奇怪物体变形为一致角色"的多轮编辑效果爆火，社区戏称 "Nano Banana"，Google 后续在官方传播中采用了该昵称。[1][3]
- **技术路线**：**原生多模态 LLM**，通过自回归方式输出图像 token，与传统基于扩散/流匹配的图像模型在原理上根本不同。这使其天然具备"用语言精准描述、局部编辑、多轮对话保持状态"的能力。[1][3]

## 2. 核心能力

### 2.1 对话式编辑与多轮一致性
- 可以通过自然语言进行多轮局部编辑，在整条对话线内**保持人物/主体/布景一致**，这是其对扩散模型最大的差异化优势。[1][3]
- 支持多图融合（multi-image fusion）：一次上传多张图，模型按指令合成新场景，角色、光线、比例保持一致。[3]

### 2.2 局部/精准编辑
- 可指定区域修改，其余部分保持不变（不依赖显式 mask）。[3]

### 2.3 文字渲染
- 2.5 Flash Image 版本的文字渲染良好但并非最强；在 **Nano Banana Pro**（Gemini 3 Pro Image）上大幅提升，达到"SOTA 级清晰文字、在图中嵌入多语言长文本"的水平。[4][5]

### 2.4 世界知识
- 由底层 LLM 继承知识（知识截止约 2025-06），可基于事实生成（例如"画一张 2023 F1 西班牙大奖赛起跑格位"），Pro 版进一步支持 **Grounding with Google Search**，保证时效准确性。[2][4]

### 2.5 SynthID 水印
- 所有输出默认加上**不可见的 SynthID 水印**；Nano Banana Pro 版开始进一步叠加 **C2PA Content Credentials** 元数据，便于来源溯源。[4][5]

### 2.6 分辨率与长宽比
- Flash Image (稳定版)：支持 10 种长宽比（21:9、16:9、9:16、3:4、4:3、1:1 等），生产级分辨率（约 1K 级别）。[2]
- Nano Banana Pro：支持 **2K 与 4K** 输出、多种镜头类型（广角、全景、特写）与景深控制。[4][5]

## 3. 典型用途

1. **对话式修图 / 创意迭代**：像和设计师对话一样改图，是其最核心的使用场景。[1][3]
2. **角色一致的分镜与故事板**：同一角色在不同场景下保持一致，是扩散模型难以稳定做到的。[3][5]
3. **多图融合的品牌资产**：参考图 A 的服装 + 参考图 B 的场景 + 参考图 C 的光线。[3]
4. **信息图 / 带文字素材**（尤以 Pro 版）。[4][5]

## 4. API 可用性

- **官方渠道**：Gemini API、Google AI Studio、Vertex AI。[2]
- **模型 ID**：
  - Flash Image 稳定版：`gemini-2.5-flash-image`
  - Pro 版：`gemini-3-pro-image-preview`[4]
- **第三方**：OpenRouter、fal.ai（`fal-ai/nano-banana`、`fal-ai/nano-banana-pro`）、CreateIO、各聚合代理。[6][7]
- **官方定价**（Gemini API）：
  - **Nano Banana / 2.5 Flash Image**：按输出 token 计，每张图约 **1290 output tokens × \$30/M = \$0.039/张**；输入文本 \$0.30/M、输出文本 \$2.50/M；输入图像 \$0.30/M、输出图像 \$30/M。[6]
  - **Nano Banana Pro / Gemini 3 Pro Image**：官方价 **约 \$0.134/张（1K–2K）**，4K 更高；第三方聚合最低可到约 \$0.09/张。[4][7]
- **延迟**：Flash Image 通常几秒内出图，是同档位中最快之一；Pro 版因分辨率与质量档位提升，延迟更高。[6]
- **商用许可**：商用允许；SynthID/C2PA 水印默认开启，Google AUP 与 Generative AI 使用条款约束。[2][4]

## 5. 基准评测

- 发布初期 **LMArena Image Arena 榜首**（匿名投票冠军）。[1][6]
- Artificial Analysis：**图像编辑榜第一**，Elo ≈ **1212**；文生图榜上略逊于字节系某些版本与 GPT-4o Image。[6]
- 与 Seedream 4：对话式编辑 / 多轮一致性 Nano Banana 占优；中文渲染、东方审美 Seedream 占优。[8]
- Nano Banana Pro：在高分辨率、文字渲染、世界知识、信息图等场景"显著超越"Flash 版。[4][5]

## 6. 已知局限

- Flash Image 版在中文字符、复杂排版上弱于 Seedream。[8]
- 文生图最高质量仍有场景落后于 Seedream 4 / GPT-Image-1（Artificial Analysis 文生图榜）。[6]
- 强制 SynthID 水印，部分对元数据敏感的工作流需注意。[4]

## 参考来源
1. Google Blog·Nano Banana 命名与 Google Trends 总结：https://blog.google/products-and-platforms/products/gemini/nano-banana-google-trends-2025/
2. Gemini API·gemini-2.5-flash-image 文档：https://ai.google.dev/gemini-api/docs/models/gemini-2.5-flash-image
3. 36Kr·Nano Banana 技术解读：https://m.36kr.com/newsflashes/3440358498506120
4. Google Blog·Nano Banana Pro 发布（开发者视角）：https://blog.google/innovation-and-ai/technology/developers-tools/gemini-3-pro-image-developers/
5. DeepMind·Gemini Image (Pro) 产品页：https://deepmind.google/models/gemini-image/pro/
6. Gemini API 定价：https://ai.google.dev/gemini-api/docs/pricing?hl=zh-cn
7. 腾讯云开发者·Nano Banana Pro 接入与定价：https://cloud.tencent.com/developer/article/2596455
8. 302.AI·Seedream 4 vs Nano Banana 实测：https://302.ai/blog/302-ai-benchmark-lab-review-on-seedream-4-0-vs-nano-banana/
