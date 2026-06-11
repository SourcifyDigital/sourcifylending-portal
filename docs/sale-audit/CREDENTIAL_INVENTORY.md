# Credential Inventory — SourcifyLending

**Status:** ⏳ Ready for Phase 4 handoff
**Purpose:** Complete inventory of everything being transferred to buyer.

---

## 1. Domain — sourcifylending.com

| Item | Details |
|------|---------|
| Registrar | Bluehost |
| Domain | sourcifylending.com |
| Transfer Method | EPP code / registrar transfer |

**Action:** Unlock at Bluehost → get EPP code → transfer to buyer

---

## 2. Stripe

| Field | Value | Notes |
|-------|-------|-------|
| Account Owner | Vidalyfe LLC / Abel Fernandez | Transfer to Winterpirce Inc |
| Publishable Key | `NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY` | In `.env` |
| Secret Key | `STRIPE_SECRET_KEY` | In `.env` |
| Webhook Secret | `STRIPE_WEBHOOK_SECRET` | In `.env` |
| Price ID — Program A | `STRIPE_PRICE_ID_PROGRAM_A` | In `.env` |
| Price ID — Program B | `STRIPE_PRICE_ID_PROGRAM_B` | In `.env` |
| Price ID — Program C | `STRIPE_PRICE_ID_PROGRAM_C` | In `.env` |

**Action:** Transfer entire Stripe account to Winterpirce Inc
**Verify:** Buyer can process test payments and access dashboard

---

## 3. Facebook Ad Account

| Item | Details |
|------|---------|
| Platform | Meta Business Manager |
| Account ID | [Find in Business Manager] |
| Current Owner | Vidalyfe LLC |

**Action:** Add buyer as admin → transfer ad account ownership
**Verify:** Buyer can create and run campaigns

---

## 4. Facebook Business Page

| Item | Details |
|------|---------|
| Page Name | SourcifyLending |
| Platform | Facebook |
| Current Admin | Abel Fernandez |

**Action:** Add buyer as admin → transfer page to buyer's Business Manager
**Verify:** Buyer can post and manage settings

---

## 5. Instagram Business Account

| Item | Details |
|------|---------|
| Handle | [Instagram handle] |
| Platform | Instagram (via Facebook Business Manager) |
| Linked To | SourcifyLending Facebook page |

**Action:** Transfer via Business Manager → update contact info to buyer
**Verify:** Buyer can post and manage

---

## 6. GitHub Repository

| Item | Details |
|------|---------|
| Repository | SourcifyDigital/sourcifylending-portal |
| Host | github.com |
| Default Branch | main |

**Action:** Transfer repo to buyer's GitHub org
**Verify:** Buyer can clone, build, deploy

---

## 7. Vercel

| Item | Details |
|------|---------|
| Project | SourcifyLending |
| Framework | Next.js |
| Custom Domain | sourcifylending.com |

**Action:** Transfer project to buyer's Vercel team
**Verify:** Build succeeds, domain resolves

---

## Not Being Transferred (not in use)
- ❌ Notion — not used
- ❌ Vapi (voice) — not used
- ❌ AWS SES — not used
- ❌ Anthropic / Claude — not used
- ❌ Resend — not used
- ❌ Twilio — not used

---

## Environment Variables

The file `.env.local.example` in the repo root has all the variable names.
After transfer, buyer should update their own `.env.local` with values from their own accounts for any services they set up.

---

**Document generated:** June 11, 2026 — Updated to actual transfer items
**Prepared for:** Winterpirce Inc / Wilmer Ojeda
