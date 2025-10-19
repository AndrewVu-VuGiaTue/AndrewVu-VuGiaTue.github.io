# Personal Website - Gia Tue Vu

A modern, bilingual personal portfolio website with smooth animations and professional design.

## 🚀 Quick Start

### Method 1: Open Directly in Browser (Easiest)

1. Open File Explorer
2. Navigate to `D:\Personal Website`
3. Double-click `vugiatue.html`
4. The website will open in your default browser

### Method 2: VS Code Live Server (Recommended)

1. Open VS Code
2. Open folder: `File → Open Folder → D:\Personal Website`
3. Install "Live Server" extension (if not installed):
   - Press `Ctrl+Shift+X`
   - Search for "Live Server"
   - Click "Install"
4. Right-click on `vugiatue.html`
5. Select "Open with Live Server"
6. Website will open at `http://localhost:5500/vugiatue.html`

**Benefit**: Auto-reload when you edit code

### Method 3: Python HTTP Server

1. Open PowerShell or Command Prompt
2. Navigate to project directory:
   ```powershell
   cd "D:\Personal Website"
   ```
3. Run Python HTTP server:
   ```powershell
   # Python 3
   python -m http.server 8000
   
   # Python 2
   python -m SimpleHTTPServer 8000
   ```
4. Open browser and visit: `http://localhost:8000/vugiatue.html`

### Method 4: Node.js http-server

1. Install http-server (one-time only):
   ```powershell
   npm install -g http-server
   ```
2. Navigate to directory:
   ```powershell
   cd "D:\Personal Website"
   ```
3. Run server:
   ```powershell
   http-server
   ```
4. Open browser and visit: `http://localhost:8080/vugiatue.html`

---

## ✨ Key Features

✅ **Responsive Design** - Works seamlessly on all devices
✅ **Modern UI/UX** - Clean, professional interface inspired by modern portfolio websites
✅ **🌐 Multi-language Support** - **English (Default) & Vietnamese** with language switcher
✅ **Smooth Animations** - Fade-in effects, parallax scrolling, and smooth transitions
✅ **Hero Section Animation** - Sequential fade-in effects on page load
✅ **Transparent Navigation** - Navigation becomes solid when scrolling
✅ **Parallax Effect** - Background moves with scroll (desktop only)
✅ **Scroll Reveal** - Sections fade in when scrolling into view
✅ **Gradient Text** - Eye-catching gradient headings
✅ **Enhanced Typography** - Professional fonts (Inter & Playfair Display)
✅ **Scroll Indicator** - Animated arrow pointing down in hero section
✅ **Button Hover Effects** - Shimmer effect on hover
✅ **LocalStorage Language Preference** - Remembers language choice
✅ **Portfolio Showcase** - Display projects and achievements
✅ **Contact Form** - Interactive contact form

---

## 🌐 Multi-language Feature

### Supported Languages:
- 🇺🇸 **English** (Default)
- 🇻🇳 **Vietnamese**

### How to Use:

1. **Switch Language:**
   - Click the 🌐 icon in the top-right navigation bar
   - Select **English** or **Vietnamese** from the dropdown menu
   - Website switches instantly

2. **Language Persistence:**
   - Your language choice is saved to `localStorage`
   - Next time you visit, the website will display your preferred language

3. **Location:**
   - Desktop: Top-right corner of navigation bar
   - Shows current language code (EN/VI)
   - Dropdown menu with country flags 🇺🇸 🇻🇳

### Translated Sections:
- ✅ Navigation menu
- ✅ Hero section (greeting, subtitle, buttons)
- ✅ About section (title, paragraphs)
- ✅ All section headings & subtitles
- ✅ Scroll indicators
- ✅ Call-to-action buttons

---

## 📂 Projects Page

The website features a **dedicated projects page** (`projects.html`) that opens in a new tab:

- **Separate Page**: Click "Projects" in navigation to open the projects showcase in a new tab
- **Focused View**: Dedicated space to display all your technical projects
- **Bilingual Support**: Full English/Vietnamese translation support
- **Enhanced Cards**: Beautiful project cards with gradient overlays
- **Interactive**: Hover effects, animations, and scroll reveals
- **Quick Navigation**: Easy access back to home page from navigation bar

### Features:
- ✅ Grid layout with responsive design
- ✅ Project cards with images, descriptions, and tech stacks
- ✅ "View Demo" and "Code" buttons for each project
- ✅ "More projects coming soon" section
- ✅ Same styling and animations as main page
- ✅ Language switcher with localStorage persistence

---

## 🎨 Animation Features

### 1. Hero Section Animations
- Fade-in for profile image
- Sequential fade-in for heading, subtitle, and buttons
- Gradient text effect for name
- Hover scale effect for avatar

### 2. Navigation Effects
- Transparent at top of page
- Becomes solid white when scrolling > 100px
- Smooth transitions between states

### 3. Scroll Animations
- **Parallax Background** - Hero background moves slower than content (desktop only)
- **Scroll Reveal** - All sections fade in when entering viewport
- **Scroll Indicator** - Bouncing arrow animation at bottom of hero

### 4. Button Hover Effects
- Shimmer effect on hover
- Lift up effect (translateY)
- Shadow enhancement
- Color transitions

### 5. Typography
- **Playfair Display** (Display font) - Elegant serif for headings
- **Inter** (Sans-serif) - Modern, readable for body text
- **Pacifico** (Script) - Playful for logo
- **Gradient Text** - Gradient for section titles

---

## 📁 File Structure

```
D:\Personal Website\
├── vugiatue.html              # Homepage (Hero + Skills)
├── about.html                 # About Me page
├── projects.html              # Projects showcase
├── awards.html                # Honors & Awards page
├── blog.html                  # Blog & Insights
├── contact.html               # Contact form
├── README.md                  # This file
├── CHANGELOG.md               # Version history
├── LANGUAGE-GUIDE.md          # Language feature guide
├── HOW-TO-TEST.md             # Testing instructions
├── PAGE-CREATION-GUIDE.md     # Guide for creating pages
└── IMPLEMENTATION-SUMMARY.md  # Complete setup summary
```

---

## 🛠️ Technologies Used

- **HTML5** - Structure and content
- **TailwindCSS 3.4.16** - Utility-first CSS framework
- **RemixIcon 4.6.0** - Modern icon library
- **JavaScript (ES6+)** - Interactivity and animations
- **CSS3 Animations** - Keyframe animations and transitions
- **Intersection Observer API** - Scroll reveal effects
- **LocalStorage API** - Language preference storage
- **Google Fonts**
  - **Inter** (300-800 weights) - Body text
  - **Playfair Display** (600-800 weights) - Headings
  - **Pacifico** - Logo

---

## 🎯 Design Inspiration

- Modern portfolio websites with clean aesthetics
- Smooth animation principles
- Professional typography hierarchy
- Accessible and user-friendly interface

---

## 📝 Notes

- This HTML file uses CDN for TailwindCSS and RemixIcon, requires internet connection for full display
- Images are loaded from external API, may take a few seconds on first load
- Best compatibility with Chrome, Firefox, Safari, and Edge (latest versions)
- JavaScript must be enabled for full functionality

---

## 📞 Contact

- **Email**: vgt2800@gmail.com
- **Phone**: (+84) 914 654 745
- **Website**: [andrewvu-vugiatue.github.io](https://andrewvu-vugiatue.github.io/)

---

## 📖 Documentation

For more detailed information:
- **CHANGELOG.md** - Version history and updates
- **LANGUAGE-GUIDE.md** - Complete language feature guide
- **HOW-TO-TEST.md** - Testing checklist and instructions

---

**Created by Gia Tue Vu** | © 2024 All rights reserved
