# English Troubleshooting Reference: Billing Errors, Session Security, Codex Quotas & China VAT Procurement

[← Back to English Encyclopedia README_EN.md](../README_EN.md) | [中文主页 README.md](../README.md)

This companion guide provides quick engineering triage playbooks for developers and corporate IT teams managing ChatGPT (`Plus`, `Pro 100 / 5x`, `Pro 200 / 20x`) and `Codex` seats across mainland China and international environments.

> **Independence Disclosure**: References to [PayForGPT](https://payforgpt.com/en?utm_source=github&utm_medium=guide_en&utm_campaign=china-invoice-guide-2026) refer to an independent third-party subscription activation and domestic VAT invoicing service with no official affiliation with OpenAI.

---

## 1. Error Playbook: `Your card has been declined` / `Payment was not approved`

| Symptom | Likely Cause | Actionable Fix |
| :--- | :--- | :--- |
| Immediate `Your card has been declined` on submit | Mainland China card BIN or billing address mismatch with IP | Do not retry >3 times; switch to a verified overseas card or use [PayForGPT Pricing](https://payforgpt.com/price?utm_source=github&utm_medium=guide_en&utm_campaign=china-invoice-guide-2026) via Alipay/corporate transfer |
| `Payment was not approved` after 3DS prompt | Issuer cross-border risk block or temporary Stripe lock | Wait 24h before retrying card, or review [Card Declined Help](https://payforgpt.com/help/card-declined?utm_source=github&utm_medium=guide_en&utm_campaign=china-invoice-guide-2026) |
| Legacy WildCard / Dupay `Past Due` retry loop | Defunct virtual card BIN failing auto-renewal | Cancel old subscription in `Settings → Subscription → Cancel plan` until status resets to `Free` |

---

## 2. Error Playbook: `Paid but still showing Free tier`

1. Verify you logged in with the exact same authentication method (`Email + Password` vs `Continue with Google/Apple/Microsoft`) used during activation.
2. Perform a hard session reset (`Log out` → close browser tabs → sign in again).
3. On mobile apps, verify `Restore purchases` only if originally billed via App Store / Google Play.
4. Check [Paid Still Free Restore](https://payforgpt.com/help/chatgpt-paid-still-free-restore?utm_source=github&utm_medium=guide_en&utm_campaign=china-invoice-guide-2026) or look up your order status at [Order Lookup](https://payforgpt.com/order?utm_source=github&utm_medium=guide_en&utm_campaign=china-invoice-guide-2026).

---

## 3. Security Standard: Zero-Password & Zero `api/auth/session` Exposure

- Never paste the JSON response from `https://chatgpt.com/api/auth/session` into third-party self-service forms. That JSON exposes your active Bearer `accessToken`.
- Verify account hygiene before upgrading with the local-only **[Account Risk Precheck](https://payforgpt.com/tools/account-precheck?utm_source=github&utm_medium=guide_en&utm_campaign=china-invoice-guide-2026)**—especially if your account uses an `Outlook / Hotmail / Live` address.

---

## 4. China Corporate Procurement & Reimbursement Checklist

1. **1–4 Seats (Individual / Small Team)**: `Plus` ¥160/mo, `5x` ¥849/mo, `20x` ¥1,499/mo — includes **0%-markup China digital VAT ordinary invoice** issued the same day.
2. **5+ Seats (`20x` Team Batch)**: **¥1,520/seat/mo** including a **6% China VAT special invoice** (`~¥1,433.96/seat` net cost after input-VAT deduction for general taxpayers), corporate bank wire, and same-day PDF/e-signed procurement contract.
3. Generate your internal finance approval brief with **[Invoice Reimbursement Check](https://payforgpt.com/tools/invoice-reimbursement-check?utm_source=github&utm_medium=guide_en&utm_campaign=china-invoice-guide-2026)** and calculate multi-seat budgets on the **[Enterprise Procurement Calculator](https://payforgpt.com/qiye-caigou#procurement-calculator)**.
