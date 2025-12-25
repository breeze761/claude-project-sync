# Project: LASIK Surgeons Atlanta

> Claude Sync Enabled

## Quick Context
LASIK surgeons directory for Atlanta area at lasiksurgeonsatlanta.com. Directory of 16+ surgeons and 7 practices with monetized claimed listings at $29/mo.

## Current State
- Working: 16+ doctor profiles, 7 practice listings, SEO optimized
- In Progress: Adding more surgeons, practice outreach
- Blocked: None

## Tech Stack
- Framework: Static HTML/CSS (Node.js generator)
- Build: `node scripts/generate-site.js`
- Hosting: Vercel

## Key Files
- `scripts/generate-site.js` - Site generator
- `data/doctors.json` - Surgeon information
- `data/practices.json` - Practice information

## Business Model
- **Free**: Doctor profiles (SEO content)
- **$29/month**: Claimed practice listings with full contact info and booking

## Sync Config
SYNC_URL=https://claude-sync-api.vercel.app
SYNC_KEY=72ab20994f8b1eab933b5cf5d62a08f0bcc803437ccf7a1318d10e04a7bd2d3e
PROJECT=lasik-atlanta

---

## Commands

### When I say "sync this session":
1. Update this CLAUDE.md with what we accomplished
2. Run this curl command:
```bash
curl -X POST https://claude-sync-api.vercel.app/sync/lasik-atlanta \
  -H "Authorization: Bearer 72ab20994f8b1eab933b5cf5d62a08f0bcc803437ccf7a1318d10e04a7bd2d3e" \
  -H "Content-Type: application/json" \
  -d '{"summary": "WRITE_SESSION_SUMMARY_HERE", "claude_md": "PASTE_UPDATED_CLAUDE_MD_HERE"}'
```
3. Run: git add -A && git commit -m "Sync: SESSION_SUMMARY" && git push
4. Output this block for Claude.ai memory (copy/paste to Claude.ai):
```
=== CLAUDE.AI MEMORY UPDATE ===
PROJECT: LASIK Atlanta (lasiksurgeonsatlanta.com)
DATE: [TODAY'S DATE]
ACCOMPLISHED: [BULLET LIST OF WHAT WE DID]
CURRENT STATE: [WHAT'S WORKING/IN PROGRESS/BLOCKED]
NEXT STEPS: [WHAT TO DO NEXT SESSION]
================================
```

### When I say "continue where we left off":
Read this CLAUDE.md and tell me the current state before we start working.

---

## Folder Structure

```
lasik-surgeons-atlanta/
├── index.html          # Homepage
├── doctors/            # Doctor profile pages
├── practices/          # Practice listing pages
├── styles/             # CSS
├── scripts/            # Generator script
├── data/               # JSON data files
└── images/             # Doctor/practice photos
```

## Quick Commands

```bash
# Generate site
node scripts/generate-site.js
```

---

## Session Log

### 2024-12-25
- Added Claude Sync configuration

### Previous Work
- Built site with 16+ doctor profiles
- 7 practice listings
- SEO optimized with Schema.org markup
- Deployed to Vercel at lasiksurgeonsatlanta.com
