# Credential Inventory — SourcifyLending

**Status:** ⏳ Ready for Phase 4 handoff
**Purpose:** Complete inventory of every external account, API key, and configuration value that must be transferred or recreated by the buyer.

---

## 1. Supabase

| Field | Value | Location |
|-------|-------|----------|
| Project URL | `NEXT_PUBLIC_SUPABASE_URL` | `.env` |
| Anon Key | `NEXT_PUBLIC_SUPABASE_ANON_KEY` | `.env` |
| Service Role Key | `SUPABASE_SERVICE_ROLE_KEY` | `.env` |
| Database Schema | `supabase/migrations/` | GitHub repo |
| RLS Policies | Applied via migrations | Supabase dashboard |

**Transfer action:** Add buyer as owner → remove seller access

---

## 2. Stripe

| Field | Value | Location |
|-------|-------|----------|
| Publishable Key | `NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY` | `.env` |
| Secret Key | `STRIPE_SECRET_KEY` | `.env` |
| Webhook Secret | `STRIPE_WEBHOOK_SECRET` | `.env` |
| Price ID — Program A | `STRIPE_PRICE_ID_PROGRAM_A` | `.env` |
| Price ID — Program B | `STRIPE_PRICE_ID_PROGRAM_B` | `.env` |
| Price ID — Program C | `STRIPE_PRICE_ID_PROGRAM_C` | `.env` |

**Transfer action:** Transfer Stripe account or recreate in buyer's Stripe account

---

## 3. Twilio

| Field | Value | Location |
|-------|-------|----------|
| Account SID | `TWILIO_ACCOUNT_SID` | `.env` |
| Auth Token | `TWILIO_AUTH_TOKEN` | `.env` |
| Caller ID | `TWILIO_CALLER_ID` | `.env` |
| TwiML App SID | `TWILIO_TWIML_APP_SID` | `.env` |
| API Key SID | `TWILIO_API_KEY_SID` | `.env` |
| API Key Secret | `TWILIO_API_KEY_SECRET` | `.env` |
| Phone Number | N/A | Twilio console |

**Transfer action:** Transfer Twilio account or create new subaccount for buyer

---

## 4. Resend (Transactional Email)

| Field | Value | Location |
|-------|-------|----------|
| API Key | `RESEND_API_KEY` | `.env` |
| Sending Domain | `resend.com` dashboard | Buyer needs to verify |

**Transfer action:** Add buyer as owner of sending domain

---

## 5. Anthropic (Claude API)

| Field | Value | Location |
|-------|-------|----------|
| API Key | `ANTHROPIC_API_KEY` | `.env` |

**Transfer action:** Share key or buyer creates own

---

## 6. OpenAI / LLM

| Field | Value | Location |
|-------|-------|----------|
| API Key | `OPENAI_API_KEY` | `.env` |
| Base URL (optional) | `OPENAI_BASE_URL` | `.env` |

**Transfer action:** Share key or buyer creates own

---

## 7. Google (Calendar / OAuth)

| Field | Value | Location |
|-------|-------|----------|
| Client ID | `GOOGLE_CLIENT_ID` | `.env` |
| Client Secret | `GOOGLE_CLIENT_SECRET` | `.env` |
| Redirect URI | `GOOGLE_REDIRECT_URI` | `.env` |
| Refresh Token | `GOOGLE_REFRESH_TOKEN` | `.env` |
| Calendar ID | `GOOGLE_CALENDAR_ID` | `.env` |
| Timezone | `GOOGLE_CALENDAR_TIMEZONE` | `.env` |
| Booking URL | `NEXT_PUBLIC_BOOKING_URL` | `.env` |

**Transfer action:** Transfer Google Cloud project or buyer creates own OAuth credentials

---

## 8. Vapi (Voice AI)

| Field | Value | Location |
|-------|-------|----------|
| API Key | `VAPI_API_KEY` | `.env` |
| Assistant ID | `VAPI_ASSISTANT_ID` | `.env` |
| Phone Number ID | `VAPI_PHONE_NUMBER_ID` | `.env` |
| Webhook Secret | `VAPI_WEBHOOK_SECRET` | `.env` |

**Transfer action:** Transfer account ownership or share access

---

## 9. AWS SES (Campaign Email)

| Field | Value | Location |
|-------|-------|----------|
| Region | `AWS_REGION` | `.env` |
| Access Key ID | `AWS_ACCESS_KEY_ID` | `.env` |
| Secret Access Key | `AWS_SECRET_ACCESS_KEY` | `.env` |
| Configuration Set | `AWS_SES_CONFIGURATION_SET` | `.env` |
| Campaign Topic ARN | `AWS_SES_CAMPAIGN_TOPIC_ARN` | `.env` |
| From Email | `AWS_SES_FROM_EMAIL` | `.env` |
| From Name | `AWS_SES_FROM_NAME` | `.env` |

**Transfer action:** Create IAM user for buyer or buyer uses own AWS

---

## 10. Notion (Lead Sync)

| Field | Value | Location |
|-------|-------|----------|
| Integration Token | `NOTION_API_KEY` | `.env` |
| Database IDs | Code references | Source code |

**Transfer action:** Share integration or buyer creates own

---

## 11. Vercel (Deployment)

| Field | Value | Location |
|-------|-------|----------|
| Project Name | SourcifyLending | Vercel dashboard |
| Framework Preset | Next.js | Vercel settings |
| Build Command | `next build` | `package.json` |
| Environment Variables | Full set from `.env` | Vercel dashboard |
| Custom Domain | sourcifylending.com | Vercel domains |

**Transfer action:** Add buyer as team member → transfer project

---

## 12. GitHub (Source Code)

| Field | Value | Location |
|-------|-------|----------|
| Repository | SourcifyDigital/sourcifylending | github.com |
| Branch | `main` | GitHub |

**Transfer action:** Transfer repo to buyer's GitHub org

---

## 13. Partner / Affiliate

| Item | Value | Location |
|------|-------|----------|
| Kashu Affiliate URL | `NEXT_PUBLIC_KASHU_AFFILIATE_URL` | `.env` |
| Google Calendar Booking | `NEXT_PUBLIC_BOOKING_URL` | `.env` |

---

## Environment File Template

The file `.env.local.example` in the repo root contains all variable names.
Buyer must create their own `.env.local` with real values for their accounts.

---

**Document generated:** June 11, 2026
**Prepared for:** Winterpirce Inc / Wilmer Ojeda
