# Strand i — Logical Plan

**Project:** Student Simulator — Landing Page
**Designer / Main Coder:** Ryan Yang
**Class:** Digital Design — Teacher Howard
**Repo:** `mdid-howard-lee/student-simulator`
**Deployment target:** `https://mdid-howard-lee.github.io/student-simulator/` (GitHub Pages)

---

## 1. Brief Summary

Design and ship a landing page that *markets* the Student Simulator game concept
(originally written as a design brief for "Designing Identity Through Games").
The page must read like a real product launch — not a school report — and must
be shippable to GitHub Pages.

---

## 2. Tools & Materials

| Category | Tool | Why |
|---|---|---|
| Code editor | **VS Code** | Standard editor for HTML/CSS/JS |
| Version control | **Git + GitHub** | Required by brief — commit history is evidence (C-ii) |
| Deployment | **GitHub Pages** | Free static hosting at the target URL |
| AI partner | **Claude (Sonnet 4.5)** | Generates draft + iterates on copy/CSS |
| Language stack | **HTML5 + CSS3 + vanilla JS** | No build step → faster ship; works on GitHub Pages without config |
| Fonts | **Google Fonts** (Fraunces, Caveat, Special Elite, VT323, Press Start 2P) | Distinctive typography over generic system fonts |
| Browser testing | Chrome + Safari | Verify rendering across engines |

---

## 3. Logical Sequence (Plan of Attack)

1. **Read the original brief** (Designing Identity Through Games essay)
2. **Pick a visual direction** — chose "school notebook + game HUD" for theme fit
3. **Draft v1 with AI** (single-file HTML/CSS/JS)
4. **Review v1 critically** — does it sell the game, or just describe it?
5. **Rewrite v2 copy** — flip from report tone to marketing tone
6. **Atomic git commits** for every change (one edit = one commit)
7. **Write planning docs** (this file + justification + testing)
8. **Push to GitHub** + enable Pages
9. **Gather peer feedback** for D-i
10. **List weaknesses + upgrades** for D-iii

---

## 4. Gantt Chart (per-period time allocation)

> *Time unit = one class period. "P1" means the first period the project was worked on, not period 1 of the school day.*

| Step | P1 | P2 | P3 | P4 | P5 | P6 | P7 | P8 |
|---|---|---|---|---|---|---|---|---|
| Read brief + decide direction          | █ |   |   |   |   |   |   |   |
| Choose visual style + typography       | █ |   |   |   |   |   |   |   |
| AI-assisted v1 draft (single file)     |   | █ |   |   |   |   |   |   |
| Review v1 critically                   |   |   | ▓ |   |   |   |   |   |
| Rewrite hero copy                      |   |   | █ |   |   |   |   |   |
| Rewrite body sections (hook/features/vibes/loop) | | | █ | █ | | | | |
| Replace closing with CTA + FAQ         |   |   |   | █ |   |   |   |   |
| Polish footer + nav                    |   |   |   | █ |   |   |   |   |
| Atomic granular commits (12 of them)   |   |   |   |   | █ |   |   |   |
| Write planning doc (this file)         |   |   |   |   |   | █ |   |   |
| Write justification doc                |   |   |   |   |   | █ |   |   |
| Write testing + upgrades doc           |   |   |   |   |   |   | █ |   |
| Push to GitHub Pages + verify deploy   |   |   |   |   |   |   |   | █ |
| Gather peer feedback                   |   |   |   |   |   |   |   | █ |

Legend: █ = primary work · ▓ = review/iterate

---

## 5. Per-Step Detail

| # | Step | Time | Tools | Output |
|---|---|---|---|---|
| 1 | Read brief | 15 min | PDF + brief essay | Notes on what game is about |
| 2 | Pick direction | 20 min | Reference search | "Notebook + Game HUD" |
| 3 | AI v1 draft | 1 period | Claude + VS Code | `index.html` v1 (report-shaped) |
| 4 | Critical review | 10 min | Live preview in browser | Verdict: too report-y, needs rewrite |
| 5 | Rewrite hero | 20 min | Claude + Edit tool | Commit `359a71b` |
| 6 | Rewrite body | 1 period | Claude + Edit tool | Commits `db3560a` → `5b3e60c` |
| 7 | New CTA section | 30 min | Claude + Edit tool | Commit `dae2938` |
| 8 | Granular re-commits | 30 min | Git reset + redo | Commits `fb6ac75` → `9a0c800` |
| 9 | Planning doc | 30 min | Markdown | `docs/01-plan.md` |
| 10 | Justification doc | 30 min | Markdown + git log | `docs/02-justifications.md` |
| 11 | Test + upgrades doc | 30 min | Markdown | `docs/03-test-and-upgrades.md` |
| 12 | Deploy + verify | 15 min | `git push` + GitHub Pages settings | Live URL |

---

## 6. Risk / Mitigation

| Risk | Mitigation |
|---|---|
| AI gives generic output | Review every section, rewrite tone where weak (see C-iv doc) |
| One-file HTML gets unmanageable | Keep below ~1000 lines, comment section headers clearly |
| Merge conflicts if teammates join | Adopt brief's recommendation: one CSS file per person (`ryan.css`), included in `<head>` of all pages |
| Forget to `git pull` | Pull before every editing session (brief rule) |
| Repo collaborators not authorized | Teacher authorizes during class period (brief requirement) |

---

## 7. Acceptance Criteria

- [ ] Page deploys at the target URL
- [ ] Renders on Chrome + Safari without console errors
- [ ] Hero reads as marketing, not as essay
- [ ] At least 12 atomic git commits exist (evidence for C-ii)
- [ ] All three planning docs are in `docs/`
- [ ] Justification doc references specific commit hashes
