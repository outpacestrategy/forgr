# Strategic Positioning

The locked-in strategic decisions. Everything in this doc has been thought through and committed to. Reopening any of these is a bigger move than tweaking branding or features.

---

## The opportunity in one sentence

Build the modern coach CMS for Hyrox and hybrid-athlete coaches — wearable-agnostic, AI-assisted, multi-coach gym workspaces — and beat FITR by being the platform that actually does the thing FITR's users complain about not being able to do.

---

## Who we're building for

**Primary customer:** B2B — coaches pay for the software, athletes get a white-labeled app.
- Hyrox-affiliated gym head coaches and assistant coaches
- Independent online hybrid coaches with 10–50 athletes
- Mid-tier coaches who currently duct-tape FITR + TrainingPeaks + spreadsheets together

**Buyer profile:**
- Pays $25–$100/mo today on FITR or similar
- 10–50 active athletes
- Programs run + lift in the same week
- Tech-savvy enough to switch tools if the new one is meaningfully better
- Frustrated with FITR's UX, lack of AI, broken multi-coach admin, no wearable sync

**Not the customer:**
- General fitness coaches with no endurance component
- Triathlon coaches (different product — TrainingPeaks owns this)
- Pure CrossFit affiliates (different programming model)
- Individual athletes (B2C is a different motion; we'd lose to Edge)

---

## Market sizing

Real numbers, current as of April 2026:

- **2024/25 season:** ~650,000–750,000 Hyrox athletes globally
- **2025 Hyrox revenue:** ~$130M
- **2026 projection:** 1.3M+ athletes, 85 cities, 30 countries
- **Affiliated training clubs:** 10,000+ (doubled YoY from 5,000 end of 2024)
- **Demographics:** 38% female, 65%+ over age 30, high spend per athlete ($50–$90 race entry plus gym, coaching, travel, gear)

**The number that matters:** 10,000+ affiliated gyms × ~2 coaches each = 20,000+ Hyrox-affiliated coaches globally, before counting independent online coaches without gym affiliation. Total addressable coach population: 25,000–40,000 globally.

**ARR ceiling math:** 5,000 paying coaches × $99/mo × 12 = $5.94M ARR. 10,000 paying coaches × $129/mo × 12 = $15.48M ARR. This is a $5–15M ARR business if executed well. Not venture-scale. Real-business-scale.

---

## The wedge

FITR owns the official Hyrox coach software contract. We don't take that head-on. We win on the things FITR does poorly:

1. **Wearable-agnostic data ingestion** — Garmin, Apple Watch, Amazfit, Coros, Polar, Whoop, all in one coach view. FITR ingests almost nothing.
2. **AI-assisted weekly plan adjustments** — When an athlete misses Tuesday's threshold session, the coach opens the app and sees three suggested rebalances for the rest of the week with reasoning. One-tap approve. This is the demo that closes coaches.
3. **Hybrid programming model** — Run + lift + carry + station work in one weekly view. No tool does this well.
4. **Multi-coach gym workspaces** — Real B2B-for-gyms tier. Head coach, assistant coaches, owners. Roles, permissions, shared programming. FITR makes coaches share logins.
5. **Race-week and race-day execution** — Pacing strategy from actual splits, station-by-station fueling, taper plans tied to wearable data, post-race debrief. Standalone wedge that pulls in athletes.

**One-line positioning:** "The coaching platform built for athletes who run AND lift in the same week."

---

## Why this opportunity is real (validation signals)

- Amazfit signed a three-year exclusive wearable partnership with Hyrox in April 2026, including hardware + app integrations. NYSE-listed company committing this hard = the audience is large and underserved enough to justify investment.
- Hyrox affiliated gym count doubled in one year (5K → 10K).
- Athlete count nearly doubled (650K → projected 1.3M).
- FITR's pricing model just changed to client-band tiers — a sign they're optimizing for revenue, not user love.
- Edge raised real money to be "the Runna for hybrid athletes" — proves the category supports venture investment on the athlete side.
- Coaches in Capterra/GetApp/Trustpilot reviews of FITR independently describe the same pain points (clunky UX, no AI, no wearable sync, broken multi-coach admin).

---

## What we're explicitly NOT doing

- Not competing with Edge on B2C athlete UX (they have 18 months and real engineering)
- Not chasing the official Hyrox partnership before having product (FITR has it; Hyrox won't switch on a deck)
- Not building for everyone (the minute we say "we also do CrossFit and triathlon and powerlifting," we become Everfit)
- Not skipping wearable sync (it's the hardest engineering work and the highest-defensibility moat)
- Not pricing under FITR (signals we're a worse version; we price at or above and justify it with AI + wearable layer)

---

## Pricing thesis

**v1 launch pricing (when ready):**
- $99/coach/mo flat for up to 25 athletes
- $179/coach/mo flat for unlimited athletes
- 20% annual discount
- White-label athlete app included
- Wearable sync included
- AI plan adjustments included

**Why this works:**
- Below TrainingPeaks at scale (their per-athlete fees add up)
- Above FITR's mid-tier (signals premium, not budget)
- No revenue cut (CoachRx takes 2%; we don't)
- Flat per-coach (predictable for buyers)

---

## Build order (when validation says go)

1. **Coach CMS** — plan builder with reusable run + lift + station blocks
2. **Athlete roster dashboard** — compliance, TSS trend, red flags, at-a-glance health
3. **Garmin + Strava sync** — covers ~80% of athletes; Apple Watch via HealthKit later
4. **AI plan adjustment engine** — one moment, well-executed: "athlete missed Tuesday, here are 3 rebalances"
5. **Bare-minimum athlete app** — today's workout with zones, post-workout RPE + note, weekly view

**Skip in v1:** nutrition tracking, in-app video coaching, social feed, race calendar, payments to athletes. All scope creep.

---

## Tech stack (committed direction)

- Next.js + Supabase + Stripe (web coach CMS)
- React Native / Expo (athlete app, same backend)
- Anthropic API (AI plan-adjustment reasoning)
- Garmin Connect API + Wahoo API + Apple HealthKit + Strava API (wearable ingestion)
- Mux or Cloudflare Stream (only if video added later)

Solo-buildable to a real beta in 8–12 weeks once the validation phase clears.
