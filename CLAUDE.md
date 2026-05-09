# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static Arabic RTL website for **مورد مساعدة** (Source for Help), advertising mental health training programs (CBT, DBT, Play Therapy, EMDR, and others). No build step — open any `.html` file directly in a browser to preview.

## Deployment

Deployed on Netlify. Push to `main` or drag-and-drop the folder at netlify.com/drop. No build command needed.

## Site Structure

| File | Purpose |
|---|---|
| `index.html` | Home page — programs grid, hero, footer |
| `cbt.html` | Program detail page (CBT Fundamentals — Dr. Allen Miller) |
| `cbt-anxiety.html` | Program detail page (CBT Anxiety & Personality — Dr. Sofia Chernoff) |
| `dbt.html` | Program detail page (DBT Basic Training — Prof. Dr. Martin Bohus) |
| `styles.css` | All styles, single shared file |
| `script.js` | Scroll animations, sticky nav, mobile menu, lazy loading |

## Adding a New Program Page

Copy `cbt-anxiety.html` as the template (most complete, supports multiple instructors). Sections in order: `hero → about (instructor) → program (modules) → details (card grid) → partnerships* → cta-section (#register) → footer`. All pages share the same `styles.css` and `script.js`.

The **partnerships section** is only included when there is an actual external institutional partner (e.g., Beck Institute). Omit it entirely when مورد مساعدة is the sole organiser — it is the main entity, not a partner.

The **hero partner block** (`.hero-partner` with logo) follows the same rule: only present when a named partner exists.

When editing `styles.css` or `script.js`, update the `?v=YYYYMMDD` cache-bust string (use today's date) on **every** HTML page that references those files.

## Registration & Contact

All program registration CTAs (both index cards and detail page CTA sections) link to the **same single Google Form**:

```
https://forms.gle/jfznRRDA9aPHiVkD6
```

Use this URL for any new or existing program page. Do not create program-specific forms unless explicitly instructed.

For direct contact / WhatsApp inquiries the number is **+201145804645** (`https://wa.me/201145804645`). Currently shown on `dbt.html`; add to other pages only if asked.

## Program Card States (index.html)

Three mutually exclusive states for cards in `.programs-grid`:

| State | Badge class | Card class | CTA |
|---|---|---|---|
| Open for registration | `badge-available` | *(none)* | `btn btn-primary` linking to detail page |
| Coming soon | `badge-soon` | *(none)* | `btn btn-secondary` mailto |
| Fully booked | `badge-booked` | `program-card-booked` | `btn btn-booked` (non-clickable span) |

## Design Tokens

All colors, shadows, and radii are defined as CSS variables in `:root` at the top of `styles.css`. Never hardcode hex values — use the tokens. Key ones: `--primary`, `--accent`, `--gold`, `--ink`, `--ink-2`, `--muted`, `--gradient-primary`, `--shadow`.

Fonts: **Cairo** (Arabic body text) + **Poppins** (Latin/English). Loaded from Google Fonts.

## RTL

All pages use `<html lang="ar" dir="rtl">`. CSS logical properties and flexbox direction are already RTL-aware. SVG arrow icons use `transform: scaleX(-1)` to flip direction for RTL — see `.btn-primary svg` in `styles.css`.

## Assets

Trainer photos live in `assets/`. Filenames may be Arabic (e.g., `assets/احمد ابو الوفا.jpg`) — use the literal filename in `src` attributes, no URL-encoding needed in HTML.
