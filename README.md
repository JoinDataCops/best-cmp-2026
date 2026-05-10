# Best CMP 2026: 25 consent platforms graded honestly (and why most comparisons are wrong)

Let's be real. The CMP market in 2026 is a mess.

OneTrust enforced a $10,000/year minimum in Q2 2026 and laid off staff in June 2026. Cookiebot doubled Premium pricing in August 2025 (about EUR 15 to EUR 30 per domain) and restricted Premium Small to 4+ domain accounts, which is just a clean 2x for everyone with one to three sites. Quantcast Choice, the free TCF CMP that ran on countless ad-supported sites, was discontinued. Didomi rolled up Addingwell in April 2025 and Sourcepoint in July 2025 for an enterprise unification play. Veeam acquired Securiti for $1.725B in December 2025 to bolt privacy onto data protection. Iubenda absorbed CookieFirst in January 2025. The category just compressed in front of everyone.

Meanwhile every "best CMP" page on Google was written by a CMP vendor that ranks itself first. So the question worth answering is not which banner looks prettiest. The real question in 2026 is whether your CMP actually delivers a clean, signed consent signal to Google Consent Mode v2, to your CAPI pipeline, to your ad platforms, with an audit trail that survives a regulator request, at a price you can predict. Most banners look fine. Most signal pipelines downstream are broken. That's the gap this post graded against.

25 consent platforms tested across four criteria: native Consent Mode v2 wiring, server-side consent propagation to CAPI and ad APIs, audit trail durability, and price transparency. Half-point /10 scores per tool. Decision tool at the bottom.

If you've read three vendor blogs already this morning, this is the brutally honest version.

---

## Quick stuff people keep asking

**What's the cheapest legitimate CMP in 2026?** Free tiers exist on CookieHub (1,000 sessions/mo), Termly (1 policy, 10K banner views), CookieYes (15K pageviews, 1 domain), Iubenda (basic), Ketch (5,000 users/mo), Secure Privacy and Enzuzo. Paid entry under $10/mo on Termly, Secure Privacy, Enzuzo, CookieFirst, Privado and CookieYes. DataCops bundles a TCF 2.2 first-party CMP into the free tier with the rest of the trust stack.

**Why did Cookiebot pricing change?** August 2025 "price reset" by Usercentrics (Cookiebot's parent). Premium base doubled and the single-domain Premium Small tier was restricted to accounts holding 4+ domains. Trustpilot logged a wave of complaints about price changes communicated late or not at all.

**Is OneTrust still worth it?** For Fortune 500 procurement, yes, the module catalog is the deepest in the category. For everyone else, the $10K/year minimum and the pattern of layoffs make it hard to justify. Ketch, Securiti and DataGrail will all migrate you off.

**What about Quantcast Choice?** Discontinued. If you're still on it, you have to migrate. CookieHub, CookieFirst, Sirdata or DataCops are the closest free or free-adjacent replacements depending on your stack.

**What's actually different about a first-party CMP?** Consent state stored on your subdomain, not a third-party domain. Not blocked by Safari ITP, uBlock, Brave Shields. Same architectural reason first-party analytics works, applied to consent. DataCops and a handful of enterprise CMPs ship this. Most legacy CMPs do not.

---

## How the scoring works

Four weighted factors, each scored on /10, then averaged. Half points where it's a real half.

1. **Consent Mode v2 native wiring.** Does the CMP push the right `gtag('consent', 'update', ...)` signals without you stitching it together by hand?
2. **Server-side consent propagation.** Does the consent state actually reach your CAPI pipeline and ad APIs, or does it stop at the browser banner?
3. **Audit trail durability.** Can you produce, on request from a DPA, a signed proof of consent for any session in the last 24 months?
4. **Price transparency.** Is the pricing public and predictable, or do you have to call sales?

Most "best CMP" lists score banner UX. That's the wrong unit. Banner UX is a five-minute conversation. Pipeline integrity is a 24-month conversation.

---

## Tier 1: SMB self-serve CMPs (under $50/mo)

This is where most operators live. Single site or small portfolio, free or cheap entry, transparent paid tiers, can self-onboard in an hour. The honest answer for most readers is in this tier.

**1. CookieHub**

The Good: Session-based pricing instead of pageview metering means a content-heavy site that gets re-visited doesn't get double-billed. Genuinely useful free tier (1,000 sessions/mo, ~25K pageviews) with proof of consent and Consent Mode v2.

Frustrations: Multi-domain syncing is reported cumbersome. G2 reviewers note limited features compared to OneTrust/Usercentrics tier (no A/B testing, no advanced consent analytics).

Wish List: Cleaner multi-site console. Lightweight A/B test built in.

Value for Money: 7.5/10. Most of what you need from Cookiebot at roughly half the cost, especially after the 2025 Cookiebot reset.

Pricing: Free (1K sessions); Starter EUR 6/mo (5K); Basic EUR 10/mo (30K); Business EUR 30/mo (120K to 1M, IAB TCF 2.3, white-label); Enterprise custom. Overage ~EUR 0.10 per 1K.

---

**2. CookieYes**

The Good: Generous free tier (15K pageviews, 1 domain, auto-scan). Native WordPress plugin (formerly Cookie Law Info) with over 1M active installs; drop-in for the long tail of WP sites.

Frustrations: Per-domain pricing punishes multi-site operators (agencies pay Pro $40/mo per domain). No DSAR automation, no API access, no policy generator on lower tiers.

Wish List: A multi-domain bundle. DSAR on Pro.

Value for Money: 6.5/10. Excellent for one WordPress site, painful past three.

Pricing: Free (15K pageviews, 1 domain); Basic ~$10/mo; Pro $40/mo (300K pageviews); Ultimate $55/mo (unlimited). All per domain. Overage $0.30/1K. Annual ~16.67% off.

---

**3. Termly**

The Good: Bundles policy generator (privacy policy, ToS, disclaimer) with the CMP. One-stop for solo operators and freelancers.

Frustrations: Free/Starter caps (1 to 2 policies, 10 edits, quarterly scans) push casual users to upgrade fast. Multi-site math gets awkward.

Wish List: Multi-site discount.

Value for Money: 7/10. Best-value all-in-one for solo operators and small SaaS.

Pricing: Free (1 policy, 10K banner views); Starter $10/mo; Pro+ $15/mo (2 policies, 50K banner views, monthly scans). 30-day money-back. Annual discount available.

---

**4. Enzuzo**

The Good: Genuine Shopify-native integration that bundles policy generation, cookie consent, DSAR automation and multi-domain into the Shopify dashboard. Google Gold CMP Partner.

Frustrations: Free-tier privacy policy customization is limited. Lower-tier support is slow; some complain there's no in-app way to contact support.

Wish List: Faster support escalation. Bigger free-tier customization.

Value for Money: 7.5/10. Strongest dedicated option for Shopify and SMB ecommerce.

Pricing: Free; Starter $9/mo ($7 annual); Growth $29/mo ($22); PLG Pro $59/mo annual (10 domains); mid-market from $300/mo.

---

**5. Secure Privacy**

The Good: 55+ global privacy laws covered including GDPR, CCPA/CPRA, LGPD and India's DPDP Act. Aggressive entry pricing with Consent Mode v2 wired in.

Frustrations: Smaller brand than OneTrust/Didomi/Cookiebot, so enterprise procurement adds extra security questionnaires. Advanced reporting gated to higher tiers.

Wish List: Better SOC 2 visibility for procurement.

Value for Money: 7/10. Solid budget CMP that nails Consent Mode v2 out of the box.

Pricing: Free; from $8.33/mo. Custom Enterprise.

---

**6. CookieFirst**

The Good: Google CMP Gold Partner with native Consent Mode v2, GTM integration, 44+ auto-translated languages. Cheapest serious CMP in the iubenda family.

Frustrations: Acquired by iubenda (team.blue) in January 2025. Free tier limited to 1 third-party script.

Wish List: Roadmap clarity post-acquisition.

Value for Money: 6.5/10. No-nonsense pricing, just watch the iubenda integration plan.

Pricing: Free (1 script); Basic EUR 9/mo (EUR 99/yr); Plus EUR 19/mo (EUR 209/yr); Enterprise custom. Soft 250K pageviews/domain on all plans.

---

**7. ConsentManager**

The Good: Strong A/B testing and ML-driven banner optimization with claimed 15%+ consent-rate lift. Live reporting with 12 dimensions and 30+ metrics.

Frustrations: Pricier entry (EUR 19 to 23/mo). Bulk editing of new cookies and auto-detected provider search reportedly buggy.

Wish List: Cleaner cookie management UI.

Value for Money: 7/10. Worth the premium if consent rate is a real KPI.

Pricing: From EUR 19 to 23/mo (5 tiers + free trial). Enterprise quoted.

---

**8. Iubenda**

The Good: Mature 360-degree privacy suite (policy generator, CMP, T&C, DSAR, whistleblowing, accessibility) since the team.blue umbrella deal in February 2022. Google Gold CMP Partner (December 2024).

Frustrations: Trustpilot has documented complaints about post-cancellation "threatening emails" and forced account deletion as the only off-ramp. Lower-tier support response stretches a week or more.

Wish List: A cleaner cancellation flow.

Value for Money: 7/10. Solid for many EU languages, not for shops that ever cancel.

Pricing: Free (basic, up to 3 services); Starter (1 language, branded); Essentials $6.99/site/mo; Advanced $27.99/site/mo (multi-language, API); Ultimate $119.99/site/mo (unlimited).

---

**9. Borlabs Cookie**

The Good: WordPress-native plugin with deep integration. Library of 350+ pre-built cookie/script packages. IAB TCF support, geo-restriction, Facebook Pixel assistant.

Frustrations: WordPress-only. Once your annual subscription lapses, premium features (library, geo, IAB TCF, scanner, translations) stop working.

Wish List: Portability if a customer migrates to Shopify or headless.

Value for Money: 7/10. Hard to beat at the price if you live on WordPress and stay there.

Pricing: Personal EUR 49/yr (1 site); Business EUR 109/yr (5 sites); Agency Small EUR 229/yr (25 sites); Agency Large EUR 499/yr (99 sites). Annual only, ex VAT.

---

## Tier 2: Mid-market CMPs ($50 to $500/mo)

This is where teams with portfolios, agencies and growth-stage SaaS land. Real session volumes, multiple domains, some compliance team to please.

**10. Usercentrics**

The Good: Strong EU/GDPR pedigree (Munich) plus Cookiebot SMB line after the 2021 merger. Affordable entry tiers compared to OneTrust/TrustArc.

Frustrations: Auto-upgrade to higher tiers when session limits are exceeded leads to surprise charges. Inaccurate session-limit warnings and billing bugs cited by Capterra reviewers.

Wish List: Hard caps instead of silent auto-upgrades.

Value for Money: 6.5/10. Solid for EU-first teams who can stomach the rough edges.

Pricing: Free under 1K sessions; Essential ~EUR 7/mo (1 domain, 1.5K sessions); Plus ~EUR 15/mo; Pro ~EUR 30/mo (3 domains, 15K sessions); Business ~EUR 50/mo (10 domains, 50K sessions). USD ~$8 to $56/mo.

---

**11. Cookiebot (Usercentrics-owned)**

The Good: Established CMP with broad regulator/agency familiarity. TCF v2.2 + Google CMP partner status. Free plan for 1 domain, 50 subpages.

Frustrations: August 2025 "price reset" doubled Premium base from ~EUR 15 to ~EUR 30/mo per domain. Premium Small was restricted to 4+ domain accounts, effectively a 2x for 1 to 3 domain customers.

Wish List: Honest, advance-notice pricing changes with grandfathering. A real single-domain Premium Small.

Value for Money: 5.5/10. Once the default pick for European agencies, increasingly the option people are switching away from.

Pricing: Free (1 domain, 50 subpages); Premium Lite EUR 7/mo; Premium Small EUR 15/mo (4+ domains); Premium Medium EUR 30/mo; Premium Large EUR 50/mo; Premium XL EUR 90/mo. Usercentrics Advanced custom.

---

**12. Osano**

The Good: Industry-only $500,000 "No Fines, No Penalties" contractual guarantee. Strong AI-assisted cookie classification with confidence scores. Free tier for very small sites.

Frustrations: Self-serve cookie consent now starts at $199/mo for 1 domain capped at 30K monthly visitors. Banner customization is repeatedly called out as limited.

Wish List: More banner layout flexibility. Cheaper Plus tier.

Value for Money: 7/10. Worth it if compliance risk is your top fear; hard to justify if you just need a banner.

Pricing: Free for very small sites. Plus $199/mo (1 domain, 30K visitors). Basic Privacy and Enterprise sales-led.

---

**13. Ketch**

The Good: Free tier covers up to 5K users/mo with full CMP functionality (visitor count, no feature gating). Published pricing all the way to $499/mo Plus. OneTrust migrator program.

Frustrations: Initial setup complex; reviewers note confusing navigation and naming conventions. Some cite poor interface design.

Wish List: Clearer onboarding.

Value for Money: 7.5/10. Genuinely competitive for OneTrust escapees.

Pricing: Free (5K users); Starter $150/mo (30K users); Plus $499/mo annual (100K users + 1,000+ integrations); Pro custom.

---

**14. Privado**

The Good: Genuinely novel "privacy-as-code" approach: scans your codebase to auto-build data maps, RoPAs, PIAs and DPIAs without engineer interviews. AI agents (October 2025) for automating the assessments legal previously did by hand.

Frustrations: Heavy false-positive rate in code scans. Limited customization and slow scan performance on large monorepos.

Wish List: Tighter false-positive controls. Faster scans.

Value for Money: 7/10. The only credible option for engineering-heavy orgs that want RoPAs to fall out of CI.

Pricing: Free-forever tier. Paid from $10/mo (annual). Enterprise on request.

---

**15. Sirdata**

The Good: Deeply embedded in the publisher market, 20,000+ publisher sites running ABconsent CMP. IAB TCF v2.1 certified and well-tuned for AdTech (vendor management per-purpose, leak prevention).

Frustrations: "Free in exchange for your data" model is a non-starter for brands with strict first-party data policies. Less brand-recognized in North America.

Wish List: A pure paid tier without the data-share trade.

Value for Money: 6.5/10. Best-in-class for European publishers comfortable with the data trade.

Pricing: Free (data-share). ABconsent paid plans from EUR 25/mo with a 14-day trial.

---

## Tier 3: Enterprise privacy platforms ($10K+/yr)

Procurement-led, sales-only pricing, multi-module, the consultant-and-implementation-partner crowd.

**16. OneTrust**

The Good: Deepest module catalog in the category (consent, DSAR, data mapping, vendor risk, PIA/DPIA, GRC, ESG). Dominant enterprise market share.

Frustrations: Massive layoffs (about 950 staff, 25%, in June 2022; further rounds reported July 2024 and June 2026). Pricing opaque. New $10K/year minimum as of Q2 2026. Mid-market $40K to $120K/yr; enterprise $120K to $500K+. Trustpilot reviewers cite "sales proactive at renewal, slow after signing."

Wish List: Published pricing or even just a starting floor. Post-sale support parity.

Value for Money: 6/10. Safe procurement checkbox for Fortune 500. Everyone else is paying enterprise tax for features they won't use.

Pricing: No public pricing. $10K/year minimum (Q2 2026). Consent & Preference Essentials ~$827/mo for 1 domain; CCPA $1,125/mo; GDPR $2,275/mo. 2 to 3 year commitments unlock discounts.

---

**17. Didomi**

The Good: 2025's European consolidator: acquired Addingwell (sGTM, April 2025) and Sourcepoint (CMP, May/July 2025), backed by an $83M Marlin Equity majority. CMP + sGTM under one roof.

Frustrations: Setup complexity is the recurring complaint: per-partner triggers in GTM, technical-level integration, multi-day implementations. Dashboard called "clunky" once you're managing many policies/vendors.

Wish List: Faster onboarding for non-AdTech buyers.

Value for Money: 7.5/10. Enterprise-grade for European publisher and AdTech-heavy sites. Setup overhead is real.

Pricing: No public pricing. Indicative range EUR 50/mo to $1,000+/mo; annual $2K to $15K depending on domains and traffic. No free plan.

---

**18. Sourcepoint (acquired by Didomi, July 2025)**

The Good: Deep publisher pedigree, started as anti-ad-blocking tech in 2015, grew to 200+ global enterprise customers. Strong TCF/GPP coverage.

Frustrations: Mid-merger uncertainty into the Didomi platform. Pricing, packaging and roadmap continuity unsettled.

Wish List: Roadmap clarity post-merge.

Value for Money: 7/10. Best-in-class for publishers, but "wait and see" is the rational stance through 2026.

Pricing: Sales-led, custom enterprise pricing only.

---

**19. TrustArc**

The Good: Comprehensive privacy suite (CMP, DSR automation, PIA/DPIA, regulatory intelligence). Long history (founded as TRUSTe in 1997), recognized seal/certification programs.

Frustrations: Average customer pays roughly $22K/year; enterprise deals reach $137K+. 8% pricing increases reported in renewal cycles. Pricing widely flagged as inflexible.

Wish List: Faster modernization on the UI side.

Value for Money: 6/10. Reliable but dated incumbent; enterprise prices for breadth, not innovation.

Pricing: Custom. Average ~$22K/yr, max ~$137K (Vendr). Privacy Rights Automation $25K to $60K/yr for 100 to 500 DSRs.

---

**20. Securiti (acquired by Veeam, December 2025)**

The Good: $1.725B Veeam acquisition gives instant access to 550K+ Veeam customers. True "Data Command Center" breadth (DSPM, privacy ops, AI governance, RoPA/DSAR, CMP).

Frustrations: Pricing fully sales-led, no public pricing. Sprawl: customers report long onboarding and module-by-module licensing.

Wish List: A self-serve tier.

Value for Money: 8/10. Enterprise data + AI governance leader. Overkill for everyone else.

Pricing: No public pricing. Custom quotes only.

---

**21. DataGrail**

The Good: Vera AI agent (March 2026) automates PIAs/DPIAs/AI risk assessments using live system metadata. First production-ready Model Context Protocol (MCP) server for privacy.

Frustrations: No public pricing. Consent module priced separately (+30 to 50% on ACV); vendor risk +20 to 40%. Modular sticker shock.

Wish List: Public pricing on at least one entry tier.

Value for Money: 7.5/10. Strongest mid-market alternative if you're escaping OneTrust pricing but still need an enterprise privacy ops platform.

Pricing: No public pricing. Mid-market deals typically mid-five-figures to low-six-figures annually. No free tier.

---

**22. BigID**

The Good: Named a Challenger in the 2026 Gartner Magic Quadrant for Data and Analytics Governance. Industry-leading data discovery + classification across cloud, hybrid, on-prem.

Frustrations: Pricing opaque and routinely flagged higher than competitors. Clunky UI, slow performance, lengthy deployments per G2/PeerSpot reviews.

Wish List: A faster deployment path.

Value for Money: 6.5/10. A contender for regulated enterprise. Massive overkill for SMB consent.

Pricing: Quote-only. Subscription based on data sources, connectors, deployment type.

---

**23. Transcend**

The Good: Over 1,300 pre-built integrations for data discovery and DSR automation. Leader in the 2025 IDC MarketScape for Worldwide Data Privacy Compliance Software.

Frustrations: Pricing starts around $10,000/year and scales fast. Custom integrations can take weeks to wire up.

Wish List: SMB tier.

Value for Money: 7.5/10. Best-of-breed for engineering-led privacy programs. Overpriced for everyone else.

Pricing: Custom only. From ~$10,000/yr (Capterra/Vendr); enterprise $25K to $100K+.

---

**24. Quantcast Choice (discontinued)**

The Good: Was one of the only genuinely free TCF v2.0-compliant CMPs. Drop-in script, low configuration overhead. Historic favorite among ad-supported publishers.

Frustrations: Discontinued in late 2025. Existing users must migrate. Limited customization compared to paid CMPs.

Wish List: Honestly, just a migration ramp; that's done now.

Value for Money: 4/10. Not viable in 2026.

Pricing: Discontinued.

---

## Tier 4: First-party trust infrastructure (the new tier)

This tier is new in 2026. Not just a CMP. The CMP plus the analytics, the CAPI mediation and the bot/fraud filter all running on one CNAME on your subdomain. The reason this tier exists is the gap most CMP comparisons don't talk about: a banner on its own does not deliver clean consent signal to your CAPI pipeline. You need the whole signal chain.

**25. DataCops**

The Good: TCF 2.2 certified first-party CMP with consent state stored on your subdomain (`datacops.yourdomain.com`), so it survives Safari ITP, uBlock, Brave Shields and Pi-hole. The CMP is part of a five-product bundle that also includes first-party CNAME analytics, server-side CAPI to Meta + Google + TikTok + LinkedIn, signup fraud detection and traffic-fraud validation. Consent signals propagate server-side into the CAPI pipeline rather than dying at the browser banner. Fraud-filtered consent (don't honor consent from bots) is a small but meaningful detail. Setup is one script tag plus one CNAME, live in 5 to 30 minutes.

Frustrations: SOC 2 Type II is in progress, not yet attested. ISO 27001 is planned. SSO and SAML are planned. Younger product than OneTrust or Cookiebot, smaller agency case-study pile.

Wish List: Ship SOC 2. More built-in A/B test surface on the banner.

Value for Money: 8.5/10. Hard to beat when the bundle math fits.

Pricing: Free (2,000 sessions/mo, free CMP, unlimited bot detection). Growth $7.99/mo (5K sessions, unlimited Meta + Google CAPI). Business $49/mo (50K sessions + HubSpot integration). Organization $299/mo (300K sessions). Enterprise on Talk-to-Sales (dedicated environment, dedicated IP reputation database, custom DPA, EU/US residency, white-label).

---

## So what should you actually use?

Want a free CMP for one site, no fuss? Try **CookieHub**, **Termly**, **CookieYes**, **Iubenda Free**, **Ketch Free** or **DataCops Free**.

Want Shopify-native consent + policy + DSAR? Try **Enzuzo**.

Want WordPress-native and you'll never leave WordPress? Try **Borlabs Cookie**.

Want the lowest-friction Consent Mode v2 wiring at SMB price? Try **Secure Privacy**, **CookieFirst**, or **DataCops Growth**.

Want A/B test on the banner and consent-rate optimization? Try **ConsentManager**, **Didomi**.

Want a contractual fines guarantee? Try **Osano** ($500K "No Fines" guarantee).

Want to escape OneTrust? Try **Ketch** (literally has a migrator), **DataGrail** or **Securiti**.

Want publisher-grade TCF v2.2 + GPP? Try **Sourcepoint** (mid-merger), **Sirdata** or **Didomi**.

Want privacy-as-code, RoPAs falling out of CI? Try **Privado**.

Want the bundle (CMP + analytics + CAPI + bot filter) on one bill, one CNAME? Try **DataCops**.

Want enterprise procurement checkbox with the deepest module catalog and don't blink at $40K to $500K/yr? Stay on **OneTrust**.

---

## The mistake I see people make

Grading a CMP on whether the banner looks pretty. The banner is the smallest part of the system. The actual job is delivering a clean, signed consent signal end to end, from the visitor's first click, into Google Consent Mode v2, into your CAPI pipeline, into your ad platforms, with an audit trail that survives a regulator request 18 months later. Most legacy CMPs solve the banner and then leave you to stitch the rest together with custom GTM tags, vendor partner slots and a prayer. The CMPs worth paying for in 2026 either ship the whole signal chain or integrate cleanly with the rest of your trust stack. The ones that don't are why everyone is migrating.

---

## Now your turn

What's your CMP today, and what's your real bill (after the August 2025 reset, after the per-domain math, after the auto-upgrade)? Drop your stack and I'll model where the bundle vs unbundle math actually lands.

---

Research by [DataCops](https://www.joindatacops.com) · First-party tracking, consent infrastructure & fraud prevention.
