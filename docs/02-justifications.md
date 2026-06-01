# Strand iv — Justification of Changes to the AI Output

> **Brief requirement (extended explanation):**
> *"I am expecting you guys to use AI generated site, but ... I am also
> expecting you guys to not only take what the AI gives you as a whole, but
> rather inclined to adjust what the AI would give you. This change should
> then be recorded to your written document to explain why your team decides
> such changes."*

This document records every meaningful change made to the AI's output,
the **reason** for each change, and the **commit hash** that proves the
change happened.

---

## TL;DR

The AI's first draft (`b51ef39`) was a **visually polished landing page
that read like a school report**. It described the game design document
instead of selling the game. We rejected v1 wholesale, kept the visual
shell (notebook + game HUD aesthetic), and rewrote almost every line of
copy. Twelve separate, named commits prove this.

---

## The Change Log

| # | Commit | What the AI gave us (v1) | What we changed it to (v2) | Why |
|---|---|---|---|---|
| 1 | `fb6ac75` | Title: "A Game About Being Seen" + description summarising the game design brief | Title: "How are you, really?" + benefit-focused description ("100 energy. 7 periods. 4 stats you can't all keep alive.") | A landing page title is the first thing a user sees in a search result or a tab. v1 sounded like an essay title. v2 hooks the visitor with the universal student lie. |
| 2 | `b66f079` | Nav: "The Role / Research / Game Analysis / Daily Loop" + decorative "due April 2, 2026" deadline | Nav: "The Hook / Mechanics / Vibes / A Tuesday / Play" + a real CTA ("▶ play the demo") | Report chapter names tell a visitor "this is an assignment." Marketing section names tell a visitor "this is a product I can explore and try." The nav-right slot is prime CTA real estate — wasted on a date. |
| 3 | `359a71b` | Headline: "A game about being seen (not just graded)" — abstract, third-person, thesis-shaped | Headline: "How are you, fine really?" with a strike-through on "fine" — second-person, emotionally specific | The original was a *statement about the game*. The rewrite is a *question to the visitor*. Hooks beat theses on landing pages. The strikethrough on "fine" carries the joke without explaining it. |
| 4 | `05d3d5c` | Sticky note: "this is YOU after period 4" | Sticky note: "this is you after period 4" | A small but meaningful tonal fix. All-caps "YOU" shouts. Lowercase matches the handwritten notebook aesthetic and the quiet, internal voice the rest of the page now uses. |
| 5 | `38b97c0` | Ticker scrolling at bottom of hero: to-do list ("finish the lab report", "say hi to the new kid") | Ticker: fake review quotes ("i felt seen", "the saddest stardew valley", "i replayed Tuesday three times") | To-dos describe the game *world*. Pull-quotes provide *social proof* — the marketing signal that says "real people played this and it landed." Same pixel real estate, far more persuasive use. |
| 6 | `db3560a` | A whole section titled "The Role" explaining *what 'student' means in our game* — third-person, definitional | A section titled "The Hook" with a second-person "have you ever:" checklist (stayed up finishing a thing you didn't care about, said 'i'm fine' three times before lunch) | The AI section *justified* the design choice to a grader. The rewrite *makes the visitor feel implicated*. The pull-quote also flipped from "players have to work toward personal goals" to "you already know the controls. we just gave them buttons." — same idea, infinitely more shareable. |
| 7 | `2560bc4` | Student ID card rows: Class / Resources / Energy / Save points | ID card rows: Difficulty: real life / Lives: 1 / Quit button: not included | The original metadata read like a character sheet from a tutorial. The rewrite reframes the same fields as *game language with a wink* — every row is a small joke that lands because students have felt it. "Quit button: not included" is the line. |
| 8 | `2dc9742` | "Research Plan" section ranking four research priorities (Time Management → Daily Routines → Pressure → Decision Making), described academically | "Four Mechanics That'll Hit Different" reframed as features: "Time is a currency", "Your week is the map", "Pressure is a meter", "Choices stick" | Research priorities answer the question *what did we study?* Features answer the question *why should I play?* Same four ideas, different question being answered. The AI was answering the rubric. We answered the audience. |
| 9 | `ff93463` | "Game Analysis" section with Minecraft vs. Sakura School Simulator as academic comparison ("compare · contrast · combine"), plus a "vs" divider | "For Fans Of" section with the same two games but reframed as *vibes you've already felt* — and a "+" divider because it's a fusion, not a competition. Plus a one-line pitch: "Stardew Valley if the farm was you, and the crop was your GPA." | Comparison sections describe two things to a third party. "For Fans Of" sections grab a visitor who already loves something *they've already chosen to love*, and tell them "this is more of that." The "+" instead of "vs" was a micro-change that fixed a macro-misunderstanding of what the section is for. |
| 10 | `5b3e60c` | Section head: "One Tuesday." with a long subhead about save screens | Section head: "Five choices. One you." with a tighter subhead ending "the only path that doesn't hurt is the one nobody plays." | Three-word subheads land harder than ten-word ones. The closing line earns the section by promising something honest. |
| 11 | `dae2938` | Closing section titled "Intended Impact" — a thesis statement explaining what the game argues, followed by a designer signoff | Closing section is a full conversion CTA: PLAY DEMO + WISHLIST buttons, a metadata strip (solo dev / 25 min / browser / controller), and a 4-question founder-voice FAQ ("Is it sad?" "Is there a 'win'?") | This was the biggest change. The original ended the page like a report — with a thesis and a signature. A real landing page ends with the **ask** — the action you want the visitor to take. Without this section, the page would read like a beautiful artifact with no conversion path. |
| 12 | `9a0c800` | Footer titled "Assignment / Credits" with class name, teacher name, date — full assignment metadata as the closing impression | Footer titled "Student Simulator / Made By" — keeps the assignment credit ("Originally a brief for Teacher Howard's Digital Design class") but moves it out of the headline position | The assignment context is true and worth keeping for honesty. But it shouldn't be the *last thing* the visitor reads — that slot should reinforce the product, not break the spell. The credit stays, just demoted from headline to footnote. |

---

## Two structural changes that aren't single-line edits

### A. We threw away the "Chapter 01 / Chapter 02" numbering scheme

v1 numbered every section like a report (Chapter 01, 02, 03...). v2 uses
marketing labels ("▶ THE HOOK", "▶ FOUR MECHANICS", "▶ FOR FANS OF",
"▶ A TUESDAY", "▶ NOW THEN —"). This was a small visual change with a
big semantic one: it stopped signalling "you are reading a document" and
started signalling "you are exploring a product."

### B. We kept the visual shell

We did NOT change:
- The "school notebook + game HUD" aesthetic
- The five-font typography system (Fraunces / Caveat / Special Elite / VT323 / Press Start 2P)
- The paper background, red margin line, sticky notes, scotch-tape strips
- The animated stat bars on scroll
- The asymmetric tilted card layouts

This was deliberate. The aesthetic was the *one thing the AI got right
on the first try* — it picked a visual direction that fit the subject
matter (a sim about being a student should *look* like a student's
notebook). Keeping the shell and rewriting the copy let us focus our
effort on the part that wasn't working, instead of starting from zero.

---

## Why we used granular commits

The brief asks for evidence that we "actively used tools" and "safely
and correctly applied technical skills" (Strand ii). Twelve separately
named copy commits prove a process — read the AI output critically,
identify a specific weakness, make one targeted change, commit it
with a message that explains the *why*, move on.

A single "rewrote everything" commit would erase all that evidence.
We even reset and redid the work with finer-grained commits after
realising the first attempt at this had batched too much into three
big commits.

---

## What we'd change if we did it again

See `03-test-and-upgrades.md`. Short version: hero copy still does most
of the heavy lifting; the body sections could go further in the same
direction (more "you", less "we").
