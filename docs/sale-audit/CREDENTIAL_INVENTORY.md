# Credential Inventory — SourcifyLending

**Status:** ⏳ Ready for Phase 4 handoff
**Purpose:** Complete inventory of everything remaining to transfer.

> Vercel, Supabase, and GitHub were already transferred in Phase 3.
> Only items below are part of Phase 4.

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
| Price IDs | All programs | In `.env` |

**Action:** Transfer entire Stripe account to Winterpirce Inc
**Verify:** Buyer can process payments and access dashboard

---

## 3. Facebook Ad Account

| Item | Details |
|------|---------|
| Platform | Meta Business Manager |
| Current Owner | Vidalyfe LLC |

**Action:** Add buyer as admin → transfer ad account ownership

---

## 4. Facebook Business Page

| Item | Details |
|------|---------|
| Page Name | SourcifyLending |
| Current Admin | Abel Fernandez |

**Action:** Add buyer as admin → transfer to buyer's Business Manager

---

## 5. Instagram Business Account

| Item | Details |
|------|---------|
| Platform | Instagram (via Facebook Business Manager) |
| Linked To | SourcifyLending Facebook page |

**Action:** Transfer via Business Manager → update contact info to buyer

---

## Already Transferred in Phase 3
- ✅ GitHub repository
- ✅ Vercel project and deployment
- ✅ Supabase database access

---

**Document generated:** June 11, 2026
**Prepared for:** Winterpirce Inc / Wilmer Ojeda
