# image-gen-models-research-cn

> 中文调研报告：系统对比 **Seedream 4.0**（字节跳动豆包 Seed）· **Nano Banana / Gemini 2.5 Flash Image**（Google DeepMind）· **Imagen 4 Fast**（Google DeepMind）· **FLUX 2 Pro**（Black Forest Labs）四款 2025–2026 年主流图像 AI 模型。

## TL;DR

2025 年 Q3–Q4 是图像生成 AI 的"第二次寒武纪爆发"，四款主流模型沿着**两条技术路线**错位竞争：

- **Seedream 4.0**（扩散 Transformer，DiT）— **中文渲染 / 东方审美代差领先**，4K 原生。
- **Nano Banana (Gemini 2.5 Flash Image)**（原生多模态 LLM）— **对话式编辑、多轮一致性体验代际领先**。
- **Imagen 4 Fast**（扩散）— **\$0.02/张最便宜**，成本/速度/稳定性三角最优，英文批量场景首选。
- **FLUX 2 Pro**（Rectified Flow Transformer + Mistral 3 24B VLM）— **照片级写实 + 最多 10 张参考图 + 提供开源权重 [dev]**，写实与合规友好的唯一选择。

**没有全能王**。选型建议：中文选 Seedream、对话式选 Nano Banana、批量英文选 Imagen 4 Fast、写实/多参考选 FLUX 2 Pro。详见 [`report.md`](./report.md) 与 [`comparison.md`](./comparison.md)。

## 目录

- [`report.md`](./report.md) — 主报告正文（完整调研、7 大章节）
- [`comparison.md`](./comparison.md) — 横向对比矩阵、场景 → 模型推荐表、决策树
- [`models/seedream.md`](./models/seedream.md) — Seedream 4.0 深度档案
- [`models/nano-banana.md`](./models/nano-banana.md) — Nano Banana / Nano Banana Pro 深度档案
- [`models/imagen-4-fast.md`](./models/imagen-4-fast.md) — Imagen 4 Fast 深度档案
- [`models/flux-2-pro.md`](./models/flux-2-pro.md) — FLUX 2 Pro 深度档案
- [`references.md`](./references.md) — 全部参考资料索引（50+ 条官方与权威来源）

## 核心参数速览

| 模型 | 团队 | 发布 | 技术路线 | 最大分辨率 | 每张价格 | 亮点 |
|---|---|---|---|---|---|---|
| Seedream 4.0 | 字节跳动 豆包 Seed | 2025-09-09 | DiT | **4K** | ~¥0.2 / \$0.03 | 中文渲染 SOTA |
| Nano Banana | Google DeepMind | 2025-08-26 | 原生多模态 LLM | ~1K | \$0.039 | 对话式编辑一哥 |
| Nano Banana Pro | Google DeepMind | 2025-11-20 | 原生多模态 LLM | **4K** | \$0.134 | 文字渲染 SOTA，Google Search Grounding |
| Imagen 4 Fast | Google DeepMind | 2025-08-14 | 扩散 | 2K | **\$0.02** | 最便宜 |
| FLUX 2 Pro | Black Forest Labs | 2025-11-25 | Rectified Flow Transformer | 4MP | \$0.03–\$0.06 | 10 张参考图 + 开源 [dev] |

## 调研方法

- 信息时间锚定：2025 年 4 月 – 2026 年 4 月。
- 来源以官方博客、API 文档、厂商技术报告为主，辅以 Artificial Analysis、LMArena、302.AI Benchmark Lab、WaveSpeed、MindStudio、36Kr、腾讯云开发者社区等权威第三方评测。
- 所有关键数值（价格、分辨率、发布时间、Elo、模型 ID）都在对应章节以 `[序号]` 标注具体 URL，索引见 [`references.md`](./references.md)。

## 许可

报告内容为独立调研产物。各模型官方信息与引用片段的版权归其原始发布者所有。
