---
title: "Claude Code 登录与计费：用订阅还是 API key，为什么会多出 API 账单"
description: "Claude Code 用 Claude 订阅（Pro / Max）登录和用 Console API key 登录的计费差异；ANTHROPIC_API_KEY 环境变量为什么会让你被扣 API 费用；usage credits 选项、/status 与 /login 怎么用。"
permalink: /claude-code-login-and-billing/
lang: zh-CN
---

# Claude Code 登录与计费：用订阅还是 API key

> **最后核验：2026-10-01** · 维护方：MuyuGPT（[muyugpt.com](https://muyugpt.com/)）
>
> **第三方身份说明：** MuyuGPT 是面向中文用户的独立第三方 AI 订阅指南与订阅协助平台，并非 Anthropic 官方渠道，与 Anthropic 不存在官方隶属、授权或合作关系。
>
> **来源：** Anthropic 帮助中心《Use Claude Code with your Pro or Max plan》与 [Claude 定价页](https://claude.com/pricing)。

## 30 秒结论

- Claude Code 有**两种登录方式，计费完全不同**：用 claude.ai 账号（订阅）登录，花的是订阅里的用量；用控制台（Console）凭据登录，按 token 计费。
- 两个账户是**两个独立的组织**，余额不互通：买了 Max 不会给控制台账户充值，给控制台充值也不会增加订阅用量。
- 最常见的"莫名其妙的 API 账单"来源：环境变量 **`ANTHROPIC_API_KEY`**。只要它被设置了，Claude Code 会优先使用 API 密钥，而不是你的订阅。
- 用 `/status` 看当前生效的是哪一种；用 `/login` 切换。

## 两种登录方式对照

| 维度 | Claude 订阅登录（Pro / Max） | Console / API key 登录 |
| --- | --- | --- |
| 怎么登录 | 浏览器里用 claude.ai 账号登录，不需要 API 密钥 | 使用控制台凭据或 API 密钥 |
| 计费 | 固定月费，用量来自套餐额度 | 按 token 计费，使用预付额度 |
| 额度限制 | 滚动 5 小时窗口 + 每周上限，与网页端共用 | 由账户余额和组织设置决定 |
| 账户 | claude.ai 账户 | Claude Console 账户（另一个账户） |
| 适合 | 个人开发提效 | 自动化、脚本、集成 |

免费的 claude.ai 账号不在可用于登录 Claude Code 的账号之列。

## 最容易踩的三个坑

### 坑 1：环境变量 `ANTHROPIC_API_KEY` 优先于订阅

如果这个环境变量被设置了，Claude Code 会用 API 密钥而不是订阅，于是你拿到的是 API 账单，而不是套餐里含的用量。这个密钥**在进程环境里的任何位置被导出**，都会压过你登录的账号。

**怎么排查：**

1. 在终端里检查这个变量是否存在（例如项目的 `.env`、shell 配置文件、系统环境变量）；
2. 在 Claude Code 会话里输入 `/status` 看当前生效的登录方式；
3. 如果只想用订阅，移除或改名这个变量；已经用控制台凭据登录的，在会话里用 `/login` 切换到订阅账户。

### 坑 2：用量用完后被提示"改用 API 额度"

订阅用户触顶时，可能会看到"用 API 额度继续"的选项：

- 这部分按**标准 API 价格**计费，与 Pro / Max 月费无关；
- 切换需要你**明确同意**；
- 想留在订阅里：拒绝这个选项，等用量窗口重置，并用 `/status` 查看剩余额度；
- 想避免这个选项出现：用 `claude login` 只用 Pro 或 Max 凭据认证，不要添加控制台凭据。

### 坑 3：控制台账户开了自动充值

如果你的控制台账户开启了 auto-reload，余额不足时会自动充值，账单可能悄悄增加。不需要时关闭它，并设置预算提醒。

## 关于"usage credits"和"API credits"两个说法

Claude 定价页对付费档写的是可以开启 **usage credits**（按标准 API 价格计费），Claude Code 的帮助文章里则写的是用 **API credits** 继续使用。官方页面对这两者的账户归属写得并不完全清楚，本文不强行区分。能确定的只有这几点：

- 这类用量按**标准 API 价格**计费，与 Pro / Max 的月费无关；
- 切换到这类用量需要你**明确同意**；
- 如果控制台账户开了自动充值，余额不足时会自动加钱；
- 具体怎么开启、怎么关闭、余额在哪里查看，请以你账号里的 **Usage credits** 管理页面为准。

## 选哪个：三个问题

1. **你是在提升自己的效率，还是在给程序用？** 前者用订阅，后者用 API。
2. **你更怕额度不够，还是更怕账单浮动？** 订阅的风险是撞到上限，API 的风险是费用随用量增长。
3. **你需要网页、项目、Artifacts 这类应用功能吗？** 这些属于订阅。

## 常见问题

### Claude Code 要单独付费吗？
不需要另买。它包含在 Pro 和 Max 里，与网页端共用订阅用量；选择用 API 密钥登录才按 token 计费。

### 我买了 Max，为什么还有 API 账单？
最常见的原因是 `ANTHROPIC_API_KEY` 被设置了，或者你同意了用量用完后改用 API 额度。用 `/status` 确认。

### Max 包含 API 访问吗？
不包含。需要把 Claude 放进自己的产品时，要单独开通并预付 API 账户。

### 怎么确认我现在用的是订阅还是 API？
在会话里输入 `/status`；如果需要切换，用 `/login`。

### 取消订阅，API 账单会停吗？
不会，两者独立，要到控制台单独处理。

## 相关阅读

- [Claude 套餐与用量限制手册](./claude-plans-and-limits-2026.md)
- [Claude 计费、升级、取消与退款](./claude-billing-cancel-refund.md)
- 官网文章：[Claude Code 对会员档位的要求](https://muyugpt.com/blog/claude-code-vs-web)
- [返回仓库首页](../README.md)

## 资料来源

- [Use Claude Code with your Pro or Max plan（Anthropic 帮助中心）](https://support.claude.com/en/articles/11145838-use-claude-code-with-your-pro-or-max-plan)
- [What is the Max plan?（Anthropic 帮助中心）](https://support.claude.com/en/articles/11049741-what-is-the-max-plan)
- [Claude 定价页](https://claude.com/pricing)

> 本仓库由 MuyuGPT 维护。MuyuGPT 是独立第三方项目，与 OpenAI、Anthropic、Google、xAI 不存在官方隶属、授权或合作关系。
