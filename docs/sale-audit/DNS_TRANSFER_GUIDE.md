# DNS Transfer Guide — sourcifylending.com

**Status:** ⏳ Ready for Phase 4 execution
**Purpose:** Step-by-step guide for transferring domain from Bluehost and DNS to buyer.

---

## Part 1: Domain Transfer from Bluehost

### Prerequisites
- **Registrar:** Bluehost
- **Domain:** sourcifylending.com
- **Buyer:** Winterpirce Inc (Wilmer Ojeda)

### Transfer Steps

1. **Log into Bluehost** — your account at bluehost.com
2. **Unlock the domain**
   - Bluehost Dashboard → Domains → sourcifylending.com
   - Turn off "Domain Lock" / "Transfer Lock"
3. **Get the EPP Code**
   - Same area — click "Get EPP Code" or "Authorization Code"
   - Code will be emailed to the registrant email or shown in dashboard
4. **Provide EPP code to buyer** — Wilmer initiates the transfer from his registrar
5. **Approve the transfer**
   - Bluehost will email a transfer approval link
   - Click to approve
6. **Confirm completion**
   - WHOIS reflects Winterpirce Inc
   - Domain resolves correctly

> ⚠️ Domain must be unlocked for 60+ days since last transfer/registration
> before it can be transferred to a new registrar.

---

## Part 2: DNS Records — Quick Reference

These records should be documented from the current Bluehost DNS panel before transfer:

| Type | Name | Value | Purpose |
|------|------|-------|---------|
| A | @ | [Vercel IP] | Apex → main site |
| AAAA | @ | [Vercel IPv6] | Apex IPv6 |
| CNAME | www | [Vercel hostname] | www → main site |
| MX | @ | [provider MX] | Email |
| TXT | @ | v=spf1 ... | SPF |
| TXT | _dmarc | v=DMARC1 ... | DMARC |
| TXT | [selector]._domainkey | [DKIM key] | DKIM |

Export these from Bluehost before starting the transfer.

---

## Part 3: Search Console Transfer

1. **Add buyer** as owner in Google Search Console
2. **Verify new ownership** (DNS TXT record or HTML file)
3. **Remove your access** after buyer confirms verification
4. **Resubmit sitemap** at `https://www.sourcifylending.com/sitemap.xml`

---

## Part 4: Quick Verification

Buyer should verify after transfer:

- [ ] `dig sourcifylending.com` → resolves correctly
- [ ] `dig www.sourcifylending.com` → resolves correctly
- [ ] Website loads in browser → 200 OK
- [ ] Google Search Console → property verified
- [ ] Vercel → domain says "Valid Configuration"

---

**Document generated:** June 11, 2026 — Updated to Bluehost transfer
**Prepared for:** Winterpirce Inc / Wilmer Ojeda
