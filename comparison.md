# 图像 AI 模型横向对比矩阵（v2 · 刷新版）

> 更新时间：2026-04-21
> 阵容：**Seedream 5.0（旗舰，Preview）** · **Seedream 5.0 Lite** · **Nano Banana (Gemini 2.5 Flash Image)** · **Nano Banana Pro (Gemini 3 Pro Image)** · **Imagen 4 Fast**
> 对照参考：**FLUX 2 Pro**（Black Forest Labs）

---

## 1. 一览表：核心参数

| 维度 | Seedream 5.0（Preview） | Seedream 5.0 Lite | Nano Banana (2.5 Flash Image) | Nano Banana Pro (3 Pro Image) | Imagen 4 Fast | FLUX 2 Pro（对照） |
|---|---|---|---|---|---|---|
| **研发团队** | 字节跳动 豆包 Seed | 字节跳动 豆包 Seed | Google DeepMind | Google DeepMind | Google DeepMind | Black Forest Labs |
| **发布状态** | **未 GA**，仅 Preview | **已 GA（2026-02-13）** | GA（2025-10） | GA（2025-11-20） | GA（2025-08-14） | GA（2025-11-25） |
| **技术路线** | DiT + 智能层（Visual CoT / 流式 / 检索增强） *[Preview]* | DiT + CoT 推理 + 联网检索 | 原生多模态 LLM（自回归） | 原生多模态 LLM（Gemini 3 Pro 底层） | 扩散（Imagen 4 家族） | Rectified Flow Transformer + Mistral 3 24B VLM |
| **最大分辨率** | 2K 直接 / 4K AI 增强 *[Preview]* | 2K | 4K（分档计价） | **原生 2K & 4K** | 2K | 4MP（~2K×2K） |
| **中文渲染** | SOTA *[Preview]* | **★★★★★** | ★★★ | ★★★★ | ★★ | ★★ |
| **英文 / 多语言文字渲染** | 强 *[Preview]* | ★★★★ | ★★★★ | **★★★★★ SOTA** | ★★★★ | ★★★★★ |
| **对话式多轮编辑** | 强（流式交互） *[Preview]* | ★★★ | **★★★★★** | ★★★★★ | ☆（Fast 不支持编辑） | ★★★ |
| **多图 / 参考一致性** | 很强 *[Preview]* | ★★★★ | ★★★★ | ★★★★ | ☆ | **★★★★★（10 张）** |
| **世界知识 / 推理** | 强（含实时检索） *[Preview]* | ★★★★ | ★★★ | **★★★★★（Google Search Grounding）** | ★★★ | ★★★ |
| **SynthID / 水印** | 无 | 无 | SynthID | **SynthID + C2PA** | SynthID | 无 |
| **开源权重** | 否 | 否 | 否 | 否 | 否 | **是（[dev] 档）** |

---

## 2. 价格对比（官方权威定价）

| 模型 | 1K / 张 | 2K / 张 | 4K / 张 | Batch API | 备注 |
|---|---|---|---|---|---|
| Seedream 5.0（Preview） | 未公布 | 未公布 | 未公布 | — | 旗舰未 GA，价格待定 |
| **Seedream 5.0 Lite** | \$0.035（统一价，第三方代理）[A] | — | — | — | 火山引擎新人 ¥19 起；高级版年付 ¥200k 含 220 万张 |
| **Nano Banana (2.5 Flash Image)** | \$0.067 | \$0.101 | \$0.151 | -50% | 官方 Gemini API[B] |
| **Nano Banana Pro (3 Pro Image)** | **\$0.134** | **\$0.134** | **\$0.24** | -50% | 官方 Gemini API；1K/2K 同价[B] |
| **Imagen 4 Fast** | **\$0.02**（全档统一） | — | — | — | 四家最便宜[B] |
| Imagen 4 (Standard) | \$0.04 | — | — | — | [B] |
| Imagen 4 Ultra | \$0.06 | — | — | — | [B] |
| FLUX 2 Pro | \$0.03–\$0.06 | — | — | — | 随分辨率/参考图[C] |

[A] APIYi · Seedream 5.0 Lite API Guide: https://help.apiyi.com/en/seedream-5-0-lite-api-guide-cheaper-than-4-5-en.html
[B] Gemini API 定价页: https://ai.google.dev/gemini-api/docs/pricing
[C] bfl.ai / fal.ai 定价页

---

## 3. 延迟对比

| 模型 | 典型延迟 |
|---|---|
| FLUX 2 [klein] | 亚秒 |
| Imagen 4 Fast | 1–3 s |
| Nano Banana (2.5 Flash Image) | 几秒 |
| Seedream 5.0 Lite | 几秒 |
| FLUX 2 Pro / Seedream 5.0 旗舰（Preview） | 几秒 |
| **Nano Banana Pro (3 Pro Image)** | **10–20 s**（高分辨率更久，非实时定位） |

---

## 4. 场景 → 模型推荐表

| 业务场景 | 首选 | 次选 | 备注 |
|---|---|---|---|
| **中文电商主图 / 详情页 / 海报** | **Seedream 5.0 Lite** | 旗舰 5.0（GA 后） | 中文渲染 SOTA + \$0.035/图 性价比 |
| **中文广告 slogan / KV / 品牌延展** | **Seedream 5.0 Lite** | Seedream 4.5 / 旗舰 5.0 | 中文文字 + 排版 |
| **需要实时事件 / 时效数据的配图** | **Nano Banana Pro** | Seedream 5.0 Lite | Pro = Google Search Grounding；Lite = 中文 + 联网检索 |
| **对话式修图 / 多轮迭代改稿** | **Nano Banana** | Nano Banana Pro | 便宜快的对话式首选；Pro 用于高质量定稿 |
| **角色一致的分镜 / 故事板** | **Nano Banana Pro** | Seedream 5.0 Lite | Pro 一致性更稳 |
| **专业信息图 / 带长文本排版 / 多语言本地化** | **Nano Banana Pro** | FLUX 2 Pro | SOTA 文字 + 世界知识 |
| **UI / 设计草图 / 原型** | **Imagen 4 Fast** | Nano Banana | \$0.02 + 1-3 s |
| **英文批量广告素材 A/B 变体** | **Imagen 4 Fast** | FLUX 2 [klein] | 成本最低 |
| **照片级写实 / 产品摄影大片** | **FLUX 2 Pro** | Nano Banana Pro | BFL 写实档位 |
| **游戏角色立绘 / 多参考 IP 一致性** | **FLUX 2 Pro**（10 张参考） | Seedream 5.0 Lite | 10 张参考上限独一份 |
| **本地部署 / 数据合规 / 私有化** | **FLUX 2 [dev]**（开源） | — | 四家里唯一可私有化 |
| **企业合规图像生产（C2PA 溯源）** | **Nano Banana Pro** | — | 默认 SynthID + C2PA |

---

## 5. 决策树（v2）

```
你的首要需求是什么？
│
├── 1) 中文内容 / 海报 / 中文字符精准渲染？
│      └── 首选：Seedream 5.0 Lite（已 GA + \$0.035/图）
│           旗舰 5.0 GA 后升级为首选
│
├── 2) 需要实时事件 / 时效性数据准确的图像？
│      └── 首选：Nano Banana Pro（Google Search Grounding）
│           次选：Seedream 5.0 Lite（联网检索）
│
├── 3) 对话式反复改图、多轮保持角色一致？
│      ├── 快而便宜：Nano Banana（\$0.067 起）
│      └── 高质量定稿：Nano Banana Pro（\$0.134 起）
│
├── 4) 专业信息图 / 多语言文字 / 长文本排版？
│      └── 首选：Nano Banana Pro（SOTA 文字）
│
├── 5) 照片级写实 / 10 张参考图 / 角色 IP？
│      └── 首选：FLUX 2 Pro
│
├── 6) 英文批量、成本极致敏感？
│      └── 首选：Imagen 4 Fast（\$0.02/图）
│
└── 7) 数据不出域 / 私有化部署？
       └── FLUX 2 [dev]（开源权重）
```

---

## 6. 一句话差异化总结（v2）

- **Seedream 5.0（Preview）** = "智能层"升级的下一代 DiT：Visual CoT + 流式生成 + 实时检索；未 GA，建议关注。
- **Seedream 5.0 Lite** = 中文世界的"主力产线"：\$0.035、联网检索、CoT、已 GA 可用。
- **Nano Banana** = 对话式多轮编辑的代际优势版，快而便宜。
- **Nano Banana Pro** = Gemini 3 Pro 下的"工作室级"图像：SOTA 文字 + 世界知识 Grounding + 2K/4K。
- **Imagen 4 Fast** = \$0.02/图，英文批量场景 TCO 最优。
- **FLUX 2 Pro（对照）** = 照片级写实 + 10 张参考图 + 唯一开源档位。
