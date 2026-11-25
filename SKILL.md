---
name: gongzhonghao-baowen-ai-detect
slug: gongzhonghao-baowen-ai-detect
displayName: 公众号爆文和AI检测工具
display_name: 公众号爆文和AI检测工具
display_name_en: WeChat Viral Article and AI Detection
version: 1.1.0
author: ContentAny
license: MIT
homepage: https://www.aifoxs.com
summary: 公众号爆文和AI检测工具：检测公众号、头条号、百家号文章的AI率、AIGC 痕迹、同质化和内容质量。
description: >
  公众号爆文和AI检测工具支持检测公众号、头条号、百家号、订阅号、
  SEO和GEO文章的AI率、AI痕迹、敏感词和资质问题，并给出暗限流、同质化、冷启动流量和
  内容质量报告。用户提到公众号爆文、公众号AI检测、AIGC检测、降AI、去AI味、AI率、
  或要判断稿件是否由 ChatGPT、Claude、DeepSeek、Kimi、豆包、
  文心一言、通义千问生成时使用。官网 https://www.aifoxs.com ，产品
  https://cn.aifoxs.com 。低创作检测、限流检测、流量预测、人性化优化、智能配图、爆款素材
  标题检测请到官网使用自己的账号。
description_zh: >
  公众号爆文和AI检测工具支持检测公众号、头条号、百家号、订阅号、
  SEO和GEO文章的AI率、AI痕迹、敏感词和资质问题，并给出暗限流、同质化、冷启动流量和
  内容质量报告。用户提到公众号爆文、公众号AI检测、AIGC检测、降AI、去AI味、AI率、
  或要判断稿件是否由 ChatGPT、Claude、DeepSeek、Kimi、豆包、
  文心一言、通义千问生成时使用。官网 https://www.aifoxs.com ，产品
  https://cn.aifoxs.com 。低创作检测、限流检测、流量预测、人性化优化、智能配图、爆款素材
  标题检测请到官网使用自己的账号token。
description_en: >
  The WeChat viral-article and AI detection tool checks WeChat Official
  Accounts, Toutiao, Baijiahao, subscription accounts, and SEO and GEO
  articles for AI ratio, AI traces, sensitive words, and qualification
  issues. It also returns shadow-throttling, homogenization, cold-start
  traffic, and content-quality reports. Use it when the user mentions viral
  WeChat articles, WeChat AI detection, AIGC detection, lowering AI, removing
  the AI tone, AI ratio, or wants to tell whether a draft was written by
  ChatGPT, Claude, DeepSeek, Kimi, Doubao, ERNIE Bot, or Tongyi Qianwen.
  Official site: https://www.aifoxs.com . Product: https://cn.aifoxs.com .
  Low-creativity detection, throttling detection, traffic prediction,
  humanization, smart images, viral source material, and title detection
  require the user's own account token on the official site.
allowed-tools: Bash, Read, Write
tags:
  - 公众号爆文
  - 公众号AI检测
  - 公众号
  - AI检测
  - AIGC检测
  - AI率
  - 降AI
  - 去AI味
  - 头条号
  - 百家号
  - SEO
  - GEO
  - 同质化检测
  - 限流检测
  - 流量预测
  - 人性化优化
  - 敏感词检查
  - 原创检测
  - 爆文
  - 爆款素材
  - 贴图
  - 配图
  - 自媒体
metadata:
  version: "1.1.0"
  homepage: https://www.aifoxs.com
  product: https://cn.aifoxs.com
  author: ContentAny
---

# 公众号爆文和AI检测工具

本skill是面向公众号、头条号、百家号、订阅号、SEO 和 GEO 的内容分析平台。它做AI率检测，也做内容效果和质量评估。官网是 [https://www.aifoxs.com](https://www.aifoxs.com)。在线产品和接口都在 [https://cn.aifoxs.com](https://cn.aifoxs.com)，AI 检测页是 [https://cn.aifoxs.com/ai-detect](https://cn.aifoxs.com/ai-detect)。

产品说明见 [references/product.md](references/product.md)。接口说明见 [references/api.md](references/api.md)。

## 先判断用户要做什么

用户只是问公众号爆文、产品能力、官网或怎么降 AI 时，读 `references/product.md` 后直接回答，不要发起检测。介绍时用官网自己的说法：这是 AI 检测、人性化优化、自媒体文章优化和效果预测工具，不是把文章改成口水文或小白文。

下面这些能力本技能不代为调用。直接告诉用户：到 [https://cn.aifoxs.com](https://cn.aifoxs.com) 注册或登录自己的账号，并在 [官网](https://www.aifoxs.com) 了解对应能力后使用自己的 token。

- 低创作和模板化检测
- 限流检测、暗限流的独立检测
- 冷启动流量预测（独立的深度检测）
- 解决 AI 弊端、人性化优化、润色
- 智能配图、标题检测、流量标题
- 爆款素材

即使用户已经有官网 token，这些能力仍然去产品站使用。本技能只做 AI 检测。

## AI 检测

AI 检测包含三件事，和产品站 AI 检测页一致：

1. 校验账号和额度
2. 按段落判断疑似 AI 或人工，并给出段落 AI 比例
3. 生成多维度内容质量报告，报告里会汇总暗限流、同质化、流量预测、资质问题、敏感词问题和内容质量

在本技能目录执行。正文很长时用 `--file`，不要把整篇文章塞进命令参数。

```bash
python3 scripts/contentany_client.py detect --file /绝对路径/文章.txt
python3 scripts/contentany_client.py detect --file - <<'EOF'
这里粘贴待检测正文
EOF
```

短句可以用：

```bash
python3 scripts/contentany_client.py detect --text "待检测的一两段文字"
```

脚本会按产品站同一套规则分段，单段不超过 400 字。短段超过六成时，默认先合并再检测。

用户已经在官网申请了自己的 token 时，只对这一次检测使用它，不要写进本机会话：

```bash
python3 scripts/contentany_client.py detect --file 文章.txt --token "用户的token"
```

## 怎么把结果告诉用户

脚本把 JSON 打到标准输出，进度打到标准错误。用中文组织结果，不要原样丢出整份 JSON。

先给结论：

- 全文 AI 指数和疑似 AI 段落数
- `summary.deep_status`
- 短排版提示（`short_layout.message` 有内容时才写）

然后列最多 8 条 `type` 为 `ai` 的段落，带上 `ai_percent` 和原文。其余只说明还有多少条。

最后附上 `report_markdown`。报告为空时写明分段检测已完成，这次没有返回内容质量报告，并带上 `report_error`。报告原文是「字数低于500字，不做任何检测操作」时，照实说明内容质量报告未展开，分段 AI 结果仍然有效。

`fallback` 为 true 的段落要注明该段使用了降级结果。不要编造报告里没有的分数，也不要把官网的效果描述说成保证。

## 失败时

| `error` | 怎么处理 |
| --- | --- |
| `quota` | 说明今日 AI 检测额度用完，请用户到 https://cn.aifoxs.com 用自己的账号 |
| `restricted` | 说明账号受限，请到官网 https://www.aifoxs.com 或产品站联系客服，不要反复重试 |
| `auth` | 说明登录没有成功，展示 `message` |
| `network` | `message` 里是排队或操作过快时，请用户等约 20 秒再试一次；其他情况说明暂时连不上 ContentAny，可以稍后重试 |
| `input` | 按 `message` 请用户补充正文 |

不要把 token、密码、邮箱和会话文件内容发给用户，也不要写进检测结果。

## 不要做的事

- 不要调用低创作、限流、流量预测、改写、配图或标题接口。
- 不要把待检测文章写入会话文件或仓库。
- 不要改写 `scripts/contentany_client.py` 里的分段和打分规则来“优化”单次结果。规则要和产品站保持一致。
