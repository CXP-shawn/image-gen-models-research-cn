# FLUX 2 Pro 深度档案（对照参考）

> 模型 ID：`flux-2-pro`（BFL API、fal.ai 等多平台托管）
> 家族：`flux-2-pro` / `flux-2-flex` / `flux-2-dev` / `flux-2-klein`
> 发布：2025-11-25
> 研发方：Black Forest Labs（德国弗赖堡；由 Stable Diffusion 原班人马创立）

> 本档案在本次调研中作为**对照参考**，用于衡量 Seedream 5.0 / Nano Banana Pro 等主角模型在"照片级写实 + 多参考图 + 开源私有化"维度上的相对位置。

## 1. 模型定位与技术归属

- **归属**：Black Forest Labs (BFL)，创始团队为原 Stability AI 核心成员（Stable Diffusion 架构作者群）。[1][2]
- **发布**：**2025-11-25** 正式发布 FLUX.2 系列，直接对标 Nano Banana Pro、Seedream 4.x、Midjourney v7。[1][3]
- **技术路线**：**32B 参数 Rectified Flow Transformer (潜空间 Flow Matching)** + **Mistral 3 24B VLM** 文本/图像编码器，较 FLUX.1 的 CLIP+T5 组合在多模态理解与世界知识上明显增强。[1][3][4]
- **家族分档**：
  - **[pro]**：旗舰闭源 API，生产级 SLA。[1][4]
  - **[flex]**：延迟高但暴露更多推理超参。[4]
  - **[dev]**：**开源权重**，可本地运行（四家模型中唯一开源档）。[3][4]
  - **[klein]**：亚秒级，实时应用。[1]

## 2. 核心能力

- **照片级真实感 / 电影级画质**：对标 Midjourney v7 与 GPT-Image。[1][4]
- **多参考图一致性（标志性）**：**最多 10 张参考图**，用于角色 / 产品 / 风格一致性、光线与布局控制。[1][3]
- **文字渲染**：支持复杂排版、品牌风格指南遵循、JSON 结构化 prompt 生成信息图。[1][4]
- **分辨率**：最高 **4MP**（~2K×2K 或相应长宽比）。[1][3]
- **图像编辑**：基于参考图的编辑、inpainting、局部重绘。[1][4]

## 3. 典型用途

1. 照片级写实广告大片、产品摄影风格图。
2. 电商主图 / 静物 / 珠宝 / 汽车 / 家居（多参考控制材质与光线）。
3. 角色 IP 一致性（10 张参考 → 多风格多场景输出）。
4. **本地部署 / 私有化**（[dev] 开源权重，合规友好）。
5. [klein] 亚秒级画笔式工作流。

## 4. API 可用性与价格

- **官方**：BFL API、BFL Playground。[1]
- **合作渠道**：fal.ai、Replicate、Together AI、Azure AI Foundry（`FLUX.2-pro`）、Nvidia RTX AI Garage、CometAPI。[2][5][6][7][8]
- **价格**：[pro] 约 **\$0.03–\$0.06 / 图**（随分辨率/是否启用参考图）。[klein]/[dev] 另算。
- **延迟**：[pro] 几秒；[klein] 亚秒。[1]

## 5. 基准位置

- 照片级写实与多参考一致性上与 Nano Banana Pro 相当或领先。
- 对话式多轮编辑弱于 Nano Banana 系列。
- 中文渲染弱于 Seedream 系列。

## 6. 已知局限

- 中文字符与东方排版弱于 Seedream 系列。
- 对话式多轮编辑粒度不如 Nano Banana 原生多模态 LLM。
- 至今无完整 FLUX.2 技术论文，部分架构细节以官方博客为准。[1]

## 参考来源
1. Black Forest Labs 官方博客·FLUX.2：https://bfl.ai/blog/flux-2
2. Azure AI Foundry·FLUX.2-pro：https://ai.azure.com/catalog/models/FLUX.2-pro
3. Novalogiq·FLUX.2 挑战 Nano Banana Pro：https://novalogiq.com/2025/11/26/black-forest-labs-launches-flux-2-ai-image-models-to-challenge-nano-banana-pro-and-midjourney/
4. MindStudio·FLUX Pro 2：https://www.mindstudio.ai/models/flux-pro-2/
5. Nvidia RTX AI Garage·FLUX 2 + ComfyUI：https://blogs.nvidia.com/blog/rtx-ai-garage-flux-2-comfyui/
6. CometAPI·FLUX 2：https://www.cometapi.com/what-is-flux-2-and-flux-2-is-now-available-on-cometapi/
7. GLBGPT·FLUX 2 Pro 指南：https://www.glbgpt.com/hub/flux-2-pro-guide/
8. RunDiffusion·FLUX 2 部署：https://www.rundiffusion.com/flux-2-coming-soon
