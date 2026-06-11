# Phase 4 — Final Ownership Transfer Checklist

**Buyer:** Winterpirce Inc (Wilmer Ojeda)
**Price:** $1,000 (via escrow.com)
**Status:** ⏳ Ready for execution

> Phase 4 transfers the remaining ownership items not covered in Phase 3:
> domain, Stripe, and social accounts.

---

## □ 1. Domain Transfer — sourcifylending.com (Bluehost)

- [ ] Log into Bluehost account
- [ ] Unlock domain for transfer
- [ ] Obtain EPP / authorization code
- [ ] Transfer domain to buyer's registrar account (or within Bluehost)
- [ ] Verify WHOIS updates to Winterpirce Inc info
- [ ] Confirm domain resolves after transfer
- [ ] Update nameservers or confirm buyer's NS preference

## □ 2. DNS Records — Complete Mapping

- [ ] Export all current DNS records as a backup file
- [ ] Document every record (type, name, value, TTL) for buyer
- [ ] Hand DNS management to buyer
- [ ] Verify: apex domain resolves correctly
- [ ] Verify: www subdomain resolves correctly

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

## □ 3. Search Console & SEO Handoff

- [ ] Add buyer as owner in Google Search Console
- [ ] Verify new domain ownership (DNS TXT record or HTML file)
- [ ] Remove seller access after transfer
- [ ] Submit current sitemap
- [ ] Confirm robots.txt is accessible on production host

## □ 4. Stripe Account Transfer

- [ ] Transfer Stripe account ownership to Winterpirce Inc
- [ ] Document: publishable key, secret key, webhook secret
- [ ] Document: price IDs for all programs
- [ ] Verify webhook endpoints are configured
- [ ] Confirm buyer can process test payments

## □ 5. Facebook Ad Account Transfer

- [ ] Add buyer as admin in Facebook Business Manager
- [ ] Transfer ad account ownership to buyer's Business Manager
- [ ] Document: ad account ID, current campaigns
- [ ] Remove seller access after transfer
- [ ] Verify buyer can create and run ads

## □ 6. Facebook Business Page Transfer

- [ ] Add buyer as admin on the Facebook page
- [ ] Transfer page ownership to buyer's Business Manager
- [ ] Remove seller access
- [ ] Verify buyer can post, respond, manage settings

## □ 7. Instagram Account Transfer

- [ ] Ensure Instagram is connected to the Facebook page
- [ ] Transfer Instagram account ownership via Business Manager
- [ ] Verify buyer can post and manage the account
- [ ] Update contact info and bio to buyer's details

## □ 8. Documentation Handoff

- [ ] Deliver credential inventory ([CREDENTIAL_INVENTORY.md](./CREDENTIAL_INVENTORY.md))
- [ ] Deliver DNS transfer guide ([DNS_TRANSFER_GUIDE.md](./DNS_TRANSFER_GUIDE.md))

## □ 9. Final Verification

- [ ] Buyer confirms: domain resolves correctly
- [ ] Buyer confirms: Stripe payments work
- [ ] Buyer confirms: Facebook ad account is theirs
- [ ] Buyer confirms: Facebook page is theirs
- [ ] Buyer confirms: Instagram account is theirs
- [ ] Buyer signs off on Phase 4 delivery
- [ ] Escrow.com — Phase 4 funds released ✅

---

**Document generated:** June 11, 2026
**Prepared for:** Winterpirce Inc / Wilmer Ojeda
