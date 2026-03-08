# Tampermonkey Scripts

## Custom Crex (v1.9)

A Tampermonkey userscript for crex.com that adds TTS (Text-to-Speech) score announcements and fixes theme persistence for live cricket matches.

### Features

1. **TTS Score Announcer**
   - Announces score changes during live matches
   - Announces over summaries with runs, wickets, and overs
   - Customizable voice selection
   - Volume control with slider
   - Mute/unmute toggle (keyboard shortcut: 'm')

2. **Flicker-Free Theme Persistence** (v1.9 - Optimized)
   - Fixes crex.com's broken theme persistence
   - **No theme flicker** on page load - theme applied before page renders
   - Automatically saves your theme preference (dark/light) to cookies
   - Restores your theme instantly on page reload and navigation
   - Works exactly how the site intends it to work

3. **Fixed Duplicate Controls Issue** (v1.6)
   - Resolved issue where controls (especially volume slider) appeared multiple times
   - Improved URL change detection and script initialization

### How Theme Persistence Works

**Key Improvement in v1.9:**
- Script now runs at `document-start` (instead of `document-idle`)
- Theme is applied **immediately** before the page renders
- Eliminates the theme flicker that occurred in v1.8

**Implementation Details:**
After inspecting crex.com's actual code, the script properly implements theme persistence:

**How crex.com's theme system works:**
- Stores theme in cookie named `system-theme` with value `'dark'` or `'light'`
- Uses `data-theme` attribute on the `<html>` element
- Site has inline script that tries to read cookie and apply theme on load

**What the script does:**
1. **Immediately** (at document-start) reads `system-theme` cookie
2. Applies theme to `data-theme` attribute on `<html>` before page renders
3. On DOM ready, sets up monitoring for theme changes
4. When theme changes (user clicks toggle), updates the cookie with 1-year expiration
5. Ensures cookie persists correctly across sessions

**This fixes the site's broken persistence** - The site's native implementation doesn't properly maintain the cookie, so theme resets on reload. This script ensures the cookie persists correctly with no flicker.

### Installation

1. Install Tampermonkey browser extension
2. Create a new script in Tampermonkey
3. Copy the contents of `Custom Crex` file
4. Save and enable the script
5. Visit crex.com and set your preferred theme
6. Theme will now persist across page reloads and navigation **without any flicker**

### Technical Details

**Theme Implementation:**
- Storage: Cookie `system-theme` (not localStorage)
- DOM Target: `<html>` element with `data-theme` attribute
- Values: `'dark'` or `'light'`
- Cookie Expiration: 1 year
- Script Timing: `document-start` (critical for flicker-free loading)
- No CSS classes used for theming

**Version History:**
- v1.9: Eliminated theme flicker by running at document-start
- v1.8: Fixed theme persistence using cookies
- v1.6: Fixed duplicate controls issue
- v1.5: Initial TTS implementation

