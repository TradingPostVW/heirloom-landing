# Heirloom marketing landing

Static site for **heirloomportraits.love** — soft-launch waitlist + brand hero.

**Status: SHIP LOCKED (Vince 2026-09-25)** — landscape + mobile SOTs. Publishing to the live domain.

## Layout lock (Vince — 2026-09-25)

1. **Blank cream** page fill `#F3EEE6` everywhere — no parchment panels, no full-bleed splash stack, no centered portrait plate as the main column.
2. **Hero dog in the upper-right** — `img/hero-dog.webp` / `.png` with painted soft alpha brush bleed into cream (dog plate is bleed source of truth). No hard rectangle, oval vignette, or straight cut. Dog only (no carousel).
   - Landscape (≥900px): dog ~upper-right half after 20% shrink pass.
   - Mobile: dog dominates top; wordmark sits ~4px under brush; short scroll reaches footer.
3. **Copy XY-centered** in the viewport (wordmark, tagline, flourish, descriptor, lede, Join Waitlist). Ink `#2B2A28` on cream.
4. **Landscape lede mask only:** hard-edged cream fill + **2px** padding on `.lede` alone — no soft halo / box-shadow under the whole copy stack. Mobile: no lede mask (leave as-is).
5. Tagline: `Keep your loved ones close.` (sentence case). Exact soft-launch lede with 20% first-order offer. Waitlist opens in a native `<dialog>`; FormSubmit + `thank-you.html`.

QA shots: `shots/desktop-landscape.png`, `shots/mobile-vertical.png`.

## Paths

| File | Role |
|------|------|
| `index.html` | Landing (cream + UR dog + centered waitlist CTA) |
| `thank-you.html` | Post-submit confirmation |
| `commission/index.html` | Commissioned-artist interest form (FormSubmit) |
| `EDITING.md` | How Vince edits copy without regenerating the site |
| `styles.css` | Brand styles (cream / ink / Tenor Sans + Source Sans 3) |
| `img/` | Brush-bleed `hero-dog` (webp/png) |
| `shots/` | Local screenshot QA (not deployed) |

## Brand (locked)

- **HEIRLOOM** — Optima / Tenor Sans, letter-spaced
- Tagline: Keep your loved ones close.
- Descriptor: Portraits for pets, their people, and the things they love most.
- Colors: cream `#F3EEE6`, ink `#2B2A28`, soft `#5C5852`
- CTA: solid ink, cream/white label, ~14px radius
- Waitlist fields / chips / consent / **Save my spot** / commission footer: from `canon/waitlist/` (locked)

## FormSubmit

Form posts to `https://formsubmit.co/hello@heirloomportraits.love`.

Hidden fields: `_subject` = `Heirloom waitlist`, `_captcha` = `false`, `_next` → `https://heirloomportraits.love/thank-you.html`.

**First submit:** FormSubmit emails `hello@heirloomportraits.love` a one-time activation link. Confirm once before soft launch.

## Deploy

Static host as site root. Custom domain apex + www; **preserve Namecheap Private Email MX** when changing DNS (do not leave URL Forward parking).

## Commission form

Live path: **`/commission/`** (`commission/index.html`).

Footer on `index.html` links to `commission/` (online form, not mailto).

FormSubmit (same inbox as waitlist):

- action: `https://formsubmit.co/hello@heirloomportraits.love`
- `_subject` = `Heirloom commission interest`
- `_captcha` = `false`
- `_next` → `https://heirloomportraits.love/thank-you.html`

Fields: Name, Email*, Zip/city, subjects chips (Pet(s)/People/Other Subjects), style preference, notes, consent*.

## Editing copy without a rebuild

See **`EDITING.md`** — Vince can edit `index.html` / `commission/index.html` in the GitHub UI and commit to `main`.

## robots

`index.html` is `index,follow` when live. `thank-you.html` stays `noindex,follow`.
