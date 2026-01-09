# Project: OpticianStudy

> Claude Sync Enabled

## CRITICAL SHORTCUTS - Use These!

### "ss" - Save Session (use before closing)
**When user says "ss", "save", or "save session", do ALL of the following:**
1. Update this CLAUDE.md with detailed notes (problems, solutions, dead ends, files changed)
2. Add to Lessons Learned if we discovered something important
3. Document approaches that didn't work so we don't repeat them
4. Create structured summary (Problem → Root Cause → Solution → Files → Next Steps)
5. Commit to git with descriptive message and push
6. List pending tasks for next session

### "rr" - Resume/Read (use at start of session)
**When user says "rr", "resume", or "read project", do ALL of the following:**
1. Read this CLAUDE.md file completely
2. Read any other .md files in the project root
3. Run `git log --oneline -10` to see recent changes
4. Run `git status` to see current state
5. Summarize: what we were working on, current status, and pending tasks
6. Ask if user wants to continue where we left off or start something new

---

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
