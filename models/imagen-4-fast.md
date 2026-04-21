# Imagen 4 Fast 深度档案

> 模型 ID：`imagen-4.0-fast-generate-001`（Gemini API / Vertex AI）
> 发布：2025 Google I/O 预览 → **2025-08-14/15 正式 GA**
> 研发方：Google DeepMind
> 家族：Imagen 4 Fast / Imagen 4 (Standard) / Imagen 4 Ultra

## 1. 模型定位与技术归属

- **归属**：Google DeepMind，Imagen 家族的第四代；Fast 档专为"大批量、低延迟、低成本"场景设计。[1][2]
- **发布节奏**：
  - 2025 年 5 月 Google I/O 预览（Gemini 应用、Vertex AI Media Studio）。[3]
  - 2025 年 8 月 14–15 日，Imagen 4、Imagen 4 Fast、Imagen 4 Ultra 三档一起在 **Gemini API** 与 **Google AI Studio** 正式 GA。[1][4]
- **技术路线**：Imagen 家族延续 Google 的**扩散模型路线**（未采用 Gemini 原生多模态的自回归路径），Imagen 4 在 Imagen 3 基础上重点改进文字渲染、提示词保真度与面部/排版细节。[1][3]
- **三档差异**：
  - **Fast**：比前代提速约 **10×**，价格最低，品质接近 Imagen 4，适合量产/原型。[1][2]
  - **Standard (Imagen 4)**：旗舰款，平衡品质/速度。[1]
  - **Ultra**：最高品质，复杂场景与精确控制。[1][4]

## 2. 核心能力

### 2.1 文生图质量
- 在文本渲染、提示词保真度、面部与版式细节上显著优于 Imagen 3，发布初期官方对标 DALL·E / Midjourney 并在多个维度胜出。[1][3]

### 2.2 文字渲染
- Imagen 4 系列相比 Imagen 3 最大改进点之一，尤其英文长文本、拼写正确率、标题排版。[1][3]

### 2.3 分辨率与长宽比
- 长边最高 **2K**，支持常见长宽比（1:1、16:9、9:16、4:3、3:4）。[1][4]
- 每次调用可一次生成 1–4 张图。[1][4]

### 2.4 图像编辑
- **Fast 档不支持** mask 编辑 / 物体插入移除 / 风格转换等 editing 能力；Vertex AI 上有独立的 `imagen-3-capability` / `imagegeneration` 编辑端点服务这些场景。[4]

### 2.5 SynthID 水印
- 所有 Imagen 4 输出默认加入**不可见 SynthID 水印**，可通过 Vertex AI 的 SynthID 验证 API 检测。[1][4]

### 2.6 商用许可
- 通过 Gemini API / Vertex AI 商用许可开放；受 Google Responsible AI 与 AUP 条款约束。[1][4]

## 3. 典型用途

1. **批量广告素材变体、A/B 测试图**：Fast 档的成本 + 速度组合极具吸引力。
2. **原型与 UI 设计草图**：需要快速试多个方向。
3. **社交媒体配图**：成本敏感 + 输出稳定。
4. **印刷/营销物料**：Imagen 4 Standard/Ultra 更合适。

## 4. API 可用性

- **Gemini API / Google AI Studio**：模型 ID `imagen-4.0-fast-generate-001`，文本输入 ≤ 480 token，一次输出 1–4 张图。[2]
- **Vertex AI**：同模型 ID，集成 Google Workspace、支持 SynthID 验证。[4]
- **官方价格**（截至 2025 Q4）：
  - **Imagen 4 Fast：\$0.02 / 张**。[1]
  - Imagen 4 (Standard)：\$0.04 / 张。[1][5]
  - Imagen 4 Ultra：\$0.06 / 张。[1][5]
- **延迟**：Fast 档官方称为前代 **10×**，常见 1–3 秒。[1][2]

## 5. 基准评测

- Google 官方对比：Imagen 4 在文本渲染、提示保真度、面部质量等维度超越 Imagen 3 与市面主流竞品。[1][3]
- 第三方评测中，Imagen 4 Fast **定位于"高性价比档"**，综合画质略逊于 Nano Banana Pro、FLUX 2 Pro、Seedream 4，但在成本/延迟/稳定性组合上非常有竞争力。[1][5]

## 6. 已知局限

- Fast 档不支持 mask 编辑、物体插入/移除、风格迁移等编辑能力。[4]
- 最高分辨率为 2K，低于 Nano Banana Pro 的 4K、FLUX 2 的 4MP。[1][4]
- 中文渲染表现显著弱于 Seedream。

## 参考来源
1. Google Developers Blog·Imagen 4 Fast 家族 GA：https://developers.googleblog.com/announcing-imagen-4-fast-and-imagen-4-family-generally-available-in-the-gemini-api/
2. Gemini API·Imagen 文档：https://ai.google.dev/gemini-api/docs/models/imagen?hl=zh-tw
3. MindStudio·What is Imagen 4 Fast：https://www.mindstudio.ai/blog/what-is-imagen-4-fast-google-4f1ae/
4. Vertex AI·Imagen 4 模型参考文档：https://docs.cloud.google.com/vertex-ai/generative-ai/docs/models/imagen/4-0-generate?hl=zh-tw
5. WaveSpeed·Imagen 4 Fast 托管与价格：https://wavespeed.ai/blog/zh-tw/posts/introducing-google-imagen4-fast-on-wavespeedai/
