# Tampermonkey Scripts

## Custom Crex (v1.8)

A Tampermonkey userscript for crex.com that adds TTS (Text-to-Speech) score announcements and fixes theme persistence for live cricket matches.

### Features

1. **TTS Score Announcer**
   - Announces score changes during live matches
   - Announces over summaries with runs, wickets, and overs
   - Customizable voice selection
   - Volume control with slider
   - Mute/unmute toggle (keyboard shortcut: 'm')

2. **Theme Persistence Fix** (v1.8 - Properly Implemented)
   - Fixes crex.com's broken theme persistence
   - Automatically saves your theme preference (dark/light) to cookies
   - Restores your theme on page reload and navigation
   - Works exactly how the site intends it to work

3. **Fixed Duplicate Controls Issue** (v1.6)
   - Resolved issue where controls (especially volume slider) appeared multiple times
   - Improved URL change detection and script initialization

### How Theme Persistence Works

After inspecting crex.com's actual code, the script now properly implements theme persistence:

**How crex.com's theme system works:**
- Stores theme in cookie named `system-theme` with value `'dark'` or `'light'`
- Uses `data-theme` attribute on the `<html>` element
- Site has inline script that tries to read cookie and apply theme on load

**What the script does:**
1. On page load, checks if `system-theme` cookie exists
2. If cookie exists, applies it to `data-theme` attribute on `<html>`
3. If no cookie but theme is set in HTML, saves it to cookie
4. Monitors the `data-theme` attribute for changes (when you click toggle)
5. When theme changes, updates the cookie with 1-year expiration

**This fixes the site's broken persistence** - The site's native implementation doesn't properly maintain the cookie, so theme resets on reload. This script ensures the cookie persists correctly.

### Installation

1. Install Tampermonkey browser extension
2. Create a new script in Tampermonkey
3. Copy the contents of `Custom Crex` file
4. Save and enable the script
5. Visit crex.com and set your preferred theme
6. Theme will now persist across page reloads and navigation

### Technical Details

**Theme Implementation:**
- Storage: Cookie `system-theme` (not localStorage)
- DOM Target: `<html>` element with `data-theme` attribute
- Values: `'dark'` or `'light'`
- Cookie Expiration: 1 year
- No CSS classes used for theming

**Previous Issues (v1.7):**
- ❌ Used localStorage instead of cookies
- ❌ Looked for CSS classes that don't exist
- ❌ Applied theme incorrectly

**Current Implementation (v1.8):**
- ✅ Uses cookie `system-theme` (same as site)
- ✅ Monitors only `data-theme` attribute on `<html>`
- ✅ Applies theme correctly via attribute
- ✅ Works with site's native theme system

