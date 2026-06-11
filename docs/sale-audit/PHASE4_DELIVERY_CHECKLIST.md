# Phase 4 — Final Ownership Transfer Checklist

**Buyer:** Winterpirce Inc (Wilmer Ojeda)
**Price:** $1,000 (via escrow.com)
**Status:** ⏳ Ready for execution

> Phase 4 transfers **full ownership** of domain, DNS, credentials,
> social accounts, and all remaining access. After this phase,
> Winterpirce Inc has independent control.

---

## □ 1. Domain Transfer — sourcifylending.com

- [ ] Unlock domain at current registrar
- [ ] Obtain EPP / authorization code
- [ ] Transfer domain to buyer's registrar account
- [ ] Verify WHOIS updates to buyer's information
- [ ] Confirm domain resolves after transfer
- [ ] Update nameservers or confirm buyer's NS preference

## □ 2. DNS Records — Complete Mapping

- [ ] Export all current DNS records as a backup file
- [ ] Document every record (type, name, value, TTL) for buyer reference
- [ ] Transfer DNS management to buyer's account
- [ ] Verify: apex domain resolves to correct host
- [ ] Verify: www subdomain resolves to correct host
- [ ] Verify: email DNS records (MX, SPF, DKIM, DMARC) resolve
- [ ] Verify: any API/dashboard subdomains resolve

### Current DNS Record Map *(fill in before transfer)*

| Type  | Name               | Value                            | TTL    |
|-------|--------------------|----------------------------------|--------|
| A     | @                  | [Vercel IP / target]             | 600    |
| AAAA  | @                  | [Vercel IPv6 / target]           | 600    |
| CNAME | www                | [Vercel hostname]                | 600    |
| MX    | @                   | [email provider MX]              | 3600   |
| TXT   | @                  | [SPF record]                     | 3600   |
| TXT   | _dmarc             | [DMARC policy]                   | 3600   |
| TXT   | [selector]._domainkey | [DKIM key]                    | 3600   |
| CNAME | [subdomain]        | [target]                         | 600    |
|       | *additional rows as needed* |                             |        |

## □ 3. Search Console & SEO Handoff

- [ ] Add buyer as owner in Google Search Console
- [ ] Verify new domain ownership (DNS TXT record or HTML file)
- [ ] Remove seller access after transfer
- [ ] Submit current sitemap (`/sitemap.ts`)
- [ ] Confirm robots.txt is accessible on production host
- [ ] Document IndexNow key and host configuration (if enabled)

## □ 4. External Provider Account Transfer

### Supabase
- [ ] Add buyer as team member / owner on Supabase project
- [ ] Verify database schema parity (run migration list)
- [ ] Transfer project ownership to buyer's Supabase org
- [ ] Remove seller access
- [ ] Document: project URL, anon key, service-role key

### Stripe
- [ ] Transfer Stripe account ownership or create new account for buyer
- [ ] Document: publishable key, secret key, webhook secret
- [ ] Document: price IDs for all programs (A, B, C)
- [ ] Verify webhook endpoints are configured in buyer's account
- [ ] Verify customer portal configuration

### Twilio
- [ ] Transfer Twilio account or provide credentials
- [ ] Document: Account SID, auth token, caller ID
- [ ] Document: TwiML app SID, API key SID, API key secret
- [ ] Verify phone number ownership
- [ ] Verify voice app webhook URLs

### Resend (Email)
- [ ] Transfer Resend account or provide API key
- [ ] Add buyer as owner on sending domain
- [ ] Document: API key, sending domain
- [ ] Verify DMARC/DKIM/SPF for sending domain

### Anthropic (Claude API)
- [ ] Document: API key
- [ ] Note: Buyer may create their own key

### Google (Calendar / OAuth)
- [ ] Document: client ID, client secret, redirect URI
- [ ] Transfer Google Cloud project ownership or provide OAuth credentials
- [ ] Document: calendar ID, refresh token
- [ ] Verify booking flow works with buyer's account

### Vapi (Voice)
- [ ] Document: API key, assistant ID, phone number ID, webhook secret
- [ ] Transfer account ownership or share access

### Notion (Lead Sync)
- [ ] Document: integration token, database IDs
- [ ] Transfer Notion integration ownership

### AWS SES
- [ ] Document: region, access key ID, secret access key
- [ ] Document: configuration set, topic ARN, from email/name
- [ ] Transfer IAM access or provide credentials

## □ 5. GitHub Repository Transfer

- [ ] Add buyer as collaborator on GitHub repo
- [ ] Transfer repo ownership to buyer's GitHub org
- [ ] Or: provide full `.zip` export of the repo
- [ ] Verify buyer can clone, build, and run locally
- [ ] Run final `npm run build` to confirm zero errors

## □ 6. Vercel Deployment Transfer

- [ ] Add buyer as team member on Vercel project
- [ ] Transfer project to buyer's Vercel team
- [ ] Verify deployment builds from buyer's GitHub repo
- [ ] Verify environment variables are set in buyer's project
- [ ] Verify custom domain works on buyer's Vercel deployment
- [ ] Document: project settings, framework preset, build command

## □ 7. Social Media & Brand Assets

- [ ] Transfer social media account logins and ownership
- [ ] Deliver brand assets package:
  - Logo files (PNG, SVG, full, circle variants)
  - Color palette and typography guide
  - Email templates used in campaigns
  - Marketing copy and taglines
- [ ] Update social profiles to buyer's contact info

## □ 8. Documentation Handoff

- [ ] Deliver credential inventory ([CREDENTIAL_INVENTORY.md](./CREDENTIAL_INVENTORY.md))
- [ ] Deliver DNS transfer guide ([DNS_TRANSFER_GUIDE.md](./DNS_TRANSFER_GUIDE.md))
- [ ] Deliver all 8 SOPs:
  1. CRM & Lead Management
  2. Admin Operations
  3. Dialer System
  4. Application & Funding
  5. AI & Chatbot
  6. Voice System
  7. Lead Capture & Public Form
  8. Affiliate Program
- [ ] Deliver payment credential inventory (Stripe price IDs, webhooks)

## □ 9. Codebase Final Scrub (Pre-Transfer)

- [ ] Remove `.env.local` (contains live credentials)
- [ ] Remove `.claude/`, `.windsurf/`, `.playwright-cli/` (developer artifacts)
- [ ] Remove backup files (\*.zip, \*.csv exports, \*.wav recordings)
- [ ] Remove test/demo seed files or gate behind `SHOW_DEMO_TOOLS=false`
- [ ] Verify no founder-name references remain in source
- [ ] Verify `site-config.ts` defaults are buyer-neutral
- [ ] Run `npm run build` — confirm ✅
- [ ] Run `npm run security:preflight` if available

## □ 10. Final Verification

- [ ] Buyer confirms: can access GitHub repo
- [ ] Buyer confirms: can deploy to Vercel
- [ ] Buyer confirms: can access Supabase
- [ ] Buyer confirms: domain resolves correctly
- [ ] Buyer confirms: email sending works
- [ ] Buyer confirms: payment/billing works (Stripe)
- [ ] Buyer confirms: voice/dialer functions
- [ ] Buyer signs off on Phase 4 delivery
- [ ] Escrow.com — Phase 4 funds released ✅

---

**Document generated:** June 11, 2026
**Prepared for:** Winterpirce Inc / Wilmer Ojeda
