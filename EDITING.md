# How Vince edits landing copy (no rebuild)

The live site is **static HTML** on GitHub Pages from repo
[`TradingPostVW/heirloom-landing`](https://github.com/TradingPostVW/heirloom-landing)
(branch `main`). There is no CMS and no build step — change a sentence in a file,
commit, and Pages refreshes in about a minute.

## What to edit

| What | File | Find |
|------|------|------|
| Soft-launch lede (long paragraph under the descriptor) | `index.html` | `class="lede"` or `<!-- COPY: soft-launch lede` |
| Tagline / descriptor / CTA label | `index.html` | `class="tag"`, `class="descriptor"`, Join Waitlist button |
| Commission footer sentence | `index.html` | `<!-- COPY: commission footer` or `artists-note` |
| Commission form intro / fields labels | `commission/index.html` | `<!-- COPY: commission lede` |
| Thank-you page | `thank-you.html` | heading / body text |

Do **not** regenerate images or redesign layout for a wording tweak.

## Two ways to change text

### A) GitHub web UI (fastest for Vince)

1. Open https://github.com/TradingPostVW/heirloom-landing
2. Click the file (e.g. `index.html`)
3. Click the pencil (Edit)
4. Change only the sentence you need — search for `lede` or the old phrase
5. Commit to **main** (Commit changes)
6. Wait ~1 minute, then hard-refresh https://heirloomportraits.love/

### B) Ask Loom

Send the **exact new sentence** (and which block: lede, tagline, commission intro, etc.). Loom will edit source + deploy.

## Commission form

Live URL: **https://heirloomportraits.love/commission/**

Submissions go to `hello@heirloomportraits.love` via FormSubmit (same as waitlist).
Subject line: `Heirloom commission interest`. After submit, visitors land on `thank-you.html`.

## Source of truth (for Loom)

- Editable marketing source: `/workspace/heirloom/landing/`
- Deploy clone (what Pages serves): `/workspace/heirloom/landing-deploy/` — keep in sync with `landing/` before push.
