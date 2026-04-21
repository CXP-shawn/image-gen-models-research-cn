# 主流图像 AI 模型系统对比（v2）

> 更新：2026-04-21
> 新阵容：**Seedream 5.0（旗舰 · Preview）** · **Seedream 5.0 Lite** · **Nano Banana (Gemini 2.5 Flash Image)** · **Nano Banana Pro (Gemini 3 Pro Image)** · **Imagen 4 Fast** · FLUX 2 Pro（对照）

---

## 摘要 (TL;DR)

2026 年初图像 AI 的关键事实：

1. **字节系**：Seedream 4.0 已被 4.5 / 5.0 Lite 接力取代，旗舰 **Seedream 5.0 仍在 Preview**（Atlas Cloud 承诺 Day 0 API），**Seedream 5.0 Lite 于 2026-02-13 正式 GA**，带来 Chain-of-Thought 推理 + **首次支持实时联网检索**，价格约 **\$0.035/图**，是当前中文场景下最具性价比的主力产线。[1][2]
2. **Google 系**：Nano Banana（Gemini 2.5 Flash Image）和 Nano Banana Pro（Gemini 3 Pro Image）**并列存在**：基础版定价已升级为按分辨率分档（1K \$0.067 / 2K \$0.101 / 4K \$0.151），Pro 版 1K/2K \$0.134、4K \$0.24，Batch API 全线半价；Pro 独有 **Google Search Grounding**、**SOTA 文字渲染**、**SynthID + C2PA**。[3]
3. **批量档**：**Imagen 4 Fast 仍稳定在 \$0.02/图**，至今未见 Imagen 5 官宣，仍是英文 / 设计草图 / 量产变体的 TCO 最优解。[4][5]
4. **照片级对照**：FLUX 2 Pro（2025-11-25）以 32B Flow Matching + Mistral 3 24B VLM + 最多 10 张参考图在写实和角色 IP 延展上依然独特，并提供唯一的开源权重 [dev] 档位。[6]

**没有全能王**：中文 → Seedream 5.0 Lite（未来旗舰 5.0）；对话式修图 → Nano Banana；高端定稿 / 世界知识 / 信息图 → Nano Banana Pro；英文批量 → Imagen 4 Fast；照片写实 / 私有化 → FLUX 2 Pro。

---

## 目录

1. [研究方法与时间锚定](#1-研究方法与时间锚定)
2. [Seedream 家族版本演进](#2-seedream-家族版本演进)
3. [模型定位与技术归属](#3-模型定位与技术归属)
4. [核心能力分析](#4-核心能力分析)
5. [价格、延迟、API](#5-价格延迟api)
6. [场景推荐与选型建议](#6-场景推荐与选型建议)
7. [结论](#7-结论)
8. [单模型深度档案](#8-单模型深度档案)

---

## 1. 研究方法与时间锚定

- 本报告基于 2025 年 Q2 至 2026 年 4 月期间的官方博客、技术报告、Gemini API 与 Vertex AI 文档、火山引擎官方公告 / 火山方舟文档、Black Forest Labs 发布、以及 Artificial Analysis / LMArena 基准数据、第三方深度评测（302.AI Benchmark Lab、WaveSpeed、APIYi、ComfyUI、Akool、Atlas Cloud、36Kr、腾讯云、凤凰科技、每日经济新闻）。
- 所有关键论断均在子文档中以 `[序号]` 标注具体来源；**对于 Preview 阶段的 Seedream 5.0 旗舰，严格区分"已官方确认"与"Preview 预告 / 第三方预热"**，后者在行尾注明 *[Preview]*。

## 2. Seedream 家族版本演进

| 版本 | 发布 | 定位 |
|---|---|---|
| Seedream 3.0 | 2025-04 | 原生 2K、3 秒出图、纯文生图；有完整技术报告。 |
| Seedream 4.0 | 2025-09-09 | DiT 统一文生图 + 编辑；原生 4K；推理速度 10× 提升。 |
| Seedream 4.5 | 2025-12 前后 | "4.0 的完整形态"；多图一致性与 4K / SOTA 中文文字。 |
| **Seedream 5.0（旗舰）** | **Preview（未 GA）** | "智能层"升级：Visual CoT、流式生成、实时检索、极致写实。 |
| **Seedream 5.0 Lite** | **2026-02-13 GA** | 轻量款先行：CoT 推理 + 联网检索；\$0.035/图。 |

> 本报告不再把 Seedream 4.0 作为独立章节展开。主战场是 **5.0 Lite（已可用）** 与 **旗舰 5.0（Preview）**。

## 3. 模型定位与技术归属

| 模型 | 团队 | 技术路线 | 定位 |
|---|---|---|---|
| Seedream 5.0（Preview） | 字节跳动 Seed | DiT + Visual CoT + 流式 + 检索增强 *[Preview]* | 下一代旗舰；专业创意生产 |
| Seedream 5.0 Lite | 字节跳动 Seed | DiT + CoT + 实时联网检索 | 低成本主力产线；中文场景最佳 TCO |
| Nano Banana (2.5 Flash Image) | Google DeepMind | 原生多模态 LLM | 对话式修图、多轮一致性代际优势 |
| Nano Banana Pro (3 Pro Image) | Google DeepMind | 原生多模态 LLM（Gemini 3 Pro 底层） | 工作室级精度；Grounding + SOTA 文字 |
| Imagen 4 Fast | Google DeepMind | 扩散（Imagen 4 家族） | \$0.02 批量 / 原型档 |
| FLUX 2 Pro | Black Forest Labs | Rectified Flow Transformer + Mistral 3 24B VLM | 照片级写实 + 10 张参考 + 开源档 |

**两条技术路线 + 一条商业路线**：

- **扩散 / 流匹配** 路线（Seedream / Imagen / FLUX）—— 细节密度、中文字符、复杂排版上持续领先。
- **原生多模态 LLM** 路线（Nano Banana 系列）—— 对话式编辑、多轮一致性、世界知识代际领先；Pro 版叠加 Google Search Grounding 与 SOTA 文字渲染。
- **商业路线**：BFL [dev] 是唯一可私有化的开源档；其他均为闭源 API。

## 4. 核心能力分析

### 4.1 文生图画质 & 审美

- **写实 / 电影级**：FLUX 2 Pro ≈ Nano Banana Pro > Seedream 5.0 旗舰（Preview）> Seedream 5.0 Lite > Imagen 4 Fast。
- **东方审美 / 中文美学**：Seedream 5.0 Lite（> 所有对手）> Nano Banana Pro > 其他。
- **复杂构图 / 多主体**：Nano Banana Pro ≈ FLUX 2 Pro（多参考）> Seedream 5.0 Lite > Imagen 4 Fast。

### 4.2 文字渲染

- **中文**：Seedream 5.0 Lite（与旗舰）是 SOTA 级，远胜其他。
- **英文 / 多语言 / 长文本 / 信息图**：**Nano Banana Pro SOTA**，其次 FLUX 2 Pro、Imagen 4 Fast。

### 4.3 对话式多轮编辑

- **Nano Banana / Pro** 仍然是代际领先，原生 LLM 天然胜任。
- 其他扩散族模型即使强化了编辑也更像"每次独立 prompt"。

### 4.4 多图 / 参考一致性

- **FLUX 2 Pro** 最多 10 张参考图独占鳌头。
- Nano Banana 系列靠对话线内一致性取胜。
- Seedream 5.0 Lite 通过多图输入做组图 / 续写，体验排名次之。

### 4.5 世界知识 / 实时检索

- **Nano Banana Pro**：Google Search Grounding，事实准确。
- **Seedream 5.0 Lite**：首次搭载联网检索，东方 / 中文数据源覆盖更优。
- 其他模型均为"离线模型"，无实时知识。

### 4.6 分辨率

| 模型 | 最大分辨率 |
|---|---|
| Seedream 5.0 Lite | 2K |
| Seedream 5.0 旗舰 | 2K 直接 / 4K AI 增强 *[Preview]* |
| Nano Banana | 1K/2K/4K 分档计价 |
| Nano Banana Pro | 原生 2K & 4K |
| Imagen 4 Fast | 2K |
| FLUX 2 Pro | 4MP |

## 5. 价格、延迟、API

### 5.1 价格（官方权威）

见 [`comparison.md`](./comparison.md) 第 2 节完整表格。要点：

- 最便宜档：**Imagen 4 Fast \$0.02** 全档统一。
- 中文性价比档：**Seedream 5.0 Lite \$0.035**。
- 对话式便宜档：**Nano Banana 1K \$0.067 / 2K \$0.101**（Batch -50%）。
- 高端档：**Nano Banana Pro 1K/2K \$0.134 / 4K \$0.24**（Batch -50%）。
- 照片写实档：**FLUX 2 Pro \$0.03–0.06**。
- **Seedream 5.0 旗舰**：价格待定（未 GA）。

### 5.2 延迟

- 亚秒：FLUX 2 [klein]
- 1–3 s：Imagen 4 Fast
- 几秒：Nano Banana、Seedream 5.0 Lite、FLUX 2 Pro、Seedream 5.0 旗舰（Preview）
- 10–20 s：**Nano Banana Pro**（定位专业生产而非实时）

### 5.3 API

- **Seedream 系列**：火山引擎 / 火山方舟、即梦、豆包、Atlas Cloud、WaveSpeed、ComfyUI、Akool、APIYi。
- **Google 系列**：Gemini API、Google AI Studio、Vertex AI、OpenRouter、fal.ai、Together AI。
- **FLUX 2 Pro**：BFL API / Playground、fal.ai、Replicate、Together AI、Azure AI Foundry、Nvidia RTX AI Garage、CometAPI。

## 6. 场景推荐与选型建议

完整场景表与决策树见 [`comparison.md`](./comparison.md)。精简版：

1. 中文 / 海报 / 东方审美 → **Seedream 5.0 Lite**；未来 GA 后升级到旗舰 5.0。
2. 时效性 / 事件配图 → **Nano Banana Pro**（Google Search Grounding）；东方语料优先 **Seedream 5.0 Lite**（联网检索）。
3. 对话式修图 → **Nano Banana** 便宜；**Nano Banana Pro** 精修。
4. 专业信息图 / 多语言排版 → **Nano Banana Pro**。
5. 英文批量 / 设计草图 → **Imagen 4 Fast**。
6. 照片写实 / 多参考 / 私有化 → **FLUX 2 Pro** / **FLUX 2 [dev]**。

## 7. 结论

- "No single winner." 四/五家阵容在能力雷达上继续错位：中文审美（Seedream）/ 对话式体验（Nano Banana）/ TCO（Imagen 4 Fast）/ 照片写实（FLUX 2）仍各自占据独有象限。
- Google 在 Pro 版上把"工作室级精度 + 世界知识 + SOTA 文字"首次带进了可调 API，但价格决定它是"定稿"而非"日常"。
- 字节以 Lite 版先一步把"CoT + 实时检索"带进生产，\$0.035/图 的价格显著拉低了"带知识型图像"的批量成本。
- 最健康的生产组合仍然是**多模型编排**：Nano Banana 做草稿 + Seedream 5.0 Lite / Nano Banana Pro 做定稿 + Imagen 4 Fast 做变体 + FLUX 2 Pro 做写实硬菜。

## 8. 单模型深度档案

- [Seedream 5.0（旗舰 · Preview）](./models/seedream-5.md)
- [Seedream 5.0 Lite](./models/seedream-5-lite.md)
- [Nano Banana (Gemini 2.5 Flash Image)](./models/nano-banana.md)
- [Nano Banana Pro (Gemini 3 Pro Image)](./models/nano-banana-pro.md)
- [Imagen 4 Fast](./models/imagen-4-fast.md)
- [FLUX 2 Pro（对照）](./models/flux-2-pro.md)
- [参考资料索引](./references.md)

---

### 引文（主报告内直接使用）
1. 字节 Seed 博客·Seedream 5.0 Lite：https://seed.bytedance.com/zh/blog/deeper-thinking-more-accurate-generation-introducing-seedream-5-0-lite
2. PixVerse / Atlas Cloud · Seedream 5.0 Preview 能力预告：https://pixverse.blog/zh/blog/seedream-5-0/ · https://www.atlascloud.ai/blog/ai-updates/Seedream-5.0-is-coming-soon
3. Gemini API 定价页：https://ai.google.dev/gemini-api/docs/pricing
4. Google Developers Blog · Imagen 4 Fast 家族 GA：https://developers.googleblog.com/announcing-imagen-4-fast-and-imagen-4-family-generally-available-in-the-gemini-api/
5. Vertex AI · Imagen 4 模型文档：https://docs.cloud.google.com/vertex-ai/generative-ai/docs/models/imagen/4-0-generate
6. Black Forest Labs · FLUX.2 发布：https://bfl.ai/blog/flux-2
