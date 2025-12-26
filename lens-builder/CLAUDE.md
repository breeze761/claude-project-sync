# Project: Gazal Lens Builder

> Claude Sync Enabled

## Quick Context
Custom lens tint builder for Gazal Eyecare. First-to-market interactive tool with real-time gradient preview for sun lenses. Single-page HTML app with no framework dependencies. Now includes **Customer Profile System** for boutique mode.

## Current State
- Working: Lens tint selection, gradient preview, color controls, PD measurement, **Customer Profiles**, **Boutique Mode**, **Save/Load with Thumbnails**
- In Progress: None - ready for shop testing
- Blocked: None

## Tech Stack
- Framework: Vanilla HTML/CSS/JavaScript (single file)
- Server: Node.js (Profile API on port 3001, http-server on port 8080)
- Storage: JSON file (`public/data/profiles.json`) synced via OneDrive
- Hosting: Local network at Gazal Eyecare

## Key Files
- `public/index.html` - **CURRENT PRODUCTION** (with profile system)
- `public/index-test.html` - Previous test version (deprecated)
- `server.js` - Profile API server (port 3001)
- `START-LENS-BUILDER.bat` - **One-click startup** - starts both servers and opens boutique mode
- `public/data/profiles.json` - Customer profiles storage
- `BASELINE-2024-12-25.md` - Pre-profile system documentation (rollback reference)

## How to Run
Run `START-LENS-BUILDER.bat` which:
1. Starts Profile API on http://localhost:3001
2. Starts http-server on http://localhost:8080 (serves `public/` folder)
3. Opens http://localhost:8080/index.html?mode=boutique (auto boutique mode)

## Customer Profile System

### Features
- **Boutique Mode**: Always-on (no URL parameter needed) - customer selection flow automatic
- **New Customer**: Name, email, DOB form with duplicate email detection
- **Returning Customer**: Search by name, email, or DOB
- **Customer Banner**: Gold banner at top shows current customer
- **Save to Profile**: Save lens configurations with custom names and thumbnail previews
- **View Saved**: Load or delete saved lens designs with thumbnail preview
- **Persistence**: Profiles saved to JSON file, syncs across shop computers via OneDrive

### Key Functions
- `loadProfiles()` / `saveProfiles()` - API + localStorage fallback
- `saveNewCustomer()` - Create customer with validation
- `searchCustomers()` - Real-time search
- `setCurrentCustomer()` - Set active customer, show banner
- `confirmSaveToProfile()` - Save lens config to customer
- `loadCustomerLens()` - Load saved configuration

### Modals
- `boutiqueWelcomeModal` - New/Returning Customer selection
- `newCustomerModal` - Create profile form
- `customerSearchModal` - Search existing customers
- `saveToProfileModal` - Name and save lens design
- `customerLensesModal` - View/load/delete saved lenses
- `currentCustomerBanner` - Shows selected customer

## Development Guidelines
All development should be done in `public/index.html`. The `index-test.html` version is now deprecated.

---

## Roadmap / To-Do List

### Priority 0: Bug Fixes
- [ ] Fix scrollbar in controls section (add `overflow: hidden`)
- [ ] Hide Previous button on Step 1
- [ ] Add null checks in `selectLensType()` for controls
- [ ] Increase modal z-index to 10002
- [ ] Fix accordion collapse behavior (one opens, others close)
- [ ] Add Shopify `addToCart()` placeholder function

### Priority 1: Mobile-Friendly Version
- [ ] Responsive layout for phones/tablets
- [ ] Touch-friendly controls (larger buttons, swipe gestures)
- [ ] Mobile-optimized lens preview
- [ ] Test on iOS and Android devices

### Priority 2: Shopify Integration (Future)
- [ ] Create `index-shopify.html` version (localStorage only, no server needed)
- [ ] OR: Set up cloud backend (Firebase/Supabase) for profile sync
- [ ] Remove Node.js server dependency for Shopify hosting
- [ ] **IMPORTANT**: Replace Nodemailer email with Shopify Email API or third-party service (current server.js email won't work on Shopify)
- [ ] Test embed in Shopify theme

### Priority 3: Enhancements
- [x] Export lens design as PNG image - **DONE**
- [x] Email lens design to customer - **DONE**
- [x] Print-friendly summary page - **DONE**

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
# Start dev server (both at once)
START-LENS-BUILDER.bat

# Or manually:
node server.js                    # Profile API (port 3001)
npx http-server ./public -p 8080  # Web server (port 8080)

# Access URLs:
# Boutique Mode: http://localhost:8080/index.html?mode=boutique
# Standard Mode: http://localhost:8080/index.html
```

---

## Session Log

### 2024-12-26 (Session 6)
- **Custom Email Modal** - Replaced browser prompt with styled modal (gold/black theme)
- **Lens Images in Email** - Embedded PNG thumbnails using CID attachment
- **SVG to PNG Conversion** - Added `sharp` npm package to convert SVG thumbnails server-side
- **Social Sharing** - Added Reddit (featured), Facebook, X, Pinterest, Instagram buttons
- **Reddit Optimization** - SEO-friendly pre-filled titles for AI search discovery
- **Async Thumbnail Capture** - New `captureLensThumbnailAsync()` saves as PNG instead of SVG
- Committed and pushed: `074b87f`

### 2024-12-25 (Session 5)
- Implemented **Server-Side Email** with Nodemailer (sends from andy@gazaleyewear.com)
- Created `.env` file for secure email credential storage
- Updated `.gitignore` to protect credentials from git commits
- Updated `emailLensDesign()` and `emailSavedLens()` to use server API with mailto fallback
- Added email validation and different templates for customer vs lab emails
- Configured Gmail App Password for secure authentication
- Added Shopify email integration warning to roadmap
- Verified social share feature already implemented (URL-based config sharing)

### 2024-12-25 (Session 4)
- Added **Export as Image** feature - downloads lens design as PNG with Gazal branding
- Added **Print Summary** feature - opens print-friendly page with lens specs
- Added **Email Design** feature - opens email client with lens configuration
- Added export/print/email buttons to both Prescription (Step 4) and Plano (Step 3) final steps
- Updated roadmap with **Priority 0** bug fixes from index-test.html (LENS306/LENS307)
- Identified pending bug fixes that need to be ported from index-test.html

### 2024-12-25 (Session 3)
- Made **Boutique Mode always-on** - no URL parameter needed
- Fixed **View Saved button** - now correctly opens customer's saved lenses modal
- Fixed **savedLensesGrid element ID** mismatch preventing lenses from displaying
- Added **thumbnail capture** when saving lens configurations
- Added **thumbnail display** in saved lenses list
- Verified **Load functionality** works correctly to restore all lens settings
- Customers can now save 10+ lens designs and reload them later with full settings preserved

### 2024-12-25 (Session 2)
- **Ported Customer Profile System** from index-test.html to index.html
- Added 6 profile modals (welcome, new customer, search, banner, save, view lenses)
- Added 20+ profile management functions
- Updated START-LENS-BUILDER.bat to auto-open boutique mode
- Created BASELINE-2024-12-25.md for rollback reference
- Created profile-system-tests.html for testing
- Profile API server (server.js) confirmed working on port 3001
- Profiles save to public/data/profiles.json (OneDrive synced)

### 2024-12-25 (Session 1)
- Updated Anti-Glare card verbiage: "Standard Coating" and "Premium Anti-Glare"
- Created comprehensive todo list for bug fixes from LENS306/LENS307
- Analyzed differences between index.html and index-test.html

### 2024-12-25
- Added Claude Sync configuration
- Converted from numbered versions to git-tracked single file approach

### Previous Work
- Built lens tint builder with gradient preview
- PD measurement functionality
- Multiple iterations (lens144 through lens227)
