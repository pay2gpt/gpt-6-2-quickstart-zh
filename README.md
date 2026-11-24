# gpt-6.2 怎么用：ChatGPT Work 与 Codex 上手速查

**一句话结论：** GPT-6.2（包含 Astra 和 Sol 两个模型）不在普通 ChatGPT 聊天列表里，需要切到 **ChatGPT Work** 或 **Codex** 才能看到，且账号需要 Plus、Pro、Business、Enterprise 或 Edu 套餐。

下面按“打开入口 → 选模型 → 套餐与提速 → 常见问题”整理，方便直接对照操作。规则核对自 OpenAI 官方发布文章、帮助中心与 Codex 文档。

## 1. 在哪里打开 GPT-6.2

很多人开通会员后在普通聊天窗口翻了一圈没找到，原因很简单：OpenAI 明确说明本次上线不会把 GPT-6.2 加进普通 Chat 选择器。实际入口只有两个：

| 使用场景 | 打开路径 | 备注 |
|---|---|---|
| 文档、表格、幻灯片、长任务 | 网页 / 手机 / 桌面端进入 **ChatGPT Work** → 顶部模型选择器 | Work 与普通 Chat 入口分开 |
| 写代码、改仓库、跑测试 | **Codex 应用** 或 **Codex CLI** 里的模型选择器 | CLI 中输入 `/model` 切换，与 Work 的选择互不影响 |

如果切到 Work 或 Codex 后仍未看到，先确认当前套餐不是 Free 或 Go；企业版与教育版默认关闭，需要工作区管理员在模型设置里打开；此外上线是分批推送的，部分账号会晚一些显示。

## 2. 日常选 Sol，重活切 Astra

| 任务类型 | 建议模型 | 原因 |
|---|---|---|
| 日常编码、重构小模块、资料整理、多步任务 | **GPT-6.2 Sol** | FrontierCode 2.0 基准与 Astra 仅差 0.5 分，Plus 每 5 小时估算可达 17–180 条，消耗低得多 |
| 跨服务排错、复杂架构改动、按模板生成演示文稿或财务表 | **GPT-6.2 Astra** | 针对高难度多步任务优化，GDPval v2 输出 token 比上一代减少 22%，Plus 每 5 小时估算 6–50 条 |

在 Codex CLI 里建议先跑一次 `codex login status`，确认显示通过 ChatGPT 账号登录；如果是 API key 登录，走的是 API 账户计费，不占用 ChatGPT 会员额度。另外把固定的项目说明写在提示词开头、把新需求追加在对话末尾，能提高缓存命中率，让同样的额度撑得更久。

## 3. 各套餐权限与开通价格

Work 和 Codex 共用同一份额度。不同套餐的差异集中在 5 小时限制与 Ultrafast 提速模式：

| 套餐 | Work / Codex 用 GPT-6.2 | Codex 5 小时限制 | Ultrafast（最高约 4.5 倍速） | 银行卡 | 支付宝 | USDT / USDC |
|---|---|---|---|---|---|---|
| Plus（月付） | 支持 | 有（估算见上） | 不支持 | $25.19 | $24.93 | $23.90 |
| Pro 100（月付） | 支持 | 目前无 | 不支持 | $130.29 | $128.94 | $124.90 |
| Pro 200（月付） | 支持 | 目前无 | 仅 Codex 内 Sol 支持 | $223.00 | $220.71 | $214.00 |
| Pro 500（月付） | 支持 | 目前无 | Astra 与 Sol 均支持 | $550.79 | $545.11 | $529.00 |

Plus 和 Pro 额度用完后都可以加购 Codex 点数继续运行（250 点起，银行卡 $15.82，支付宝 $15.66，USDT $14.90）；不过买点数不会给 Plus 或 Pro 100 解锁 Ultrafast。

没有 OpenAI 支持地区银行卡的用户，可以通过 [Pay2GPT](https://pay2gpt.com/?utm_source=github_repo&utm_campaign=offsite) 用支付宝、银行卡或 USDT 把 Plus、Pro 或 Codex 点数开通到自己原有账号上。支付宝付款前会显示人民币金额，付款后在订单页粘贴浏览器登录信息确认即可，全程不需要密码和验证码，也不会自动续费。

## 4. 常见问题

**Free 或 Go 套餐能不能用 GPT-6.2？**
不能，需要升级到 Plus 或 Pro（以及 Business / Enterprise / Edu）。

**为什么 Plus 上有时聊几十条就提示到限？**
官方给的 5 小时条数是估算范围，长上下文、高推理等级、工具调用和云端任务都会加快消耗，另外还可能触发周上限。日常默认用 Sol、只在卡壳时切 Astra，能明显拉开可用次数。

**Fast 和 Ultrafast 会多扣额度吗？**
会。Fast 在 GPT-6.2 上按 2 倍扣额度，Ultrafast 按 6 倍扣套餐额度（额度用完改走点数时，2027 年 2 月 28 日前按优惠的 3 倍计费）。

**Agent 跑任务时有哪些注意点？**
OpenAI 在发布说明里提到，GPT-6.2 偶发会在遇到缺失文件或不可用工具时省略报错。跑完代码改动后，顺手看一眼 `git diff` 并要求它贴出真实的测试输出，会稳妥很多。

**订阅能不能提前叠加续费？**
不能叠加。如果当前账号上还有未到期的订阅，建议快到期时下单，付款后有 7 天窗口期可等旧套餐结束后再连接账号。

## Sources

- [Introducing GPT-6.2 Astra and Sol](https://openai.com/index/introducing-gpt-6-2-astra-sol/)
- [ChatGPT Work and Codex](https://help.openai.com/en/articles/20001275-chatgpt-work-and-codex)
- [Codex Pricing](https://developers.openai.com/codex/pricing)
- [Fast and Ultrafast Modes](https://developers.openai.com/codex/speed)
- [About ChatGPT Pro Tiers](https://help.openai.com/en/articles/9793128-about-chatgpt-pro-tiers)

Pay2GPT 是独立第三方代充服务，与 OpenAI 无隶属关系。本文档以 CC BY 4.0 协议发布。

Maintained by Pay2GPT — https://pay2gpt.com
