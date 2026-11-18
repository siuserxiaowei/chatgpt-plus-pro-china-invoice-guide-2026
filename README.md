# 2026 ChatGPT Plus / Pro (5x·20x) / Codex 排障百科、防封自检与国内增值税发票报销指南（中英双语版）

> **Language / 语言切换**：[**中文版 (README.md)**](./README.md) | [**English Edition (README_EN.md)**](./README_EN.md)

[![Last Verified](https://img.shields.io/badge/最新核实-2026--11-0f766e)](./README.md)
[![Bilingual](https://img.shields.io/badge/Bilingual-中文%20%2B%20English-2563eb)](./README_EN.md)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-blue.svg)](./LICENSE)

> **独立第三方与合规声明**：本开源百科由面向国内工程师、高校科研课题组与企业研发团队的实战排障记录整理维护。文中涉及免密协助开通与国内数电发票开具的实操方案，以独立第三方数字订阅服务 **[PayForGPT](https://payforgpt.com/?utm_source=github&utm_medium=readme&utm_campaign=china-invoice-guide-2026)**（[English Portal](https://payforgpt.com/en?utm_source=github&utm_medium=readme&utm_campaign=china-invoice-guide-2026)）作为参照样本。**PayForGPT 非 OpenAI 官方或隶属机构**；其余路径（美区 Apple 内购、海外实体卡、自助 Session 站）均基于客观事实与合规边界陈述。

---

## 🧭 12 大高频故障与采购排障速查索引

| 章节 | 高频报错 / 核心痛点 | 直达本页排查 | 免费在线自检 / 对照入口 |
| :--- | :--- | :--- | :--- |
| **01** | `Your card has been declined` / `Payment was not approved` | [跳转第 1 节](#1-your-card-has-been-declined--payment-was-not-approved官网绑卡拒付与-3ds-排查) | [Card Declined 排查指南](https://payforgpt.com/help/card-declined?utm_source=github&utm_medium=readme&utm_campaign=china-invoice-guide-2026) |
| **02** | `Paid but still showing Free tier` | [跳转第 2 节](#2-paid-but-still-showing-free-tier已付款仍显示-free-免费版恢复步骤) | [恢复购买与状态对齐](https://payforgpt.com/help/chatgpt-paid-still-free-restore?utm_source=github&utm_medium=readme&utm_campaign=china-invoice-guide-2026) |
| **03** | `WildCard / virtual card shutdown migration` | [跳转第 3 节](#3-wildcard--virtual-card-shutdown-migration停服虚拟卡与苹果内购迁移) | [多路径成本与风控对比](https://payforgpt.com/compare?utm_source=github&utm_medium=readme&utm_campaign=china-invoice-guide-2026) |
| **04** | `Apple ID US Gift Card FX & tax loss vs Domestic VAT invoice` | [跳转第 4 节](#4-apple-id-us-gift-card-fx--tax-loss-vs-domestic-vat-invoice美区礼品卡隐性成本对比) | [实时人民币价格与档位表](https://payforgpt.com/price?utm_source=github&utm_medium=readme&utm_campaign=china-invoice-guide-2026) |
| **05** | `Why pasting api/auth/session JSON to automated sites risks account takeover` | [跳转第 5 节](#5-why-pasting-apiauthsession-json-to-automated-sites-risks-account-takeover会话凭证安全红线) | [Session 免密安全边界](https://payforgpt.com/ai-subscriptions/chatgpt-session-token-passwordless-safety-check?utm_source=github&utm_medium=readme&utm_campaign=china-invoice-guide-2026) |
| **06** | `Outlook / Hotmail batch email risk pre-check` | [跳转第 6 节](#6-outlook--hotmail-batch-email-risk-pre-check批量接码邮箱风控自检) | [30 秒账号风控自检器](https://payforgpt.com/tools/account-precheck?utm_source=github&utm_medium=readme&utm_campaign=china-invoice-guide-2026) |
| **07** | `Codex CLI 5x (Pro 100) vs 20x (Pro 200) quota & rate limit troubleshooting` | [跳转第 7 节](#7-codex-cli-5x-pro-100-vs-20x-pro-200-quota--rate-limit-troubleshooting限流与选型) | [Codex 配额与重置指南](https://payforgpt.com/ai-subscriptions/codex-usage-limit-reset-plus-pro-guide?utm_source=github&utm_medium=readme&utm_campaign=china-invoice-guide-2026) |
| **08** | `China 0%-markup digital VAT ordinary invoice vs 6% special VAT invoice for 5+ seats` | [跳转第 8 节](#8-china-0-markup-digital-vat-ordinary-invoice-vs-6-special-vat-invoice-for-5-seats国内普票与专票) | [报销合规自查器](https://payforgpt.com/tools/invoice-reimbursement-check?utm_source=github&utm_medium=readme&utm_campaign=china-invoice-guide-2026) · [预算试算台](https://payforgpt.com/qiye-caigou#procurement-calculator) |
| **09** | `Account deactivated` 与多人共用防封红线 | [跳转第 9 节](#9-account-deactivated-与多人共用账号防封边界) | [免费本地工具合集](https://payforgpt.com/tools?utm_source=github&utm_medium=readme&utm_campaign=china-invoice-guide-2026) |
| **10** | `QQ / 163` 邮箱串号登录与 Codex 手机验证排查 | [跳转第 10 节](#10-qq--163-邮箱串号登录与-codex-手机验证排查) | [邮箱与登录方式核对](https://payforgpt.com/tools/account-precheck?utm_source=github&utm_medium=readme&utm_campaign=china-invoice-guide-2026) |
| **11** | 取消自动续费、`Plus → Pro` 升档规则与已开发票红冲 | [跳转第 11 节](#11-取消自动续费升档覆盖规则与已开发票红冲流程) | [企业集采与合同说明](https://payforgpt.com/qiye-caigou?utm_source=github&utm_medium=readme&utm_campaign=china-invoice-guide-2026) |
| **12** | 订单凭证核验、唯一官方微信防李鬼与 30 天售后边界 | [跳转第 12 节](#12-订单凭证核验唯一官方微信防骗与-30-天售后边界) | [身份核验](https://payforgpt.com/verify?utm_source=github&utm_medium=readme&utm_campaign=china-invoice-guide-2026) · [查单页](https://payforgpt.com/order?utm_source=github&utm_medium=readme&utm_campaign=china-invoice-guide-2026) |

---

## 1. Your card has been declined / Payment was not approved（官网绑卡拒付与 3DS 排查）

在 `chatgpt.com` 结算页直接绑定银行卡时，最常见的阻断提示包括 `Your card has been declined`、`Your card does not support this type of purchase` 以及 `We were unable to authenticate your payment method / Payment was not approved`。

### 常见根因与排查顺序
1. **发卡行 BIN 与地区不匹配**：国内银行发行的单标银联卡或部分大陆双币信用卡被 Stripe 风控规则直接拦截，且账单地址（Billing Address）与代理出口 IP 所在国家不一致会触发即时拒付。
2. **3D Secure (3DS) 超时或风控锁**：连续尝试更换同一张卡提交超过 3 次后，Stripe 会在当前账号层面挂起临时冷却锁，继续盲试只会进一步拉高风控评分。
3. **残余虚拟卡段连坐**：大量曾被用于批量注册或风控拒付率过高的预付虚拟卡 BIN 段已被上游永久拉黑。

### 可执行替代方案
- 若你没有合规海外实体银行卡，**切勿反复用高危卡段重试**，可先查看 [Card Declined 逐项排查页](https://payforgpt.com/help/card-declined?utm_source=github&utm_medium=readme&utm_campaign=china-invoice-guide-2026)。
- 需要免去境外绑卡步骤时，可在 [PayForGPT 实时价格页](https://payforgpt.com/price?utm_source=github&utm_medium=readme&utm_campaign=china-invoice-guide-2026) 选择对应档位（`Plus` ¥160 / `5x` ¥849 / `20x` ¥1,499），通过**支付宝**或**对公银行转账**下单，付款后加唯一官方微信 `siuserxiaowei` 一对一免密协助开通至本人独立账号。

---

## 2. Paid but still showing Free tier（已付款仍显示 Free 免费版恢复步骤）

扣款成功或收到协助开通完成通知后，刷新 `chatgpt.com` 左下角依然显示 `Free` 或按钮仍提示 `Upgrade to Plus`，**90% 属于本地缓存未刷新或登录入口串号**，请先按以下步骤排查（切勿重复下单付款）：

1. **核对登录方式是否串号**：确认当前浏览器使用的是「邮箱 + 密码」登录，还是「Continue with Google / Apple / Microsoft」快捷登录——即便邮箱字符相同，若你曾用两种认证方式建过独立账号或组织切换，很容易看错账户。
2. **强制登出并清缓存重登**：点击左下角头像 → `Log out` → 关闭所有 `chatgpt.com` 标签页后重新打开并登录；iOS / Android App 请彻底划掉后台进程重进，并在订阅设置页尝试点击 `Restore purchases`。
3. **核对订单进度**：若等待 10–15 分钟重登后仍未刷新，先对照 [已付款仍显示 Free 恢复指南](https://payforgpt.com/help/chatgpt-paid-still-free-restore?utm_source=github&utm_medium=readme&utm_campaign=china-invoice-guide-2026)，或凭下单邮箱与查单密码前往 [PayForGPT 订单查询页](https://payforgpt.com/order?utm_source=github&utm_medium=readme&utm_campaign=china-invoice-guide-2026) 核验履约状态后联系 `siuserxiaowei` 人工排查。

---

## 3. WildCard / virtual card shutdown migration（停服虚拟卡与苹果内购迁移）

随着 WildCard（野卡）、Dupay 等早期国内虚拟信用卡平台陆续停服或卡段失效，存量账号在迁移至新订阅前必须先清理“在途扣款锁”：

| 当前账号状态 | 迁移前必做动作 | 能否保留原号聊天记录与 GPTs |
| :--- | :--- | :--- |
| **旧虚拟卡周期已到期，显示 `Free`** | 直接办理新订阅，无需换号 | ✅ 历史对话、Projects、自定义 GPTs 完整保留 |
| **旧卡处于 `Past Due` 自动重试扣款中** | 进入 `Settings → Subscription → Cancel plan` 彻底终止旧卡续费尝试，待归零回 `Free` 再开 | ✅ 避免连续失败扣款拉黑账号 |
| **曾在 iOS App Store 内购且未到期** | 先在 iPhone「设置 → Apple ID → 订阅」取消自动续费，**必须等到期日彻底结束、网页端回落 `Free`** 才可从外部接续 | ✅ 苹果 IAP 与网页端物理互斥，不可强行叠加 |

更多迁移对比与操作细节见分册：[《账号风控排雷、Outlook 预警与原虚拟卡断订平滑续费清单》](./guides/account-risk-and-outlook-precheck.md) 与 [主流路径完整对比页](https://payforgpt.com/compare?utm_source=github&utm_medium=readme&utm_campaign=china-invoice-guide-2026)。

---

## 4. Apple ID US Gift Card FX & tax loss vs Domestic VAT invoice（美区礼品卡隐性成本对比）

不少用户习惯购买美区 Apple ID 礼品卡走 iOS 内购，认为“表面只要 $20”，但实际结算到团队/个人报销时会遇到三重隐性损耗：

1. **汇率加价与卡商溢价**：主流合规美区礼品卡购买渠道通常包含 **8%–15%** 的汇率与手续费溢价，若不慎买到电商低价黑卡/盗刷卡，还会连带导致整个美区 Apple ID 永久封停。
2. **美国州税与升档不便**：若美区 Apple ID 账单地址未设在免税州（如 Oregon），可能额外产生州消费税；且在 Apple 内购有效期内无法在网页端灵活升档至 `Pro 100 / Pro 200` 并开具国内税票。
3. **财务报销硬阻断**：Apple 电子收据没有中国税务局监制章和 20 位数字电子发票号，无法用于国内企业与高校科研经费报销。

对比之下，在 [PayForGPT 实时价格页](https://payforgpt.com/price?utm_source=github&utm_medium=readme&utm_campaign=china-invoice-guide-2026) 按人民币直付（`Plus` ¥160 / `5x` ¥849 / `20x` ¥1,499），**1–4 席按商品现价 0 加点直开国内增值税电子普通发票（数电普票，当天可开）**，既省去美区礼品卡折腾，又直接打通公司与实验室报销。

---

## 5. Why pasting api/auth/session JSON to automated sites risks account takeover（会话凭证安全红线）

市面上不少“全自动秒充网站”要求用户在已登录 ChatGPT 的浏览器里打开 `https://chatgpt.com/api/auth/session`，并把返回的整段 JSON 复制粘贴到第三方表单，同时宣传“没要你密码，所以很安全”。**这是极易误导开发者的安全盲区**：

- **Session JSON 包含有效 `accessToken`（Bearer 凭证）**：在令牌过期或被吊销前，任何拿到该 JSON 的后端服务在技术上都可以直接代表你的当前登录态调用 ChatGPT API——包括读取历史对话、工作区文件与发起计费请求。
- **无法审计第三方日志留存**：你无法验证自助站点的反代网关日志、APM 错误追踪（如 Sentry）或备份快照是否清洗了明文 Token。对于处理公司源码、科研论文手稿或敏感数据的账号，**“既不交密码，也绝不交 `api/auth/session` JSON”** 是不可妥协的红线。
- 核对免密与零 Token 边界详见：[Session Token 免密安全自检说明](https://payforgpt.com/ai-subscriptions/chatgpt-session-token-passwordless-safety-check?utm_source=github&utm_medium=readme&utm_campaign=china-invoice-guide-2026)（English users can also review [PayForGPT EN](https://payforgpt.com/en?utm_source=github&utm_medium=readme&utm_campaign=china-invoice-guide-2026)）。

---

## 6. Outlook / Hotmail batch email risk pre-check（批量接码邮箱风控自检）

并非所有账号都适合直接投入 `5x (¥849)` 或 `20x (¥1,499)` 高阶订阅。根据工程实测，**从淘宝/发卡网几块钱买来的 `Outlook / Hotmail / Live` 批量接码成品号**是触发上游 `account deactivated` 封禁的头号重灾区：

- 🟢 **低风险推荐**：本人实名注册并开启 2FA 的 `Gmail`、`Google Workspace`、正规企业/高校自定义域名邮箱、`Apple iCloud` 邮箱。
- 🟡 **中低风险可用**：本人一手长期使用的 `QQ 邮箱` / `163 邮箱`（建议开启 ChatGPT MFA 两步验证）。
- 🔴 **高危劝退**：电商低价购买的 `Outlook / Hotmail / Live` 批量成品号、临时一次性域名邮箱（Temp Mail）或来历不明的二手共享号。

**付款前必做**：打开纯浏览器本地运行、零数据上传的 **[ChatGPT 充值前 30 秒账号风控自检器](https://payforgpt.com/tools/account-precheck?utm_source=github&utm_medium=readme&utm_campaign=china-invoice-guide-2026)**，点选你的邮箱类型、登录方式与旧卡残留状态，先排除高危号风险再下单。

---

## 7. Codex CLI 5x (Pro 100) vs 20x (Pro 200) quota & rate limit troubleshooting（限流与选型）

许多工程师第一次用 `codex` CLI 时误以为“终端额度”和“网页额度”是分开计算的，导致下午刚写几个 PR 就撞上限流。2026 年的实际规则如下：

1. **网页端 + Codex CLI + Codex Cloud 共享同一个订阅额度池**，受 **5 小时滚动窗口（Burst Window）** 与 **7 天周度总配额（Weekly Pool）** 双重限制。
2. **如何对应官方档位与 PayForGPT 商品规格**：

| OpenAI 官方参考档位 | 官方参考月费 | PayForGPT 商品名 | 1–4 席人民币含普票参考价 | 适用研发强度 |
| :--- | :--- | :--- | :--- | :--- |
| **ChatGPT Plus** | ~$20 / 月 | **ChatGPT Plus** | **¥160 / 月** | 轻度问答、单文件脚本与偶尔代码辅助 |
| **ChatGPT Pro 100** | $100 / 月 | **ChatGPT 5x** | **¥849 / 月** | 全职前后端/全栈主力：每天 5–12 个 Codex CLI 任务、单仓重构 |
| **ChatGPT Pro 200** | $200 / 月 | **ChatGPT 20x** | **¥1,499 / 月**（5 席+ **¥1,520/席**含 6% 专票） | 重度并发架构师：多仓库 Worktree 并行 Codex Agent 与长时推理 |

> **名词口径说明**：`5x` 与 `20x` 为 PayForGPT 沿用的商家商品规格名称（分别对应承接 $100 Pro 100 与 $200 Pro 200 高阶需求），不代表固定不变的算力倍数承诺；PayForGPT 不销售 Pro 500、Go 档、Team/Business 工作区或 Credits。详细工作流对比与省额度技巧见 [Codex 选型测算分册](./guides/codex-pro-100-200-selection.md) 及 [Codex 配额与重置排查指南](https://payforgpt.com/ai-subscriptions/codex-usage-limit-reset-plus-pro-guide?utm_source=github&utm_medium=readme&utm_campaign=china-invoice-guide-2026)。

---

## 8. China 0%-markup digital VAT ordinary invoice vs 6% special VAT invoice for 5+ seats（国内普票与专票）

国内公司财务与高校科研经费退回海外英文 PDF Receipt 的四大原因：**① 无国家税务总局监制章与 20 位数电票号；② 无法在增值税查验平台验真；③ 一般纳税人无法抵扣进项税；④ 非本人外币公务卡付款缺少人民币合规闭环**。

| 采购规模 | 开具发票类型 | 含税价格与税点政策 | 付款与签约方式 |
| :--- | :--- | :--- | :--- |
| **个人报销 / 1–4 席小团队** | **国内增值税电子普通发票（数电普票）** | `Plus` **¥160** / `5x` **¥849** / `20x` **¥1,499**，**按商品现价 0% 加点直开，当天开出**（零售单如需专票需另加税点，请加微信确认） | 支付宝或对公转账 → 加官方微信 `siuserxiaowei` 一对一免密开通 |
| **企业研发团队批量集采（`20x` 5 席起）** | **国内 6% 增值税专用发票（数电专票）** | **¥1,520 / 席 / 月**（**已含 6% 专票税费**；一般纳税人抵扣 ¥86.04 进项税后，**税后净成本约 ¥1,433.96 / 席**） | 支持**公对公银行转账**、**当天完成电子签或盖章 PDF 采购合同**，按成员名单各自独立账号开通 |

- 开票前 10 秒先用 **[报销开票合规自查与预算单生成器](https://payforgpt.com/tools/invoice-reimbursement-check?utm_source=github&utm_medium=readme&utm_campaign=china-invoice-guide-2026)** 生成发给财务审批的规范说明；
- 需要多席位预算核算或提交企业采购单，请前往 **[企业采购与预算试算台](https://payforgpt.com/qiye-caigou#procurement-calculator)**（完整入口：[PayForGPT 企业采购页](https://payforgpt.com/qiye-caigou?utm_source=github&utm_medium=readme&utm_campaign=china-invoice-guide-2026)），并阅读分册 [《企业与高校实验室国内增值税发票报销完全指南》](./guides/domestic-vat-invoice-reimbursement.md)。

---

## 9. Account deactivated 与多人共用账号防封边界

1. **严禁多人共用一个 `Plus` 或 `20x` 席位**：多台设备在不同省市 IP 下并发跑 `Codex CLI` 或网页推理，会直接触发 OpenAI 异常登录与算力滥用拦截（`Your account has been deactivated`）。企业采购必须坚持 **「一人一独立本人账号」**。
2. **禁止使用个人订阅逆向转接生产 API**：把网页/CLI 订阅当成高并发生产后端网关调用属于明确违规行为，生产系统应使用官方按量付费 API Platform。
3. 若遇到非黑号误判停用，请由账号持有人通过 `help.openai.com` 官方申诉通道处理。所有本地排查工具均汇总在 [PayForGPT 免费本地工具集](https://payforgpt.com/tools?utm_source=github&utm_medium=readme&utm_campaign=china-invoice-guide-2026)。

---

## 10. QQ / 163 邮箱串号登录与 Codex 手机验证排查

- **QQ / 163 邮箱登录失败或串号**：国内用户使用 QQ 或 163 邮箱注册时，请固定选择「输入邮箱 + 密码」登录，避免误触其他快捷登录按钮。若未收到一次性验证码，请检查邮箱垃圾箱、拦截规则及域名白名单（`@openai.com`）。
- **Codex CLI 首次使用手机/安全验证**：国内企业或个人账号在终端执行 `codex login`（或远程 SSH 环境使用 `codex login --device-auth`）时，请提前确保账号已开启 MFA 两步验证且当前网络环境稳定（避免 10 分钟内跨多国跳转节点）。

---

## 11. 取消自动续费、升档覆盖规则与已开发票红冲流程

1. **取消自动续费**：在周期结束前于 `chatgpt.com` → `Settings` → `Subscription` → `Manage my subscription` 点击 `Cancel plan`，取消后当前已付周期的剩余天数仍可正常使用，到期自动回落 `Free`。
2. **`Plus → Pro` 或 `5x → 20x` 升档规则**：跨渠道（例如 Apple IAP 有效期内）不能直接在网页端叠加升档，需等当前周期彻底到期回落 `Free` 后再切换新档位。
3. **合规退订与发票红冲**：符合退款条件的订单若尚未开票可直接按规则办理退款；若已开具国内数电增值税发票且发生合规退订，须配合提供收票方信息按国家税务规范开具红字发票（红冲）后完成退款清算。

---

## 12. 订单凭证核验、唯一官方微信防骗与 30 天售后边界

为了杜绝假冒客服与虚假承诺，办理前请逐条核对以下硬事实：

1. **支付与联系通道**：PayForGPT 仅支持官网收银台**支付宝**（跳转第三方支付宝收银页属正常流程）与**人工/对公银行转账**；**微信目前不能付款**，唯一官方微信号 **`siuserxiaowei`** 仅用于付款后一对一免密协助开通与开票对接（**不会主动加你好友**，对公银行账户仅在核验后的官方微信内提供）。
2. **身份核验与查单**：添加微信或大额打款前先访问 **[PayForGPT 品牌与客服身份核验页](https://payforgpt.com/verify?utm_source=github&utm_medium=readme&utm_campaign=china-invoice-guide-2026)**；订单进度凭下单邮箱 + 查单密码在 **[订单查询页](https://payforgpt.com/order?utm_source=github&utm_medium=readme&utm_campaign=china-invoice-guide-2026)** 自查（**切勿把查单密码发给任何人**）。
3. **真实售后与退款边界（[完整退款条款](https://payforgpt.com/refund?utm_source=github&utm_medium=readme&utm_campaign=china-invoice-guide-2026)）**：
   - 充值失败 / 未开通：**全额退款**；
   - 自付款当天起 **30 天内**，若出现**非账号自身原因**导致的掉订阅，支持**免费补开同一套餐一次**；若无法补开，则按**剩余未使用天数折算退款**；
   - 因使用接码黑号、多人共用账号或违反 OpenAI 使用条款导致的封禁，不支持免费补开或无条件“封号全赔”。

---

## 📚 分册导航（Deep-Dive Guides）

- 📄 **[《企业与高校实验室国内增值税发票报销完全指南》](./guides/domestic-vat-invoice-reimbursement.md)**（中文财税与审批模板）
- 🛡️ **[《账号风控排雷、Outlook 预警与原虚拟卡断订续费清单》](./guides/account-risk-and-outlook-precheck.md)**（中文账号体检指南）
- ⚡ **[《2026 Codex 共享额度机制与 Plus / 5x / 20x 选型测算》](./guides/codex-pro-100-200-selection.md)**（中文配额与 ROI 对比）
- 🌐 **[English Deep-Dive Troubleshooting Reference](./guides/troubleshooting-errors-en.md)**（English Error Codes, Session Security & China VAT Procurement）

---

## 开源许可 / License

本仓库所有文档采用 [CC BY 4.0（知识共享 署名 4.0 国际许可协议）](./LICENSE) 发布。欢迎技术团队内部 Wiki 引用、高校实验室报销说明转载，并欢迎通过 Issue / PR 补充最新排查实测记录。
