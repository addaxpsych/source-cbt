# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static Arabic RTL website for **مورد مساعدة** (Source for Help), advertising mental health training programs (CBT, DBT, Play Therapy, EMDR, and others). No build step — open any `.html` file directly in a browser to preview.

## Deployment

Deployed on Netlify from the `main` branch of `github.com/addaxpsych/source-cbt`. Push to `main` and Netlify auto-deploys. No build command needed.

## Site Structure

| File | Purpose |
|---|---|
| `index.html` | Home page — hero, about, founders, programs grid, events gallery, footer |
| `cbt.html` | Program detail page (CBT Fundamentals — Dr. Allen Miller) |
| `cbt-anxiety.html` | Program detail page (CBT Anxiety & Personality — Dr. Sofia Chernoff) |
| `dbt.html` | Program detail page (DBT Basic Training — Prof. Dr. Martin Bohus) |
| `styles.css` | All styles, single shared file |
| `script.js` | Smooth scroll, sticky nav shadow, IntersectionObserver fade-ins, mobile menu, lazy loading |
| `assets/` | Trainer photos, logos. Filenames may be Arabic — use literal filenames in `src`, no URL-encoding needed |
| `events_images/` | Photos from past training events, shown in the "من فعالياتنا" gallery on `index.html` |

## Adding a New Program Page

Copy `cbt-anxiety.html` as the template (most complete, supports multiple instructors). Sections in order: `hero → about (instructor) → program (modules) → details (card grid) → partnerships* → cta-section (#register) → footer`. All pages share the same `styles.css` and `script.js`.

The **partnerships section** is only included when there is an actual external institutional partner (e.g., Beck Institute). Omit it entirely when مورد مساعدة is the sole organiser.

The **hero partner block** (`.hero-partner` with logo) follows the same rule: only present when a named partner exists.

Add the **floating WhatsApp button** (see below) to every new page just before `</body>`.

When editing `styles.css` or `script.js`, update the `?v=YYYYMMDD` cache-bust string (use today's date) on **every** HTML page that references those files.

## Registration & Contact

All program registration CTAs link to the **same single Google Form**:

```
https://forms.gle/jfznRRDA9aPHiVkD6
```

For WhatsApp contact the number is **+201500990658** (`https://wa.me/201500990658`). This appears as both an inline button on `dbt.html` and as the floating button on all pages.

For email contact use **training@sourceforhelp.com**. This is used in all `mailto:` links across the site.

## Floating WhatsApp Button

Every page has a fixed circular WhatsApp button (bottom-right, `.floating-whatsapp`) defined in `styles.css`. Add this snippet just before `</body>` on any new page:

```html
<a href="https://wa.me/201500990658" class="floating-whatsapp" target="_blank" rel="noopener noreferrer" aria-label="تواصل عبر واتساب">
    <svg width="28" height="28" viewBox="0 0 24 24" fill="currentColor" aria-hidden="true"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/></svg>
</a>
```

## Program Card States (index.html)

Three mutually exclusive states for cards in `.programs-grid`:

| State | Badge class | Card class | CTA |
|---|---|---|---|
| Open for registration | `badge-available` | *(none)* | `btn btn-primary` linking to detail page |
| Coming soon | `badge-soon` | *(none)* | `btn btn-secondary` mailto to `training@sourceforhelp.com` |
| Fully booked | `badge-booked` | `program-card-booked` | `btn btn-booked` (non-clickable span) |

Current programs (in grid order): CBT Fundamentals (booked), DBT Training (available), Play Therapy (soon), CBT Anxiety & Personality (available), Complex Trauma (soon), Playful EMDR (soon), العلاج بالتراحم (soon), خلوة الصمت (soon).

## Design Tokens

All colors, shadows, and radii are CSS variables in `:root` at the top of `styles.css`. Never hardcode hex values — use the tokens. Key ones: `--primary`, `--accent`, `--gold`, `--ink`, `--ink-2`, `--muted`, `--gradient-primary`, `--shadow`.

Fonts: **Cairo** (Arabic body text) + **Poppins** (Latin/English). Loaded from Google Fonts.

## RTL

All pages use `<html lang="ar" dir="rtl">`. CSS logical properties and flexbox direction are already RTL-aware. SVG arrow icons use `transform: scaleX(-1)` to flip direction for RTL — see `.btn-primary svg` in `styles.css`.
