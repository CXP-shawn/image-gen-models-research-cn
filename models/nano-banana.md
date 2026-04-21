# Nano Banana (Gemini 2.5 Flash Image) 深度档案

> 模型 ID：`gemini-2.5-flash-image`（稳定版，2025-10 GA）
> 发布：2025-08-26
> 研发方：Google DeepMind / Google AI
> 升级版（独立档案）：`gemini-3-pro-image-preview` — 见 [`nano-banana-pro.md`](./nano-banana-pro.md)

## 1. 模型定位与技术归属

- **归属**：Google DeepMind，Gemini 2.5 Flash 家族的图像分支。[1][2]
- **发布**：2025-08-26 以 preview 形式上线，2025-10 进入生产就绪（GA），新增多档长宽比与更高分辨率档位。[1][2]
- **命名由来**：在 LMArena 匿名测试阶段因"香蕉变形一致角色"的多轮编辑效果爆红，社区昵称 Nano Banana 后被 Google 官方传播采用。[1][3]
- **技术路线**：**原生多模态 LLM**，通过自回归方式输出图像 token（与扩散模型的去噪/流匹配机制根本不同），天然适合"对话式精修、多轮保持一致、多图融合"。[1][3]

## 2. 核心能力

### 2.1 对话式 / 多轮编辑
- 在整条对话线内保持主体、布景、光线一致；这是相对扩散模型的代际差异优势。[1][3]
- 支持多图融合（multi-image fusion）。[3]

### 2.2 局部精准编辑
- 不依赖显式 mask 也能改"某个局部"，其余部分保持不变。[3]

### 2.3 文字渲染
- Flash Image 版文字渲染良好但不是 SOTA；SOTA 级在 Pro 版实现，见 [`nano-banana-pro.md`](./nano-banana-pro.md)。[4][5]

### 2.4 世界知识
- 由 Gemini LLM 继承世界知识（2.5 系列知识截止 ~2025-06）；事实性场景可用但不支持 Google Search Grounding（Pro 版支持）。[2][4]

### 2.5 水印
- 输出默认带 **SynthID 不可见水印**。[2]

### 2.6 分辨率与长宽比
- GA 后支持 10 种长宽比（21:9、16:9、9:16、3:4、4:3、1:1 等），分辨率覆盖 1K / 2K / 4K 三档。[2]

## 3. 典型用途

1. **对话式修图 / 创意迭代**：核心场景。[1][3]
2. **角色一致的分镜、故事板**。[3]
3. **多图融合的品牌资产合成**：服装 + 场景 + 光线。[3]
4. **快节奏社交媒体图文**：延迟低、价格友好。

## 4. API 可用性与价格（2026 年最新官方定价）

- **官方渠道**：Gemini API、Google AI Studio、Vertex AI。[2]
- **模型 ID**：`gemini-2.5-flash-image`。
- **第三方托管**：OpenRouter、fal.ai（`fal-ai/nano-banana`）、Together AI、多家聚合代理。[6]
- **官方价格（Gemini API 定价页，按分辨率计）**[6]：

| 分辨率 | 价格 / 张 |
|---|---|
| 1K | **\$0.067** |
| 2K | **\$0.101** |
| 4K | **\$0.151** |

> **价格刷新说明**：早期按 output token 计算的 \$0.039/图 报价，在 GA 后已切换为"按分辨率分档"的上述价格表；后者以 https://ai.google.dev/gemini-api/docs/pricing 为权威。[6]

- **Batch API**：上述价格 50% 折扣。[6]
- **延迟**：几秒级（同档位最快之一）。
- **商用许可**：商用允许；SynthID 强制；受 Google Generative AI 使用条款与 AUP 约束。[2]

## 5. 基准评测

- 发布初期 **LMArena Image Arena 榜首**（匿名投票冠军）。[1]
- Artificial Analysis：**图像编辑榜第一**（Elo ≈ 1212）；文生图榜上略逊于某些字节系 / GPT-4o Image 版本。[6]
- 与 Seedream：对话式编辑 / 多轮一致性 Nano Banana 占优；中文渲染 / 东方审美 Seedream 占优。[7]
- 与 Pro 版：见 [`nano-banana-pro.md`](./nano-banana-pro.md) 表格。

## 6. 已知局限

- 中文字符与复杂中文排版弱于 Seedream 系列。[7]
- 文生图绝对画质仍有场景落后于专门扩散/流匹配旗舰（Seedream 5.0 Lite、FLUX 2 Pro、Imagen 4 Ultra）。
- 强制 SynthID 水印。

## 参考来源
1. Google Blog·Nano Banana Google Trends 2025：https://blog.google/products-and-platforms/products/gemini/nano-banana-google-trends-2025/
2. Gemini API·gemini-2.5-flash-image 文档：https://ai.google.dev/gemini-api/docs/models/gemini-2.5-flash-image
3. 36Kr·Nano Banana 技术解读：https://m.36kr.com/newsflashes/3440358498506120
4. Google Blog·Nano Banana Pro 开发者视角：https://blog.google/innovation-and-ai/technology/developers-tools/gemini-3-pro-image-developers/
5. DeepMind·Gemini Image Pro 产品页：https://deepmind.google/models/gemini-image/pro/
6. Gemini API 定价页：https://ai.google.dev/gemini-api/docs/pricing
7. 302.AI·Seedream 4 vs Nano Banana 实测：https://302.ai/blog/302-ai-benchmark-lab-review-on-seedream-4-0-vs-nano-banana/
