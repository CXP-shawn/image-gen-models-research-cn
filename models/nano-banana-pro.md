# Nano Banana Pro (Gemini 3 Pro Image) 深度档案

> 模型 ID：`gemini-3-pro-image-preview`
> 发布：2025-11-20
> 研发方：Google DeepMind — 基于 Gemini 3 Pro 的高端图像模型
> 关系：Nano Banana (Gemini 2.5 Flash Image) 的**高端旗舰版**，两者并列存在（非替换）。

## 1. 模型定位与技术归属

- **归属**：Google DeepMind；与 Gemini 3 Pro 共享底层推理与世界知识能力。[1][2]
- **发布**：2025-11-20 在 blog.google 与 cloud.google.com 同步发布；上线 Gemini API、Google AI Studio、Vertex AI 企业通道。[1][2][3]
- **定位**：**工作室级精度控制** —— 强推理 + 高分辨率 + SOTA 文字渲染；对标 FLUX 2 Pro、Seedream 5.0 旗舰。[1][2][4]
- **技术路线**：与基础 Nano Banana 同属原生多模态 LLM 路线；差异在"上层 Gemini 3 Pro 带来的知识、推理、Grounding 能力"以及"更高分辨率档位"。[2][3]

## 2. 相对基础版 Nano Banana 的增强点

| 维度 | Nano Banana（2.5 Flash Image） | **Nano Banana Pro（3 Pro Image）** |
|---|---|---|
| 底层模型 | Gemini 2.5 Flash | **Gemini 3 Pro** |
| 推理与世界知识 | 继承 2.5 LLM | **Gemini 3 高级推理 + Google Search Grounding**（实时天气/体育/数据）[1][2] |
| 文字渲染 | 良好 | **SOTA**：多语言可读（纹理、字体、书法级）[1][2][4] |
| 分辨率 | 最高 4K | **原生 2K & 4K；专业相机级精度**[1][4] |
| 镜头 / 景深 | 基础长宽比 | 多镜头（广角/全景/特写）、景深控制、光照/构图/色彩分级物理控制[1][4] |
| 水印 | SynthID | **SynthID + C2PA Content Credentials 元数据**[3] |
| 延迟 | 几秒 | 更长（10–20 秒区间，高分辨率更久）[4] |
| 价格 | 见基础档案 | 见下节 |

## 3. 官方定价（Gemini API 定价页，权威）

| 分辨率 | 实时 API / 张 | **Batch API / 张（-50%）** |
|---|---|---|
| 1K / 2K | **\$0.134** | \$0.067 |
| 4K | **\$0.24** | \$0.12 |

- 计费基础：1K/2K 消耗 1,120 输出 token（\$120/M）；4K 消耗 2,000 输出 token。[5]
- 与基础 Nano Banana（1K **\$0.067**、2K **\$0.101**、4K **\$0.151**）相比，Pro 版在 1K/2K 上约 **2× 溢价**，4K 上约 **1.6× 溢价**。[5]

## 4. 核心能力详解

### 4.1 推理与世界知识（最大差异化）
- 直接连接 Google Search 做 **Grounding**：可以基于"今天""刚刚发生"这类时效性描述生成事实准确的图像，例如"把今天旧金山天气画成一张信息图"。[1][2]
- 历史场景 / 体育 / 科学 / 烹饪配方等知识密集类图像的事实准确性显著提升。[1][2]

### 4.2 文字渲染 SOTA
- 多语言清晰可读、从 tagline 到整段 paragraph；支持自定义字体、书法纹理、艺术排版。[1][2][4]
- 是"一图多语言嵌入"和"信息图 / 长文本报告图"最合适的闭源模型之一。

### 4.3 物理控制
- 长宽比、镜头类型（广角 / panoramic / close-up）、景深、光照角度、色彩分级、构图全部可通过 prompt 精确控制。[1][4]

### 4.4 多轮编辑
- 继承 Nano Banana 的对话式多轮编辑与主体一致性，再叠加 Pro 推理层。[4]

### 4.5 水印 / 溯源
- 每张图默认带 **SynthID + C2PA Content Credentials**；符合企业合规与内容溯源诉求。[3]

## 5. 典型用途

1. **专业信息图、带实时数据的图像**（天气/体育/财经/历史）—— 独有能力。
2. **长文本带图、多语言本地化广告创意**。
3. **高分辨率广告大片 / 产品视觉**。
4. **企业合规要求高的 AI 图像生产**（C2PA 溯源）。
5. **与 Adobe Firefly / Photoshop 集成的专业修图流程**。[6]

## 6. 基准位置

- Artificial Analysis 与 LMArena 尚未对 Pro 版单独列出稳定 Elo，媒体评测普遍称其在"文字渲染 + 世界知识 + 物理控制"三项上领先 FLUX 2 Pro 与 Seedream 4.x / 5.0 Lite。[4][5]

## 7. 已知局限

- **昂贵**：\$0.134 / 1K 和 \$0.24 / 4K 的价格使其不适合大批量场景；Batch API 半价可缓解但仍远高于 Imagen 4 Fast（\$0.02）与基础 Nano Banana。
- **延迟较长**：非实时交互优先，Google 官方表述其为"专业生产用"而非"高速迭代用"。[4]
- **中文字符 / 东方审美**：表现好于基础版但仍略逊于 Seedream 系列。

## 参考来源
1. DeepMind·Gemini Image Pro 产品页：https://deepmind.google/models/gemini-image/pro/
2. Google Blog·Nano Banana Pro 发布：https://blog.google/innovation-and-ai/products/nano-banana-pro/
3. Google Cloud Blog·Nano Banana Pro for enterprise：https://cloud.google.com/blog/products/ai-machine-learning/nano-banana-pro-available-for-enterprise
4. Google Blog·Nano Banana Pro 开发者视角：https://blog.google/innovation-and-ai/technology/developers-tools/gemini-3-pro-image-developers/
5. Gemini API 定价页（官方权威）：https://ai.google.dev/gemini-api/docs/pricing
6. Adobe Blog·Nano Banana Pro 与 Firefly / Photoshop 集成：https://blog.adobe.com/en/publish/2025/11/20/google-gemini-3-nano-banana-pro-firefly-photoshop
7. Vertex AI·Gemini 3 Pro Image 文档：https://docs.cloud.google.com/vertex-ai/generative-ai/docs/models/gemini/3-pro-image
8. AI Studio·Gemini 3 Pro Image：https://aistudio.google.com/models/gemini-3-pro-image
9. AI for Developers·Image Generation 文档：https://ai.google.dev/gemini-api/docs/image-generation
