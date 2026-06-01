# Criterion D — Testing & Upgrades

Covers Strand i (design testing methods) and Strand iii (identify
weaknesses + propose realistic upgrades). Per the brief, Strands ii
and iv of Criterion D are not graded for this summative.

---

## Strand i — Testing Method

### Method chosen: 5-person guerrilla usability test + peer feedback survey

We chose a **two-part method** because a landing page has two distinct
jobs that need two distinct kinds of evidence:

1. **Does it convert?** → 5-person guerrilla usability test
2. **Does it land?** → peer feedback survey on tone, voice, and design

### Why these methods (and not others)

| Method we considered | Why we rejected / accepted it |
|---|---|
| **Analytics (e.g. heatmaps, scroll depth)** | ❌ Rejected — requires real traffic over weeks. We don't have a launch budget or that timeline. |
| **A/B test (v1 vs v2)** | ❌ Rejected — requires statistically meaningful traffic. Not realistic for a class project. |
| **5-person guerrilla usability test** | ✅ Accepted — Jakob Nielsen's research shows 5 users catch ~85% of usability issues. We can run it in one lunch break. |
| **Peer feedback survey** | ✅ Accepted — we already have access to a peer group (classmates) and they're literally the target audience (students). |
| **Heuristic / expert review** | ✅ Accepted as a free supplement — Teacher Howard's marking notes will function as expert review. |

### Usability test protocol

For each of 5 testers, in person, on a laptop:

1. **Pre-task question** (no looking at site yet): *"If you saw this
   game called 'Student Simulator', what would you expect it to be?"*
   → Captures expectations baseline.
2. **Land them on the page** and silently watch. We time how long
   before they scroll, where their eyes go, and where they pause.
3. **Task**: *"Find out what kind of game this is and tell me whether
   you'd want to try it."*
   → Pass if they reach the conclusion within 60 seconds.
4. **Task**: *"Find the button you would press to play it."*
   → Pass if they reach `#play` within 2 attempts.
5. **Post-task interview** (5 questions):
   - What was the one line that stuck with you?
   - What confused you?
   - Did anything feel like a school project?
   - Did anything feel like a real game site?
   - Would you share this with a friend? Why / why not?

### Survey instrument (peer feedback)

Distributed via Google Form to ~10 classmates. Likert 1–5 + 2 open questions:

- The page feels **emotionally honest** about being a student (1–5)
- The page feels like a **real game launch**, not a school report (1–5)
- The page is **visually distinctive** (1–5)
- The page is **easy to scroll and read** (1–5)
- One thing you loved (open)
- One thing you'd change (open)

### How we'll record results

A separate `04-test-results.md` file will be added once testing runs.
Each tester gets a numbered row (no names, for honesty). We'll record:

- Time-to-comprehension
- Pass / fail on the two tasks
- Verbatim quotes from the interview
- Survey averages + flagged open responses

---

## Strand iii — Weaknesses & Realistic Upgrades

### Known weaknesses (identified pre-test, by self-review)

| # | Weakness | Severity | Evidence |
|---|---|---|---|
| W1 | The "PLAY DEMO" button doesn't go anywhere — `href="#"` is a dead link | **CRITICAL** | Inspect the CTA. The brief asks for a working solution. |
| W2 | The "WISHLIST" button also dead-links to `#` | **CRITICAL** | Same — `index.html` line in `#play` section. |
| W3 | Fake review ticker quotes ("i felt seen") could read as dishonest if a visitor realises no one has played it | **HIGH** | Pre-launch marketing pages usually use *quotes from testers / playtest impressions*, not fake quotes. |
| W4 | The CTA card's red box-shadow may not meet WCAG contrast under some screens | **MEDIUM** | `box-shadow: 14px 14px 0 -2px var(--ink-red)` — needs contrast check. |
| W5 | Page is a single HTML file (~1100 lines) — hard to maintain if teammates join | **MEDIUM** | Brief recommends splitting CSS files per person (`ryan.css`, `eva.css` etc.). We didn't do this. |
| W6 | No `<meta property="og:*">` social sharing tags — link previews on Discord/iMessage will be plain | **MEDIUM** | Inspect `<head>` — only basic meta exists. |
| W7 | Font loading: 5 Google Font families × multiple weights = ~300kb of font data, blocks first paint slightly | **LOW** | Network tab on first load. Targets in `~/.claude/rules/web/performance.md` say "max two font families unless there is a clear exception" — we have five, by design choice. |
| W8 | No `prefers-reduced-motion` support — the stat-bar fill animation and ticker still run for users who've asked their OS for reduced motion | **MEDIUM** | Accessibility audit. Trivial CSS fix. |
| W9 | Mobile (< 540px) hides the entire nav-links row instead of collapsing into a menu | **LOW** | Resize browser to 375px. Acceptable for v1, not ideal. |
| W10 | The "have you ever:" hook in the role section uses non-standard list formatting (`<p>→ ...</p>`) instead of a real `<ul>` | **LOW** | Hurts semantic HTML + screen reader UX. |

### Proposed upgrades for v2 (post-test)

| # | Fixes | Upgrade | Effort | Priority |
|---|---|---|---|---|
| U1 | W1, W2 | Wire `PLAY DEMO` to either a real demo build OR a "Coming soon — drop your email" mini-form. Wire `WISHLIST` to a mailto: or a Google Form for now. | 1 period | P0 |
| U2 | W3 | Replace fake quotes with real quotes from the 5 usability testers + the peer survey. Anonymise as "tester #3, age 15" etc. | 1 period | P0 |
| U3 | W8 | Add `@media (prefers-reduced-motion: reduce) { ... }` block to disable the ticker animation, stat-bar fill transition, and hover-tilt corrections. | 15 min | P0 |
| U4 | W6 | Add Open Graph + Twitter Card meta tags so the link previews well in Discord, iMessage, and X. Include a 1200×630 OG image. | 30 min | P1 |
| U5 | W9 | Replace the `display: none` mobile nav with a hamburger menu using a `<details>` element (no JS framework needed). | 30 min | P1 |
| U6 | W10 | Convert the `<p>→ ...</p>` hook items into a real `<ul>` with custom `::marker` styling. | 10 min | P1 |
| U7 | W4 | Run the live page through WAVE or axe DevTools, fix any AA contrast failures. | 30 min | P1 |
| U8 | W5 | If we keep the page single-file, add clear section comment banners. If we recruit teammates, split into `main.css` + `ryan.css` + per-person CSS as the brief recommends. | 30 min | P2 |
| U9 | W7 | Self-host the two fonts that actually do the heavy lifting (Fraunces + Press Start 2P), drop the other three to one weight each, or move them to `font-display: optional`. | 1 period | P2 |
| U10 | new | Add a "Press kit" link in the footer with logo + screenshots + one-paragraph description, so the page can be linked by school newsletters / press without us writing more copy. | 1 period | P3 |

### What we will NOT change in v2 (and why)

| Thing kept | Reason |
|---|---|
| The notebook + game HUD aesthetic | Subject-matter fit. Changing it would be cosmetic novelty for its own sake. |
| The "How are you, really?" headline | It's the highest-signal line on the page. Don't fix what's working. |
| The five-font system | The "max two fonts" performance guideline is a default rule with an explicit exception clause. This page's typography *is* a feature — that's the exception. We'll optimize the load (U9) rather than reduce the system. |
| Single-page layout (no second pages) | Adding a "Features" or "About" sub-page would re-introduce report shape. The whole site fits in one scroll, on purpose. |

---

## Summary

- **Testing method**: 5-user guerrilla usability test + 10-person peer survey,
  chosen because they catch the most issues per hour of effort at the
  scale of a class project.
- **Top 3 critical fixes for v2**: wire up the CTAs, replace fake quotes
  with real tester quotes, add `prefers-reduced-motion` support.
- **One thing we deliberately won't touch**: the visual aesthetic — it's
  the part that already works.
