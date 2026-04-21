# Seedream 5.0 深度档案（旗舰 · Preview）

> **状态（截至 2026-04-21）：Preview 阶段，尚未正式 GA。** Seedream 5.0 Lite 已于 2026-02-13 先行发布，参见 [`seedream-5-lite.md`](./seedream-5-lite.md)。
> 研发方：字节跳动 豆包 Seed 团队
> 预期接入：火山引擎 / 豆包 / 即梦 / Atlas Cloud / WaveSpeed

> ⚠️ 本档案严格区分"已确认信息"和"Preview / 媒体报道但未官方确认"两类。所有来自 Preview 预告、第三方托管方预热稿的内容均在行尾注明 *[Preview]*。

## 1. 版本演进脉络

| 版本 | 发布时间 | 主要特点 |
|---|---|---|
| Seedream 3.0 | 2025-04 | 原生 2K、3 秒出图、中英双语；发布了完整技术报告。[1] |
| Seedream 4.0 | 2025-09-09 | DiT 架构统一文生图与通用编辑，扩展到 4K；推理速度提升 10×。[2] |
| Seedream 4.5 | 2025-12 前后 | 被媒体形容为"4.0 的完整形态"，强化多图一致性、角色延续、4K、SOTA 中文文字渲染。[3] |
| **Seedream 5.0** | **Preview（旗舰版未 GA）** | 目标是从"规模/精修"走向"交互智能"—— Visual CoT、流式生成、实时联网检索、结构稳定性与极致写实。[3][4] |
| Seedream 5.0 Lite | 2026-02-13 | 轻量款率先 GA；先行带来推理、联网检索、统一编辑能力。[5][6] |

## 2. 模型定位与技术归属

- **归属**：字节跳动 豆包 Seed 团队的下一代旗舰图像模型。[5]
- **发布状态**：旗舰 5.0 至今**未在 seed.bytedance.com 给出正式博客或技术报告**；仅 Atlas Cloud、WaveSpeed 等第三方托管方以及剪映/CapCut 内测预告其能力。Atlas Cloud 明确标注"Day 0 API"将在旗舰版发布后首日上线。[4]
- **技术路线**：延续 Seedream 4.x 的 Diffusion Transformer (DiT) + 统一生成/编辑框架，并新增"智能层"（Visual Chain-of-Thought、流式/实时潜空间生成、深度推理、Grounded Retrieval）。*[Preview]*[3][4]

## 3. Preview 期已被披露的能力

> 以下内容来自 Preview 预告与第三方分析稿，**非官方最终规格**。

### 3.1 分辨率
- **直接 2K 输出；通过 AI 增强可到 4K**（继承并扩展 Seedream 4.5 的 4K 能力）。*[Preview]*[3][4]

### 3.2 核心能力升级
- **深度提示词理解、精细细节、文字渲染、复杂知识任务**。*[Preview]*[3]
- **首次支持检索增强生成（Retrieval-based Generation）**：模型可在生成前实时查询外部知识库。*[Preview]*[3]
- **Visual Chain-of-Thought**：让图像生成过程具备可解释的"思考"步骤。*[Preview]*[4]
- **流式生成 / 实时潜空间交互**：用户对 prompt 做小幅改动即可得到近实时的视觉反馈。*[Preview]*[4]
- **结构稳定性 + 极致写实**：官方/Preview 描述 5.0 旗舰对比 5.0 Lite，主要差距在"结构稳定性与极致写实"上。[6]

### 3.3 中文理解与文字渲染
- 继承 4.5 阶段被业内称为 SOTA 的中文文字渲染能力；5.0 在此基础上对"长文本、复杂版式、知识性图表"继续优化。*[Preview]*[3]

## 4. 典型用途（预期）

1. **专业创意生产**：广告大片、品牌 KV、带长文本的信息图。
2. **知识图像生成**：结合实时检索生成"历史/体育/天气/技术类"带准确数据的图片。
3. **高复杂度多图场景**：保持角色/主体/光线一致的系列产出。
4. **流式"画笔式"工作流**：实时潜空间交互适合设计师反复微调。

## 5. API 可用性

- 火山引擎（Volcano Engine）、豆包、即梦、剪映/CapCut 为主入口；Atlas Cloud / WaveSpeed 承诺 Day 0 API 托管。[4][7]
- **截至 2026-04-21，无官方 API 价格与延迟数据披露**。第三方预期其价格会高于 Lite（Lite 约 \$0.035/图，见 [`seedream-5-lite.md`](./seedream-5-lite.md)）。

## 6. 基准评测

- 旗舰 5.0 在官方榜单与 Artificial Analysis 上**尚未出现正式条目**。
- Lite 版的内部雷达图显示其 Elo 超过 4.5，在指令遵循 / 一致性领先；旗舰版的相对位置预期更高，但无量化数据。*[Preview]*[4][5]

## 7. 已知局限（截至 Preview 期）

- **非 GA**：当前不可稳定作为生产依赖。建议在生产中先用 Seedream 5.0 Lite 或 Seedream 4.5，并密切跟踪正式发布。
- **官方技术报告缺失**：与 3.0 不同，5.0（以及 4.0/4.5）至今没有对应的 arXiv 完整技术报告公开。
- **4K 是"AI 增强"**：非原生 4K 扩散过程，这在极端精度任务上可能不如原生 4K 管线。*[Preview]*[3]

## 参考来源
1. Seedream 3.0 技术报告：https://seed.bytedance.com/zh/blog/seedream-3-0-text-to-image-model-technical-report-released
2. Seedream 4.0 项目主页：https://seed.bytedance.com/seedream4_0
3. PixVerse Blog·Seedream 5.0 预告与能力分析：https://pixverse.blog/zh/blog/seedream-5-0/
4. Atlas Cloud·Seedream 5.0 is coming soon（Day 0 API 计划）：https://www.atlascloud.ai/blog/ai-updates/Seedream-5.0-is-coming-soon
5. 字节 Seed 博客·Seedream 5.0 Lite 发布：https://seed.bytedance.com/zh/blog/deeper-thinking-more-accurate-generation-introducing-seedream-5-0-lite
6. 36Kr EU·Seedream 5.0 Lite vs 旗舰版差异：https://eu.36kr.com/en/p/3677025348395653
7. WaveSpeed·ByteDance Seedream v5.0 Lite 托管：https://wavespeed.ai/blog/posts/introducing-bytedance-seedream-v5-0-lite-on-wavespeedai/
