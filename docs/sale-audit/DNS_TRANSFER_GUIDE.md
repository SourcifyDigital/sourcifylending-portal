# DNS Transfer Guide — sourcifylending.com

**Status:** ⏳ Ready for Phase 4 execution
**Purpose:** Step-by-step guide for transferring domain and DNS from seller to buyer.

---

## Part 1: Domain Transfer

### Current Registrar
- **Registrar:** [Verify current registrar — e.g., Namecheap, GoDaddy, Cloudflare]
- **Registry Expiration:** [Verify date]
- **EPP Code:** Generate from current registrar dashboard

### Transfer Steps

1. **Unlock the domain** at current registrar
   - Dashboard → Domain Management → Lock Status → Disable

2. **Obtain EPP / Authorization Code**
   - Request from registrar; sent via email or shown in dashboard

3. **Initiate transfer at buyer's registrar**
   - Buyer starts transfer, enters EPP code
   - Seller approves transfer request via email

4. **Confirm transfer completion**
   - WHOIS reflects buyer's info
   - Domain resolves to buyer's DNS

### Post-Transfer
- **Nameservers:** Buyer can use their own or keep current
- **DNSSEC:** Disable before transfer, re-enable after

---

## Part 2: DNS Records — Full Mapping

### Apex Domain (@)

| Record | Value | TTL | Purpose |
|--------|-------|-----|---------|
| A | 76.76.21.21 | 600 | Vercel edge network (prod) |
| AAAA | 2600:9000:... | 600 | Vercel IPv6 |
| MX | [provider MX] | 3600 | Email delivery |
| TXT | v=spf1 include:[provider] ~all | 3600 | SPF / sender auth |
| TXT | v=DMARC1; p=quarantine; | 3600 | DMARC policy |

### Subdomains

| Record | Name | Type | Value | TTL | Purpose |
|--------|------|------|-------|-----|---------|
| www | www | CNAME | cname.vercel-dns.com | 600 | Main site |
| [other] | [name] | [type] | [value] | 600 | [purpose] |

### Email Authentication Records

| Type | Name | Value | Purpose |
|------|------|-------|---------|
| TXT | @ | v=spf1 include:spf.resend.com ~all | Resend sending SPF |
| TXT | resend._domainkey | [Resend DKIM key] | Resend DKIM |
| TXT | _dmarc | v=DMARC1; p=quarantine; rua=mailto:[report] | DMARC reporting |

---

## Part 3: Search Console Transfer

1. **Add buyer** as owner in Google Search Console
   - Property → Settings → Users & Permissions → Add User
   - Role: Owner

2. **Verify new ownership**
   - Option A: Add TXT record to DNS (easiest during transfer)
   - Option B: Upload HTML verification file

3. **Remove seller access** after buyer confirms verification

4. **Resubmit sitemap**
   - Sitemap URL: `https://www.sourcifylending.com/sitemap.xml`

---

## Part 4: Quick Verification Checklist

After transfer, buyer should verify:

- [ ] `curl -I https://www.sourcifylending.com` → 200 OK
- [ ] `dig www.sourcifylending.com` → resolves to Vercel IP
- [ ] `dig sourcifylending.com MX` → email MX records present
- [ ] `dig sourcifylending.com TXT` → SPF + DKIM + DMARC present
- [ ] Google Search Console → property verified
- [ ] Vercel dashboard → custom domain says "Valid Configuration"

---

**Document generated:** June 11, 2026
**Prepared for:** Winterpirce Inc / Wilmer Ojeda
