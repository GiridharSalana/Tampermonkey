# Tampermonkey Scripts 🚀

A collection of modern, feature-rich Tampermonkey userscripts that enhance your web browsing experience with beautiful UIs and powerful functionality.

---

## 📜 Scripts

### Custom Crex (v4.2) 🎤🏏

Enhance your crex.com live cricket match experience with TTS score announcements, theme persistence, and a beautiful glassmorphism UI.

### ✨ Features

#### 1. **TTS Score Announcer**
- 🔊 Real-time ball-by-ball score announcements
- 📢 Over summaries with runs, wickets, and overs
- 🎙️ Modal voice selector with all available system voices
- 🎚️ Smooth volume control slider
- 🔇 Mute/unmute toggle (keyboard shortcut: 'M')
- 💾 Remembers your voice and volume preferences

#### 2. **Modern Glassmorphism UI** (v4.0+)
- 🎨 Beautiful frosted glass control bar
- 🎤 Modal voice selector with professional design
- ✨ Smooth hover effects and animations
- 🔵 Blue accent colors with elegant shadows
- 📱 Compact, centered design that doesn't interfere with content
- 🎭 Backdrop blur effects for premium look

#### 3. **Flicker-Free Theme Persistence** (v1.9+)
- 🌗 Fixes crex.com's broken theme persistence
- ⚡ Zero flicker - theme applied before page renders
- 🍪 Automatically saves theme preference to cookies
- 🔄 Instant theme restoration on reload/navigation
- 🔧 Works with the site's native theme system

#### 4. **Bulletproof Implementation**
- ✅ No duplicate controls
- ✅ Works with SPA navigation
- ✅ Proper cleanup on page changes
- ✅ Error handling for edge cases
- ✅ Optimized performance

### 🎨 UI Design

**Compact Control Bar:**
```
┌─────────────────────────────────────┐
│  🎤  [🔉 ━━━●━━━ 🔊]  🔇         │
└─────────────────────────────────────┘
```

- **Voice Icon (🎤)**: Click to open modal with all voices
- **Volume Slider**: 120px smooth range slider with hover effects
- **Mute Button**: Circular button with glow effect
- **Glassmorphism**: Frosted glass background with blur
- **Smooth Animations**: Scale, fade, and transform effects

**Modal Voice Selector:**
- Full-screen overlay with blur
- Centered, scrollable voice list
- Selected voice highlighted in blue
- Close with ✕ button or click outside
- Smooth fade-in/slide-in animations

### 📦 Installation

#### Quick Install (Recommended)
```
1. Install Tampermonkey extension in your browser
2. Click this link: https://cdn.jsdelivr.net/gh/GiridharSalana/Tampermonkey@main/Custom%20Crex
3. Click "Install" when Tampermonkey opens
4. Visit crex.com and enjoy!
```

#### Manual Install
```
1. Install Tampermonkey browser extension
2. Open Tampermonkey dashboard
3. Click "Create a new script"
4. Copy contents from: https://github.com/GiridharSalana/Tampermonkey/blob/main/Custom%20Crex
5. Save (Ctrl+S)
6. Visit crex.com
```

### 🎮 Usage

1. **Navigate** to any live match on crex.com
2. **Controls appear** below the score header
3. **Click 🎤** to select your preferred voice
4. **Adjust volume** with the slider
5. **Press M** to mute/unmute anytime
6. **Enjoy** real-time score announcements!

### 🛠️ Technical Details

**Architecture:**
- Runs at `document-start` for flicker-free theme loading
- MutationObserver for score change detection
- Event-driven voice popup system
- Glassmorphism CSS with backdrop-filter
- localStorage for preferences, cookies for theme

**Theme Implementation:**
- Cookie: `system-theme` (not localStorage)
- DOM: `data-theme` attribute on `<html>`
- Values: `'dark'` or `'light'`
- Expiration: 1 year
- Zero flicker with pre-render application

**Controls Implementation:**
- Container: `.team-result > div` (inside score header)
- Modal: Fixed position overlay with z-index: 100000
- Voice loading: On-demand when modal opens
- Animations: CSS transitions (0.2-0.3s ease)

### 📝 Version History

- **v4.2** (Current): Professional modal voice selector
- **v4.1**: Fixed voice loading in popup
- **v4.0**: Modern glassmorphism UI overhaul
- **v3.4**: Margin-based spacing, 180px width
- **v3.0-3.3**: Single-line layout iterations
- **v2.0-2.9**: UI improvements and positioning fixes
- **v1.9**: Eliminated theme flicker
- **v1.8**: Fixed theme persistence with cookies
- **v1.6**: Fixed duplicate controls
- **v1.5**: Initial TTS implementation

### 🎯 Key Improvements from v1.0 → v4.2

| Feature | v1.0 | v4.2 |
|---------|------|------|
| UI Design | Basic dropdowns | Glassmorphism modal |
| Theme | Broken | Flicker-free |
| Voice Selection | Small dropdown | Full modal |
| Animations | None | Smooth transitions |
| Layout | Two lines | Compact one line |
| Styling | Minimal | Premium design |
| Reliability | Duplicates | Bulletproof |

### 🤝 Contributing

Found a bug or have a suggestion? Open an issue or PR!

### 📄 License

MIT - Feel free to use and modify!

---

**Made with ❤️ for enhancing web experiences**
