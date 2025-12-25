# Project: Gazal Lens Builder

> Claude Sync Enabled

## Quick Context
Custom lens tint builder for Gazal Eyecare. First-to-market interactive tool with real-time gradient preview for sun lenses. Single-page HTML app with no framework dependencies.

## Current State
- Working: Lens tint selection, gradient preview, color controls, PD measurement
- In Progress: UI polish, additional lens options
- Blocked: None

## Tech Stack
- Framework: Vanilla HTML/CSS/JavaScript (single file)
- Server: Node.js Express (local dev server)
- Hosting: Local network at Gazal Eyecare

## Key Files
- `public/index-test.html` - **CURRENT PRODUCTION** (running at Gazal Eyecare shop)
- `public/index.html` - Previous version
- `public/lens305.html` - Numbered version (consider consolidating)
- `server.js` - Profile API server (port 3001)
- `START-LENS-BUILDER.bat` - Starts both servers and opens browser

## How to Run
Run `START-LENS-BUILDER.bat` which:
1. Starts Profile API on http://localhost:3001
2. Starts http-server on http://localhost:8080 (serves `public/` folder)
3. Opens http://localhost:8080/index-test.html

## Development Guidelines
All development should be done in `public/index-test.html`. The numbered versions in `backup/` folder (lens1 through lens227) are archived.

## Sync Config
SYNC_URL=https://claude-sync-api.vercel.app
SYNC_KEY=72ab20994f8b1eab933b5cf5d62a08f0bcc803437ccf7a1318d10e04a7bd2d3e
PROJECT=lens-builder

---

## Commands

### When I say "sync this session":
1. Update this CLAUDE.md with what we accomplished
2. Run this curl command:
```bash
curl -X POST https://claude-sync-api.vercel.app/sync/lens-builder \
  -H "Authorization: Bearer 72ab20994f8b1eab933b5cf5d62a08f0bcc803437ccf7a1318d10e04a7bd2d3e" \
  -H "Content-Type: application/json" \
  -d '{"summary": "WRITE_SESSION_SUMMARY_HERE", "claude_md": "PASTE_UPDATED_CLAUDE_MD_HERE"}'
```
3. Run: git add -A && git commit -m "Sync: SESSION_SUMMARY" && git push
4. Output this block for Claude.ai memory (copy/paste to Claude.ai):
```
=== CLAUDE.AI MEMORY UPDATE ===
PROJECT: Lens Builder (Gazal Eyecare)
DATE: [TODAY'S DATE]
ACCOMPLISHED: [BULLET LIST OF WHAT WE DID]
CURRENT STATE: [WHAT'S WORKING/IN PROGRESS/BLOCKED]
NEXT STEPS: [WHAT TO DO NEXT SESSION]
================================
```

### When I say "continue where we left off":
Read this CLAUDE.md and tell me the current state before we start working.

---

## Quick Commands

```bash
# Start dev server
node server.js

# Or use batch file
START-LENS-BUILDER.bat
```

---

## Session Log

### 2024-12-25
- Added Claude Sync configuration
- Converted from numbered versions to git-tracked single file approach

### Previous Work
- Built lens tint builder with gradient preview
- PD measurement functionality
- Multiple iterations (lens144 through lens227)
