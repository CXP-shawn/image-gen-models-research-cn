# FLUX 2 Pro 深度档案

> 模型 ID：`flux-2-pro`（BFL API、fal.ai 多平台托管）
> 家族成员：`flux-2-pro` / `flux-2-flex` / `flux-2-dev` / `flux-2-klein`
> 发布：2025-11-25
> 研发方：Black Forest Labs（德国弗赖堡；由 Stable Diffusion 原班人马创立）

## 1. 模型定位与技术归属

- **归属**：Black Forest Labs (BFL)，创始团队为原 Stability AI 核心成员（Stable Diffusion 架构作者群）。[1][2]
- **发布**：**2025 年 11 月 25 日** 正式发布 FLUX.2 系列，对标 Nano Banana Pro、Seedream 4 等 2025 Q4 同档模型。[1][3]
- **技术路线**：**32B 参数潜空间 Flow Matching / Rectified Flow Transformer** 架构；文本编码端采用 **Mistral 3 24B VLM** 作为多模态文本/图像编码器，较 FLUX.1 的 CLIP+T5 组合在多模态理解与世界知识上明显增强。[1][3][4]
- **家族定位**：
  - **FLUX.2 [pro]** — 旗舰闭源档，主打"顶级画质 + 低延迟 + 生产级 SLA"。[1][4]
  - **FLUX.2 [flex]** — 延迟略高但暴露更多可调推理超参，适合深度定制。[4]
  - **FLUX.2 [dev]** — 开源权重，供开发者/研究者本地运行。[3][4]
  - **FLUX.2 [klein]** — 亚秒级迭代，实时应用与快速原型。[1]

## 2. 核心能力

### 2.1 文生图质量
- 官方称"媲美顶级闭源模型的画质"，在照片级真实感、自然光、肤质、材质上表现突出；是当前少数在"电影级写实"上可对标 Midjourney v7 / GPT-Image 的开放 API 模型。[1][4]

### 2.2 多参考与多主体一致性
- **最多 10 张参考图**一次性输入，支持角色/产品/风格一致性、灯光与布局控制 —— 这是其最核心的差异化卖点。[1][3]

### 2.3 文字渲染
- 复杂文本读写能力、遵循品牌风格指南、结构化排版（包括信息图、JSON 结构化 prompt 生成带图表版式）。[1][4]

### 2.4 分辨率
- 原生支持 **最高 4MP（~2K×2K 或更高长宽比组合）**，编辑与生成均可在该分辨率。[1][3]

### 2.5 图像编辑
- 支持基于参考图的编辑、inpainting、局部重绘，保持细节一致性。[1][4]

### 2.6 许可
- [pro] / [flex] 为闭源 API；[dev] 提供开源权重（非商用 dev 许可或商用许可见 BFL 许可条款）；[klein] 面向实时推理优化。[3][4]

## 3. 典型用途

1. **照片级写实广告大片、产品摄影风格图**。
2. **电商主图 / 静物 / 珠宝 / 汽车 / 家居** —— 多参考图控制材质与光线。
3. **角色 IP 一致性**：最多 10 张参考 → 同角色多风格多场景输出。
4. **本地部署 / 私有化** —— [dev] 档开源权重，对数据合规要求严格的企业友好。
5. **设计草图到成品迭代**：[klein] 亚秒级迭代，适合"画笔式"工作流。

## 4. API 可用性

- **官方渠道**：BFL API、BFL Playground。[1]
- **合作渠道**：fal.ai（`fal-ai/flux-2-pro` 等）、Replicate、Together AI、Azure AI Foundry（`FLUX.2-pro`）、Nvidia RTX AI Garage（ComfyUI 本地）、CometAPI。[2][5][6][7][8]
- **价格**（以 2025 年底第三方托管与官方发布为参考，具体以 bfl.ai 与 fal.ai 定价页为准）：
  - FLUX.2 [pro]：约 **\$0.03–\$0.06 / 张**（随分辨率与是否启用参考图）。
  - [flex] / [dev] / [klein] 有各自的报价档位。
- **延迟**：[pro] 几秒级，[klein] 亚秒级。[1]

## 5. 基准评测

- 官方对比：FLUX.2 在 FLUX.1 基础上显著提升真实感、一致性与效率；"直接对标并挑战 Nano Banana Pro 与 Midjourney"。[3][4]
- 独立评测（发布初期，2025-11 末至 2025-12）：在**照片级写实 / 多参考一致性**维度与 Nano Banana Pro 相当或领先；在**对话式编辑 / 世界知识**上不如 Nano Banana；在**中文渲染**上普遍不如 Seedream 4。

## 6. 已知局限

- 中文字符与东方排版弱于 Seedream 4。
- 对话式多轮编辑、自然语言粒度不如 Nano Banana 系列。
- 官方尚未发布完整 FLUX.2 技术论文，部分架构细节需以官方博客为准。[1]

## 参考来源
1. Black Forest Labs 官方博客·FLUX.2 发布：https://bfl.ai/blog/flux-2
2. Azure AI Foundry·FLUX.2-pro 模型目录：https://ai.azure.com/catalog/models/FLUX.2-pro
3. Novalogiq·FLUX.2 对标 Nano Banana Pro 与 Midjourney 报道：https://novalogiq.com/2025/11/26/black-forest-labs-launches-flux-2-ai-image-models-to-challenge-nano-banana-pro-and-midjourney/
4. MindStudio·FLUX Pro 2 介绍：https://www.mindstudio.ai/models/flux-pro-2/
5. Nvidia 博客·FLUX 2 + ComfyUI 本地运行：https://blogs.nvidia.com/blog/rtx-ai-garage-flux-2-comfyui/
6. CometAPI·FLUX 2 介绍与价格：https://www.cometapi.com/what-is-flux-2-and-flux-2-is-now-available-on-cometapi/
7. GLBGPT·FLUX 2 Pro 使用指南：https://www.glbgpt.com/hub/flux-2-pro-guide/
8. RunDiffusion·FLUX 2 部署：https://www.rundiffusion.com/flux-2-coming-soon
