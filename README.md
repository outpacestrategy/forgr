# Forgr — Project Folder

**Owner:** Drew Amunategui (Outpace Strategy Group)
**Status as of May 1, 2026:** Strategy locked. Brand name locked to **Forgr** (vowel-stripped from "forge" / "forger"). Visual direction set. Validation landing page built. Pre-deployment.
**Build status:** No application code written. Domains not yet registered. Landing page HTML built and ready to deploy.

---

## What this is

A planned B2B SaaS coaching platform for Hyrox and hybrid-athlete coaches. The thesis: FITR owns the official Hyrox coach software contract but the product is dated, has no AI, and doesn't ingest wearable data. There is room for a modern coach CMS with a hybrid programming model (run + lift + station work in one weekly view), wearable-agnostic data, AI-assisted weekly plan adjustments, and multi-coach gym workspaces. Lead with B2B (coaches pay), beta inside Nameless Run Club / Nameless Classic, expand from there.

Full market thesis lives in `competitive-analysis.md`.

---

## What's in this folder

### Strategy

| File | What's inside |
| --- | --- |
| `strategic-positioning.md` | The locked-in strategic decisions: niche, customer, wedge, market sizing. Read this first if you want the 5-minute version. |
| `competitive-analysis.md` | The deep-dive on FITR, Edge, Runna, RoxHype, Amazfit, TrueCoach, Everfit, CoachRx, TrainingPeaks. Pricing benchmarks, gaps, recommendation. |
| `next-steps.md` | The 90-day plan: validation (14 days), design partner alpha (60 days), paid beta (90 days). What to do, what not to do, what to do this week. |

### Brand

| File | What's inside |
| --- | --- |
| `branding-decisions.md` | The original naming journey — directions explored, names rejected and why (Aura, Mantra, Helium), the original four-name shortlist (Anima, Tessera, Plasma, Theta). Written before diligence. |
| `branding-diligence.md` | **The three-round diligence record.** Round 1 (original shortlist; Tessera recommended, rejected on sound). Round 2 (12 punchier candidates; Spada recommended, overridden by Drew with Endvr). Round 3 attempt 0 (Endvr killed by ENDVR Inc.'s registered Class 9 software trademark). Round 3 (12 short / vowel-stripped candidates; **Forgr cleared 5/5 and is locked**). Lessons learned for future naming work. |
| `visual-direction.md` | **The visual identity foundations.** Wordmark direction (Inter, lowercase `forgr`, weight 600, with Sodium-yellow clipped-square mark), pronunciation note, color palette (`#0B0F14` background, `#F0E54B` Sodium accent), typography pairing, tone-of-voice commandments, reference brands (Linear, Whoop, Strava, Arc, Vercel), what's explicitly NOT in v1. |

### Product

| File | What's inside |
| --- | --- |
| `product-scope.md` | **The full v1 product spec.** Two surfaces (coach web + athlete mobile), six pillar features, deep-dives on the movement library + animated demos, AI plan adjustments, the hybrid programming subsystem (lift + run + station work in one weekly view — the actual moat), wearable sync, multi-coach workspaces. Screen inventory, data model, 12-week build order, what's in v1, what's explicitly out, open decisions still needed. |

### Validation

| File | What's inside |
| --- | --- |
| `outreach-dm-script.md` | The Hyrox coach cold-outreach playbook — full Day 1 / Day 3 / Day 7 IG DM sequence, reply branches, post-call thank-you, volume guardrails, South Florida in-person variant. |
| `landing-page-spec.md` | **The validation landing page spec.** Section-by-section copy with reasoning, headline alternatives held in reserve, email capture mechanism (Formspree default), analytics setup (PostHog), accessibility commitments, pre-launch checklist (14 boxes), open decisions. |
| `landing-page.html` | **The deployable landing page itself.** Single-file, dark-mode, mobile-first, accessibility-clean. Drop on Vercel / Netlify / GitHub Pages. Replace `YOUR_FORM_ID` and `YOUR_POSTHOG_KEY`. Wordmark and brand metadata are wired to **Forgr**. |

---

## Where this is right now

### Decided
- Niche: Hyrox / hybrid athletes (run + lift in the same week)
- Customer: B2B — coaches pay, they bring athletes
- Wedge: hybrid programming model (the moat) + AI weekly plan adjustments + wearable-agnostic data + multi-coach gym workspaces
- Brand: **Forgr** (locked from `branding-diligence.md` after three rounds of diligence)
- Brand register: independent (not Nameless / not Outpace), elite & performance, hybrid-athlete framing, divine + real + modern; spelling convention follows the modern-startup vowel-strip pattern (Lyft / Tumblr / Grindr)
- Visual: dark-mode-primary, Sodium yellow `#F0E54B` accent, Inter for type, JetBrains Mono for numbers
- Pricing: $99/coach/mo flat (≤25 athletes), $179/coach/mo unlimited, 20% off annual
- v1 product scope (per `product-scope.md`)
- Landing page copy + HTML (per `landing-page-spec.md` + `landing-page.html`)

### Open / pending action
- Register **`forgr.coach`** immediately (~$45/yr at Namecheap or Porkbun — not GoDaddy). Live-URL diligence (2026-05-01 evening) revealed `forgr.com` is parked, `forgr.app` is an active Gen Z creative product, `forgr.io` is an active login-only product. `.coach` is the only open TLD and is on-message for a coaching platform.
- File USPTO trademark in Class 9 (software) and Class 41 (fitness) soon — file early because the other Forgr operators may file in their classes; we want our Class 41 fitness filing on record first.
- Reserve `@forgr.coach` on IG, X, TikTok, LinkedIn (`@forgr` likely conflicts with the existing products; align handles to domain).
- Generate `og.png` (1200×630) for social sharing.
- Wire Formspree form ID into `landing-page.html`.
- Wire PostHog project key into `landing-page.html`.
- Deploy landing page.
- **Post-validation (Day 30+):** if Day-14 gate clears, send outreach to forgr.app and forgr.io owners to explore acquisition. forgr.app is higher-priority — Lovable-built indie, likely acquirable for $5K–$25K.

### Killed (in chronological order across three rounds)
- **Aura** — six existing Aura fitness apps, dominated by Aura Health (7M users)
- **Mantra** — direct competitor at mantra.fit, mantra.care, surface association is yoga
- **Helium** — owned by Helium Network crypto company
- **Anima** — Anima Yoga + Anima Fitness app; same wellness register that killed Aura
- **Plasma** — plasma.com owned by German electronics company; @Plasma on X is 231K-follower crypto stablecoin handle
- **Theta** — theta.com owned by blockchain company; active fraud lawsuits; Theta Wellness app exists
- **Tessera** — round-1 diligence pick; rejected by Drew on sound (3 syllables, doesn't punch)
- **Vela / Cresta / Ridge / Petra / Stanza / Atra / Volta / Vena / Pyra / Pista / Forge** — round 2 alternates, all failed clearance or had real friction
- **Spada** — round-2 recommendation; overridden by Drew
- **Endvr** — Drew's pick; killed by ENDVR Inc.'s registered Class 9 software trademark (live, in commerce since 2019, 160+ retail brand customers)
- **Plyo / Krux / Strox** — round-3 hard kills (multiple fitness apps; Salesforce-owned trademark; phishing-as-a-service association)
- **Hybr / Splt / Vekt / Stridr / Glyd / Movr / Crft** — round-3 soft kills (varying degrees of fitness-app collision or trademark friction)
- **Sentr** — round-3 5/5 alternate; runner-up to Forgr

---

## Next move

Phase 0 (lock the brand) is **complete.** Phase 1 (validation) starts now.

1. **Register the domains and trademark.** `forgr.app` + `forgr.coach` immediately; pursue `forgr.com` and `forgr.io` if open. USPTO Class 9 + 41. ~$50 in domains, $350–$1,200 in trademark filings.
2. **Reserve the social handles.** `@forgr` directly should be available across IG, X, TikTok, LinkedIn (per round-3 diligence).
3. **Wire and deploy the landing page.** Formspree form ID, PostHog project key, OG image, then push to Vercel or Netlify.
4. **Run the DM playbook.** Per `outreach-dm-script.md`, 5–15 sends/day, qualified Hyrox coaches, point them at the landing page.
5. **Run the 20 coach interviews.** Per `next-steps.md`, diagnostic not pitch. Question to add: *"Walk me through how you handle a week with both a heavy lift day and a threshold run — what tools, in what order?"* (per `product-scope.md` §18).

**Day-14 gate:** 100+ email signups AND 12+ of 20 coaches independently describe the same pain. Hit both → commit to Phase 2 build per `product-scope.md`. Miss either → revisit thesis.
