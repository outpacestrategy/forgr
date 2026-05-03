# Product Scope — v1

**Owner:** Drew Amunategui (Outpace Strategy Group)
**Status as of May 1, 2026:** First-draft scope, written pre-validation. Subject to revision after the 20-coach interview phase.
**Companion docs:** `strategic-positioning.md` (the why), `competitive-analysis.md` (the market), `next-steps.md` (the timeline).

This is the long-form product spec. What we're building, what's in v1, what's out, in what order, and why.

---

## 1. One-line product description

**The coaching platform built for athletes who run AND lift in the same week** — a coach CMS with a hybrid programming model, wearable-agnostic data, AI-assisted weekly plan adjustments, multi-coach gym workspaces, and a movement library coaches actually trust.

A B2B SaaS where coaches pay $99/mo flat and athletes get a white-labeled mobile app included.

---

## 2. The two surfaces

The product is two apps sharing one backend.

| Surface | Who uses it | Where it runs | Primary jobs |
| --- | --- | --- | --- |
| **Coach CMS** | Hyrox-affiliated coaches, online hybrid coaches, gym head coaches | Web (desktop-first, tablet-tolerable) | Build plans, manage roster, react to AI suggestions, set up gym workspace, billing |
| **Athlete app** | The coach's clients | iOS + Android (React Native / Expo) | See today's session, watch demos, follow cues, log RPE/notes, track wearable sync |

The coach is the buyer. The athlete is the user the coach is trying to keep happy. Every product decision pivots on: *does this make the coach's life easier or make the athlete more likely to renew with this coach?*

---

## 3. Strategy recap (one paragraph)

FITR owns the official Hyrox coach software contract and is the incumbent. We don't take that head-on; we win on what FITR does poorly: the **hybrid programming model** (one weekly view that holds run + lift + station work with energy-system constraints across modalities — see §7), wearable-agnostic data ingestion (§8), AI-assisted weekly plan adjustments (§6), and multi-coach gym workspaces (§9). Layered on top, a movement library with clean, looping, Runna-style animated demos (§5) beats every incumbent at first impression. Pricing is $99/coach/mo flat (≤25 athletes) or $179 unlimited. Full thesis in `strategic-positioning.md`.

---

## 4. Pillar features (v1 scope)

These are the six things v1 must do well. Everything else is out.

| # | Pillar | Why it's in v1 |
| --- | --- | --- |
| 1 | **Plan Builder + Hybrid Programming model** (coach web) | Without this, there's no product. The single weekly grid that holds run + lift + station work in one view, with simultaneous endurance / strength / station volume readouts at the bottom and energy-system sequencing rules as soft warnings. This is the moat — every other tool forces coaches to pick a modality and break on the others. Deep dive in §7. |
| 2 | **Movement Library + Animated Demos** (both surfaces) | The first thing every coach AND athlete sees. If this looks worse than Runna, we lose at hello. New emphasis based on early coach signal. |
| 3 | **Athlete Roster Dashboard** (coach web) | Compliance heatmap, TSS / load trend, red flags. The coach's morning page. |
| 4 | **Wearable Sync** (background, surfaced everywhere) | Garmin + Strava only in v1. Covers ~80% of athletes. Apple HealthKit, Whoop, Coros, Polar, Amazfit are post-v1. |
| 5 | **AI Plan Adjustment** (coach web) | The closer demo. "Athlete missed Tuesday, here are 3 rebalances with reasoning, one-tap approve." This is the moment that gets a coach to switch. |
| 6 | **Athlete Today + Logging** (mobile) | Today's session with animated demos and cues, post-workout RPE + note flow, weekly view, wearable sync settings. The bare minimum to make the coach look good. |

Anything not in this list is out of v1. See section 16.

---

## 5. The Movement Library + Demos subsystem

This section is deliberately long because the early coach signal pushed it forward and because it's the most visible surface in the product.

### 5.1 What this is

A library of every movement a Hyrox / hybrid coach programs, each with:
- A clean, looping, minimalistic animated demo (Runna-style)
- Default coaching cues (1–3 short bullets)
- Variations and substitutions
- Coach-overridable cues per session
- Coach-attachable custom video (optional fallback when default doesn't fit)

### 5.2 Why it matters now

Three reasons:

1. **Initial coach signal.** A Nameless-network coach said the thing he struggles with most is "demos / explaining lifts." This is one data point — not enough to pivot the strategy, but enough to make the movement library a v1 priority instead of a v2 nice-to-have.
2. **First-impression weight.** The first thing a prospective coach does in a demo call is open a movement and see how the lift renders. If it's a YouTube embed or a stock photo, the call ends. If it's a clean looping animation with crisp cues, we look like a 2026 product. FITR looks like 2014.
3. **Athlete UX is the coach's stickiness.** When an athlete loves their workout app, the coach doesn't churn. The demos are the most touched surface in the athlete app — every workout, every movement, every rep.

### 5.3 The animation aesthetic (the "Runna look")

Reference: Runna's pre-run drill animations. Single-figure humanoid. Clean. Looping. No background clutter. Either monochrome on dark, or brand-color silhouette on neutral. 2–5 second loops. Mute by default. Autoplay on session screen.

Why this aesthetic and not real video:
- Coach-recorded videos look unprofessional unless the coach is a content creator. Most aren't.
- Real video has lighting/sound/setting variance that breaks brand consistency.
- Stock fitness video footage looks like a 2008 gym ad.
- Animations are language-agnostic, body-type-agnostic, and infinitely loopable.

What this aesthetic is NOT:
- Not 3D photoreal humans (uncanny valley, expensive)
- Not anime / illustration / cute (wrong register for elite-performance)
- Not text-only (we're better than that)

### 5.4 V1 movement coverage

~50 movements covers ~90% of what a Hyrox / hybrid coach programs. This is the v1 library.

**Lifts (25)**
- Squat patterns: back squat, front squat, goblet squat, Bulgarian split squat
- Deadlift patterns: conventional deadlift, Romanian deadlift, sumo deadlift, single-leg RDL
- Push patterns: bench press, dumbbell bench, overhead press, push press, push-up
- Pull patterns: pull-up, chin-up, bent-over row, Pendlay row, dumbbell row, lat pulldown
- Hinge & accessory: hip thrust, glute bridge, walking lunge, reverse lunge, step-up, broad jump

**Hyrox stations (10)**
- Ski erg, row erg, sled push, sled pull, sandbag lunges, sandbag carry, burpee broad jump, farmer carry, wall ball, sled drag

**Run / aerobic (6)**
- Easy run, threshold run, intervals, hill repeats, tempo, long run

**Accessory / core (10)**
- Plank, side plank, hanging leg raise, dead bug, bird dog, Copenhagen plank, bear crawl, kettlebell swing, kettlebell snatch, Russian twist

Each movement gets:
- 1 looping animation (5–10 sec)
- 3 default cues
- 0–3 variations linked
- Tags: pattern (squat/hinge/push/pull), equipment, hyrox_station (bool), category

### 5.5 Sourcing strategy for v1 animations

Realistic options for a solo founder on an 8–12 week build:

| Option | Cost | Quality | Speed | Verdict |
| --- | --- | --- | --- | --- |
| Custom 3D pipeline in-house | $$$ | High | Slow | No. Out of scope. |
| Mixamo / Adobe library + retarget | $ | Medium | Fast | Possible for stock body movements (lifts), poor coverage for Hyrox stations. |
| Lottie/After Effects animator on Upwork | $$ | High | Medium | Best v1 path. ~50 movements at $80–150 each = $4k–7.5k one-time. |
| Rotoscoped real video → outline style | $ | Medium | Medium | Backup for movements not yet animated. |
| Coach uploads custom video | $0 | Variable | N/A | Always available as override. |

**v1 plan:** Commission ~50 Lottie animations on Upwork. Allow coaches to upload custom video as override per movement per athlete. Add a "request a movement" button for coaches; we add to backlog.

### 5.6 The cues system

Every movement has three layers of cues:

1. **System defaults** — 1–3 short cues per movement, written by us and based on common Hyrox programming language (e.g. wall ball: *"chest tall", "drive through heels", "catch low"*).
2. **Coach overrides at the movement level** — a coach can replace the system defaults globally for their workspace. ("I always cue *brace before pulling* on deadlifts.")
3. **Per-session overrides** — a coach can attach 1–3 custom cues to a specific session for a specific athlete. ("Knees out, slow eccentric — you flared last week.")

Athlete sees cues in the workout view immediately above the demo. Plain text. Bullet list. Max 3.

### 5.7 Variations & substitutions

Every movement has:
- **Variations** — same pattern, different load/equipment (back squat ↔ goblet squat). Used by the AI plan adjuster when an athlete reports a missing piece of equipment.
- **Substitutions** — same training stimulus, different movement (sled push ↔ heavy walking lunges if no sled available).

These are pre-curated, not user-defined in v1. Coach can request additions; we approve.

### 5.8 Coach customization rules

- Coach can override default cues at the workspace level.
- Coach can attach custom video at the workspace level (overrides the default animation for their athletes only).
- Coach can attach per-session cues / a quick form video for a specific athlete on a specific session.
- Coach **cannot** edit the default animations themselves in v1. (Comes in v2 if demand is real.)

### 5.9 Out of v1 for this subsystem

- Athlete-uploaded form check video → coach review with markup. Real Hudl-style form check. **Out** — different product, much higher engineering cost. Revisit v2.
- AI-generated cue suggestions ("based on this athlete's last 4 weeks, suggest cues") — out.
- Movement search by EMG / muscle group — out. Coaches don't think this way.
- Multi-angle animations — out. One canonical loop is enough.

---

## 6. The AI Plan Adjustment subsystem

The closer demo. The single feature that, in a sales call, makes a coach lean forward.

### 6.1 The one-line user story

*"My athlete missed Tuesday's threshold session. I open the app and see three suggested rebalances for the rest of the week with reasoning. I tap to approve one. The plan updates. The athlete gets pinged."*

### 6.2 Trigger events (v1 scope)

The AI suggestions inbox surfaces an action when one of these fires:

| Trigger | What it means | What the AI offers |
| --- | --- | --- |
| **Missed session** | Athlete didn't log a session that was scheduled ≥24h ago | 2–3 ways to redistribute the missed work across the rest of the week |
| **Under-recovered flag** | Wearable HRV / sleep / RHR drops below athlete's rolling baseline | 2–3 ways to reduce intensity for today/tomorrow |
| **Over-performed flag** | Athlete's actual paces / loads exceed planned by >X% three sessions in a row | Suggest a small progression bump or unlock the next block earlier |
| **Race week trigger** | 14 days out from a registered Hyrox race | Auto-generate a taper proposal based on the athlete's actual training data |

Out of v1: free-form "ask the AI" coach copilot, athlete-side AI ("what should I do today?"), nutrition AI, programming-from-scratch AI.

### 6.3 The flow

1. Trigger fires (e.g., athlete missed yesterday's threshold).
2. Backend job runs: pulls last 4 weeks of plan + actuals, athlete's baseline, race date if any.
3. Calls Anthropic API with structured prompt that returns 2–3 candidate rebalances. Each candidate has: the modified week schedule, a 1–2 sentence "why this", and a confidence score.
4. Coach sees a card in the AI Suggestions Inbox: athlete name, trigger reason, three options.
5. Coach taps one. Plan updates. Athlete gets a push notification: *"Coach updated this week."*
6. Coach can dismiss with one tap. Dismissed suggestions feed the model's preference signal for that coach.

### 6.4 Reasoning surfacing

Every suggestion shows the **why**. Not "the AI says do X" — *"You scheduled a Z2 run Saturday and an interval session Wednesday. Moving the missed threshold to Friday keeps the week's Z3 minutes constant and protects Saturday's long run."* Coaches have to be able to explain it back to the athlete; the reasoning has to read like a thoughtful colleague.

### 6.5 Confidence and one-tap approve

- Each suggestion has a confidence score (low / medium / high).
- High-confidence rebalances can be one-tapped. Lower confidence forces the coach to open and review the modified week before approving.
- Coach approval → plan updates → athlete app reflects within 60 seconds.

### 6.6 What the AI does NOT do in v1

- Doesn't auto-approve anything. Coach is always in the loop.
- Doesn't write programs from scratch.
- Doesn't message the athlete directly. (Push notifications are templated, not generated.)
- Doesn't do nutrition, recovery, mindset, or any non-training advice.

---

## 7. The Hybrid Programming subsystem

The wedge that makes the product *useful*, not just better-looking. AI plan adjustments and wearable sync are how we close demo calls; the hybrid programming model is why coaches don't churn after month two.

### 7.1 What "hybrid programming" actually means

A Hyrox athlete's week has all of these in it:

- **Aerobic running** — Z2 base, threshold, intervals, hill repeats, long runs
- **Strength work** — squat / hinge / push / pull patterns at varying intensities and rep ranges
- **Hyrox-specific stations** — sled push/pull, sandbag, ski erg, row erg, wall ball, farmer carry, burpee broad jump
- **Recovery / mobility** — short, programmed, often skipped

The coach has to balance these inside one week without overtraining the athlete. The hard part is they're not additive — running compromises strength adaptation, heavy lifting compromises running quality, and station work eats both. Programming hybrid is closer to a constraint-satisfaction problem than a list-making exercise.

This is the duct-tape problem `competitive-analysis.md` calls out: TrainingPeaks does endurance and breaks on sets/reps, TrueCoach does strength and breaks on pace zones, FITR does both badly in two views that don't talk to each other. None of them think about hybrid programming as a first-class problem. We do.

### 7.2 The unified weekly view

The Plan Builder shows ONE weekly grid. Every modality lives in it. The bottom bar shows three readouts simultaneously:

- **Endurance volume:** total Z2 minutes, total Z3 minutes, total Z4+ minutes
- **Strength volume:** total tonnage, sets per pattern (squat / hinge / push / pull)
- **Station volume:** total minutes of Hyrox station work, broken out by station type

A coach sees at a glance: *"This week is 240 Z2 min · 32 Z3 min · 18 sets squat-pattern · 22 sets hinge · 14 push · 14 pull · 35 min station work."* That single readout is what FITR and TrainingPeaks can't produce. It's also the readout the AI plan adjuster uses to keep proposed rebalances within tolerance.

### 7.3 Same-session stacking

A single workout can mix modalities. The session screen handles:

- **Lift → run within one workout** ("Strength: 4×5 deadlift @ 80%, then 30 min Z2 run")
- **Run → station combos** ("Z3 5min × 4, with 2 min sled push intervals between")
- **Pure-modality sessions** ("Long run, 90 minutes Z2")

The data model supports this — a `Session` has many `SessionItems`, and items can be any movement category. The athlete app's session screen handles transitions: when a run movement is next, the screen auto-switches to a pace-zone display; when a lift is next, it switches to sets/reps/load.

### 7.4 Same-day stacking (AM / PM)

Some athletes do AM lift + PM run, or AM run + PM lift. The product treats these as two separate sessions on the same day:

- AM session (e.g., strength)
- PM session (e.g., easy run)
- Week view stacks them on the same day
- Athlete app shows AM/PM tabs on Today
- Recovery guidance: if AM was high-intensity and PM is scheduled within 6 hours, the system flags it and suggests rescheduling

### 7.5 Energy-system awareness (sequencing rules)

We don't ship a full periodization optimizer in v1. We do ship sequencing rules that surface as **soft warnings** to the coach during plan building:

| Rule | Soft warning |
| --- | --- |
| Threshold run within 24h of heavy lower-body lift (>80% 1RM) | "High-leg-stress sequence — consider 36–48h spacing" |
| Two consecutive Z4+ sessions | "Back-to-back high-intensity — common cause of stalled progression" |
| Long run scheduled day-of or day-after race-pace intervals | "Most athletes can't recover this within a week" |
| Station-heavy day directly before threshold | "Station fatigue degrades pace work — coaches usually flip these" |
| Total weekly Z3+ minutes >2× rolling 4-week average | "30%+ load increase — high injury-risk window" |

These don't block the coach. They're advisory. A coach who knows what they're doing can override every rule with one click. Coaches who don't get scaffolded.

### 7.6 Pre-built hybrid templates

Day-one templates seeded into every workspace:

| Template | Length | Sessions/wk | Audience |
| --- | --- | --- | --- |
| **Hyrox 12-week build (Doubles)** | 12 wk | 5 | Doubles entry, ≤6 hr/wk available |
| **Hyrox 12-week build (Singles)** | 12 wk | 5 | Singles entry, ≤8 hr/wk |
| **Hyrox 16-week build (Pro)** | 16 wk | 6 | Performance-tier with prior race experience |
| **Hyrox 8-week sharpening** | 8 wk | 4 | General fitness, race in 8 weeks, no time for full build |
| **Off-season hybrid base** | 8 wk | 4 | Between-races base building |
| **First-Hyrox foundation** | 12 wk | 4 | Beginner — has done a 5K but never trained for Hyrox |

Coaches start from a template and adjust. Every template is structured the same way: macro periodization → weekly blocks → sessions → movements with cues. Coaches save their own templates as well. We keep seeded ones updated as Hyrox programming evolves.

### 7.7 Substitution awareness across modalities

The AI Plan Adjustment system (§6) gets a hybrid-aware extension:

- If an athlete misses a hybrid session, the AI considers redistributing the lift portion and the run portion **separately** — they don't have to move together.
- If an athlete reports missing equipment ("no sled today"), the AI swaps to a movement with similar energy-system demands (sled push → heavy walking lunges).
- If an athlete is under-recovered, the AI can drop the run portion of a hybrid session but preserve the lift, or vice versa, based on which is the harder-to-replace stimulus that week.

### 7.8 The athlete app side of hybrid

The athlete app reflects hybrid programming in three places:

- **Today screen:** if today has both AM and PM sessions, both are visible. AM gets the primary card; PM gets a smaller second card below.
- **Session screen:** modality transitions are visible — when a run block ends and a lift block starts within a single session, the screen UI changes accordingly.
- **Week view:** modalities color-coded so the athlete sees the week's shape at a glance (orange for run, blue for lift, green for station, gray for recovery).

### 7.9 What's enforced vs. surfaced

| What | v1 behavior |
| --- | --- |
| Hard stops (e.g., "you cannot save this plan") | None. Coach always has final call. |
| Soft warnings during plan building | Yes (see §7.5) |
| AI uses hybrid context in suggestions | Yes |
| Athlete-side warnings ("this might be too much") | No. Athlete sees what coach approved. Period. |
| Auto-balancing across the week | No. Coach builds; AI suggests rebalances reactively. |

Auto-balancing the entire week from scratch is a v3 problem.

### 7.10 What's out of hybrid programming for v1

- Generative program creation ("AI, build me a 12-week hybrid plan from scratch") — out
- Athlete fitness-test calibration as a programming input (e.g., "based on this athlete's last 5K and 1RM, generate intensities") — out, would be amazing, ~1 month of work alone
- Multi-modal energy-system optimizer that assembles weeks from a bank of constraints — out, this is the real long-term moat but v3+
- Periodization mesocycle visualization — out
- Coach education content embedded in the Plan Builder ("why we recommend separating threshold from heavy lower body") — out for v1, possible v2 content layer

---

## 8. The Wearable Sync subsystem

The most defensibly hard piece of engineering. Also the largest potential moat.

### 8.1 V1 scope

Only two providers in v1:

- **Garmin Connect** (via OAuth + Health API) — covers the largest share of Hyrox athletes
- **Strava** (via OAuth) — broad coverage, lower-fidelity data, lots of coaches already use it

Combined, these cover an estimated ~80% of the athlete population. Everything else is post-v1.

Out of v1: Apple HealthKit (requires the iOS app to be more mature than v1 will be), Wahoo, Coros, Polar, Whoop, Amazfit / Zepp, Suunto, Fitbit, Oura.

### 8.2 What we ingest

Per workout:
- Type (run / ride / strength / other)
- Start time, duration, distance
- HR series (avg, max, time in zones)
- Pace series for runs
- Power for cycling/run-power if available
- Manual notes if athlete added them

Per day:
- Resting HR
- HRV (Garmin only)
- Sleep duration + stages (Garmin only, basic Strava sleep is unreliable)
- Steps / activity load if useful

### 8.3 What we display vs. what AI uses

- **Display in coach view:** weekly compliance + actuals overlay on planned, HRV / sleep / RHR trends, last 7 days of workouts as a strip
- **AI uses internally:** all of the above + rolling baselines + trend deltas to fire the under-recovered and over-performed triggers

### 8.4 Sync cadence

- Garmin: webhook-driven (push from Garmin), backfill on connect
- Strava: webhook + 4-hour fallback poll
- Both stored as normalized "Activity" records with raw payload kept for re-processing

### 8.5 What this subsystem absolutely must not do

- Don't lose data. Idempotent ingest. Replay-safe.
- Don't show stale data without flagging it. Last-sync timestamp is visible.
- Don't break the coach view if a wearable is disconnected. Athlete shows up with manual logs only; flagged "no wearable connected" once.

---

## 9. The Multi-Coach Workspace subsystem

This is the gym tier. It's also what makes the $179 unlimited price defensible.

### 9.1 Roles (v1)

| Role | Can do | Can't do |
| --- | --- | --- |
| **Owner** | Everything. Billing, invites, athlete assignment, all programming. | — |
| **Head Coach** | All programming, all athletes, invite assistants. | Billing, delete workspace. |
| **Assistant Coach** | Program for assigned athletes, view all roster, comment. | Edit other coaches' athletes' plans, billing, invites. |
| **Viewer (gym owner without coaching)** | Read-only across roster. Useful for non-coach gym owners. | Anything write. |

### 9.2 Athlete assignment model

- Every athlete has one primary coach
- Athletes can be co-coached (head + assistant)
- Athletes can be reassigned with one click; plan history transfers; athlete app reflects new coach in 24h
- Templates and program blocks created in a workspace are shared across all coaches in that workspace

### 9.3 What's out for multi-coach in v1

- Per-athlete granular permissions. Roles only.
- Internal coach-to-coach messaging. Use Slack like normal humans.
- Audit log of who edited what. Comes when a paying gym asks for it.
- Cross-workspace template marketplace. Way out of scope.

---

## 10. Athlete mobile app — full scope

The athlete app is bare-minimum-but-pristine. Anything that distracts from "see today's workout, do it, log it" is out.

### 10.1 Screen inventory

| Screen | Purpose | Key interactions |
| --- | --- | --- |
| **Auth / connect** | Sign in via invite link from coach | Email magic link or Apple/Google auth |
| **Onboarding** | Connect Garmin / Strava, set basic profile | Wearable OAuth, units, race goal entry |
| **Today** | The hero screen. Today's session, ready to do. | Tap a movement → opens session screen |
| **Session** | A workout in progress. Movements with animated demos + cues. | Auto-advance through movements, log set, mark complete |
| **Week** | This week's schedule at a glance | Tap any day to see the session |
| **Post-workout** | Capture RPE + note + manual log entries | RPE 1–10 slider, free-text note, optional manual lift loads |
| **Movement detail** | Demo + cues + recent loads/paces | Coach's per-session cues if any, attached coach video if any |
| **Race** | Countdown, race-week brief if applicable | Empty state until race date is within 14 days |
| **Profile / settings** | Manage wearable, units, coach info | Disconnect wearable, change units, contact coach |

### 10.2 The Today screen, specifically

The single most-used screen in the product. Design contract:

- Top: Date + greeting. ("Friday — threshold day.")
- Below: Today's session card. Session name, planned duration, list of movements with the animated demo as a visual hook. AM + PM tabs if same-day stacking is in effect (see §7.4).
- Below that: A small ribbon — last sync, today's HRV/sleep summary if connected, anything notable from coach (one-line note if attached).
- One CTA button at the bottom: **Start session**.
- That's it. No social feed. No leaderboard. No streaks. No badges. No nutrition. No "shop." No coach upsell. Nothing.

### 10.3 The session screen, specifically

When the athlete taps Start:

- Movement-by-movement walk-through.
- Animation auto-plays at top (looping, muted).
- Cues directly below the animation.
- Sets/reps/load fields prefilled from plan, editable.
- "Log set" advances to next set. "Skip" or "Sub" available.
- For hybrid sessions: when modality changes (run → lift, lift → run), the screen UI shifts (pace-zone display ↔ sets/reps display) — see §7.3.
- After last movement: jump to Post-workout screen.

### 10.4 What's out of athlete app v1

- In-app messaging with coach
- Social feed / friends
- Leaderboards
- Streaks / gamification
- Nutrition
- Sleep tracking UI (we ingest, we don't surface a UI for it)
- Athlete-to-athlete sharing
- Apple Watch companion app (post-v1)

---

## 11. Coach CMS — full screen inventory

Web app, desktop-first, tablet-tolerable. No mobile coach experience in v1; we make peace with the fact that coaches build plans at a desk.

| Screen | Purpose |
| --- | --- |
| **Sign in / Sign up** | Email + password or Google. Magic-link option. |
| **Onboarding wizard** | Workspace name, role (solo coach vs. gym), Stripe billing setup, invite first athlete |
| **Dashboard** | Roster compliance heatmap, AI suggestions inbox (count + glance), week-at-a-glance |
| **Athletes (index)** | Sortable list. Filters: at-risk, racing soon, new, churn risk |
| **Athlete (detail)** | Calendar view, plan, wearable trends, notes, race info, comms log |
| **Plan builder** | Drag/drop weekly view. Reusable run + lift + station blocks. Movement library accessible inline. Hybrid volume readout at bottom (see §7). |
| **Movement library** | Browse all movements. Override cues at workspace level. Attach custom video. |
| **AI suggestions inbox** | List of fired triggers. Approve / dismiss with reasoning. |
| **Templates** | Save a week or a block as a reusable template |
| **Workspace settings** | Coaches, roles, athlete assignment, branding (white-label colors / logo) |
| **Billing** | Stripe customer portal embed. Plan tier, invoices, payment method. |

### 11.1 The Plan Builder, specifically

This is the most intricate single screen. Design contract:

- **Left pane:** athlete list (current workspace), with quick-switch.
- **Center:** the weekly grid. Days as columns, sessions as cards. Drag to reorder. Drag a movement onto a session to add it. AM / PM rows when same-day stacking is in use.
- **Right pane:** the "what to add" library. Movements, blocks, templates, recently used.
- **Top bar:** week selector, athlete name, sync status, AI suggestion count.
- **Bottom bar:** weekly volume readout (Z minutes by zone, total tonnage, sets-by-pattern, station volume).
- **Soft-warning banners:** energy-system sequencing rules fire as dismissable banners when the coach saves changes that violate them (see §7.5).

The hybrid programming model means the bottom bar reads BOTH endurance metrics (zone minutes) AND strength metrics (tonnage, sets per pattern) AND Hyrox station metrics in the same view. This is the thing TrainingPeaks can't do and FITR doesn't do well. Full subsystem in §7.

### 11.2 The AI Suggestions Inbox, specifically

When a coach opens the dashboard, this is the most-actioned widget. Design contract:

- Stack-of-cards UI (like an email triage view).
- Each card: athlete name, trigger reason ("missed Tuesday threshold"), three suggestion options as small clickable chips, "why this" expandable, approve/dismiss buttons.
- Approve = plan updates + athlete pinged + card archives.
- Dismiss = card archives + signal to model's per-coach preference layer.
- After 7 days, expired triggers auto-archive with a "no action taken" log line.

---

## 12. Data model sketch

The minimum viable shape. Will evolve; the early commitments here are the ones we're least likely to undo.

### Core entities

```
Organization
  id, name, plan_tier (solo|gym|enterprise), branding_settings, created_at

Coach
  id, org_id, role (owner|head|assistant|viewer), email, name, avatar_url

Athlete
  id, org_id, primary_coach_id, name, dob, race_goals[], wearable_provider

Movement (universal library)
  id, name, category (lift|run|station|accessory),
  pattern (squat|hinge|push|pull|carry|run|station|core),
  hyrox_station (bool), default_cues[], variations[], substitutions[],
  animation_url, equipment_required[]

WorkspaceMovementOverride
  id, org_id, movement_id, custom_cues[], custom_video_url

Plan
  id, athlete_id, name, start_date, end_date, race_id (nullable)

Block
  id, plan_id, type (build|peak|race-week|recovery), week_index, week_start

Session
  id, block_id, athlete_id, day_of_week, time_of_day (am|pm|single),
  name, type (run|lift|hybrid|station|recovery),
  planned_duration, status (scheduled|completed|missed|skipped)

SessionItem
  id, session_id, movement_id, sequence_index, modality (run|lift|station),
  sets, reps, load, pace_zone, rest_sec,
  per_session_cues[], custom_video_url

Activity (wearable-ingested)
  id, athlete_id, source (garmin|strava), source_id, type, start_time,
  duration, distance, hr_series_url, raw_payload

DailyMetrics
  athlete_id, date, hrv, rhr, sleep_minutes, sleep_quality,
  baseline_hrv_30d, baseline_rhr_30d

Race
  id, athlete_id, name, date, location, division, registered (bool)

PlanSuggestion
  id, plan_id, athlete_id, trigger (missed|under_recovered|over_performed|race_week),
  candidates[] (each: modified_plan_diff, reasoning, confidence),
  status (pending|approved|dismissed|expired), fired_at, resolved_at

WeeklyVolumeRollup (computed, cached per plan-week)
  plan_id, week_start, z2_min, z3_min, z4_plus_min,
  total_tonnage, sets_by_pattern{}, station_min_by_type{}

RpeLog
  id, session_id, athlete_id, rpe, note, attachments[]
```

### Notes on the model

- `Movement` is global / shared. `WorkspaceMovementOverride` is the workspace-level customization layer.
- `SessionItem.per_session_cues` overrides everything else for this athlete on this day.
- `Session.time_of_day` lets us represent AM/PM stacking without duplicating the day-of-week logic.
- `SessionItem.modality` lets a single hybrid session contain ordered run + lift + station items, which is what powers the in-session UI transitions (§10.3).
- `WeeklyVolumeRollup` is a denormalized cache that powers the Plan Builder bottom bar (§11.1) and the AI Plan Adjuster's tolerance checks (§6) — recalculated on plan save.
- `PlanSuggestion.candidates` stores the AI's generated options as a JSON blob; we render from it. Approved candidates write a delta back to the actual `Session` records.
- `Activity` keeps raw payload so we can reprocess if we improve our metric extraction.

---

## 13. Tech stack — confirmed

Per `strategic-positioning.md`, locked direction:

| Layer | Choice | Why |
| --- | --- | --- |
| Coach web app | Next.js (App Router) on Vercel | Solo-developer-friendly, fast iteration, auth-friendly |
| Backend / DB | Supabase (Postgres + Auth + Storage + Edge Functions) | One platform, RLS for multi-tenant, real-time built-in |
| Athlete app | React Native via Expo | Same JS skillset, OTA updates, no native team needed |
| Payments | Stripe (Customer Portal, Checkout, webhooks) | Standard. White-label account upgrade later. |
| AI | Anthropic API (Claude) | Plan-adjustment reasoning, structured output |
| Wearables (v1) | Garmin Connect API + Strava API | Coverage choice — biggest two |
| Wearables (later) | Apple HealthKit, Wahoo, Coros, Polar, Amazfit, Whoop | Add by demand |
| Animations | Lottie format (commissioned) + Lottie React Native player | Vector, lightweight, looping cheap |
| Email / push | Resend (email) + Expo Push (mobile) | Standard solo stack |
| Analytics | PostHog | Product analytics, session replays, feature flags |

What we are explicitly NOT doing:
- No microservices. Monolith Next.js + Supabase until 1,000 paying coaches.
- No Kubernetes. Vercel + Supabase managed. If they go down, we go down.
- No GraphQL. REST + Supabase RLS is fine.
- No native iOS / Android beyond Expo until a real reason emerges.

---

## 14. Build order — week by week

12-week plan from the moment validation clears. This assumes Drew is the sole engineer and Phase 1 (validation) has earned the green light.

### Weeks 1–2 — Foundations
- Auth + Org + Coach + Athlete CRUD
- Workspace settings + invite flow
- Stripe Checkout + Customer Portal hookup
- Movement library schema + seeded data for ~20 most common movements (animations from a seed contract Drew kicks off in Week 1)
- Deployed to staging by end of Week 2

### Weeks 3–4 — The Plan Builder + Hybrid Programming
- Plan / Block / Session / SessionItem schema + API (with `time_of_day` and `modality` for hybrid support)
- Drag/drop weekly grid (HTML5 DnD or react-dnd)
- Movement search + insert
- Per-session cue overrides
- Save as template
- **Volume readout bar** (endurance / strength / station — §7.2)
- **Energy-system soft-warning rules engine** (§7.5)
- Seed the 6 hybrid templates (§7.6)

### Weeks 5–6 — The Athlete App (bare minimum)
- Expo project + auth flow
- Today screen + Session screen (with hybrid-modality UI transitions, §10.3)
- AM / PM tabs on Today (§7.4)
- Lottie player for animations
- Manual logging (RPE + note + load entries)
- Push notification skeleton

### Week 7 — Wearable sync (Garmin + Strava)
- OAuth flows for both
- Webhook handlers + activity ingest
- Backfill on connect
- Daily metrics rollup job

### Week 8 — Roster dashboard + compliance
- Compliance heatmap
- TSS / load trend
- Red-flag rules (3-day inactive, missed important session, RHR/HRV regression)
- Athlete detail page (calendar + actuals overlay)

### Week 9 — AI Plan Adjustment v1
- Trigger detection job (cron + event-driven)
- Anthropic API prompt + structured output (with hybrid-aware substitution logic, §7.7)
- Suggestion inbox UI
- Approve / dismiss + plan diff apply

### Week 10 — Multi-coach + race week
- Roles + permissions enforcement (RLS policies)
- Athlete reassignment flow
- Race entity + race-week trigger
- Race-week brief generation

### Week 11 — Athlete app polish + missing screens
- Week view (with modality color-coding, §7.8)
- Movement detail, Profile, Race screen
- Push notifications: plan updated, AI suggestion approved
- White-label branding pull-through (workspace colors, logo)

### Week 12 — Beta hardening
- Sentry + PostHog wiring
- Empty states everywhere
- Error boundary coverage
- Onboarding tutorial (coach + athlete)
- Billing edge cases (failed payment, downgrade)
- 5 design partners onboarded by end of Week 12

This is aggressive but solo-buildable per `strategic-positioning.md` §"Tech stack."

---

## 15. The "v1 demo loop" — what closes coaches

Every product needs to identify the 90-second demo that turns prospects into customers. For us:

1. **Open the coach app, Plan Builder.** Maria's week is up. The bottom bar reads: *240 Z2 min · 32 Z3 min · 18 sets squat-pattern · 35 min station work*. One sentence: *"This is the only place a coach can see all of that in one view."*
2. **Switch to the dashboard.** AI suggestions inbox shows three pending items.
3. **Click the top one:** *"Maria missed Tuesday's threshold."* Three rebalances appear. Reasoning underneath each.
4. **Click "Approve" on the middle one.** Plan updates. Toast: *"Maria notified."*
5. **Switch to the athlete app on the demo phone.** Maria's Today screen has updated. Open her session. The threshold work shows up Friday with a clean Lottie animation of the run zone.
6. **Pinch the demo's screen and zoom on the cues** ("controlled effort, conversational pace"). Done.

That's the demo. It's the **hybrid weekly view** + the AI moment + the wearable connection + the clean animated demo, all in one beat. Every piece of v1 is in service of that single 90-second story.

If we can't ship that demo, we don't ship v1.

---

## 16. What's explicitly OUT of v1

Listed because the value of a scope doc is in what it cuts.

- Nutrition tracking
- In-app messaging coach ↔ athlete (Slack/iMessage exists)
- Athlete form-check video upload + coach markup
- Custom-built movements (coach defines a movement from scratch)
- Coach-recorded custom demos as the default (custom video as fallback only)
- Social feed
- Streaks / badges / gamification
- Leaderboards
- Race calendar / race discovery
- Programs marketplace (coach sells a program to non-clients)
- Apple Watch companion app
- Apple HealthKit / Whoop / Coros / Polar / Amazfit / Wahoo / Suunto / Fitbit / Oura
- Web athlete app (mobile only)
- Mobile coach app (web only)
- Coach-to-coach messaging
- Cross-workspace template marketplace
- AI program-from-scratch generation
- AI nutrition / mindset / recovery advice
- Free-form coach copilot ("ask the AI anything")
- Group / class programming (one coach, many athletes simultaneously) — comes when a real Hyrox gym asks for it
- Hyrox academy content integration (no partnership yet)
- Public website / marketing site beyond the validation landing page
- Multi-modal energy-system optimizer (auto-balance the week from scratch — see §7.10, this is v3+)

Anything on this list that a design partner asks for repeatedly during weeks 1–8 gets revisited. Nothing on this list ships before Week 12 by default.

---

## 17. Open decisions to resolve before code

These are the calls that haven't been made yet. They block specific build steps.

| # | Decision | Blocks | Owner | Due |
| --- | --- | --- | --- | --- |
| 1 | ~~Final brand name~~ — **RESOLVED 2026-05-01: Forgr** (after three rounds of diligence — see `branding-diligence.md`) | — | — | Done |
| 2 | Domain + trademark clearance on chosen name | Public landing page, app store listings | Drew | Within 1 week of name choice |
| 3 | Animation contractor selection + scope | Movement library v1 | Drew | Before Week 1 of build |
| 4 | Garmin Connect partner application | Wearable sync (Garmin requires partner approval) | Drew | Before Week 7 of build (60-day approval window assumed) |
| 5 | Stripe MCC / business entity | Billing | Drew | Before Week 1 of build |
| 6 | White-label branding scope (athlete app — coach's logo + colors only, or full domain re-skin?) | Workspace settings UI | Drew | Before Week 11 |
| 7 | Pricing tiers final (current: $99 ≤25 athletes, $179 unlimited — does an "intro" $49 tier for ≤5 athletes belong?) | Pricing page, Stripe products | Drew | Before validation landing page goes live |
| 8 | First gym design partner (vs. all-solo design partners) | Multi-coach feature priority | Drew | During Phase 1 validation |
| 9 | Hybrid template authorship — Drew writes the 6 seed templates himself, or commission an outside Hyrox programming consultant? | Weeks 3–4 build (templates ship with the Plan Builder) | Drew | Before Week 3 of build |
| 10 | Energy-system rule library — ship the 5 rules in §7.5 as v1, or extend to ~10 with more nuanced thresholds? | Week 4 build | Drew | Before Week 4 of build |

---

## 18. Decision gates that gate this scope

This scope assumes Phase 1 validation clears. From `next-steps.md`:

- **Day 14 gate:** 100+ email signups AND 12+ of 20 coaches independently describe the same pain. If hit → build per this doc. If not → revisit thesis.
- **Day 60 gate:** 5 design partners actively using product weekly. If not → revisit feature set, not the strategy.
- **Day 90 gate:** 3+ paying coaches, NPS > 40, organic referral starting. If not → fix the wedge before scaling.

If the coach signal that pushed demos / lifts forward replicates in 12+ of 20 interview calls → Movement Library subsystem stays as scoped. If it doesn't → we still build it (it's table stakes), but we don't lead any marketing with it.

If 12+ of 20 coaches independently describe the duct-tape problem (using FITR + TrainingPeaks + spreadsheets to cope with hybrid programming) → the Hybrid Programming subsystem (§7) becomes the marketing lead, not the AI moment. The validation interview script should probe this directly: *"Walk me through how you handle a week that has both a heavy lift day and a threshold run — what tools do you use, in what order?"*

---

## 19. Changelog

- **2026-05-01** — Initial draft. Movement library promoted from v2 to v1 priority after a Nameless-network coach surfaced "demos / explaining lifts" as a primary pain. Hybrid Programming subsystem (§7) added as a dedicated deep-dive after Drew flagged that combined lift + run programming is the most-undersold value-add — Hyrox athletes literally have to train both, and every existing tool forces coaches to pick a modality. Plan Builder pillar (§4 #1) sharpened. Demo loop (§15) updated with an opening Plan Builder beat that leads with the hybrid volume readout. Data model gained `Session.time_of_day`, `SessionItem.modality`, and `WeeklyVolumeRollup`. Two new open decisions logged (§17 #9, #10) on hybrid template authorship and energy-system rule library scope. No changes to strategic positioning, pricing, wearable scope, or build-order weeks. No code yet.
