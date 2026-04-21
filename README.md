# image-gen-models-research-cn

> **本报告已于 2026-04-21 更新到最新版本阵容（v2）。**
>
> 中文调研报告：系统对比 **Seedream 5.0（旗舰 · Preview）** · **Seedream 5.0 Lite**（字节跳动豆包 Seed）· **Nano Banana / Gemini 2.5 Flash Image** · **Nano Banana Pro / Gemini 3 Pro Image**（Google DeepMind）· **Imagen 4 Fast**（Google DeepMind），并以 **FLUX 2 Pro**（Black Forest Labs）作为对照参考。

## TL;DR

2026 年初四家阵营的最新事实：

- **Seedream 5.0 旗舰**：**Preview 状态，尚未 GA**；已披露能力包括 Visual Chain-of-Thought、流式生成、实时检索增强、结构稳定性 + 极致写实。
- **Seedream 5.0 Lite**（**2026-02-13 GA**）：CoT 推理 + **首次实时联网检索** + 多图输入 + 中文 SOTA 文字；报价约 **\$0.035/图**，当前中文场景下最强性价比。
- **Nano Banana (Gemini 2.5 Flash Image)**：按分辨率分档定价 — 1K **\$0.067** / 2K **\$0.101** / 4K **\$0.151**；依旧是对话式多轮编辑的首选。
- **Nano Banana Pro (Gemini 3 Pro Image, 2025-11-20 发布)**：1K/2K **\$0.134** / 4K **\$0.24**（Batch 半价）；**Google Search Grounding**、**SOTA 多语言文字**、**SynthID + C2PA**。
- **Imagen 4 Fast**：稳定在 **\$0.02/图**；至今未见 Imagen 5 官宣。
- **FLUX 2 Pro（对照）**：32B Flow Matching + Mistral 3 24B VLM，**最多 10 张参考图**，提供唯一的开源权重 [dev] 档。

**选型一句话**：中文 → **Seedream 5.0 Lite**（未来旗舰 5.0）；对话式改图 → **Nano Banana**；高端定稿 / 信息图 → **Nano Banana Pro**；英文批量 → **Imagen 4 Fast**；写实 / 私有化 → **FLUX 2 Pro / [dev]**。

## 目录

- [`report.md`](./report.md) — 主报告正文（v2）
- [`comparison.md`](./comparison.md) — 横向对比矩阵、价格表、决策树
- [`models/seedream-5.md`](./models/seedream-5.md) — Seedream 5.0（旗舰 · Preview）
- [`models/seedream-5-lite.md`](./models/seedream-5-lite.md) — Seedream 5.0 Lite（已 GA）
- [`models/nano-banana.md`](./models/nano-banana.md) — Nano Banana（Gemini 2.5 Flash Image）
- [`models/nano-banana-pro.md`](./models/nano-banana-pro.md) — Nano Banana Pro（Gemini 3 Pro Image）
- [`models/imagen-4-fast.md`](./models/imagen-4-fast.md) — Imagen 4 Fast
- [`models/flux-2-pro.md`](./models/flux-2-pro.md) — FLUX 2 Pro（对照）
- [`references.md`](./references.md) — 全部参考资料（已刷新）

## 核心参数速览（v2）

| 模型 | 团队 | 状态 | 最大分辨率 | 官方价格 / 张 | 亮点 |
|---|---|---|---|---|---|
| Seedream 5.0（旗舰） | 字节 Seed | **Preview** | 2K / 4K 增强 *[Preview]* | 未定 | Visual CoT · 流式 · 检索增强 |
| **Seedream 5.0 Lite** | 字节 Seed | **GA** | 2K | **\$0.035** | CoT + 首次联网检索 + 中文 SOTA |
| Nano Banana | Google DeepMind | GA | 4K 分档 | 1K \$0.067 / 2K \$0.101 / 4K \$0.151 | 对话式编辑代际优势 |
| **Nano Banana Pro** | Google DeepMind | GA | **4K 原生** | 1K/2K \$0.134 / 4K \$0.24 | Grounding + SOTA 文字 + C2PA |
| Imagen 4 Fast | Google DeepMind | GA | 2K | **\$0.02** | 最便宜 |
| FLUX 2 Pro（对照） | BFL | GA | 4MP | \$0.03–0.06 | 10 张参考 + 开源 [dev] |

## 调研方法

- 时间锚定：2025 Q2 – 2026 Q1 + 2026-04 刷新。
- 优先来源：官方博客 / API 文档 / Vertex AI 文档 / 火山引擎文档 / 厂商发布会 / Artificial Analysis / LMArena；辅助 302.AI、APIYi、Atlas Cloud、WaveSpeed、36Kr、凤凰科技、腾讯云。
- 所有关键数值与论断均在各子档案以 `[序号]` 标注具体 URL，索引见 [`references.md`](./references.md)。
- **Preview 信息严格标注**：Seedream 5.0 旗舰尚未 GA 的条目均在行尾加 *[Preview]* 字样。

## 许可

调研内容为独立产物。各模型官方信息与引用片段的版权归其原始发布者所有。
