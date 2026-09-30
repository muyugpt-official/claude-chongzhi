---
title: "Claude 套餐与用量限制手册（2026-10）：Free、Pro、Max 5x / 20x 各包含什么，限额怎么算"
description: "Claude Free、Pro、Max 5x、Max 20x 的官方标价、包含的功能、Claude Code 是否包含，以及 5 小时会话窗口、每周上限、usage credits 的运作方式。按 Anthropic 定价页和帮助中心整理。"
permalink: /claude-plans-and-limits-2026/
lang: zh-CN
---

# Claude 套餐与用量限制手册：Free、Pro、Max 5x / 20x

> **最后核验：2026-10-01** · 维护方：MuyuGPT（[muyugpt.com](https://muyugpt.com/)）
>
> **第三方身份说明：** MuyuGPT 是面向中文用户的独立第三方 AI 订阅指南与订阅协助平台，并非 Anthropic 官方渠道，与 Anthropic 不存在官方隶属、授权或合作关系。
>
> **来源：** [Claude 定价页](https://claude.com/pricing) 与帮助中心 [What is the Max plan?](https://support.claude.com/en/articles/11049741-what-is-the-max-plan)。定价页注明"价格和套餐可能由 Anthropic 随时调整，未含税"，请以购买时的页面为准。

## 30 秒结论

- **Claude Code 包含在所有付费档**（Pro 和 Max），免费版不含；它和网页、桌面、手机共用同一份用量。
- **Max 只按月计费**，分 5x 和 20x 两档，倍数是相对 Pro 的**每个会话窗口**用量，不是"所有事情多 N 倍"。
- 限额有**两层**：每 5 小时重置的会话窗口，外加每周上限。没有固定的"消息条数"。
- 达到限额后，可以等重置、升档，或在付费档里开启 usage credits（按标准 API 价格计费）。

## 套餐对照

| 项目 | Free | Pro | Max 5x | Max 20x |
| --- | --- | --- | --- | --- |
| 官方标价（网页订阅） | $0 | $20/月；年付折合 $17/月（一次付 $200） | $100/月 | $200/月 |
| 计费周期 | — | 月付或年付 | 仅月付 | 仅月付 |
| 相对用量 | 基准 | 每个会话窗口至少为 Free 的 5 倍 | Pro 的 5 倍 | Pro 的 20 倍 |
| Claude Code | 不含 | 含 | 含 | 含 |
| Opus 模型 | 不含 | 含 | 含 | 含 |
| 其他要点 | 网页、桌面、手机聊天；联网搜索、文件、代码；记忆；Artifacts | 更多用量；安排和交接任务；Projects；更多模型；Chrome 与 Microsoft 365 集成 | 更高输出限额；新功能抢先体验；高峰期优先访问 | 同 Max 5x |

注意：

- 标价为**网页订阅价格**，手机应用内订阅的价格可能不同；税费另计。
- 帮助中心说明 Anthropic 不提供标准折扣，客服也无法发放一次性优惠券，偶尔会有限时活动。
- 各档位包含的功能和模型访问会调整，以定价页和你账号里显示的为准。

## 限额是怎么运作的

### 第一层：5 小时会话窗口

- 用量在滚动的 5 小时窗口里计算，窗口重置后恢复；
- Max 的 5x / 20x 倍数针对的就是**每个会话窗口的用量**。

### 第二层：每周上限

- 所有模型统一计算一个每周上限；
- 重置时间是**固定的**，与你何时开始使用、何时订阅无关，可以在 **Settings（设置）→ Usage（用量）** 查看；
- 官方还可能设置其他周期的上限，以及针对特定模型或功能的限制。

### 共用一个池

网页、桌面、手机和 Claude Code 的活动**共用同一份用量**。所以"Claude Code 用得多，网页就会更早触顶"是正常现象。

### 没有固定的消息条数

用量取决于对话长度、所选模型和用到的功能，官方没有给出"每天能发多少条"。定价页说的是相对倍数，不是绝对数字。

## 触顶后的选项

| 选项 | 怎么做 | 注意 |
| --- | --- | --- |
| 等重置 | 等会话窗口或每周上限重置 | 最省事，但会打断工作 |
| 升档 | 从 Pro 升 Max，或 5x 升 20x | 按剩余计费周期按比例计费；Max 仅月付 |
| usage credits | 在付费档里开启，触顶后继续用 | 按标准 API 价格计费，与订阅月费无关；需要你明确同意 |
| 重置额度（如有） | 如果账号里有可用的重置机会，可以用它恢复 5 小时或每周额度 | 以账号显示为准 |

## 选档自查

| 你的使用方式 | 更可能合适 |
| --- | --- |
| 偶尔聊天、试试功能 | Free |
| 每天问答、写作、研究，偶尔用 Claude Code | Pro |
| 每周多次撞上 Pro 的限额，经常用 Claude Code | Max 5x |
| 长时间连续的大型任务，多任务并行 | Max 20x |

判断要看**你最长的那类任务**是否经常撞上限，而不是用得最多的那类。官网文章有更多按用量画像的讨论：[Claude Pro 与 Max 按用量怎么选](https://muyugpt.com/blog/claude-pro-max-how-to-choose)、[Max 5X / 20X 额度怎么理解](https://muyugpt.com/blog/claude-max-quota-explained)。

## 常见问题

### Claude Pro 能用 Claude Code 吗？
可以。按定价页，Claude Code 包含在所有付费档，免费版不含。

### Max 20x 是 Pro 的 20 倍"所有额度"吗？
不是。倍数针对每个会话窗口的用量；每周还有统一上限，所以高档位也会触顶。

### 周上限什么时候重置？
固定在一个分配给你账号的时间，可在设置的用量页面查看，与你何时订阅无关。

### 我只用手机，价格和网页一样吗？
不一定。手机应用内订阅的价格可能与网页不同。

### 订阅包含 API 吗？
不包含。订阅和 API 是两个独立账户，见 [Claude Code 登录与计费](./claude-code-login-and-billing.md)。

## 相关阅读

- [Claude 计费、升级、取消与退款](./claude-billing-cancel-refund.md)
- [Claude Code 登录与计费：订阅还是 API key](./claude-code-login-and-billing.md)
- [返回仓库首页](../README.md)

## 资料来源

- [Claude 定价页](https://claude.com/pricing)
- [What is the Max plan?（Anthropic 帮助中心）](https://support.claude.com/en/articles/11049741-what-is-the-max-plan)

> 本仓库由 MuyuGPT 维护。MuyuGPT 是独立第三方项目，与 OpenAI、Anthropic、Google、xAI 不存在官方隶属、授权或合作关系。
