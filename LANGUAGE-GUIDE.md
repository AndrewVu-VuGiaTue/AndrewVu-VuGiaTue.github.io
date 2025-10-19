# 🌐 Language Switcher - Quick Guide

Complete guide for using the multi-language feature

---

## 📖 Introduction

The website supports **2 languages**:
- 🇺🇸 **English** - **Default**
- 🇻🇳 **Vietnamese** (Tiếng Việt)

You can switch between languages easily at any time!

---

## 🎯 How to Switch Languages

### Step 1: Find the Language Switcher
Look at the **top-right corner** of the navigation bar, you'll see:

```
🌐 EN ▼
```

- **🌐** = Globe icon
- **EN** or **VI** = Current language
- **▼** = Down arrow (dropdown menu available)

### Step 2: Open Menu
- **Hover** your mouse over the 🌐 EN icon
- Dropdown menu will automatically appear

### Step 3: Select Language
Menu displays 2 options:

```
┌─────────────────┐
│ 🇺🇸 English     │ ← Click for English
│ 🇻🇳 Tiếng Việt  │ ← Click for Vietnamese
└─────────────────┘
```

### Step 4: Enjoy!
- Website switches **instantly**
- No page reload required
- Your language choice is **automatically saved**

---

## ✨ Key Features

### 1. 🔄 Instant Switching
- No delay, no reload
- Smooth transition < 100ms

### 2. 💾 Auto-Save
- Language saved to `localStorage`
- Next visit displays your chosen language

### 3. 🎨 Visual Feedback
- Active language **highlighted** in red
- Hover effect on menu options

### 4. 📱 Responsive
- Works on Desktop, Tablet, Mobile
- UI automatically adjusts to screen size

---

## 🔍 Translated Sections

All important content is fully translated:

| Section | English | Vietnamese |
|---------|---------|------------|
| **Navigation** | Home, About, Skills, Projects, Blog, Contact | Trang chủ, Giới thiệu, Kỹ năng, Dự án, Blog, Liên hệ |
| **Hero** | Greetings from Hanoi, Vietnam! | Xin chào từ Hà Nội, Việt Nam! |
| **CTA Buttons** | Explore More, Get in Touch | Khám phá thêm, Liên hệ ngay |
| **Section Titles** | About Me, Skills & Technologies, etc. | Giới thiệu về tôi, Kỹ năng & Công nghệ, etc. |
| **About Content** | Full paragraphs | Complete paragraphs |

---

## 🖥️ Visual Demo

### When English (EN) is selected:
```
🌐 EN ▼

┌─────────────────┐
│ 🇺🇸 English   ✓ │ ← Active (light red background)
│ 🇻🇳 Tiếng Việt  │
└─────────────────┘

Hero Section:
"Greetings from Hanoi, Vietnam!"
"Computer Science student at High School..."
```

### When Vietnamese (VI) is selected:
```
🌐 VI ▼

┌─────────────────┐
│ 🇺🇸 English     │
│ 🇻🇳 Tiếng Việt ✓ │ ← Active (light red background)
└─────────────────┘

Hero Section:
"Xin chào từ Hà Nội, Việt Nam!"
"Học sinh chuyên Tin học tại Trường THPT..."
```

---

## 💡 Tips & Tricks

### Tip 1: Keyboard Shortcuts (Future)
Currently no keyboard shortcuts, but planned for future:
- Expected: `Ctrl + L` or `Alt + L` to open menu

### Tip 2: URL Parameters (Future)
Possible to add `?lang=vi` or `?lang=en` to URL to force language:
```
https://yoursite.com?lang=vi  ← Vietnamese
https://yoursite.com?lang=en  ← English
```

### Tip 3: Default Language
- First visit: **English (default)**
- After selection: Website remembers your choice

### Tip 4: Clear Preference
To reset to default, open Console (F12) and run:
```javascript
localStorage.removeItem('preferredLanguage');
location.reload();
```

---

## 🎬 Usage Scenario

**Scenario 1**: First-time Visitor (Vietnamese speaker)
```
1. Opens website → sees English
2. Notices 🌐 EN in corner
3. Hovers → sees menu with 🇻🇳 flag
4. Clicks Tiếng Việt
5. ✅ Website switches to Vietnamese instantly
6. ✅ Comfortable reading in native language
```

**Scenario 2**: Returning Visitor
```
1. Visited yesterday, chose Vietnamese
2. Returns today
3. ✅ Website remembers preference
4. ✅ Shows Vietnamese automatically
5. No need to switch again
```

**Scenario 3**: International Reviewer
```
1. Opens website → sees English (default)
2. ✅ Can immediately understand content
3. Notices language option available
4. ✅ Appreciates professional bilingual setup
```

---

## 🔧 Technical Details (For Developers)

### How it works:

1. **Data Structure**:
```javascript
const translations = {
  en: { nav: {...}, hero: {...}, about: {...} },
  vi: { nav: {...}, hero: {...}, about: {...} }
};
```

2. **HTML Markup**:
```html
<h1 data-i18n="hero.title">Default Text</h1>
```

3. **JavaScript Function**:
```javascript
function switchLanguage(lang) {
  // Update all elements with data-i18n
  // Save to localStorage
  // Update UI
}
```

4. **Storage**:
```javascript
localStorage.setItem('preferredLanguage', 'vi');
const lang = localStorage.getItem('preferredLanguage') || 'en';
```

---

## 🐛 Troubleshooting

### Issue: Language doesn't switch
**Solution**: 
- Refresh page (F5)
- Clear cache (Ctrl + Shift + Del)
- Check if JavaScript is enabled

### Issue: Menu doesn't appear
**Solution**:
- Ensure JavaScript has loaded
- Check Console (F12) for errors

### Issue: Language preference not saved
**Solution**:
- Check if LocalStorage is enabled
- Try in normal mode (not incognito)
- Check browser storage permissions

---

## 📞 Support

If you encounter issues or have questions:
- **Email**: vgt2800@gmail.com
- **Phone**: (+84) 914 654 745

---

## 🎓 Learn More

Want to learn more about the implementation?
- Read `README.md` - Technical details
- Read `CHANGELOG.md` - Development history
- View source code - `vugiatue.html` (lines 1708-1847)

---

**Created with ❤️ by Gia Tue Vu**
*Making the web accessible to everyone, regardless of language!*
