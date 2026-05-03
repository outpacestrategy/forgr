# Visual Direction — Forgr

**Status as of May 1, 2026:** Foundations only. Wordmark direction, color, type, reference brands, tone of voice. Enough to build the validation landing page on top of, not so much that we over-commit before validation.
**Companion docs:** `branding-decisions.md` (the why), `branding-diligence.md` (the three-round clearance), `landing-page-spec.md` (where this gets applied first).

The brand register is locked: independent (not Nameless, not Outpace), elite-and-performance, hybrid-athlete framing, modern, divine + real. The name is locked to **Forgr** — vowel-stripped from "forge" / "forger," in the modern-startup spelling style of Lyft / Tumblr / Grindr. This doc is what those locks turn into when light hits them.

---

## 1. The brand thesis in one paragraph

A forge is where raw material becomes shaped strength under pressure and heat. That is what hybrid coaching is — an athlete forged through the deliberate combination of run, lift, and station work, week after week, with the coach as the one applying the pressure. The brand should feel built, not designed. Hard-edged, not soft. Performance-coded, not lifestyle-coded. Built for athletes who want to be made into something, not athletes who want to feel-good their way through a week. The visual identity is the same coin: precision over warmth, type over imagery, dark over light, one accent color carrying all the energy.

Reference brands that share this register: **Linear** (the SaaS standard for hard-edged minimalism), **Whoop** (performance brand without the bro energy), **Strava** (athletic without being CrossFit-coded), **Arc** (modern, opinionated, dark). Notably *not* references: **Nike** (mass-market shouting), **Peloton** (lifestyle-coded), **Headspace / Calm** (the wellness register we are explicitly running from), any CrossFit affiliate brand (gritty bro-Hyrox is the wrong angle).

---

## 2. Wordmark direction

**Letterform:** lowercase `forgr`. Set in a geometric sans at heavy weight (600–700). Subtle negative letter-spacing (-1% to -2%) so the word reads as a single shape rather than five characters. No flourishes. No serifs. No italics ever.

**Why lowercase:** uppercase `FORGR` reads as institutional / aggressive. Lowercase reads as software / modern / approachable, and lets the vowel-stripped spelling do its work as a visual signature (the pattern: Tumblr / Lyft / Grindr — all lowercase). We are software. The vowel strip is the wordmark's signature, not its decoration.

**Why heavy weight:** thin wordmarks read as luxury or fashion. Heavy weight reads as performance / athletic / muscular. Aligns with the hybrid-athlete buyer.

**Pronunciation:** "FOR-jer" (like "forger" with the e dropped) — same way Tumblr → tumbler, Lyft → lift, Grindr → grinder. The reader resolves the missing vowel to the parent word automatically. In voice and social, write it phonetically as "forger" if disambiguation is needed.

**Type candidates for the wordmark** (in order of preference; all available on Google Fonts or commercial license):

| Font | Weight | Why | Cost |
| --- | --- | --- | --- |
| **Inter Display** | 600 | Free, performant, geometric, broadly modern. Default-positive. | Free (Google Fonts) |
| **Söhne** | 600 | The "Linear / Vercel / Substack" canonical modern sans. | $245+ (Klim Type Foundry) |
| **GT Walsheim** | Bold | Geometric with subtle character. Runs with luxury and athletic both. | ~$300+ (Grilli Type) |
| **PP Neue Montreal** | Bold | Sharp, modern, slightly more character than Inter. | ~$200+ (Pangram Pangram) |
| **Aeonik** | Bold | Geometric workhorse. Common in modern SaaS branding. | ~$150+ (CoType Foundry) |

**Default for v1:** Inter Display. Free, performant, no rights friction, looks the part. Trade up to Söhne or GT Walsheim post-validation when the brand budget exists.

### Logomark — optional, recommended

A small geometric mark to the left of the wordmark for places where the wordmark alone is too short to anchor (favicons, app icons, tight headers — though Forgr at 5 letters does fine on its own at most sizes). Direction:

- **Single-tile mark:** a square with one corner clipped at 45°. Reads as a forged plate / cooling steel / stamped tile. Sized at the wordmark's cap height. Only ever rendered in the accent color or pure white.
- **Anvil mark (alternate):** the silhouette of an anvil's working face — a clean trapezoid with a flat top. Closer to the brand metaphor but visually thicker and harder to scale to small sizes. Skip for v1; revisit for marketing collateral if the metaphor wants more visual reinforcement.

**v1 mark commitment:** the single-tile clipped square. It scales clean to a 16×16 favicon and a 1024×1024 app icon. Both are needed for the landing page metadata. The clipped corner is the brand's only geometric flourish — used consistently across favicon, OG image, and any future icon work.

---

## 3. Color palette

Dark-mode-primary. Single-accent. No gradients in v1 — they have to earn their way in by post-validation.

| Token | Hex | Usage |
| --- | --- | --- |
| **Background** | `#0B0F14` | The page background. Deep, cool, near-black with a hint of blue. Reads as "premium software" not "literal black". |
| **Surface** | `#131922` | Cards, modals, raised UI elements. One step lighter than background. |
| **Surface-2** | `#1A2230` | Hover states, second-level nesting. |
| **Border** | `#1F2937` | Hairline dividers. Never thicker than 1px. |
| **Text — primary** | `#F4F5F7` | Headlines, primary copy. Slight warmth so it doesn't feel sterile. |
| **Text — secondary** | `#9AA5B1` | Subhead, captions, metadata. |
| **Text — muted** | `#5C6675` | Placeholder, disabled. |
| **Accent — Sodium** | `#F0E54B` | The single energy color. Used on CTAs, the wordmark mark, key data callouts, hover states. **Used sparingly — every accent appearance carries weight.** |
| **Success** | `#5BFF8C` | Only for state confirmation (workout complete, plan synced). Never as a brand color. |
| **Danger** | `#FF3B30` | Only for warnings. Never as decoration. |

### Why Sodium yellow?

Three reasons.

1. **Not Hyrox green.** Hyrox the company uses a neon lime as its brand color (#C5FF00 / similar). Using anything close to that on the platform brand reads as "we're the official Hyrox app" — which we are not, and FITR's lawyers will care if we get traction. Sodium yellow sits next to neon green on the warm side, distinctive, no confusion.
2. **Not Strava orange, not Whoop green.** The two adjacent athletic SaaS brands have already claimed orange and electric green. Yellow is the unowned slot in performance fitness.
3. **Etymology fits the product.** Sodium is the electrolyte that makes neural firing possible — performance is neural. Marketing won't say this out loud, but the brand register stays coherent.

### Color application rules

- **Backgrounds dark, accents earned.** Sodium yellow appears on: the primary CTA button, the wordmark's optional logomark, ≤2 data callouts per screen (e.g., the "240 Z2 min" in a hero number), and `:hover` states on interactive elements. That is the entire accent surface area. Anywhere else, restraint.
- **Never gradients.** No "fitness app" gradient backgrounds. The brand is harder than that.
- **One accent at a time.** Success and Danger are state colors, never composed with the Sodium accent on the same surface.
- **White space is a color.** Use it more than feels comfortable.

### Light mode

Not in v1. Dark mode only. If a coach demands light mode in months 2–3, ship it then. Until validated, dark-mode-only is a register signal — it tells coaches "this is software, not a wellness app."

---

## 4. Typography pairing

| Role | Font | Weight | Size + leading rules |
| --- | --- | --- | --- |
| **Display** (hero headlines) | Inter Display | 600 | 56–96px, leading 1.05, tracking -2% |
| **H1 / H2** | Inter Display | 600 | 32–48px, leading 1.15, tracking -1% |
| **H3 / section labels** | Inter | 600 (semibold) | 18–22px, leading 1.3, tracking 0% |
| **Body** | Inter | 400 (regular) | 16–18px, leading 1.55, tracking 0% |
| **Body — small** | Inter | 400 | 14px, leading 1.5 |
| **Caption / metadata** | Inter | 500 (medium) | 12–13px, leading 1.4, tracking 0.5% |
| **Numerals (data readouts)** | JetBrains Mono | 500 | Tabular, monospace. Used for "240 Z2 min", "$99/mo", session counts, anywhere a number does work. |

All Google Fonts. All free. All web-performant. No font subsetting needed for the validation page.

### Type rules

- Section headers and body copy never end in a period — marketing copy isn't sentences. **Hero / tagline-tier exception:** the page-defining hero and standalone taglines may use a terminal period as a deliberate gravity choice (Apple convention: *"Think Different.", "iPhone. Now in five new colors."*). Used sparingly and only when the line carries enough weight to earn the punctuation.
- Body copy and section headers use sentence case. Title Case is reserved for proper nouns and **the hero / tagline-tier exception above** — the locked v1 hero (*"The All-In-One Coaching Platform For Hybrid Athletes."*) uses Title Case across the line as a deliberate composition choice, paired with the terminal period.
- Bold inside body copy is allowed for **one phrase per paragraph** maximum.
- All-caps reserved for tiny labels (≤12px). Never above, except for explicit brand-name treatments (e.g., the in-card `FORGR` wordmark on the hero `.brand-name` element).
- Numerals always tabular. A "240 Z2 min" never wobbles when sibling readouts change.

---

## 5. Tone of voice

Eight commandments. Memorize them, then write naturally.

1. **Numbers over adjectives.** "240 Z2 minutes" beats "serious endurance work."
2. **No exclamation marks.** Ever. The product is calm. Coaches are calm.
3. **No hyperbole.** No "revolutionary," "game-changing," "next-generation," "breakthrough." If we can't make the case in plain language, the case isn't there.
4. **No emojis in product UI or marketing copy.** Allowed in social DMs to coaches per `outreach-dm-script.md` because that's a different register; not here.
5. **Direct declaratives.** "We don't ingest video. Coaches do." beats "Our innovative approach..."
6. **Coach-talk, not marketing-talk.** A coach reading the page should think *"yes, exactly that"* — not *"this is well-marketed."*
7. **Concrete > abstract.** "Maria missed Tuesday's threshold" beats "an athlete's weekly compliance."
8. **Honest > clever.** If the v1 doesn't have something yet, say so. Coaches buy from people who know what they don't have.

### Words we do NOT use

`revolutionary`, `next-gen`, `cutting-edge`, `game-changing`, `breakthrough`, `disrupt`, `synergy`, `holistic`, `wellness`, `journey`, `transformation`, `unlock your potential`, `crush it`, `beast mode`, `dominate`, `level up` (sorry).

### Words we DO use

`hybrid`, `pace`, `tonnage`, `taper`, `rebalance`, `splits`, `zone`, `compliance`, `fatigue`, `recovery`, `block`, `template`, `roster`, `coach`, `athlete`, `weekly view`, `the mosaic` (sparingly, when the metaphor earns its place).

---

## 6. Imagery and motion

### Imagery

The hero image is the wordmark on a dark background, full stop. We do not use stock photography of athletes. We do not use generic "fitness people in a gym" shots. The athlete is implied; the brand is the system, not the body.

When we eventually need product imagery (post-validation): screenshots of the actual Plan Builder UI on a dark background, framed as a desktop browser mock. Real data, real names (anonymized), real Tuesday-missed-threshold scenarios. No staged "team meeting" photos.

### Motion

Subtle, never decorative. Two motion principles:

1. **Easing matches the brand.** All transitions use `cubic-bezier(0.16, 1, 0.3, 1)` (a sharp ease-out). Linear, ease-in, and bouncy easings are off-brand.
2. **Duration short.** 150–250ms for UI state changes; 400–600ms only for hero entrances. Anything longer feels marketing-y.

Lottie animations in the product (per `product-scope.md` §5) follow the same brand palette — the animated figure renders in `Sodium` on `Background`, single weight, no shadows. The figure is the only color carrier.

---

## 7. Wordmark — concrete specifications

For the landing page and any v1 collateral:

- **Word:** lowercase `forgr`
- **Font:** Inter Display 600
- **Letter-spacing:** -1.5%
- **Color (on dark):** `#F4F5F7` (text-primary). Mark in `#F0E54B`.
- **Color (on light, post-v1 light mode):** `#0B0F14`. Mark in `#0B0F14` or `#F0E54B`.
- **Mark:** clipped square, 0.85× cap height of the wordmark, sits 0.5× cap-height to the left of the `f`, vertically centered to the x-height (not the cap height — this matters for optical balance).
- **Clear space:** minimum padding around the wordmark is 0.75× cap height on all sides. Nothing breaches.
- **Minimum size:** wordmark + mark together never render below 96px wide on screen. If smaller is needed, mark only.

### Favicon / app icon

- **Favicon (16×16, 32×32):** the clipped-square mark in Sodium on Background. No wordmark — illegible at that size.
- **App icon (1024×1024 for app stores, all derived):** Background fill `#0B0F14`, centered clipped-square mark in Sodium at 60% of canvas. Add a 1px Border-color hairline inset 32px from each edge as a subtle frame nod. No bevels, no shadows, no glows.

---

## 8. Reference brands — moodboard

For visual review and design partner conversations:

- **Linear** ([linear.app](https://linear.app)) — the canonical modern SaaS dark mode. Type, spacing, and accent restraint we are aspiring to.
- **Whoop** ([whoop.com](https://whoop.com)) — performance brand register without bro coding. The way they treat data as the hero is exactly what we want for the Plan Builder bottom bar.
- **Strava** ([strava.com](https://strava.com)) — athletic credibility. We do not steal the orange, but the way Strava treats numbers and routes as the brand is the model.
- **Arc** ([arc.net](https://arc.net)) — opinionated modern software with personality. The way Arc trusts its own taste is the energy we should bring to copy.
- **Vercel** ([vercel.com](https://vercel.com)) — minimalism + opinionated dark mode + sharp type. Wordmark restraint.
- **Future** ([future.co](https://future.co)) — coach app premium feel. Less aspirational than Whoop, more aspirational than TrueCoach.

Notable anti-references: **MyFitnessPal** (cluttered, mass-market), **Calm / Headspace** (wellness register), **CrossFit affiliate sites** (gritty bro), **TrainingPeaks** (functional but visually 2014).

---

## 9. What's NOT in this doc

- Detailed logomark explorations (single tile is the v1 commitment; alternate explorations come post-validation if the brand earns a v2)
- Tone-of-voice case studies / extended examples (the eight commandments + word lists are enough for v1)
- Marketing collateral templates (decks, social cards, email templates) — produced as needed, not pre-built
- Brand book PDF — not until post-validation
- Light mode — explicitly out (see §3)
- Photography direction — explicitly out (see §6)
- Sound branding / haptics — out

This doc is the minimum a designer or developer needs to render the validation landing page on-brand. Every additional spec gets added when a real design problem demands it, not before.

---

## 10. Open decisions

| # | Decision | Blocks | Owner | Due |
| --- | --- | --- | --- | --- |
| 1 | Wordmark font: Inter Display (free) for v1, or commit to Söhne / GT Walsheim now? | All collateral | Drew | Before going to print on any physical asset |
| 2 | Sodium yellow exact hex — `#F0E54B` is the proposal; designer review may shift it ±5% for accessibility on `#0B0F14` | All UI + landing page | Drew + designer review | Before landing page launches |
| 3 | Single-tile mark vs. tile-grid mark for app icon | App store submission (post-v1) | Drew | Before v1 ships, not before landing page |
| 4 | Light mode if a design partner pushes for it | Coach CMS theming | Drew + design partner | After Day 60 gate |
| 5 | When (if) to license Söhne / GT Walsheim and trade up from Inter Display | Brand budget | Drew | After Day 90 gate (paid traction) |

---

## Changelog

- **2026-05-01 (initial)** — Initial visual direction, foundations only. Wordmark, color, type, tone, reference brands. Built specifically to support the validation landing page (`landing-page-spec.md`). Sodium yellow committed as the accent. Wordmark drafted around "tessera."
- **2026-05-01 (revised)** — Wordmark updated from "tessera" to "forgr" after three rounds of name diligence locked Forgr (see `branding-diligence.md`). Brand thesis paragraph rewritten around the forge metaphor (build through pressure and heat) instead of the mosaic metaphor. Pronunciation note added. Color, type, tone-of-voice, and reference-brand sections unchanged — the visual direction was deliberately built name-agnostic so the rename was a wordmark swap, not a redesign.
- **2026-05-01 (late)** — Type rules § 4 updated to add the **hero / tagline-tier exception** for terminal period and Title Case usage. Triggered by the locked v1 hero (*"The All-In-One Coaching Platform For Hybrid Athletes."*) being composed in three Title-Cased lines with a terminal period — Apple-convention gravity. The original rule (no period, sentence case) still governs section headers, body copy, and product UI; only the page-defining hero and standalone taglines earn the exception.
