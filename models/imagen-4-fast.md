# Imagen 4 Fast 深度档案

> 模型 ID：`imagen-4.0-fast-generate-001`（Gemini API / Vertex AI）
> 发布：2025 Google I/O 预览 → **2025-08-14 正式 GA**
> 状态更新（2026-04-21）：截至本调研时点，Imagen 5 未官宣，Imagen 4 家族仍是 Google DeepMind 扩散系旗舰。[1][2][3]
> 研发方：Google DeepMind
> 家族：Imagen 4 Fast / Imagen 4 / Imagen 4 Ultra

## 1. 模型定位与技术归属

- **归属**：Google DeepMind，Imagen 家族第四代；Fast 档专为"**大批量、低延迟、低成本**"场景设计。[1][2]
- **三档差异**：
  - **Fast**：比前代 Imagen 3 提速约 **10×**，价格最低，品质接近 Imagen 4，适合量产 / 原型。[1][2]
  - **Standard (Imagen 4)**：旗舰款，平衡品质与速度。[1]
  - **Ultra**：最高画质，复杂场景与精确控制。[1][4]
- **技术路线**：延续 Google 的**扩散模型路线**（未转向 Gemini 系的原生多模态 LLM），在 Imagen 3 基础上重点改进文字渲染、提示词保真度、面部与版式细节。[1][3]

## 2. 核心能力

- **文生图质量**：在文本渲染、提示词保真度、面部 / 版式细节上显著优于 Imagen 3。[1][3]
- **英文文字渲染**：系列最大改进点之一，长文本 / 标题排版 / 拼写正确率均提升。[1]
- **分辨率**：长边最高 **2K**，5 种常见长宽比（1:1、16:9、9:16、4:3、3:4）。[1][2]
- **一次生成 1–4 张**。[2]
- **图像编辑**：**Fast 档不支持** mask 编辑 / 物体插入移除 / 风格迁移；需在 Vertex AI 用独立 Imagen 编辑端点。[4]
- **SynthID 水印**：默认启用，不可见；可用 Vertex AI SynthID 验证 API 检测。[1][4]
- **商用许可**：通过 Gemini API / Vertex AI 开放商用，受 Google Responsible AI 与 AUP 约束。[1][4]

## 3. 典型用途

1. **批量广告素材变体 / A/B 测试图**：\$0.02/张 + 1–3 s 延迟组合极具吸引力。
2. **UI 与设计原型草图**。
3. **英文社交媒体配图**。
4. **印刷 / 高端营销物料**：推荐使用 Imagen 4 Standard 或 Ultra。

## 4. API 可用性与价格

- **Gemini API / Google AI Studio**：`imagen-4.0-fast-generate-001`，文本输入 ≤ 480 token，一次输出 1–4 张图。[2]
- **Vertex AI**：同模型 ID，集成 Google Workspace、SynthID 验证。[4]
- **官方价格（截至 2026-04-21）**[1][5]：

| 档位 | 每张价格 |
|---|---|
| **Imagen 4 Fast** | **\$0.02** |
| Imagen 4 (Standard) | \$0.04 |
| Imagen 4 Ultra | \$0.06 |

> 截至当前时间，**未见 Imagen 5 官方公告**；Imagen 4 Fast 在 Gemini API 定价页上持续稳定在 \$0.02/图。搜索结果显示主线 Google 资源仍以 Imagen 4 三档为中心。[1][2][3][5]

- **延迟**：Fast 档常见 1–3 s。[1][2]

## 5. 基准评测

- Google 官方对比：Imagen 4 在文字渲染、提示词保真度、面部 / 版式细节上超越 Imagen 3 与同期主流竞品。[1][3]
- 第三方评测：Imagen 4 Fast **定位"高性价比档"**，画质略逊于 Nano Banana Pro、FLUX 2 Pro、Seedream 4.5 / 5.0 Lite，但成本/速度/稳定性组合仍为当下英文批量场景最优。[5]

## 6. 已知局限

- Fast 档不支持 mask 编辑、物体插入/移除、风格迁移。[4]
- 最大分辨率 2K，低于 Nano Banana Pro 4K 与 FLUX 2 4MP。[1][4]
- 中文文字渲染远弱于 Seedream 系列。

## 参考来源
1. Google Developers Blog·Imagen 4 Fast 家族 GA：https://developers.googleblog.com/announcing-imagen-4-fast-and-imagen-4-family-generally-available-in-the-gemini-api/
2. Gemini API·Imagen 文档：https://ai.google.dev/gemini-api/docs/models/imagen
3. MindStudio·What is Imagen 4 Fast：https://www.mindstudio.ai/blog/what-is-imagen-4-fast-google-4f1ae/
4. Vertex AI·Imagen 4 模型参考：https://docs.cloud.google.com/vertex-ai/generative-ai/docs/models/imagen/4-0-generate
5. WaveSpeed·Imagen 4 Fast 托管：https://wavespeed.ai/blog/zh-tw/posts/introducing-google-imagen4-fast-on-wavespeedai/
6. Gemini API 定价页：https://ai.google.dev/gemini-api/docs/pricing
