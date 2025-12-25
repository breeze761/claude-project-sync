# Project: OpticianStudy

> Claude Sync Enabled

## Quick Context
Educational platform for optician certification training at opticianstudy.com. Next.js app with subscription-based study materials.

## Current State
- Working: User auth, subscription system, study materials, calculators
- In Progress: SEO optimization, glossary pages expansion
- Blocked: None

## Tech Stack
- Framework: Next.js (React)
- Database: PostgreSQL on Railway
- Hosting: Vercel

## Sync Config
SYNC_URL=https://claude-sync-api.vercel.app
SYNC_KEY=72ab20994f8b1eab933b5cf5d62a08f0bcc803437ccf7a1318d10e04a7bd2d3e
PROJECT=opticianstudy

---

## Commands

### When I say "sync this session":
1. Update this CLAUDE.md with what we accomplished
2. Run this curl command:
```bash
curl -X POST https://claude-sync-api.vercel.app/sync/opticianstudy \
  -H "Authorization: Bearer 72ab20994f8b1eab933b5cf5d62a08f0bcc803437ccf7a1318d10e04a7bd2d3e" \
  -H "Content-Type: application/json" \
  -d '{"summary": "WRITE_SESSION_SUMMARY_HERE", "claude_md": "PASTE_UPDATED_CLAUDE_MD_HERE"}'
```
3. Run: git add -A && git commit -m "Sync: SESSION_SUMMARY" && git push
4. Output this block for Claude.ai memory (copy/paste to Claude.ai):
```
=== CLAUDE.AI MEMORY UPDATE ===
PROJECT: OpticianStudy (opticianstudy.com)
DATE: [TODAY'S DATE]
ACCOMPLISHED: [BULLET LIST OF WHAT WE DID]
CURRENT STATE: [WHAT'S WORKING/IN PROGRESS/BLOCKED]
NEXT STEPS: [WHAT TO DO NEXT SESSION]
================================
```

### When I say "continue where we left off":
Read this CLAUDE.md and tell me the current state before we start working.

---

## Session Log

### 2024-12-25
- Initial CLAUDE.md created for sync system
