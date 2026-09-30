---
title: "Claude 订阅计费、升级、取消与退款：官方规则整理（2026-10）"
description: "Claude Pro / Max 怎么升级、升级如何计费、怎么取消、取消何时生效、为什么建议提前 24 小时、退款规则哪些确定哪些不确定，以及 Apple、Google Play 订阅的差别。"
permalink: /claude-billing-cancel-refund/
lang: zh-CN
---

# Claude 订阅计费、升级、取消与退款：官方规则整理

> **最后核验：2026-10-01** · 维护方：MuyuGPT（[muyugpt.com](https://muyugpt.com/)）
>
> **第三方身份说明：** MuyuGPT 是面向中文用户的独立第三方 AI 订阅指南与订阅协助平台，并非 Anthropic 官方渠道，与 Anthropic 不存在官方隶属、授权或合作关系。
>
> **读法：** 下面每条规则都标了来源。"官方说明"来自 Anthropic 帮助中心；"第三方整理"来自公开的二手文章，未能在官方页面逐字核实，请以 Anthropic 的消费者条款和当时页面为准。

## 30 秒结论

- 取消在**当前计费周期结束时**生效，周期内仍可用付费功能；想避免下一期扣款，官方建议至少提前 **24 小时**取消。
- 取消**不会**删除账号，也**不会**停止 Claude API 的计费。
- 升级按**剩余周期按比例**计费；Max 只按月。
- 退款不是默认权利：条款一般把付款视为不可退，除非条款承诺或法律要求。

## 升级

| 情形 | 规则 | 来源 |
| --- | --- | --- |
| 低档升高档（Pro → Max，或 Max 5x → 20x） | 按剩余计费周期按比例计费 | 官方说明 |
| 年付 Pro 升 Max | 剩余的 Pro 余额超过 Max 价格时，差额作为账户抵扣，用于未来费用；需要与之前订阅使用相同的账单地址。账单地址变了，要先取消 Pro，等其结束后再订 Max | 官方说明 |
| 通过 Google Play 订阅 | 付新档位的全价，旧档位未用完的价值折算成额外天数，续费日顺延几天 | 官方说明 |
| 降档 | 帮助中心的 Max 页面没有描述 | 未确认 |

## 取消

| 你是怎么订的 | 取消入口 |
| --- | --- |
| 网页或桌面 | Settings（设置）→ Billing（账单）→ Cancel |
| Android | 点击头像首字母 → Billing → Manage subscription，按提示操作 |
| iPhone / iPad | 订阅由 Apple 管理，在 Apple 的订阅管理里取消 |

**要点：**

- 必须在**订阅时所在的平台**取消；
- 生效时间是当前计费周期结束，周期内继续可用；
- 官方建议在下次扣款日前至少 24 小时操作；
- 年付订阅用到 12 个月期满。

**取消之后：**

- 账号不会被删除；据第三方整理，周期结束后回落到免费版，对话和项目保留在账号里；
- API 是独立账户，取消订阅不会自动停止 API 的计费，想停要到控制台单独处理。

## 退款

| 项目 | 内容 | 来源 |
| --- | --- | --- |
| 默认规则 | Anthropic 的消费者条款一般把付款视为不可退，除非条款承诺退款或法律要求 | 第三方整理，请对照消费者条款 |
| 取消的效果 | 只停止下一期扣款，不返还已付周期 | 官方说明与第三方整理一致 |
| 申请入口 | 据第三方整理，可在应用里通过 Get help 提交"退款申请"，做资格检查，结果以 Anthropic 为准 | 第三方整理 |
| 银行拒付 | 据第三方整理，如果已发起拒付，官方可能无法再自行退款 | 第三方整理 |
| Apple 订阅 | 只有 Apple 能审核和发放退款 | 官方与第三方一致 |

## 其他计费细节

- **手机价格**：帮助中心列出的 Max 价格仅适用于网页订阅，手机应用内可能不同；
- **折扣**：Anthropic 不提供标准折扣，客服不能发一次性优惠券，偶尔有限时活动；
- **税费**：定价页标价不含税。

## 通过 MuyuGPT 下单的情况

MuyuGPT 的订单是一次性下单，不涉及自动扣款，到期不再下单即自然停止，没有"取消订阅"这一步。站内承诺的是**充值不成功全额退款**，成功开通之后的边界见 [muyugpt-service-docs](https://github.com/muyugpt-official/muyugpt-service-docs)。产品与价格以 [Claude 产品页](https://muyugpt.com/claude) 和下单页面为准。续费的具体做法见官网文章 [Claude 会员续费方法](https://muyugpt.com/blog/claude-renewal-guide)。

## 常见问题

### 取消后还能用多久？
用到当前计费周期的最后一天。

### 为什么建议提前 24 小时取消？
官方帮助中心的建议，目的是避免在边界时间点上仍被扣下一期。

### 取消会删除我的聊天记录吗？
不会删除账号；据第三方整理，对话和项目会保留。如果你要的是注销账号，那是另一套流程。

### 我在 iPhone 上订阅的，为什么找不到取消按钮？
iPhone 应用内订阅由 Apple 管理，要到 Apple 的订阅管理里取消。

### 取消了订阅，API 还会扣费吗？
会。订阅和 API 是两个独立账户。

## 相关阅读

- [Claude 套餐与用量限制手册](./claude-plans-and-limits-2026.md)
- [Claude Code 登录与计费：订阅还是 API key](./claude-code-login-and-billing.md)
- [返回仓库首页](../README.md)

## 资料来源

- [What is the Max plan?（Anthropic 帮助中心）](https://support.claude.com/en/articles/11049741-what-is-the-max-plan)
- [Cancel your Pro or Max subscription（Anthropic 帮助中心）](https://support.claude.com/en/articles/8325617-cancel-your-pro-or-max-subscription)
- [Claude 定价页](https://claude.com/pricing)

> 本仓库由 MuyuGPT 维护。MuyuGPT 是独立第三方项目，与 OpenAI、Anthropic、Google、xAI 不存在官方隶属、授权或合作关系。
