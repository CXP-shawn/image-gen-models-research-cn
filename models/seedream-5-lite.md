# Seedream 5.0 Lite 深度档案

> 状态：**已正式发布，2026-02-13**
> 研发方：字节跳动 豆包 Seed 团队
> 接入：火山引擎（火山方舟）、即梦、豆包、Atlas Cloud、WaveSpeed、ComfyUI、Akool

## 1. 模型定位与技术归属

- **归属**：字节跳动 豆包 Seed 团队 —— Seedream 家族的"轻量旗舰"档位。官方定位为"更深入思考、更精准生成"的**生产级低成本**模型。[1][2]
- **发布时间**：**2026-02-13** 官方发布，同日登陆即梦 / 火山方舟体验中心，API 于 2 月中下旬上线火山方舟。[1][3][4]
- **技术路线**：延续 Seedream 4.x 的统一文生图 + 编辑框架，新增**深度推理（CoT）**、**实时联网检索（Retrieval-based Generation，首次搭载）**、跨模态理解。[1][2][5]
- **关系**：是 Seedream 5.0 Lite 主线，先于旗舰 5.0 正式 GA；为未来旗舰 5.0 的"智能层"能力做先行落地。[1][6]

## 2. 核心能力

### 2.1 输入与生成模式
- 支持文本生成图像、**单图输入**与**多图输入**（多图融合 / 组图生成 / 图像编辑）。[7]
- **首次搭载联网检索**：生成可结合实时互联网知识（时效性新闻、体育赛果、配方、数据等）。[1][5]

### 2.2 深度推理（CoT）
- 引入 Chain-of-Thought 结构，"从识别走向理解"，对复杂提示、知识型场景的指令遵循、结构一致性显著优于 Seedream 4.0/4.5。[1][2]

### 2.3 多图一致性与编辑
- 组图生成、角色 / 产品 / 风格延续、图像精修 —— 继承 4.x 的能力，并因为推理层的引入而提升稳定性。[1][2][6]

### 2.4 中文文字渲染
- 继承 Seedream 家族"中文字符 / 海报排版 SOTA"基因；5.0 Lite 官方把"文字渲染 + 理解"作为关键卖点之一。[1]

### 2.5 分辨率与长宽比
- 支持 2K 输出；官方与第三方文档**未明确旗舰 5.0 才有的 AI 增强 4K 是否在 Lite 上可用**。长宽比支持多档常见比例。*[官方未精确列出全部]*[1][7]

### 2.6 局限
- 官方与第三方都描述：相对未来旗舰 5.0，Lite 在"结构稳定性 / 极致写实"上有小幅差距；追求最高写实感时建议使用 Seedream 4.5 或未来的 5.0 旗舰。[6]

## 3. 典型用途

1. **批量低成本的中文电商 / 社交 / 广告内容**：\$0.035/图 的报价使其成为中文场景下最具性价比的"主力产线"。[8]
2. **带时效性的内容图像**：联网检索让其可生成"今日天气"、"今日体育赛况"、"今晚股市收盘"这类带真实数据的插图。[1][5]
3. **多图参考 / 组图 / 系列化输出**：例如同一角色的多场景延展、同一产品的多视角 SKU。
4. **生产工作流集成**：ComfyUI、Akool 等第三方已上架 Lite 节点。[5][9]

## 4. API 可用性与价格

- **官方入口**：
  - 火山方舟（Volcano Ark）体验中心；API 模型 ID 形如 `doubao-seedream-5-0-lite`（随火山引擎官方文档为准）。[3][4][10]
  - 即梦（Jimeng）、豆包 App 内嵌。[1][3]
- **第三方托管**：WaveSpeed（`bytedance-seedream-v5-0-lite`）、Atlas Cloud、ComfyUI、Akool、APIYi 聚合。[5][8][9][11]
- **价格**：
  - **第三方代理 APIYi 明示：约 \$0.035 / 图（比 Seedream 4.5 更便宜）**。[8]
  - 火山引擎端当前促销"新人首单 19 元起"；年度高级版套餐约 ¥200,000（含 ~220 万张生图额度，折合 ~¥0.09/张）。[12]
- **延迟**：第三方托管方报价为几秒级；官方未单独披露具体延迟数据。

## 5. 基准评测

- 官方公告附的雷达图显示 Lite 在"指令遵循、一致性、推理"三维度 Elo 超过 Seedream 4.5，整体综合得分领先 4.5。[1][6]
- 与 Nano Banana (Gemini 2.5 Flash Image)：对话式多轮编辑仍逊于 Nano Banana，但在中文渲染、组图一致性上更优。*[综合评估，基于两者公开能力]*
- 与 Imagen 4 Fast / FLUX 2 Pro：Lite 在"中文 + 知识检索"这对组合拳上差异化明显。

## 6. 已知局限

- 极致写实与结构稳定性略逊于 Seedream 4.5 / 未来的 5.0 旗舰。[6]
- 官方未公开完整技术报告，具体参数规模、训练细节缺失。[1]
- 联网检索需要特定 API 开关；非所有托管方都启用。[5]

## 参考来源
1. 字节 Seed 博客·Seedream 5.0 Lite 正式发布（中文）：https://seed.bytedance.com/zh/blog/deeper-thinking-more-accurate-generation-introducing-seedream-5-0-lite
2. Seed 英文博客：https://seed.bytedance.com/en/blog/deeper-thinking-more-accurate-generation-introducing-seedream-5-0-lite
3. 凤凰科技·5.0 Lite 上线火山方舟：https://tech.ifeng.com/c/8qi8LB59jd6
4. 腾讯新闻·Seedream 5.0 Lite 报道：https://news.qq.com/rain/a/20260213A03F2K00
5. WaveSpeed·Seedream v5.0 Lite 托管公告：https://wavespeed.ai/blog/posts/introducing-bytedance-seedream-v5-0-lite-on-wavespeedai/
6. 36Kr EU·Lite 与旗舰差异分析：https://eu.36kr.com/en/p/3677025348395653
7. Seedream 5.0 Lite 项目主页：https://seed.bytedance.com/zh/seedream5_0_lite
8. APIYi·Seedream 5.0 Lite API 指南与价格：https://help.apiyi.com/en/seedream-5-0-lite-api-guide-cheaper-than-4-5-en.html
9. ComfyUI Blog·Lite 接入：https://blog.comfy.org/p/seedream-50-lite-now-available-in
10. 火山引擎·新人特惠活动页：https://www.volcengine.com/activity/seedream
11. Akool Blog·Lite 上线：https://akool.com/zh/blog-posts/seedream-5-0-lite-smart-real-time-search-ai-image-model-now-live-on-akool
12. 火山引擎·豆包模型计费文档：https://www.volcengine.com/docs/82379/1544106
