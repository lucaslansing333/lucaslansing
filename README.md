# lucaslansing.com

Private practice site for Lucas Lansing — contemplative living, somatic health, and conscious partnership. Incline Village, Lake Tahoe.

## What's here

Three pages built. Static HTML. No build step. No framework. No dependencies beyond two Google Fonts.

```
/
├── index.html              # homepage — the door
├── lineage.html            # the long-form essay on tradition
├── the-practice.html       # who the work is for, who leads it, the three engagements
└── README.md               # this file
```

Three more pages still to build (the deep-dive engagement pages, Writing section, Contact).

## Design notes

**Direction:** editorial-contemplative. The site reads more like a literary magazine or a private medical practice than a wellness coaching site. The intent is to signal seriousness, lineage, and discretion to a high-net-worth reader without performing luxury.

**Typography**
- Display: **Fraunces** (variable serif, optical-size + soft/sharp axes — used to set distinctive italics in moss-green for emphasis)
- Body: **EB Garamond** (warm, classical body serif)
- Both Google Fonts, free, distinctive (deliberately avoiding Inter / Roboto / Space Grotesk / system fonts).

**Palette**
- `--paper` `#F2EDE3` — warm off-white background
- `--ink` `#1F1B16` — deep brown-black for text
- `--moss` `#3D4A38` — alpine forest accent for italic emphasis
- `--ember` `#8A5A2B` — faded ochre for links, ornamental marks
- `--rule` `#C9BFAB` — hairline dividers

**Distinctive design moves**
- SVG noise texture overlay for paper-grain feel (background-attachment: fixed)
- Drop caps on opening paragraphs, set in moss-green Fraunces
- Roman numerals in italic ochre to mark sections and engagements
- Asymmetric two-column layouts (1fr / 2fr) — labels left, content right
- Italic Fraunces in moss-green is the consistent "emphasis voice" across the site
- Staggered fade-in on page load (respects `prefers-reduced-motion`)
- Cohesive header + footer + nav across all pages

## Deployment

This is a static site. Three good options, in order of recommendation.

### Option 1 — Cloudflare Pages (recommended)

Cleanest workflow, free tier is generous, fastest CDN.

1. Push this repo to GitHub
2. Go to dash.cloudflare.com → Workers & Pages → Create → Pages → Connect to Git
3. Select the repo
4. Build settings:
   - Framework preset: **None**
   - Build command: *(leave empty)*
   - Build output directory: `/`
5. Save and Deploy
6. To use `lucaslansing.com`, go to Custom Domains in the project, add `lucaslansing.com`, and update DNS at your registrar (Cloudflare will give the exact records)

### Option 2 — GitHub Pages

Slightly clunkier but lives in the same place as the repo.

1. Push to `main` branch
2. Repo → Settings → Pages → Source: `Deploy from a branch` → Branch: `main` / `/ (root)`
3. Wait ~1 minute, site is live at `username.github.io/repo-name`
4. For the custom domain: add a `CNAME` file containing `lucaslansing.com` to the repo root, configure DNS at your registrar, then add the custom domain in repo Settings → Pages

### Option 3 — Netlify or Vercel

Both auto-detect static sites with no config. Drag-and-drop deployment also works for quick previews.

## URL routing

All three pages currently have `.html` extensions. The internal nav links are written without the extension (`/the-practice`, `/lineage`) — Cloudflare Pages and Netlify automatically resolve these. GitHub Pages also handles them in most cases.

If anything 404s after deploy, two fixes:
1. **Easy:** rename the files to live in folders — `the-practice/index.html`, `lineage/index.html`. The host will serve those at `/the-practice` and `/lineage` cleanly.
2. **Faster:** keep the files as-is and add the `.html` extension to the nav links inside each file.

## What's still to build

Listed in priority order:

- **The Concierge Engagement** page (`/the-work/concierge`)
- **Private Retreats** page (`/the-work/retreats`)
- **Family & Founder Programs** page (`/the-work/family-founder`)
- **Writing** index + a few anchor essays
- **Contact** page (currently the "Request an introduction" CTA links to `/contact` which doesn't exist yet — wire to a Tally or Formspree form, or temporarily change to `mailto:lucas.lansing.coaching@gmail.com`)

## Editing notes for Lucas

- All pages use the same CSS variables in the `:root` block. To shift the entire color palette across the site, edit those variables consistently in each file. (Eventually these should be extracted into a shared stylesheet — `style.css` — but inline is fine for now.)
- Italic emphasis (`<em>`) is set in moss-green Fraunces. Use sparingly; it loses power when overused.
- The hero image slot on the homepage is intentionally empty pending an editorial photo session. See conversation notes for the photo brief.
- Teacher names and lineage details on the Lineage page have been verified once. Worth one final cross-check against the Ananda directory before launch.

## License

© Lucas Lansing / Heart Alchemy LLC. All rights reserved.
