# 📝 Changelog - Personal Website

All notable changes to this project will be documented in this file.

---

## [Version 2.0.0] - 2025-10-19

### 🌐 Major Feature: Multi-language Support

#### Added
- **Bilingual Support**: English (default) and Vietnamese
- **Language Switcher**: Dropdown menu in navigation bar with country flags 🇺🇸 🇻🇳
- **LocalStorage Integration**: Remembers user's language preference
- **Seamless Translation**: Instant language switching without page reload
- **data-i18n System**: Attribute-based translation system for easy maintenance

#### Technical Details
```javascript
// Translation Structure
translations = {
  en: { nav, hero, about, skills, projects, blog, contact },
  vi: { nav, hero, about, skills, projects, blog, contact }
}

// Usage
switchLanguage('en') // Switch to English
switchLanguage('vi') // Switch to Vietnamese
```

#### UI/UX Improvements
- Globe icon (🌐) in navigation for easy access
- Current language indicator (EN/VI)
- Elegant dropdown with hover effect
- Active language highlight in menu
- Smooth transitions between languages

### 🎨 Design Changes
- **Default Language**: Changed from Vietnamese to English
- **HTML lang attribute**: Updates dynamically based on selection
- **Navigation Enhancement**: Added language dropdown to header
- **Responsive Design**: Language switcher adapts to all screen sizes

### 📋 Translated Content Sections
- ✅ Navigation Menu (Home, About, Skills, Projects, Blog, Contact)
- ✅ Hero Section (Greeting, Subtitle, CTAs)
- ✅ About Me (Title, Paragraphs, Timeline)
- ✅ Skills & Technologies (Headers)
- ✅ Featured Projects (Headers)
- ✅ Blog & Insights (Headers)
- ✅ Contact Section (Headers, CTAs)
- ✅ Scroll Indicators (Scroll Down text)

### 🔧 Files Modified
- `vugiatue.html` - Added translation system, language switcher UI, data-i18n attributes
- `README.md` - Documented multi-language feature
- `CHANGELOG.md` - Created this changelog

### 📈 Performance
- **Zero Impact**: No additional HTTP requests
- **Lightweight**: ~5KB added for translation data
- **Instant Switch**: < 100ms language transition
- **LocalStorage**: Persistent preference across sessions

---

## [Version 1.0.0] - 2025-10-19

### 🎉 Initial Release

#### Core Features
- **Responsive Design**: Mobile-first approach
- **Modern Animations**: Hero fade-in, scroll reveal, parallax
- **Cornell & Brown Colors**: Official brand color palette
- **Professional Typography**: Inter, Playfair Display, Pacifico
- **Navigation Effects**: Transparent to solid on scroll
- **Portfolio Sections**: About, Skills, Projects, Awards, Experience

#### Design Inspiration
- Inspired by [Anne Vu's Website](https://www.tramanhvu2508.com/)
- Color scheme from [Cornell](https://brand.cornell.edu/design-center/colors/) and [Brown University](https://engineering.brown.edu/resources/communications-creative-resources/logo-visual-identity)

#### Technical Stack
- HTML5 + TailwindCSS 3.4.16
- Vanilla JavaScript (ES6+)
- Google Fonts API
- RemixIcon 4.6.0
- CSS3 Animations & Transitions

---

## 🚀 Roadmap / Future Enhancements

### Planned Features
- [ ] **More Languages**: Add Chinese, Spanish, French
- [ ] **Dark Mode**: Toggle between light and dark themes
- [ ] **Blog Functionality**: Dynamic blog posts with translations
- [ ] **Contact Form Backend**: Functional email sending
- [ ] **Typing Effect**: Animated typing for hero text
- [ ] **Scroll Progress Bar**: Visual scroll indicator
- [ ] **Page Transitions**: Smooth navigation between sections
- [ ] **Accessibility**: ARIA labels, keyboard navigation
- [ ] **SEO Optimization**: Meta tags, Open Graph, structured data
- [ ] **Analytics Integration**: Google Analytics or similar

### Enhancement Ideas
- [ ] Custom cursor effect
- [ ] Mouse parallax (elements follow cursor)
- [ ] Loading screen animation
- [ ] Micro-interactions on hover
- [ ] Sound effects (optional, user-controlled)
- [ ] Export/Print CV functionality
- [ ] Project filtering system
- [ ] Testimonials section
- [ ] Skills progress bars animation
- [ ] Timeline hover effects

---

## 📊 Version History Summary

| Version | Date | Key Features |
|---------|------|--------------|
| 2.0.0 | 2025-10-19 | 🌐 Multi-language Support (EN/VI) |
| 1.0.0 | 2025-10-19 | 🎉 Initial Release with modern design |

---

## 🐛 Bug Fixes

### Version 2.0.0
- Fixed HTML lang attribute to change dynamically
- Improved language dropdown positioning
- Enhanced mobile responsiveness for language switcher

### Version 1.0.0
- Initial stable release (no bugs to fix yet)

---

## 🙏 Acknowledgments

- **Design Inspiration**: [Anne Vu](https://www.tramanhvu2508.com/)
- **Color Palette**: Cornell & Brown Universities
- **Icons**: RemixIcon
- **Fonts**: Google Fonts (Inter, Playfair Display, Pacifico)
- **Framework**: TailwindCSS

---

## 📞 Contact & Support

For questions, suggestions, or bug reports:
- **Email**: vgt2800@gmail.com
- **Phone**: (+84) 914 654 745
- **Website**: [andrewvu-vugiatue.github.io](https://andrewvu-vugiatue.github.io/)

---

**Maintained with ❤️ by Gia Tue Vu**

