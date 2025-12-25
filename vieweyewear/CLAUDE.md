# Project: View Eyewear Directory

> Claude Sync Enabled

## Quick Context
Luxury boutique eyewear directory at vieweyewear.com. Monetized directory of independent optical boutiques - Gazal wholesale accounts get free listings, competitors pay $9/mo.

## Current State
- Working: Static site generator (278 pages), designers, boutiques, events, blog
- In Progress: Deploy to Netlify, Stripe webhook setup
- Blocked: None

## Tech Stack
- Framework: Node.js static site generator
- Build: `node scripts/build-site.js` → outputs to `dist/`
- Preview: `npx serve dist -p 3000`
- Hosting: Netlify (pending)

## Sync Config
SYNC_URL=https://claude-sync-api.vercel.app
SYNC_KEY=72ab20994f8b1eab933b5cf5d62a08f0bcc803437ccf7a1318d10e04a7bd2d3e
PROJECT=vieweyewear

---

## Commands

### When I say "sync this session":
1. Update this CLAUDE.md with what we accomplished
2. Run this curl command:
```bash
curl -X POST https://claude-sync-api.vercel.app/sync/vieweyewear \
  -H "Authorization: Bearer 72ab20994f8b1eab933b5cf5d62a08f0bcc803437ccf7a1318d10e04a7bd2d3e" \
  -H "Content-Type: application/json" \
  -d '{"summary": "WRITE_SESSION_SUMMARY_HERE", "claude_md": "PASTE_UPDATED_CLAUDE_MD_HERE"}'
```
3. Run: git add -A && git commit -m "Sync: SESSION_SUMMARY" && git push
4. Output this block for Claude.ai memory (copy/paste to Claude.ai):
```
=== CLAUDE.AI MEMORY UPDATE ===
PROJECT: View Eyewear (vieweyewear.com)
DATE: [TODAY'S DATE]
ACCOMPLISHED: [BULLET LIST OF WHAT WE DID]
CURRENT STATE: [WHAT'S WORKING/IN PROGRESS/BLOCKED]
NEXT STEPS: [WHAT TO DO NEXT SESSION]
================================
```

### When I say "continue where we left off":
Read this CLAUDE.md and tell me the current state before we start working.

---

## Project Overview

**Owner:** Saeed - owns Gazal Eyecare in Roswell, GA
**Website:** vieweyewear.com
**Goal:** Monetized directory of independent eyewear boutiques

## Business Model

| Listing Type | Cost | Who |
|--------------|------|-----|
| Claimed - Free | $0 | Gazal wholesale accounts (44 total) |
| Claimed - Paid | $9/mo | Non-Gazal boutiques who claim |
| Unclaimed | Free | Competitors (pressure to claim) |

## Key Files

- `scripts/build-site.js` - Main static site generator (generates 278 pages)
- `data/designers.json` - 67 designer brands
- `data/boutiques.json` - 40 claimed boutiques
- `data/unclaimed-boutiques.json` - 43 unclaimed competitor boutiques
- `data/events.json` - 17 eyewear events
- `data/blog-posts.json` - 18 blog articles
- `data/releases.json` - Product releases
- `data/images.json` - Image mappings with SEO alt tags

## Design Specs (Updated 2024-12-19)

**Mixed Theme (Option C):**
- Dark hero sections: `#0a0a0a` to `#1a1a1a` gradient
- Accent: Gold `#c9a962`
- Light content areas: `#fff` and `#f8f8f8`
- Dark header/footer: `#0a0a0a`
- Text on dark: `#fff` (headings), `#a0a0a0` (body)
- Text on light: `#111` (headings), `#444` (body)
- Headings: Playfair Display, Georgia, serif
- Body: Montserrat, weight 300, 17px
- Cards: White with `#e5e5e5` border, gold hover

## Completed
- [x] Static site generator - 278 pages total
- [x] 67 designer pages + 67 trunk show pages
- [x] 40 claimed boutique pages
- [x] 43 unclaimed boutique pages (competitor pressure)
- [x] 18 state index pages
- [x] 50 city pages for local SEO
- [x] 17 event pages
- [x] 18 blog posts (Frame of the Month)
- [x] Pillar page: Luxury Eyewear Guide + 4 cluster articles
- [x] About page with E-E-A-T signals
- [x] Claim page with Stripe integration ($9/mo)
- [x] PWA support (manifest.json, service worker)
- [x] SEO: sitemap.xml (335 URLs), robots.txt, structured data
- [x] **DESIGN OVERHAUL** - Mixed theme with dark heroes, light content (2024-12-19)

## Next Steps
- [ ] Deploy to vieweyewear.com (Netlify)
- [ ] Set up Stripe webhook for claim processing
- [ ] Add more unclaimed boutiques to increase pressure

## Generated Listings (40 total)

**By State:**
- Georgia: 11 (Gazal, Family Eye Care Atlanta, Midtown, Druid Hills, etc.)
- South Carolina: 6 (Premier, My Eyewear Co, Indigo Vision, Eyes on Lake, Eye on Gervais)
- Florida: 4 (Seaview, View Optical, Optic Shop, Spectacles of Naples)
- Texas: 3 (Lakeway, Optique Austin, Bass Eye Care)
- Alabama: 2, Illinois: 2, Louisiana: 2
- Others: CO, IN, KS, LA, MN, NC, NV, OH, OR, TN, VA, WA, WI (1 each)

## Quick Commands

```bash
# Rebuild site
node scripts/build-site.js

# Preview locally
npx serve dist -p 3000

# View at
http://localhost:3000
```

## Important Notes

- Gazal wholesale accounts get FREE claimed listings
- Unclaimed pages pressure competitors to pay $9/mo
- URL format: /luxury-eyewear-boutiques/business-name-city-state
- All styling is inline in build-site.js (no external CSS files)

---

## Session Log

### 2024-12-25
- Added Claude Sync configuration

### 2024-12-19
- **DESIGN OVERHAUL**: Implemented mixed theme (Option C)
  - Dark gradient hero sections on all pages
  - Gold accent color (#c9a962) for CTAs and highlights
  - Light content areas with excellent contrast
  - Updated: homepage, designers, boutiques, guides, events
  - Cards have white backgrounds with gold hover borders

### 2024-12-14
- Full site audit of vieweyewear.com (306+ URLs)
- Built static site generator (scripts/build-site.js)
- Migrated all content: designers, boutiques, events, blog posts
- Added E-E-A-T about page, luxury eyewear guide pillar page
- Claim page with Stripe $9/mo integration

### 2024-12-09
- Project initialized, generator script created
- Generated 40 US boutique listings
