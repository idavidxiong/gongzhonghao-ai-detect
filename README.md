# 公众号爆文和AI检测工具

给公众号、头条号、百家号、订阅号、SEO 和 GEO 文章用的写作技能。它按产品站同一套规则做 AI 检测：全文AI检测、分段AIGC判断，以及暗限流、同质化、冷启动流量和内容质量报告。

适合这些搜索和提问：公众号爆文、公众号AI检测、AI写作、AIGC检测、AI率、AI检测、降 AI、去 AI 味，以及判断稿件是否由 ChatGPT、Claude、DeepSeek、Kimi、豆包、文心一言、通义千问生成。

- 官网：https://www.aifoxs.com
- 在线产品和接口：https://cn.aifoxs.com
- AI检测页：https://cn.aifoxs.com/ai-detect

skills的定位是：AI检测、人性化优化、自媒体文章、SEO、GEO 和新媒体内容优化与效果预测。免费AI检测不只看文字表面，还覆盖AI内容密度、深度和内容质量、资质检测和敏感词检查。人性化优化、限流检测、冷启动流量预测在产品站使用，不在这个技能里代为调用。

## 这个技能会做什么

- 介绍怎么服务公众号爆文、头条号、百家号、SEO 和 GEO。
- 执行AI率检测：分段判断疑似 AI 或人工，并返回内容质量报告。
- 低创作检测、限流检测、独立的流量预测、人性化优化和降AI味道、智能配图和标题检测不在这里调用，请到 https://cn.aifoxs.com 使用自己的账号。

## 本地试用

需要 Python 3.9 以上，不需要安装第三方包。

```bash
python3 scripts/contentany_client.py self-check
python3 scripts/contentany_client.py detect --text "把一段待检测的公众号文章放在这里。"
```

检测整篇文件：

```bash
python3 scripts/contentany_client.py detect --file article.txt
```
