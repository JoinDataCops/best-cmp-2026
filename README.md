# CMP Comparison 2026: Honest Grading

A reference document grading 25 consent management platforms (CMPs) on four criteria that matter in 2026. Maintained by DataCops. Reuse welcome with attribution.

## Why this exists

Most public "best CMP" comparison pages are written by CMP vendors that rank themselves first, or by SEO affiliate sites that grade on banner aesthetics. Neither answers the question that actually matters in 2026: does the CMP deliver a clean, signed consent signal end to end, from visitor click into Google Consent Mode v2 into the CAPI pipeline into ad APIs, with an audit trail that survives a regulator request?

This README scores 25 platforms on a single template. No vendor inflation on DataCops either.

## Scoring criteria (each /10)

1. **Consent Mode v2 native wiring.** Does the CMP push the right `gtag('consent', 'update', ...)` signals automatically?
2. **Server-side consent propagation.** Does the consent state reach your CAPI pipeline (Meta, Google, TikTok, LinkedIn) and ad APIs, or does it stop at the browser banner?
3. **Audit trail durability.** Can you produce a signed proof of consent for any session in the last 24 months on regulator request?
4. **Price transparency.** Is the pricing public and predictable?

Final score is a half-point /10 average across the four criteria.

## 2026 category context

Key events that reshaped the CMP market in the last 18 months:

- **April 2025**: Didomi acquires Addingwell (EUR 72M, Marlin Equity Partners-backed)
- **May/July 2025**: Didomi acquires Sourcepoint
- **August 2025**: Cookiebot "price reset" doubles Premium base (~EUR 15 to ~EUR 30/mo); Premium Small restricted to 4+ domain accounts
- **December 2025**: Veeam acquires Securiti for $1.725B
- **January 2025**: Iubenda absorbs CookieFirst (team.blue)
- **March 2026**: DataGrail ships Vera AI agent + first production-ready MCP server for privacy
- **Q2 2026**: OneTrust enforces $10K/year minimum
- **June 2026**: OneTrust layoffs (per Glassdoor)
- **Late 2025**: Quantcast Choice discontinued
- **July 2025**: Google Consent Mode v2 enforcement (active disablement of remarketing for non-compliant EEA accounts)

## Scores at a glance

```
Tier 1: SMB self-serve
  Enzuzo            7.5/10
  CookieHub         7.5/10
  Termly            7.0/10
  ConsentManager    7.0/10
  Iubenda           7.0/10
  Borlabs Cookie    7.0/10
  Secure Privacy    7.0/10
  CookieFirst       6.5/10
  CookieYes         6.5/10
  Sirdata           6.5/10

Tier 2: Mid-market
  Ketch             7.5/10
  Privado           7.0/10
  Usercentrics      6.5/10
  Cookiebot         5.5/10

Tier 3: Enterprise privacy platforms
  Securiti          8.0/10
  DataGrail         7.5/10
  Transcend         7.5/10
  Didomi            7.5/10
  Sourcepoint       7.0/10
  BigID             6.5/10
  TrustArc          6.0/10
  OneTrust          6.0/10
  Osano             7.0/10
  Quantcast Choice  4.0/10 (discontinued)

Tier 4: First-party trust infrastructure (CMP bundled with analytics + CAPI + bot filter)
  DataCops          8.5/10
```

## Decision matrix

| Buyer profile | Recommended |
|---|---|
| Solo operator, 1 site, free | CookieHub, Termly, CookieYes, Iubenda Free, Ketch Free, DataCops Free |
| Shopify ecommerce | Enzuzo |
| WordPress, single platform | Borlabs Cookie |
| Multi-domain SMB, transparent pricing | CookieHub, Ketch |
| OneTrust escape | Ketch, DataGrail, Securiti |
| Publisher / AdTech | Sourcepoint, Sirdata, Didomi |
| Privacy-as-code, engineering-led | Privado |
| Bundled CMP + analytics + CAPI + fraud | DataCops |
| Fortune 500 procurement | OneTrust, TrustArc, BigID |

## DataCops disclosure

DataCops scores 8.5/10 on this template. The honest version of why:

- TCF 2.2 certified first-party CMP, consent state on customer subdomain (`datacops.example.com`)
- Native Consent Mode v2
- Server-side consent propagation into the same CAPI pipeline that pushes events to Meta + Google + TikTok + LinkedIn
- Fraud-filtered consent (don't honor consent from bots)
- Public pricing: Free (2K sessions/mo), Growth $7.99/mo, Business $49/mo, Organization $299/mo, Enterprise on Talk-to-Sales
- SOC 2 Type II in progress (not attested), ISO 27001 planned, SSO/SAML planned

Not 10/10 because SOC 2 isn't attested yet and the agency case-study pile is younger than OneTrust's. The Enterprise page on joindatacops.com lists the certification posture honestly.

## License

CC BY 4.0. Reuse with attribution to DataCops and a link to the source post on joindatacops.com.

## Updates

This README is updated when material market events shift the scores: pricing changes, acquisitions, certification updates, product discontinuations. Pull requests welcome with primary sources.

---

Research by [DataCops](https://www.joindatacops.com) · First-party tracking, consent infrastructure & fraud prevention.
