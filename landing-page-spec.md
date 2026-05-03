# Landing Page Spec — Forgr Validation Page v1

**Status as of May 1, 2026:** Spec locked, copy locked, page built (`landing-page.html`). Awaiting deployment + email-capture wiring.
**Companion docs:** `next-steps.md` (Phase 1 validation goals), `visual-direction.md` (visual language), `outreach-dm-script.md` (where this URL goes when a coach replies).

This is the validation landing page. Its only job is to convert a coach who arrived from a DM, a subreddit thread, an IG post, or a Hyrox Discord into an email address. **Goal: 100 signups in 14 days.** Below that, the demand isn't there, and we know now (per `next-steps.md` Day-14 gate).

---

## 1. The brief

| Field | Value |
| --- | --- |
| **URL** | `forgr.coach` (locked) — `forgr.com` / `.app` / `.io` are all registered to other parties (see `branding-diligence.md` §"Locked: Forgr (revised)"). `.coach` is on-message for a coaching platform anyway. |
| **Goal** | Email capture from qualified Hyrox / hybrid coaches |
| **Conversion target** | 30–40% of qualified DM-driven visitors; 8–15% of cold social traffic |
| **Visitor budget** | 60–90 seconds of attention |
| **Audience** | Hyrox-affiliated gym coaches, online hybrid coaches with 10–50 athletes, mid-tier coaches duct-taping FITR + TrainingPeaks + spreadsheets |
| **Source channels** | IG DMs (per `outreach-dm-script.md`), Hyrox subreddit, Hyrox coaches Facebook group, Hyrox Discord, @drewtegui IG, Nameless Run Club channels |
| **Page type** | Single-page, single-column, dark-mode, mobile-first responsive |
| **Word count** | ~600–800 visible words. Beyond that, coaches bounce. |

---

## 2. Page structure (top to bottom)

| # | Section | Purpose | Words |
| --- | --- | --- | --- |
| 1 | **Hero** | Wordmark + headline + subhead + email form. Closes in 5 seconds or it doesn't. | ~50 |
| 2 | **The duct-tape problem** | Name the pain in language the coach already uses. Get the nod. | ~100 |
| 3 | **The product** | Four feature cards. The hybrid programming view as the lead, AI plan adjustments as the closer demo. | ~200 |
| 4 | **The hybrid wedge (deep)** | One paragraph + a numbers callout. Prove we understand what they actually program. | ~100 |
| 5 | **Pricing teaser** | $0 design partner / $99 / $179 — flat per coach, no per-athlete. | ~60 |
| 6 | **Founder note** | Drew, why this exists. Honest about pre-alpha status. | ~120 |
| 7 | **Second email capture** | After the founder note, second-chance signup. | ~20 |
| 8 | **FAQ** | Five questions. Address the predictable objections. | ~250 |
| 9 | **Footer** | Minimal. Copyright, contact, social links. | ~10 |

Above the fold (mobile + desktop): the hero only. Everything else earned by scroll.

---

## 3. Section-by-section copy

### Section 1 — Hero

**Wordmark + clipped-square mark**, top left of viewport.

**Headline** (display, 56–72px desktop, 36–44px mobile, broken to three lines via three sequential `<h1>` elements for cinematic GSAP reveal):

> The All-In-One
> Coaching Platform
> For Hybrid Athletes.

**Subhead** (body large, 18–20px, text-secondary) — replaced in current cinematic build by an in-card CTA panel ("Build it with us. Free for the first 10 design-partner coaches. $99/mo flat after. Alpha opens mid-July 2026."), with the spec-sheet subhead held in reserve as an alternate:

> Hyrox-native. Hybrid programming model. AI-assisted weekly plan adjustments. Wearable-agnostic. Modern.

**Email form**:

- Single input: `you@yourgym.com` placeholder
- Single CTA button: **Get early access**
- Below button, in caption-12 size, text-muted: *Free for the first 10 coaches. $99/mo flat after.* (or the cinematic-build variant: *No marketing email. We'll ping you when the alpha opens.*)

The email form is the only call to action above the fold. No "Learn more." No "Watch the demo." There is no demo.

**Why this hero copy:**
- "All-In-One" is a **consolidation claim**, not a generalist claim — bounded by a narrow audience (Hybrid Athletes), it reads as the answer to the FITR + TrainingPeaks + spreadsheet duct-tape pain in `competitive-analysis.md`. The phrase carries SaaS-cliché baggage in isolation, but the audience qualifier reframes it: "you don't need three tools, you need this one."
- "Hybrid Athletes" matches the locked brand register in `branding-decisions.md` (*"hybrid-athlete framing, Hyrox-relevant but not Hyrox-explicit"*) and avoids implied FITR-official affiliation that "for Hyrox" would risk.
- **Title Case + terminal period** are deliberate stylistic choices for hero/tagline-tier copy — Apple convention ("Think Different.", "iPhone. Now in five new colors."). Gives the line gravity. Captured as an exception in `visual-direction.md` § 4 type rules.
- The 3-line break is composed for visual rhythm: short / medium / long, with the audience claim landing as the resolution. In the HTML build, each line is a separate `<h1>` for the GSAP cinematic reveal — first two lines fade-and-rise together (`text-track`), the third reveals via clip-path wipe (`text-days`).
- "Get early access" beats "Sign up" / "Join the waitlist" — implies the coach is being granted something, not joining a list.
- The scarcity line is true (per `next-steps.md` Phase 2: 5 design partners free, then expand). True scarcity converts; fake scarcity poisons.

### Section 2 — The duct-tape problem

**Section label** (h3, semibold uppercase 12px, sodium):
> THE PROBLEM

**Headline** (h1, 36–44px):
> Your tools weren't built for hybrid athletes.

**Body** (body, 16–18px):
> TrainingPeaks ingests your runs but doesn't know what a sled push is. TrueCoach handles your strength blocks but breaks the moment you program a threshold session. FITR does both — badly, in two views that don't talk to each other. Coaches end up reconciling three tools into a spreadsheet on Sunday night. We're building the tool that means you don't.

**Three problem cards** in a row (collapse to stacked column on mobile):

| Card 1 | Card 2 | Card 3 |
| --- | --- | --- |
| **TrainingPeaks** | **TrueCoach** | **FITR** |
| Endurance gold standard. Cannot do sets/reps. | Lifts work fine. Pace zones don't exist. | Both, badly. Multi-coach admin is broken. |

**Why this section:**
- The first line ("your tools weren't built for hybrid athletes") gets the nod before the coach scrolls further. That nod is everything.
- Naming the three competitors is risky and worth it. Coaches respect a founder who can name the alternatives. Coaches distrust a page that pretends competitors don't exist.
- The cards are short on purpose. Each is a single, specific, true criticism. Not "TrainingPeaks is bad" — "TrainingPeaks doesn't know what a sled push is."

### Section 3 — The product

**Section label:**
> WHAT WE'RE BUILDING

**Headline:**
> One coach app. One weekly view. Built for the way you actually program.

**Four feature cards** (2×2 grid desktop, single column mobile). Each card has a short title, two-line description, and a placeholder space for an animated demo / screenshot mock.

**Card 1 — Hybrid programming, one view**
> Run, lift, and station work in a single weekly grid. Bottom bar reads endurance minutes, strength tonnage, and station volume — at the same time, for the same week. The view TrainingPeaks can't make.

**Card 2 — AI weekly plan adjustments**
> An athlete misses Tuesday's threshold. Open the app. See three suggested rebalances with reasoning. Tap to approve. The plan updates. The athlete gets pinged. You go back to coaching.

**Card 3 — Movement library, demos that don't embarrass you**
> 50+ Hyrox and hybrid movements with clean, looping animated demos. Three coaching cues per movement, overridable per athlete. No more "Google sandbag lunges, see what comes up."

**Card 4 — Wearable-agnostic**
> Garmin and Strava in v1. Apple Watch, Coros, Polar, Whoop on the roadmap. Your athletes wear what they wear. Your view stays unified.

**Why this section:**
- Cards 1 and 2 are the wedge. They lead because they are what makes coaches sit forward in a sales call.
- Card 3 (movement library / demos) is the early-coach signal we elevated to v1. Visible evidence the product looks like 2026, not 2014.
- Card 4 (wearable) closes a common objection ("does this work with my athlete's [watch]?") before it's raised.

### Section 4 — The hybrid wedge, in detail

**Section label:**
> THE WEDGE

**Headline:**
> Hybrid programming isn't endurance plus strength. It's a constraint problem.

**Body:**
> Running compromises strength adaptation. Heavy lifting compromises run quality. Station work eats both. The coach's job is to balance all of it inside a week without overtraining the athlete. Every existing tool forces a choice — and breaks at the boundary. We don't.

**Numbers callout** (mono / tabular, large, sodium accent on the numbers):
> 240 Z2 min · 32 Z3 min · 18 sets squat · 22 hinge · 14 push · 14 pull · 35 min station
>
> *— a single week, in a single readout, in a single view.*

**Why this section:**
- This is the section the page can drop and still convert at high level — but for the highest-fit coaches (the ones who are actually programming hybrid weeks), this section is what differentiates us from "another coaching app." It rewards the close-reader.
- The numbers callout is the brand's tone-of-voice in one element: numbers over adjectives, mono type, sodium accent on the data, dry caption.
- "Constraint problem" is a slightly nerdy framing on purpose. Coaches who get it self-select.

### Section 5 — Pricing teaser

**Section label:**
> PRICING

**Three-card row** (collapses on mobile):

| Free for first 10 | Coach | Gym |
| --- | --- | --- |
| **$0** | **$99/mo** | **$179/mo** |
| Six months free for design partners. Weekly call with founder. Build the product with us. | Up to 25 athletes. White-label athlete app. Wearable sync. AI adjustments. Everything in v1. | Unlimited athletes. Multi-coach workspace. Roles + permissions. Same features. Same flat price. |
| **Apply →** | **Get notified at launch →** | **Get notified at launch →** |

Below the cards (caption-12, text-muted):
> 20% off annual. No per-athlete fees. No revenue cut. Cancel anytime.

**Why this section:**
- Three tiers shown but only the first card is a live CTA — the design-partner application. The other two are "get notified." That matches reality (not shipping yet) and drives the email capture toward the highest-intent prospects.
- "No per-athlete fees. No revenue cut." is two specific shots at TrainingPeaks (per-athlete) and CoachRx (2% revenue cut). Coaches who pay those tools right now will recognize themselves.
- Pricing exposed pre-launch is unusual and brand-positive. Hides nothing. Coaches respect that.

### Section 6 — Founder note

**Section label:**
> WHO'S BUILDING THIS

**Headline:**
> Built by a coach who needed it.

**Body** (longer-form, 2 paragraphs):

> I'm Drew. I run [Outpace Strategy Group](https://outpacestrategygroup.com) and [Nameless Run Club / Nameless Classic](https://outpacestrategygroup.com). I program hybrid weeks for the athletes I coach, and I've used FITR, TrainingPeaks, and a Sunday-night spreadsheet for three years. None of it scaled past 30 athletes without something breaking. Forgr is the tool I would buy.
>
> We're pre-alpha. No code is shipping today. The first 10 design-partner coaches will help build the product with me — weekly calls, real feedback, real influence on what gets shipped. The thing I'm building, I want to use myself. If that resonates, drop your email and let's talk.

**Avatar / photo:** Optional — Drew's headshot (small, 64×64, circular, top-right of the section). If no headshot ready, skip — the brand is the system, not the body (per `visual-direction.md` §6).

**Why this section:**
- "Pre-alpha. No code shipping today." is honesty as a brand asset. Coaches who feel duped by SaaS marketing have been duped by SaaS marketing. Honesty pre-empts that.
- Linking out to Outpace and Nameless Run Club is a credibility ladder for coaches who don't know Drew. It also helps Google understand the brand's founder/entity.
- "I would buy" — first person, declarative. Matches tone-of-voice rule §5.5 in `visual-direction.md`.

### Section 7 — Second email capture

**Tile-grid background** (subtle, ~5% opacity sodium tile pattern). Centered.

**Headline:**
> If your week has both run and lift in it, this is for you.

**Email form** (same as hero):
- Input + button.
- Microcopy below: *We won't send marketing email. You'll hear from us when the alpha opens — 8–12 weeks out.*

**Why:**
- The microcopy promise ("we won't send marketing email") is a specific anti-anxiety move. Coaches drown in marketing email. Promising less of it is a feature.

### Section 8 — FAQ

**Section label:**
> FAQ

Five questions, expandable accordion. Each answer 1–3 sentences max.

**Q1 — When does it launch?**
> Alpha to 5 design partners around mid-July 2026. Paid beta around mid-August. We're prioritizing depth with a few coaches over surface area with many.

**Q2 — What does it integrate with at launch?**
> Garmin Connect and Strava for wearable data. Stripe for billing. Apple Watch (HealthKit), Coros, Polar, Whoop, and Amazfit are on the roadmap, not in v1.

**Q3 — How is this different from FITR / Edge / Runna?**
> FITR is the official Hyrox coach software but built for selling pre-made programs at scale, not for high-touch hybrid coaching. Edge and Runna are athlete apps — coaches don't pay for them, athletes do. Forgr is built for coaches who run a roster, ingest wearable data, and adjust plans week to week.

**Q4 — Who's behind this?**
> Drew Amunategui — Outpace Strategy Group and Nameless Run Club / Nameless Classic. Building solo through alpha; will hire after the Day-90 gate (3+ paying coaches, see `next-steps.md`).

**Q5 — Can my athletes use this without a coach?**
> Not in v1. Forgr is built around the coach-athlete relationship — the athlete app is the white-labeled extension of what the coach sets up. If you're an athlete looking for a self-coached app, Edge and Runna are good options.

**Why these questions:**
- Q1 buys credibility with a real date. "Coming soon" loses; "mid-July 2026" wins.
- Q2 is the most-asked question in the wearable era. Answering it preempts dropoff.
- Q3 is the name-your-competitor question. Same logic as section 2 — naming wins respect.
- Q4 is for coaches who don't know Drew yet. Recommendation by reputation.
- Q5 is the disqualification question. We say "not for individual athletes" out loud. That filters the email list to actual coaches.

### Section 9 — Footer

Minimal. Three rows.

Row 1: Forgr wordmark (reduced size). Row 2: links — `Privacy` · `Contact (info@outpacestrategygroup.com)` · `IG (@drewtegui)`. Row 3: copyright (`© 2026 Forgr. Built by Outpace Strategy Group.`).

---

## 4. Headline alternatives (held in reserve)

If 14-day signups undershoot, swap the hero headline. Alternatives, in order of preference:

| Variant | Headline | When to swap |
| --- | --- | --- |
| **A (LOCKED)** | The All-In-One Coaching Platform For Hybrid Athletes. | Locked 2026-05-01. Three-line hero composed for cinematic GSAP reveal. Title Case + terminal period chosen as deliberate Apple-style gravity. "All-In-One" reads as a consolidation claim against the duct-tape stack when bounded by the narrow audience. |
| **B (thesis-led, original)** | The coaching platform built for athletes who run AND lift in the same week. | Original locked thesis from `strategic-positioning.md`. Most precisely on-thesis but 14 words — long for a cinematic hero. Swap back to this if the AND wedge needs to be louder. |
| **C (problem-led)** | Your coaching tools weren't built for hybrid athletes. | If A under-converts and the duct-tape framing is what's resonating in DM replies. |
| **D (product-led)** | One weekly view. Run, lift, and station work — built for Hyrox coaches. | If coaches respond more to the unified-view product story. |
| **E (FITR-flank)** | The coach platform FITR should have been. | Most aggressive. Higher-risk; only if the coach DM responses are reading as anti-FITR specifically. |

Track headline performance via PostHog session count + conversion. Swap after 7 days if A is below 5% conversion on DM-driven traffic.

---

## 5. Email capture mechanism

**Default in v1: Formspree (`formspree.io`).**

Why: simplest setup, no JS dependency, no Mailchimp lock-in early, the form posts to a URL and the user gets an email digest. Free tier = 50 submissions/month, paid = $10/mo for 1,000. Sufficient for the 100-signup goal.

**Form action:** `https://formspree.io/f/YOUR_FORM_ID` — replace `YOUR_FORM_ID` with the ID after creating the form. Built into `landing-page.html` as a placeholder.

**Migration path** (when paid traction earned, post-Day-90):
- Move to ConvertKit (free up to 10K subs, broadcast emails included). Form embed plug-and-play.
- Or Mailchimp (free up to 500 subs).
- Don't migrate before there's a real reason to send broadcast emails. Formspree → ConvertKit is a 30-minute swap.

**Required fields:** email only. Name and "are you a coach?" radio button considered, deliberately cut. Friction kills.

**Anti-spam:** Formspree's built-in honeypot (`_gotcha` field, hidden from CSS). Sufficient for v1 traffic levels.

---

## 6. Analytics + telemetry

**Default: PostHog** (per `product-scope.md` §13 tech stack — same tool we'll use for the product itself).

What to track:
- Page view + source (UTM)
- Scroll depth (25%, 50%, 75%, 100%)
- Email submitted
- FAQ accordion clicks (which question — useful signal)
- CTA clicks per section

Don't overthink. The conversion event (email submitted) is the only metric the Day-14 gate cares about. Everything else is post-mortem context.

**Setup:** PostHog snippet in `<head>`. Project key `YOUR_POSTHOG_KEY` to replace post-deployment. Free tier covers this volume forever.

---

## 7. SEO + sharing metadata

The page is not optimizing for search — at 14 days of age, it won't rank for anything. But share metadata matters for IG / Discord / Slack link previews.

- **Title:** `Forgr — the coaching platform built for hybrid athletes`
- **Meta description:** `A modern coach CMS for Hyrox and hybrid coaches. AI-assisted weekly plan adjustments. Wearable-agnostic. $99/mo flat. Limited beta opening soon.`
- **OG image:** 1200×630, dark background `#0B0F14`, Forgr wordmark + clipped-square mark in sodium, headline as text below. Generated as `og.png`. (Will need to commission or design before deployment.)
- **Twitter card:** `summary_large_image`, same OG image.
- **Favicon:** clipped-square mark in sodium on `#0B0F14`, 32×32 and 16×16. (See `visual-direction.md` §7.)

---

## 8. Accessibility commitments

Don't ship a landing page that fails accessibility. The audience includes coaches in their 50s and 60s — many are over 30, per `strategic-positioning.md` market sizing.

- All text contrast ≥ AA on dark mode (`#F4F5F7` on `#0B0F14` clears 13:1; `#9AA5B1` clears 7:1).
- All accent uses (`#F0E54B`) on dark clear AAA.
- Email input has visible focus ring (`:focus-visible` outline in sodium).
- Form labels (visually hidden if necessary, `aria-label` always present).
- Tab order matches visual order.
- Tested at 200% zoom — no horizontal scroll.
- Tested with VoiceOver / NVDA — headlines + subheads + form readable in correct order.

---

## 9. Pre-launch checklist

Before the page goes live:

- [ ] `forgr.app` (or `forgr.coach`) registered + DNS pointed to host (Vercel / Netlify / GitHub Pages all fine)
- [ ] Formspree form created; form ID plugged into HTML
- [ ] PostHog project created; key plugged into HTML
- [ ] `og.png` generated and uploaded
- [ ] Favicon generated (16×16, 32×32) and uploaded
- [ ] Apple touch icon (180×180) generated and uploaded
- [ ] All five FAQ answers reviewed by Drew for tonal accuracy
- [ ] Pricing numbers double-checked against `strategic-positioning.md` ($99 / $179, 20% annual)
- [ ] Outpace + Nameless links tested
- [ ] Email submission tested end-to-end (form → Formspree → Drew's inbox)
- [ ] Mobile responsive at 360px, 414px, 768px, 1280px tested
- [ ] Lighthouse score ≥ 95 (performance, a11y, best-practices, SEO)
- [ ] Sample inbound DM written referencing the page URL

Once all 14 boxes are checked, the page goes live and the DM playbook in `outreach-dm-script.md` runs.

---

## 10. Open decisions

| # | Decision | Blocks | Owner | Due |
| --- | --- | --- | --- | --- |
| 1 | Domain choice — `.app` (preferred) vs. `.coach` | Page deployment | Drew | This week |
| 2 | Email service — Formspree (default) vs. ConvertKit (richer) vs. Mailchimp (legacy) | Email-capture wiring | Drew | Before page goes live |
| 3 | Drew headshot in founder note — include or skip | Section 6 design | Drew | Before page goes live |
| 4 | OG image — design in-house (Drew + Inter Display in Figma) vs. commission | Sharing metadata | Drew | Before page goes live |
| 5 | Pricing card structure — 3 tiers (current) vs. 2 tiers (drop the "Free for first 10" if it dilutes paid intent) | Section 5 | Drew + first 5 DM responses | Day 7 of validation |
| 6 | Headline variant to ship first — A (locked) vs. B/C/D | Hero | Drew | Default A; revisit Day 7 |
| 7 | Add a "Get the 20-coach interview script questions" lead magnet — or keep page lean | Page scope | Drew | Before page goes live |

---

## Changelog

- **2026-05-01 (initial)** — Initial spec written under the working name "Tessera." Companion HTML page (`landing-page.html`) built using this spec verbatim. Headline A locked from `strategic-positioning.md` thesis. Formspree as default email capture; PostHog as default analytics. Page is a single-column, dark-mode, mobile-first build sized to convert in 60–90 seconds of attention.
- **2026-05-01 (revised)** — Brand name changed from Tessera to **Forgr** after three rounds of diligence (see `branding-diligence.md`). Find/replace pass applied across spec and HTML. Domains updated to `forgr.app` / `forgr.coach`. Copy, structure, and all section reasoning unchanged — the brand swap doesn't affect what the page says, only what's in the wordmark.
- **2026-05-01 (evening)** — Live-URL diligence (`dig` + `curl`) revealed `forgr.com` parked, `forgr.app` and `forgr.io` both occupied by other active products using "Forgr" branding (Gen Z creative app + login-only SaaS). `.coach` is the only open TLD and the locked launch domain. Spec § 1 brief and HTML `og:url` updated to `forgr.coach`. See `branding-diligence.md` § "Locked: Forgr (revised)" for the full reassessment.
- **2026-05-01 (late)** — **New hero headline locked: "The All-In-One Coaching Platform For Hybrid Athletes."** Three-line cinematic composition (separate `<h1>` elements for sequential GSAP reveal). Old headline (*"The coaching platform built for athletes who run AND lift in the same week."*) demoted to Variant B in § 4 alternates table — held in reserve. "All-In-One" kept against initial pushback because the audience qualifier (Hybrid Athletes) reframes it as a consolidation claim against the FITR + TrainingPeaks + spreadsheet duct-tape pain rather than a generalist signal. Title Case + terminal period codified as a hero/tagline-tier exception in `visual-direction.md` § 4.
