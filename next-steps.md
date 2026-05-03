# Next Steps — 90-Day Plan

Three phases. You don't move to the next one until the previous one earns it.

---

## Phase 0: Lock the brand (this week)

Before anything else.

- Pick the name from the current shortlist (Anima, Tessera, Plasma, Theta — see `branding-decisions.md`)
- Run domain and trademark diligence on the chosen name
- Buy the .com if available; .app or .coach as fallback
- Reserve handles on Instagram, X, TikTok
- Sketch a wordmark direction (clean sans-serif, performance-coded, not soft)

**Time required:** 2–4 hours of decision-making, 1 day of admin.

---

## Phase 1: Validate demand (next 14 days, no code)

Two workstreams in parallel.

### Workstream 1: Fake-door landing page

- Single page positioned at Hyrox coaches: "The coaching platform built for hybrid athletes."
- Email capture with three mocked-up coach CMS screenshots
- Pricing teaser: $99/coach/mo, free for first 10 design partners
- Distribution channels:
  - Hyrox subreddit
  - Hyrox coaches Facebook group
  - Hyrox Discord servers
  - @drewtegui Instagram
  - Nameless Run Club channels
  - Targeted DMs to 30–50 Hyrox coaches on Instagram

**Goal:** 100 email signups in 14 days. If you can't hit that, the demand isn't there and you should know now before writing a line of code.

### Workstream 2: 20 coach interviews, 30 minutes each

**Outreach playbook is locked in `outreach-dm-script.md`** — Day 1 / Day 3 / Day 7 cadence, reply branches for every realistic response, post-call thank-you, volume guardrails (15 DMs/day max), and a South Florida in-person variant. Use it as-is for cold IG outreach.

Recruit from the email list plus your existing network. **The interview is diagnostic, not a pitch.** You're testing the assumptions in the competitive analysis: do they actually use FITR? What do they hate about it? What do they duct-tape together? What would make them switch? What would they pay?

Interview script structure:
1. Walk me through your week — what tools do you open, in what order?
2. Tell me about a moment in the last month when your tool failed you.
3. If you could wave a wand and fix one thing about your coaching workflow, what would it be?
4. How do you handle a missed session right now? Walk me through the actual steps.
5. What would have to be true for you to switch tools?
6. What's a fair price for [described product]?
7. Who else should I talk to?

**Goal:** If 12+ of 20 coaches independently describe the same pain, you have a real wedge. Commit to Phase 2. If the answers are scattered, pivot or kill.

---

## Phase 2: Design partner closed alpha (days 15–60)

If validation hits, pick 5 coaches from those 20 to be design partners. Free for 6 months in exchange for weekly 30-minute calls. Build with them in the room.

### Build order — ruthless

1. **Coach CMS first** — plan builder with reusable run + lift + station blocks
2. **Athlete roster dashboard** — compliance, TSS trend, red flags, at-a-glance health
3. **Garmin + Strava sync** — covers ~80% of athletes; Apple Watch via HealthKit later
4. **AI plan adjustment engine** — one moment, well-executed: "athlete missed Tuesday, here are 3 rebalances with reasoning, one-tap approve"
5. **Bare-minimum athlete app** — today's workout with zones, post-workout RPE + note, weekly view

### Skip in v1

Nutrition tracking. In-app video coaching. Payments to athletes. Social feed. Race calendar. All scope creep.

### Tech stack

- Next.js + Supabase + Stripe (web coach CMS)
- React Native / Expo (athlete app, same backend)
- Anthropic API (AI plan-adjustment reasoning)
- Garmin Connect API + Wahoo API + Apple HealthKit + Strava API
- Mux or Cloudflare Stream (only if video added later)

Solo-buildable to a real beta in 8–12 weeks once Phase 1 clears.

---

## Phase 3: Paid beta and positioning (days 60–90)

Convert design partners to paying. Use their results as case studies.

- Convert 5 design partners → 3–5 paying coaches at $99/mo
- Hyrox-coach-specific content under @drewtegui and Outpace channels (you have the audience advantage no other founder has)
- Approach 2–3 mid-tier Hyrox-affiliated gyms about multi-coach pricing
- Don't chase the official Hyrox partnership yet — earn it with traction. FITR will lose it if a better product exists, but only if a better product exists first.

---

## What NOT to do

- **Don't write code in the first 14 days.** If you build before validating, you'll fall in love with what you built and ignore the signal.
- **Don't try to compete with Edge on B2C.** They're 18 months ahead and well-funded. We're B2B.
- **Don't price below FITR.** Race to the bottom. We price at or above and justify with AI + wearable layer.
- **Don't build wearable hardware.** Software only. Stay agnostic.
- **Don't expand into triathlon or general endurance** until you own Hyrox coaching. The minute you say "we also do X," you become Everfit.
- **Don't chase the official Hyrox partnership early.** Traction first, partnership second.
- **Don't skip the AI moment.** "Athlete missed Tuesday, here are 3 rebalances" is the demo that closes coaches. It's the wedge against FITR. Don't ship without it.

---

## What to do this week

1. Lock the brand name (decision in `branding-decisions.md`)
2. Buy the domain and reserve social handles
3. Draft the validation landing page copy and wireframe
4. Build a target list of 30–50 Hyrox coaches to DM (using the qualification rules in `outreach-dm-script.md`)
5. Set up Calendly + $25 gift card delivery system before sending Day 1 DMs

DM script is already done — the playbook in `outreach-dm-script.md` is ready to run the moment the target list is built. Once the landing page is live and the target list is qualified, the next 30 days are about volume: push the page everywhere, run the DM sequence at 5–15 sends/day, book the calls.

---

## Decision gates

| Gate | Trigger to proceed | Trigger to pivot/kill |
| --- | --- | --- |
| End of Phase 1 (day 14) | 100+ email signups AND 12+ of 20 coaches describe same pain | Below either threshold |
| End of Phase 2 (day 60) | 5 design partners actively using product weekly | Less than 3 active weekly users |
| End of Phase 3 (day 90) | 3+ paying coaches, NPS > 40, organic referral starting | Less than 3 paying or no organic pull |

If you hit a kill gate, the lesson is in the data — what was wrong about the thesis, the wedge, the customer, or the product. Don't keep building through a no-signal phase.
