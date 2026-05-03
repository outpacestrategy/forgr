# Hyrox Coaching App: Competitive Analysis

Prepared for Drew Amunategui, Outpace Strategy Group
Date: April 30, 2026

## TL;DR

The Hyrox coaching market has a clear leader on the coach side (FITR) and a clear leader on the athlete side (Edge), but neither owns the full stack and neither is purpose-built. There is a real, defensible wedge for a Hyrox-native coaching platform that combines a modern coach CMS with wearable-agnostic athlete data and AI-assisted weekly adjustments. The market is large enough to support a real business and growing fast enough that timing is on your side, but small enough that incumbents like Everfit and TrainingPeaks have not bothered to build for it specifically.

The honest read: this is a $5–15M ARR opportunity if executed well, not a venture-scale outcome. That is fine if you want a real business that funds the rest of your life.

## Market Size and Trajectory

Hyrox is not a niche anymore in absolute terms. It is niche relative to general fitness, which is exactly the sweet spot.

- 2024/25 season: roughly 650,000 to 750,000 athletes globally
- 2025 revenue for Hyrox the company: approximately $130M
- 2026 projected: 1.3M+ athletes in 85 cities across 30 countries
- Affiliated training clubs: doubled from 5,000 (end of 2024) to over 10,000 (end of 2025)
- Affiliate growth rate: 260% year-over-year
- Demographics: 38% female, 65%+ over age 30, paying customers with high spend per athlete (£50–£90 race entry plus gym, coaching, travel, gear)

The number that matters most for your business: 10,000+ affiliated gyms, each of which has multiple coaches, all of whom need a coaching tool. Even at 2 coaches per gym, that is 20,000+ Hyrox-affiliated coaches globally, growing fast. Plus independent online coaches who train Hyrox athletes without gym affiliation.

## The Competitive Landscape, By Layer

The Hyrox training stack splits into four distinct layers. Most companies only play in one. That is the opportunity.

### Layer 1: The Official Wearable (Amazfit)

Amazfit, owned by Zepp Health (NYSE: ZEPP), is the official wearable and timekeeper of Hyrox through 2028 under a recently extended three-year deal. They have a built-in Hyrox Race Mode covering all 8 stations, a Helio Ring, and integration into Hyrox 365.

What they do: sell watches and rings. Provide race-day timing and basic recovery metrics through the Zepp app.

What they do not do: coach athletes, build training plans, manage coach-athlete relationships, or compete in the SaaS layer. Their software ambitions are limited to making their hardware more compelling.

Implication for you: friend, not foe. You build a coaching platform that ingests Amazfit data alongside Garmin, Apple Watch, Coros, Polar, and Whoop. Wearable-agnostic by design.

### Layer 2: The Official Coach Software (FITR)

FITR is the official remote coaching software for Hyrox, exclusively for Hyrox-affiliated trainers and gyms. They power Mat Fraser's HWPO Training App and many of the largest CrossFit and hybrid programs.

Strengths:

- Exclusive Hyrox templates, official movement videos, pre-loaded Hyrox divisions and benchmarks
- 90-day free trial for Hyrox Performance Coaches plus 20% off for 12 months
- Stripe-integrated payments, white-label custom app option
- Strong storefront for selling programs at scale (one program to thousands of buyers)
- Decent customer support and active feature shipping

Weaknesses (these are your wedge):

- UX consistently described as "clunky" in reviews on Capterra, GetApp, and Trustpilot
- Programming is "a blank canvas" with no smart suggestions or AI assistance
- No real wearable data ingestion or auto-adaptive plans
- Multi-coach admin access is broken: coaches share logins to manage tracks, which is a security and scaling nightmare
- Cannot view two athletes' calendars side-by-side, cannot drag sessions between athletes
- Built primarily for selling pre-built programs at scale, not for high-touch 1:1 hybrid coaching with adjustments
- Pricing model recently changed to client-band tiers: roughly £25–£100/mo, no free tier above 3 clients

The big strategic gap: FITR is a content distribution and payments platform that happens to support coaching. It is not a coaching intelligence layer. They have no answer for "this athlete missed Tuesday, now what?"

### Layer 3: B2C Athlete Apps

This layer is crowded but instructive. Five real players:

**Edge (findyouredge.app)** The clear best-in-class for hybrid athletes right now. Founded in London, ~11,000–15,000 users, £19.99+/mo. Builds bespoke (not template) plans for hybrid athletes, integrates with Strava, Garmin, Apple Health, Coros, Polar, Suunto, Fitbit. Has structured workouts that push to your watch and import back. Strong content marketing (their blog ranks for nearly every "best Hyrox app" query). They have explicitly positioned as the Runna for hybrid athletes.

This is your real B2C competitor if you ever go direct-to-athlete. They have a 12–18 month head start and are clearly well-funded or at least well-run.

**Runna** Owns running. Recently added Hyrox-specific running plans with strength accessories. Their strength side is weak. They are the #1 running coaching app and have brand recognition Edge cannot match, but they are not actually built for Hyrox, they bolted it on.

**RoxHype** AI-only Hyrox app on the App Store. Generates plans based on race date, fitness level, equipment. Solo founder vibe. Direct-to-athlete. Has positive reviews but limited scale.

**RoxFit** Workout library + custom workout builder for Hyrox. Lacks coaching, lacks community, lacks plan adaptation. Useful as a workout database but not a real platform.

**RMR Training App** Coach-led app from Rich Ryan and Meg Jacoby (2024 Hyrox World Champion). $49.95/mo, includes community, programs, leaderboard. This is the model for "coach as brand" Hyrox apps. They are not selling software, they are selling Rich and Meg's programming.

**Warrior Lab** Similar model, coach-led, with a paid PRO tier. Smaller than RMR.

Pattern: every successful B2C Hyrox app is either a tech play (Edge, Runna, RoxHype) or a personality play (RMR, Warrior Lab). None of them are coach platforms in the FITR sense.

### Layer 4: General Coaching Platforms (Indirect Competitors)

These are what coaches use when FITR is not the right fit:

**TrueCoach (~$30/mo, owned by Xplor)** Older, US-focused, weaker payments outside US, simpler UX than FITR but limited Hyrox-specific features.

**Everfit (~$19–49/mo)** Modern UX, generalist, decent for 1:1 coaches but weak for endurance zones and hybrid programming. No Hyrox content.

**CoachRx ($24/mo + 2% revenue cut)** Modern coaching tool with built-in AI for programming, lifestyle tracking, billing. The 2% revenue cut adds up quickly. Aimed at general fitness, not Hyrox-specific.

**TrainingPeaks ($19.95+/mo)** Endurance gold standard. Garmin and Wahoo integration is best-in-class. Coach interface is dated. Cannot do strength programming well. Used by triathlon and run coaches but rejected by hybrid coaches because it does not understand sets/reps.

**TeamBuildr / Volt / TrainHeroic** Strength-focused, weak on running and zone-based work.

The duct-tape problem for Hyrox coaches today: they use FITR for programming and payments, but cope with its weak adaptation logic. Or they use TrainingPeaks for the running side and TrueCoach for the lifting side, then manually reconcile the two. Or they use spreadsheets. None of this is a good experience for either the coach or the athlete.

## Where the Real Gaps Are

Looking across all four layers, here are the unmet jobs-to-be-done:

1. **No wearable-agnostic coach platform exists for hybrid athletes.** FITR ingests almost no wearable data. TrainingPeaks ingests endurance data but cannot handle sets/reps. Nothing pulls Garmin + Apple Watch + Amazfit + Whoop into one coach view that respects both pace zones and load percentages.

2. **AI-assisted weekly plan adjustment is missing.** Edge has it on the athlete side. No coach platform has it. When an athlete misses Tuesday's threshold run or comes in under-recovered, the coach manually rebuilds the week. This is the #1 complaint on Capterra.

3. **Group and community programming is awkward in every tool.** Hyrox is community-driven, gyms run group classes, run clubs train together. FITR has "tracks" but no real group-class programming. Everfit cannot do it. There is a real opportunity for a "team workspace" inside the coach tool.

4. **Race-week tapering and race-day execution have no software answer.** Amazfit has the timer. Edge has the plan. Nothing connects "here is your 12-week build, here is your race-week taper, here are your splits and pacing strategy on race morning, here is your debrief and recovery plan after."

5. **Multi-coach admin and gym ownership is broken.** Hyrox affiliated gyms have head coaches, assistant coaches, owners. FITR forces them to share logins. There is no real B2B-for-gyms tier in any platform.

6. **The Hyrox 365 educational layer is not connected to the training tools.** Hyrox runs an Academy with periodisation, biomechanics, business strategy content. None of this is integrated into the actual coaching software. There is a credibility play here if you can get integrated.

## Pricing Benchmarks

What coaches actually pay today, sorted by relevance:

| Tool | Coach Cost | Notes |
| :---- | :---- | :---- |
| FITR | £25–£100/mo (5 to unlimited clients) | Hyrox affiliate discount: 20% off + 90-day trial |
| TrueCoach | $30/mo flat | Per-client athlete app |
| Everfit | $19–$49/mo | Tiered by clients |
| CoachRx | $24/mo + 2% rev cut | AI-assisted |
| TrainingPeaks Coach | $19.95–$59/mo + per-athlete | Endurance only |

What athletes pay for their own apps:

| Tool | Athlete Cost |
| :---- | :---- |
| Edge | £19.99/mo |
| Runna | £9.99/mo |
| RMR Training | $49.95/mo |
| RoxHype | ~$15/mo |

Pricing inference: there is room for a coach platform at $79–$129/mo flat with no per-athlete cost, that includes wearable sync, AI adjustments, group programming, and a white-label athlete app. That is meaningfully more than FITR's mid-tier and meaningfully less than TrainingPeaks at scale, but you justify it with "it actually does the thing you need."

## Strategic Positioning Options

There are three plays available to you. They are not mutually exclusive but you should pick one to lead with.

### Play A: Coach-First B2B SaaS, Hyrox-Native

"FITR is the official coach software. We are the better one."

Build a coach CMS that does what FITR does badly: real wearable sync, AI-assisted weekly adjustments, multi-coach gym workspaces, hybrid-specific programming model. Charge coaches $79–$129/mo flat. Distribution is direct outreach to Hyrox-affiliated gym owners and online hybrid coaches.

Pros: clear wedge against FITR's weaknesses, recurring revenue, defensible moat once gyms are on it (switching costs are high). Cons: FITR has the official partnership, you cannot use Hyrox templates, you are competing with the incumbent on their home turf.

### Play B: Athlete-First B2C, Run Club + Hybrid Community

"Edge is for individual athletes. We are for run clubs, hybrid teams, and Hyrox crews."

Build a community-first athlete app where the unit is the team or run club, not the individual. Each crew has a coach (or coaches), shared programming, leaderboards, group events. Distribution: launch with Nameless Run Club + Nameless Classic athletes, expand to other community-driven groups.

Pros: leverages your existing distribution (Nameless Run Club, Nameless Classic, @drewtegui), no one else has this exact angle, Hyrox is fundamentally a community sport. Cons: B2C is harder to monetize, you compete indirectly with Edge for individual athlete attention, and you are not the buyer.

### Play C: The Race-Day Layer Nobody Owns

"Everyone has a training app. We own race week."

Narrower but defensible: a Hyrox-specific race-day execution tool. Pacing strategy based on your actual splits, station-by-station fueling, taper plans tied to your wearable data, race-morning checklist, post-race debrief. Could be a feature of A or B, but on its own it could be a Strava-like tool that gets adopted by every Hyrox racer.

Pros: nobody owns this, the market is highly engaged, virality is built in (people share splits). Cons: smaller standalone business, easier for Amazfit or Edge to copy.

## The Recommendation

Lead with Play A but use Play B as your beta. Specifically:

1. **Build the coach CMS first**, designed for hybrid coaches, with the wearable-agnostic AI adjustment as the hero feature.
2. **Launch it inside Nameless Run Club + Nameless Classic.** You become the first coach on the platform. Your athletes are the beta. This gets you 50–100 real users without any sales motion.
3. **Recruit 5–10 Hyrox-affiliated coaches in South Florida** (Miami, Fort Lauderdale, Boca, Tampa) as your first paying coaches. South Florida has a real Hyrox scene. Offer them 6 months free in exchange for weekly feedback.
4. **Then go national with content marketing** under your existing @drewtegui and Outpace brands, using Nameless Classic as the case study.
5. **Layer in Play C (race-day tools)** as a wedge to get individual athletes onto the platform without needing a coach. They become a top-of-funnel that converts to coached athletes over time.

Pricing v1: $99/coach/mo flat for up to 25 athletes, $179 for unlimited, includes white-label athlete app and wearable sync. Annual discount of 20%.

## What You Should Not Do

- Do not try to compete with Edge on B2C athlete UX. They have an 18-month head start and a real engineering team.
- Do not try to get the official Hyrox partnership before having a working product. FITR has it, and Hyrox is not going to switch on a pitch deck.
- Do not build for everyone. The minute you say "and we also do CrossFit and triathlon and powerlifting" you become Everfit.
- Do not skip the wearable sync. It is the hardest engineering work and the highest-defensibility moat. Garmin Connect API is painful but essential.
- Do not price under FITR. Pricing under the incumbent signals you are a worse version of them. Price at or above and justify it with the AI and wearable layer.

## Next Decisions

If you want to keep going, these are the next forks:

1. **Branding:** does this live under Outpace, get its own brand, or partner with Nameless Run Club as the launch tenant? My instinct is its own brand, but Outpace as the parent agency builds it.
2. **Tech stack:** Next.js + Supabase + Stripe, with the coach CMS as a web app and the athlete app as a React Native or Expo app pulling from the same backend. Anthropic API for the AI plan-adjustment layer.
3. **First 90 days:** validation phase. Talk to 20 Hyrox coaches in the next 30 days, build wireframes for the coach CMS, then make the build/no-build call.

I would also suggest, before you write a single line of code, doing a "fake door" test: a landing page positioned as "the coaching platform built for Hyrox coaches," collect emails, see if you get 100 signups in two weeks. That is much cheaper than building.
