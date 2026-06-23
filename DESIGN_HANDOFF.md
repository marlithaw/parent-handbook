# Handoff: Matchbook Learning — Parent & Student Handbook (2026–2027)

## Overview
A family-facing Parent & Student Handbook for Matchbook Learning Schools of Indiana. It is published in two forms that carry **identical content**:
- A **web handbook** — a single scrolling page with sticky navigation, anchor sub-nav, hero, and richly formatted sections.
- A **print document** — the same content reflowed for letter-size printing (Print → Save as PDF).

Both cover school identity, family communication, daily operations, academics, attendance, culture, support systems (MTSS/CICO/re-entry), conduct/dress/technology, the full **Student Code of Conduct**, health & safety, the calendar/supplies/glossary, and family agreement forms.

## About the Design Files
The files in this bundle are **design references created in HTML** — prototypes that show the intended look, content, and structure. They are **not production code to copy directly**. The task is to **recreate these designs in the target environment** (e.g. a CMS template, a React/Vue marketing site, or a print/PDF pipeline) using that environment's established patterns — or, if no environment exists yet, to choose the most appropriate stack and implement them there.

If this becomes part of the Matchbook website, use the existing **Matchbook Learning Design System** (the `colors_and_type.css` tokens included here are the source of truth) rather than re-deriving styles.

## Fidelity
**High-fidelity (hifi).** Final colors, typography, spacing, copy, and table content are all production-ready. Recreate the UI to match, using the codebase's existing component library where one exists.

## Screens / Views

### 1. Web Handbook (single page)
**File:** `Matchbook Parent & Student Handbook.html`
**Purpose:** Families read the full handbook online; jump to any section via the sticky sub-nav.

**Global layout**
- Centered content column, `max-width: 1080px` (wide variants `1240px`), horizontal padding `48px`.
- Sections: `padding: 88px 0`; alternating background — white and `--paper` (#F6F6F4) — for rhythm. `scroll-margin-top: 132px` so anchors clear the sticky header.

**Persistent chrome (sticky, `top:0`, `z-index:60`)**
- **Utility bar** — charcoal (#232323), white condensed uppercase text, space-between (left: tagline; right: contact link). `padding: 8px 0`.
- **Primary nav** — white, 1px hairline bottom border. Left: stacked logo lockup — line 1 Anton uppercase in Spark Red (#E21C24, 23px), line 2 Oswald 600 uppercase ink (12px, letter-spacing .12em). Right: a small "badge" (school year / version), right-aligned, Oswald.
- **Sub-nav** — horizontally scrollable row of anchor chips (Oswald 600, 13px, uppercase, letter-spacing .06em); active chip is Spark Red with a 3px Spark Red bottom border. Updated on scroll via an IntersectionObserver / scroll handler.

**Hero**
- `min-height: 560px`, content bottom-aligned. Background image `img/hero.jpg` under a top-to-bottom dark gradient (`rgba(20,20,20,.18)` → `.72`), `background-size: cover`, position `center 28%`.
- Eyebrow: Oswald 600 uppercase white, 15px, letter-spacing .18em, with a 7px Spark Red square dot.
- H1: Anton uppercase white, `font-size: clamp(56px, 9vw, 128px)`, `line-height: .9`.
- Sub-paragraph: Mulish 20px white, `max-width: 620px`, opacity .94.
- Meta row: Oswald uppercase white chips, each prefixed with a 6px Spark Red square.

**Section header pattern (repeated for all 12 sections)**
- Eyebrow: number in Anton 30px Spark Red + label in Oswald 600 uppercase ink (14px, letter-spacing .18em).
- H2: Anton uppercase ink, `clamp(36px, 5vw, 64px)`, `line-height: .94`; may contain a `<br>`.
- Red rule: `height: 5px; width: 64px; background: --spark-red`.
- Lead paragraph: Mulish 21px, `--slate` (#4A4A4A), `max-width: 760px`.
- Body paragraphs: Mulish 17px, line-height 1.7, `--slate`, `max-width: 760px`.

**Recurring content components**
- **Red manifesto band** — full-bleed Spark Red section, centered, `padding: 96px 0`; kicker (Oswald uppercase, opacity .85) + a large Anton line (`clamp(34px,5vw,58px)`) over Mulish 22px, all white.
- **Cards** (sharp corners, no radius): *dark* (charcoal bg, Anton number, Oswald H3, 44px Spark Red bar, light-grey body), *yellow* (`--dream-yellow` #F9DC7C bg, ink text — used for feature/highlight blocks), *paper* (white bg, 1px hairline border, Spark Red bar). Laid out in `.hb-grid-3` / `.hb-grid-2` CSS grids, `gap: 24px`.
- **Callout** — `--paper` bg with a `5px` Spark Red top border (`--ink` variant: charcoal bg, gold top border), `max-width: 820px`.
- **Tables** — `border-collapse`; caption in Oswald uppercase Spark Red; `th` charcoal bg / white Oswald uppercase; `td` Mulish 15.5px `--slate`; even rows `--paper`; first column ink + 600. Variants: `.red` header cells (Spark Red), `--accept` (first th charcoal / last th Spark Red), `.hl` highlighted row (`--dream-yellow`). Used heavily in Code of Conduct, attendance, calendar.
- **Diamond list** (`.hb-list`) — each `li` has hairline bottom border and an 11px Spark Red rotated-45° square bullet.
- **Values grid** (`.hb-values`) — 3-col grid with 1px hairline gaps for a tiled look.

**The 12 sections (anchor id — eyebrow label — H2):**
1. `#welcome` — Welcome & Identity — "Welcome to Matchbook Learning"
2. `#connect` — Communication & Family Partnership — "Partners In Every Step"
3. `#operations` — Daily Operations — "Every Minute Of Learning Counts"
4. `#academics` — Academics & Progress — "Learn Your Way"
5. `#attendance` — Attendance & Chronic-Absence Supports — "Be Here. Be On Time."
6. `#culture` — Culture & Recognition — "Catch Students Doing It Right"
7. `#support` — Support · MTSS, DBRC/CICO, Re-Entry — "The Right Support, At The Right Time"
8. `#conduct` — Conduct, Dress & Technology — "A Non-Violent Community"
9. `#conduct-code` — **Student Code of Conduct** — "Teach. Repair. Return To Learning."
10. `#health` — Health, Safety & Student Services — "Known, Safe & Cared For"
11. `#calendar` — Calendar, Supplies & Glossary — "Mark Your Calendar"
12. `#forms` — Forms & Family Agreements — "Let's Make It Official"

> **Section 9 (Student Code of Conduct)** is the most table-heavy: it documents the restorative philosophy, a graduated **Response Levels 1–4** framework, behavior categories, due-process steps, suspension/re-entry procedures, protections for students with disabilities, and the family-partnership commitment. Preserve all rows verbatim — this is policy text.

### 2. Print Document
**File:** `Matchbook Parent & Student Handbook - Print Document.html`
**Purpose:** The same handbook content laid out for letter-size print / PDF. Open in a browser and Print → Save as PDF. Uses the same tokens and content; chrome (sticky nav, hero treatment) is simplified for paper. Keep its content synchronized with the web version — they must always match.

## Interactions & Behavior
- **Sticky header + sub-nav:** remain pinned while scrolling.
- **Anchor navigation:** sub-nav chips are in-page anchor links; `html { scroll-behavior: smooth }`.
- **Active-section highlighting:** the chip for the section currently in view gets `.is-active` (Spark Red text + bottom border) — implement with an IntersectionObserver on each `<section>`.
- **Transitions:** sub-nav chips transition `color` and `border-color` over .18s. Buttons (design-system `Button`) darken on hover (never lighten) and scale to .97 on press, easing `cubic-bezier(.2,.7,.2,1)`.
- No data fetching or form submission logic in the prototype — the "forms" section is informational; wire real form handling per the target environment.

## State Management
Minimal — this is a content page. The only stateful behavior is the **active sub-nav section** (derived from scroll position via IntersectionObserver). No app state, auth, or persistence required.

## Design Tokens
Source of truth: **`colors_and_type.css`** (included). Key values:

**Colors**
- Spark Red `#E21C24` (primary) · pressed `#B5151A` · ember `#C8161D`
- Dream Yellow `#F9DC7C` (highlight cards) · gold `#F7B23C`
- Ink `#1A1A1A` · charcoal `#232323` · slate `#4A4A4A` · muted `#8A8A8A`
- Hairline `#E4E2DE` · paper `#F6F6F4` · cloud `#EDEDEB` · white `#FFFFFF`

**Typography**
- Display — **Anton** (ultra-bold condensed caps; hero & section H2). Fallback `'Arial Narrow', sans-serif`.
- Condensed — **Oswald** 400–700 (nav, labels, buttons, kickers, table headers). Fallback `'Arial Narrow'`.
- Body — **Mulish** 400–800 (+ italics) (all body copy). Fallback `system-ui`.
- Script — **Caveat** (playful accent, used sparingly).
- Loaded via Google Fonts `@import` at the top of `colors_and_type.css`.

**Radii** — cards & photos are **sharp** (`0`); only buttons are full pills (`999px`); small radius `4px`.

**Shadows** (flat brand, used sparingly) — sm `0 1px 3px rgba(26,26,26,.10)` · md `0 6px 20px rgba(26,26,26,.12)` · lg `0 16px 44px rgba(26,26,26,.16)`.

**Spacing scale** (4px base) — 4 / 8 / 12 / 16 / 24 / 32 / 48 / 64 / 96 / 128.

**Motion** — ease `cubic-bezier(.2,.7,.2,1)`, duration `180ms`.

## Assets
- `img/hero.jpg` — hero background photograph.
- `img/` also contains the other photographs/graphics referenced in the handbook (copied in full).
- Fonts are loaded from Google Fonts (no local font files) — see the `@import` in `colors_and_type.css`. If the target environment self-hosts fonts, substitute equivalents: Anton, Oswald, Mulish, Caveat.

## Files
- `Matchbook Parent & Student Handbook.html` — the web handbook (primary design reference).
- `Matchbook Parent & Student Handbook - Print Document.html` — print/PDF layout, same content.
- `colors_and_type.css` — design tokens (colors, type, spacing, radii, shadows). Import first.
- `img/` — all images used by the handbook.

## Note on the brand system
These files belong to the **Matchbook Learning Design System** project. The `colors_and_type.css` here is a copy of that system's token file; if you have access to the full design system, prefer its components (e.g. the signature `Button`) and tokens over re-implementing them.
