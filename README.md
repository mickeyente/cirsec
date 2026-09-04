# Cirsec Landing Page

Single-file, self-contained landing page for Cirsec (Circle Security) — cybersecurity & technology for growing businesses in Nigeria.

Built for the pre-launch phase and the **Cirsec Cybersecurity Awareness Initiative 2026** (October 2026, Lagos).

## What's inside

`cirsec-landing-page.html` — one HTML file with all CSS and images (base64-embedded) inline. No build step, no dependencies to install, no bundler. Open it in a browser and it works.

Sections, in order:
1. Nav — logo, links, "Get involved" CTA
2. Hero — headline, pre-launch pill, animated ring motif
3. Why Cirsec exists — the accessibility gap in SME cybersecurity
4. What we do — service tags + Cirsec Virtual CISO product flow (10 steps)
5. October Initiative — campaign theme, stats, 5 pillars, Sept/Oct/Nov timeline
6. Get Involved — partner enquiry, session registration, email signup
7. Partners — KnowBe4, Sophos, SolarWinds, Platview Technologies
8. Footer — contact, socials, copyright

Fonts: Space Grotesk (headings) + IBM Plex Sans (body), loaded from Google Fonts CDN.

## Before you deploy

A few placeholders need to be swapped for real values — search the file for these:

| Placeholder | Location | Replace with |
|---|---|---|
| `hello@cirsec.co` | "Get involved" mailto links + footer | Your real contact email |
| Email signup form | "Stay updated" card | Wire to Mailchimp / Google Forms / your backend — it's currently just markup, `onsubmit="return false;"` |
| `href="#"` on LinkedIn / Instagram / X | Footer | Your real social URLs |
| Favicon | `<head>` | None is set — add a `<link rel="icon">` pointing to a hosted favicon |

## Deploying

This is a static file, so any of the following work:

**Push to GitHub Pages / Netlify / Vercel**
```bash
git init
git add cirsec-landing-page.html README.md
git commit -m "Initial Cirsec landing page"
git branch -M main
git remote add origin <your-repo-url>
git push -u origin main
```
Then point GitHub Pages / Netlify / Vercel at the repo. If your host expects `index.html` at the root, rename the file:
```bash
mv cirsec-landing-page.html index.html
```

**Any static host (S3, cPanel, etc.)**
Just upload the HTML file as-is — it has no other file dependencies.

## Editing later

Everything is in one file, so:
- Copy lives inline in the HTML — search for the text you want to change.
- Colors are CSS variables at the top of the `<style>` block (`--navy-black`, `--navy-deep`, `--blue`, `--cyan`).
- Images are base64-encoded inline (`data:image/...;base64,...`). To swap a logo, replace the `src` with a new base64 string or a normal image URL/path.

## Known limitation

The file was screenshot-tested with an older WebKit renderer that doesn't support CSS Grid/flex `gap` — those checks showed single-column fallbacks. This is a renderer quirk, not a bug: all modern browsers (Chrome, Firefox, Safari, Edge — anything from 2021 onward) render the intended multi-column grid layouts correctly. Worth a quick visual check in your actual target browsers before go-live.
