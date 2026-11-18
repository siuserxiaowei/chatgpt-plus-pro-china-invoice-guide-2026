# 2026 ChatGPT Plus / Pro (5x·20x) / Codex Troubleshooting Encyclopedia & China VAT Invoice Guide (Bilingual Edition)

> **Language / 语言切换**：[**中文版 (README.md)**](./README.md) | [**English Edition (README_EN.md)**](./README_EN.md)

[![Last Verified](https://img.shields.io/badge/Verified-2026--11-0f766e)](./README_EN.md)
[![Bilingual](https://img.shields.io/badge/Bilingual-English%20%2B%20%E4%B8%AD%E6%96%87-2563eb)](./README.md)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-blue.svg)](./LICENSE)

> **Disclosure & Independence Notice**: This open-source troubleshooting encyclopedia documents real-world billing errors, security risks, Codex rate limits, and mainland China corporate VAT reimbursement workflows for developers, university labs, and R&D teams. Where third-party passwordless activation and China VAT invoicing are referenced, we cite **[PayForGPT](https://payforgpt.com/en?utm_source=github&utm_medium=readme_en&utm_campaign=china-invoice-guide-2026)** ([Chinese Main Site](https://payforgpt.com/?utm_source=github&utm_medium=readme_en&utm_campaign=china-invoice-guide-2026)), an **independent third-party digital subscription service with no official affiliation or endorsement from OpenAI**. All alternative paths (US Apple IAP, overseas bank cards, automated token sites) are documented objectively.

---

## 🧭 Quick-Jump Index: 12 Troubleshooting Sections

| # | High-Frequency Error / Procurement Blocker | Jump to Section | Live Free Diagnostic / Reference |
| :--- | :--- | :--- | :--- |
| **01** | `Your card has been declined` / `Payment was not approved` | [Section 1](#1-your-card-has-been-declined--payment-was-not-approved) | [Card Declined Checklist](https://payforgpt.com/help/card-declined?utm_source=github&utm_medium=readme_en&utm_campaign=china-invoice-guide-2026) |
| **02** | `Paid but still showing Free tier` | [Section 2](#2-paid-but-still-showing-free-tier) | [Restore & Sync Guide](https://payforgpt.com/help/chatgpt-paid-still-free-restore?utm_source=github&utm_medium=readme_en&utm_campaign=china-invoice-guide-2026) |
| **03** | `WildCard / virtual card shutdown migration` | [Section 3](#3-wildcard--virtual-card-shutdown-migration) | [4-Path Comparison](https://payforgpt.com/compare?utm_source=github&utm_medium=readme_en&utm_campaign=china-invoice-guide-2026) |
| **04** | `Apple ID US Gift Card FX & tax loss vs Domestic VAT invoice` | [Section 4](#4-apple-id-us-gift-card-fx--tax-loss-vs-domestic-vat-invoice) | [Live RMB Pricing](https://payforgpt.com/price?utm_source=github&utm_medium=readme_en&utm_campaign=china-invoice-guide-2026) |
| **05** | `Why pasting api/auth/session JSON to automated sites risks account takeover` | [Section 5](#5-why-pasting-apiauthsession-json-to-automated-sites-risks-account-takeover) | [Zero-Token Safety Boundary](https://payforgpt.com/ai-subscriptions/chatgpt-session-token-passwordless-safety-check?utm_source=github&utm_medium=readme_en&utm_campaign=china-invoice-guide-2026) |
| **06** | `Outlook / Hotmail batch email risk pre-check` | [Section 6](#6-outlook--hotmail-batch-email-risk-pre-check) | [30s Account Precheck Tool](https://payforgpt.com/tools/account-precheck?utm_source=github&utm_medium=readme_en&utm_campaign=china-invoice-guide-2026) |
| **07** | `Codex CLI 5x (Pro 100) vs 20x (Pro 200) quota & rate limit troubleshooting` | [Section 7](#7-codex-cli-5x-pro-100-vs-20x-pro-200-quota--rate-limit-troubleshooting) | [Codex Quota & Reset Guide](https://payforgpt.com/ai-subscriptions/codex-usage-limit-reset-plus-pro-guide?utm_source=github&utm_medium=readme_en&utm_campaign=china-invoice-guide-2026) |
| **08** | `China 0%-markup digital VAT ordinary invoice vs 6% special VAT invoice for 5+ seats` | [Section 8](#8-china-0-markup-digital-vat-ordinary-invoice-vs-6-special-vat-invoice-for-5-seats) | [Reimbursement Spec Generator](https://payforgpt.com/tools/invoice-reimbursement-check?utm_source=github&utm_medium=readme_en&utm_campaign=china-invoice-guide-2026) · [Cost Calculator](https://payforgpt.com/qiye-caigou#procurement-calculator) |
| **09** | `Account deactivated` & Multi-Device / Shared Seat Abuse Prevention | [Section 9](#9-account-deactivated--multi-device-shared-seat-abuse-prevention) | [Free Client-Side Utilities](https://payforgpt.com/tools?utm_source=github&utm_medium=readme_en&utm_campaign=china-invoice-guide-2026) |
| **10** | `QQ / 163` Email Login Mismatch & Codex Phone Verification | [Section 10](#10-qq--163-email-login-mismatch--codex-phone-verification) | [Email & Auth Precheck](https://payforgpt.com/tools/account-precheck?utm_source=github&utm_medium=readme_en&utm_campaign=china-invoice-guide-2026) |
| **11** | Subscription Cancellation, Plan Upgrade Rules & VAT Invoice Red-Flush | [Section 11](#11-subscription-cancellation-plan-upgrade-rules--vat-invoice-red-flush) | [Enterprise Procurement](https://payforgpt.com/qiye-caigou?utm_source=github&utm_medium=readme_en&utm_campaign=china-invoice-guide-2026) |
| **12** | Order Verification, Support Anti-Impersonation & 30-Day SLA Boundaries | [Section 12](#12-order-verification-support-anti-impersonation--30-day-sla-boundaries) | [Verify Support](https://payforgpt.com/verify?utm_source=github&utm_medium=readme_en&utm_campaign=china-invoice-guide-2026) · [Order Lookup](https://payforgpt.com/order?utm_source=github&utm_medium=readme_en&utm_campaign=china-invoice-guide-2026) |

---

## 1. Your card has been declined / Payment was not approved

When checking out on `chatgpt.com`, Stripe frequently blocks mainland China cards and mismatched cross-border billing setups with `Your card has been declined`, `Your card does not support this type of purchase`, or `Payment was not approved`.

### Root Causes & Triage Steps
1. **Issuer BIN & Region Mismatch**: Mainland UnionPay-only cards and most domestic dual-currency credit cards fail Stripe's country/BIN checks. Having a billing ZIP/address in a different country from your exit IP triggers immediate rejection.
2. **3D Secure (3DS) & Retry Cooldown**: Submitting failed card attempts more than 3 times in a short window raises the account's Stripe fraud risk score and locks the checkout session.
3. **Blacklisted Virtual Card BINs**: Prepaid virtual card BIN ranges previously abused by bulk sign-up scripts are permanently rejected upstream.

### Practical Resolution
- Stop retrying flagged virtual BINs; review the step-by-step diagnostics on [Card Declined Help](https://payforgpt.com/help/card-declined?utm_source=github&utm_medium=readme_en&utm_campaign=china-invoice-guide-2026).
- If you do not hold a compliant overseas physical card, you can review plans on [PayForGPT Live Pricing](https://payforgpt.com/price?utm_source=github&utm_medium=readme_en&utm_campaign=china-invoice-guide-2026) or the [English Overview](https://payforgpt.com/en?utm_source=github&utm_medium=readme_en&utm_campaign=china-invoice-guide-2026) (`Plus` ¥160 / `5x` ¥849 / `20x` ¥1,499), pay via **Alipay** or **corporate bank transfer**, and complete 1-on-1 passwordless activation onto your own account via official WeChat `siuserxiaowei`.

---

## 2. Paid but still showing Free tier

If your payment succeeded or activation was marked complete, yet `chatgpt.com` still displays `Free` in the bottom-left corner, **do not place a duplicate order**. Nine out of ten cases are caused by auth-method mismatch or stale client cache:

1. **Check Auth Method Mismatch**: Confirm whether your subscription is attached to an **email + password** login or **Continue with Google / Apple / Microsoft** OAuth—using the same email address across two separate auth identities can log you into a separate empty workspace.
2. **Force Session Refresh**: Click your profile avatar → `Log out`, close all `chatgpt.com` tabs, reopen, and sign back in. On iOS/Android, force-quit the app and tap `Restore purchases` if subscribed via mobile.
3. **Verify Order Status**: Follow the full checklist in [Paid Still Free Restore Guide](https://payforgpt.com/help/chatgpt-paid-still-free-restore?utm_source=github&utm_medium=readme_en&utm_campaign=china-invoice-guide-2026) or check your fulfillment status using your order email and lookup password at [PayForGPT Order Lookup](https://payforgpt.com/order?utm_source=github&utm_medium=readme_en&utm_campaign=china-invoice-guide-2026).

---

## 3. WildCard / virtual card shutdown migration

Following the shutdown of legacy cross-border virtual card platforms (such as WildCard / `bewildcard.com`, Dupay, and discontinued prepaid BINs), returning users must clear pending billing locks before switching channels:

| Current Account Billing State | Required Cleanup Before Migrating | Chat History & Custom GPTs Preserved? |
| :--- | :--- | :--- |
| **Old virtual card expired; account shows `Free`** | Ready for immediate passwordless reactivation on the same email | ✅ Yes — chats, Projects, and GPTs stay intact |
| **Billing stuck in `Past Due` auto-retry loop** | Open `Settings → Subscription → Manage → Cancel plan` to halt repeated failed charges before switching | ✅ Yes — stops Stripe risk score escalation |
| **Active Apple App Store IAP not yet expired** | Cancel auto-renew in iOS `Settings → Apple ID → Subscriptions` and **wait until the billing cycle ends and reverts to `Free`** | ✅ Apple IAP and web billing cannot overlap |

For side-by-side migration details, see [Account Risk & Migration Checklist](./guides/account-risk-and-outlook-precheck.md) and [Channel Comparison](https://payforgpt.com/compare?utm_source=github&utm_medium=readme_en&utm_campaign=china-invoice-guide-2026).

---

## 4. Apple ID US Gift Card FX & tax loss vs Domestic VAT invoice

Paying via a US Apple ID + App Store gift cards is often assumed to cost a flat `$20`, but teams and individuals encounter three hidden costs:

1. **8%–15% Gift Card Markup & Fraud Risk**: Reseller FX spreads add 8%–15% overhead, and discounted grey-market gift cards risk permanent suspension of your entire Apple ID.
2. **US State Sales Tax & Upgrade Friction**: Non-tax-free US billing states add sales tax, and while an Apple IAP subscription is active, you cannot seamlessly switch to web-billed `Pro 100` / `Pro 200` seats.
3. **Zero China Tax-Reimbursement Validity**: Apple digital receipts lack a China Tax Bureau seal and 20-digit e-VAT number, causing corporate finance and university grant offices to reject expense claims.

By comparison, purchasing via [PayForGPT Pricing](https://payforgpt.com/price?utm_source=github&utm_medium=readme_en&utm_campaign=china-invoice-guide-2026) settles in RMB (`Plus` ¥160 / `5x` ¥849 / `20x` ¥1,499) with **0%-markup domestic digital VAT ordinary invoices for 1–4 seats (issued same day)**.

---

## 5. Why pasting api/auth/session JSON to automated sites risks account takeover

Many automated self-serve recharge websites instruct users to visit `https://chatgpt.com/api/auth/session` while logged in and paste the raw JSON output into a web form, claiming *"we don't ask for your password, so it's safe."* From a security engineering perspective, this is dangerously misleading:

- **The JSON Contains a Live Bearer `accessToken`**: Until it expires or is revoked, anyone holding that `accessToken` has full programmatic session equivalence—capable of reading conversation histories, workspace metadata, and initiating account actions.
- **Unverifiable Server Retention**: You cannot audit whether a third-party recharge site logs raw request bodies in reverse-proxy logs, error trackers (e.g., Sentry), or database backups.
- **Zero-Token Standard**: For developers handling proprietary code or confidential research, **never share passwords and never paste `api/auth/session` JSON**. PayForGPT operates strictly passwordless and tokenless; see [Session Safety Breakdown](https://payforgpt.com/ai-subscriptions/chatgpt-session-token-passwordless-safety-check?utm_source=github&utm_medium=readme_en&utm_campaign=china-invoice-guide-2026).

---

## 6. Outlook / Hotmail batch email risk pre-check

Before investing in higher-tier plans (`5x` at ¥849/mo or `20x` at ¥1,499/mo), verify your underlying account hygiene. **Cheap bulk-registered `Outlook / Hotmail / Live` accounts sold on e-commerce marketplaces** are the #1 trigger for upstream `Your account has been deactivated` bans:

- 🟢 **Low Risk (Recommended)**: Personal `Gmail` (with Google 2FA), `Google Workspace`, verified corporate/university domains, or `Apple iCloud`.
- 🟡 **Moderate-Low Risk**: Long-standing personal `QQ` or `163` email accounts (enable ChatGPT MFA).
- 🔴 **High Risk (Avoid Upgrading)**: Bulk-purchased `Outlook / Hotmail / Live` burner accounts, temporary disposable domains, or shared reseller accounts.

Run a zero-upload check in 30 seconds using the browser-only **[Account Risk Precheck Utility](https://payforgpt.com/tools/account-precheck?utm_source=github&utm_medium=readme_en&utm_campaign=china-invoice-guide-2026)** before placing an order.

---

## 7. Codex CLI 5x (Pro 100) vs 20x (Pro 200) quota & rate limit troubleshooting

Engineers using `codex` CLI often assume terminal tasks have a separate quota from the web UI. In 2026, OpenAI enforces a **unified shared pool**:

1. **Shared Pool Across Web + Codex CLI + Codex Cloud**: Multi-file repo scans, test retries, and Deep Research all draw from the same account pool under a **5-hour rolling burst window** and a **7-day weekly cap**.
2. **Tier Mapping & Official Alignment**:

| Official OpenAI Tier | Official Monthly Reference | PayForGPT SKU Name | 1–4 Seats RMB Price (Incl. 0%-Markup VAT Ordinary Invoice) | Recommended Engineering Workload |
| :--- | :--- | :--- | :--- | :--- |
| **ChatGPT Plus** | ~$20 / mo | **ChatGPT Plus** | **¥160 / mo** | Light Q&A, doc drafting, single-file script edits |
| **ChatGPT Pro 100** | $100 / mo | **ChatGPT 5x** | **¥849 / mo** | Full-time developers running 5–12 daily Codex CLI tasks & single-repo refactors |
| **ChatGPT Pro 200** | $200 / mo | **ChatGPT 20x** | **¥1,499 / mo** (`5+` seats: **¥1,520/seat** incl. 6% Special VAT) | Heavy parallel `git worktree` Codex agents & multi-repo architecture migrations |

> **SKU Naming Clarification**: `5x` and `20x` are PayForGPT's catalog product names aligned to the `$100` (`Pro 100`) and `$200` (`Pro 200`) subscription tiers; they do not represent a fixed compute-multiplier guarantee. PayForGPT does not sell `Pro 500`, `Go`, `Team/Business`, or `Credits`. See [Codex Quota & Reset Guide](https://payforgpt.com/ai-subscriptions/codex-usage-limit-reset-plus-pro-guide?utm_source=github&utm_medium=readme_en&utm_campaign=china-invoice-guide-2026) and [Codex Selection Deep-Dive](./guides/codex-pro-100-200-selection.md).

---

## 8. China 0%-markup digital VAT ordinary invoice vs 6% special VAT invoice for 5+ seats

Mainland China corporate finance departments and university research offices reject overseas English Stripe PDFs for four structural reasons: **(1)** no China Tax Bureau seal or 20-digit e-VAT number, **(2)** cannot pass national VAT verification portals or OA OCR checks, **(3)** zero input-VAT credit for general taxpayers, and **(4)** missing RMB corporate/Alipay payment trail.

| Procurement Scale | China VAT Invoice Type | RMB Tax-Included Pricing | Payment & Contracting |
| :--- | :--- | :--- | :--- |
| **Individual / 1–4 Seats** | **China Digital VAT Ordinary Invoice (数电普票)** | `Plus` **¥160** · `5x` **¥849** · `20x` **¥1,499** — **0% tax markup, same-day issuance** (retail special VAT requires extra tax confirmation) | Alipay or corporate bank wire → 1-on-1 passwordless activation via WeChat `siuserxiaowei` |
| **Enterprise R&D Teams (`20x`, 5+ Seats)** | **6% China VAT Special Invoice (增值税专用发票)** | **¥1,520 / seat / mo** (**6% VAT included**; after ¥86.04 input-VAT credit, effective net cost is **~¥1,433.96 / seat**) | **Corporate bank-to-bank wire**, **same-day e-signed or stamped PDF contract**, 1-on-1 activation onto each member's own account |

- Generate a finance-ready approval memo locally via the **[Invoice & Reimbursement Spec Generator](https://payforgpt.com/tools/invoice-reimbursement-check?utm_source=github&utm_medium=readme_en&utm_campaign=china-invoice-guide-2026)**;
- Estimate multi-seat corporate totals at the **[Enterprise Procurement & Cost Calculator](https://payforgpt.com/qiye-caigou#procurement-calculator)** ([Enterprise Page](https://payforgpt.com/qiye-caigou?utm_source=github&utm_medium=readme_en&utm_campaign=china-invoice-guide-2026)).

---

## 9. Account deactivated & Multi-Device / Shared Seat Abuse Prevention

1. **Strict 1-Seat-Per-Person Policy**: Sharing a single `Plus` or `20x` account across multiple team members in different cities running concurrent `Codex CLI` sessions triggers automated abuse bans (`Account deactivated`).
2. **Never Proxy Web/CLI Subscriptions for Production APIs**: Production workloads must use OpenAI's pay-as-you-go API Platform.
3. For false-positive deactivations on clean personal accounts, the account holder must appeal directly via `help.openai.com`. Browse all browser-local diagnostics at [PayForGPT Free Tools](https://payforgpt.com/tools?utm_source=github&utm_medium=readme_en&utm_campaign=china-invoice-guide-2026).

---

## 10. QQ / 163 Email Login Mismatch & Codex Phone Verification

- **QQ / 163 Auth Consistency**: Users registered with `QQ` or `163` email addresses should consistently sign in using **email + password** rather than mixing OAuth buttons, and whitelist `@openai.com` to avoid delayed OTP verification emails.
- **Headless / SSH Codex Login**: On remote Linux servers without a browser, enable device-code login in ChatGPT security settings and run `codex login --device-auth` over a stable network exit.

---

## 11. Subscription Cancellation, Plan Upgrade Rules & VAT Invoice Red-Flush

1. **Canceling Auto-Renewal**: Navigate to `Settings → Subscription → Manage my subscription → Cancel plan` before the billing date. Remaining paid days stay active until the account reverts to `Free`.
2. **Cross-Channel Upgrade Locks**: You cannot overwrite an active Apple App Store subscription from the web; wait until the IAP term expires completely.
3. **VAT Invoice Red-Flush (红冲) on Eligible Refunds**: If a domestic VAT invoice has already been issued for a qualifying refund/cancellation order, both parties must complete standard China red-ink VAT invoice cancellation before refund settlement.

---

## 12. Order Verification, Support Anti-Impersonation & 30-Day SLA Boundaries

Verify these operational facts before transacting:

1. **Payment & Official Contact**: PayForGPT accepts **Alipay** and **manual/corporate bank transfer** (**WeChat Pay is not supported**). Official WeChat **`siuserxiaowei`** is strictly for post-payment 1-on-1 passwordless activation and invoicing support—staff will **never initiate friend requests** and corporate bank details are only shared inside verified WeChat chat.
2. **Identity & Order Lookup**: Verify official support channels at **[PayForGPT Verify](https://payforgpt.com/verify?utm_source=github&utm_medium=readme_en&utm_campaign=china-invoice-guide-2026)** and track orders at **[Order Lookup](https://payforgpt.com/order?utm_source=github&utm_medium=readme_en&utm_campaign=china-invoice-guide-2026)** (never share your lookup password with anyone).
3. **Transparent 30-Day SLA ([Full Refund Terms](https://payforgpt.com/refund?utm_source=github&utm_medium=readme_en&utm_campaign=china-invoice-guide-2026))**:
   - **Activation failure**: 100% full refund.
   - **Within 30 days of payment (non-account-fault drop)**: 1 free reactivation of the same tier, or a pro-rata refund for remaining days if reactivation is unavailable.
   - **Exclusions**: Account bans resulting from shared seats, bulk-purchased burner emails, or OpenAI ToS violations are not eligible for free replacement or unconditional "ban compensation."

---

## 📚 Deep-Dive Guides

- 🌐 **[English Error & Procurement Reference](./guides/troubleshooting-errors-en.md)**
- 📄 **[China VAT Invoice Reimbursement Guide (ZH)](./guides/domestic-vat-invoice-reimbursement.md)**
- 🛡️ **[Account Risk, Outlook & WildCard Migration Checklist (ZH)](./guides/account-risk-and-outlook-precheck.md)**
- ⚡ **[Codex Quota & Plus / 5x / 20x Selection Guide (ZH)](./guides/codex-pro-100-200-selection.md)**

---

## License

Licensed under [CC BY 4.0](./LICENSE). Contributions and verified troubleshooting updates via Issue or PR are welcome.
