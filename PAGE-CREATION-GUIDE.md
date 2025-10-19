# 📄 Page Creation Guide

## Structure Overview

All pages share common elements:
- Same navigation with all 6 menu items
- Cornell & Brown color scheme (Red: #B31B1B, #C00404 | Brown: #653819, #4E3629)
- Responsive design
- Smooth animations
- Language support ready

---

## 📁 Pages to Create

### ✅ **Created:**
1. `vugiatue.html` - Homepage (with Skills section only)
2. `about.html` - About Me page
3. `projects.html` - Projects showcase

### 🔨 **To Create:**
4. `awards.html` - Honors & Awards
5. `blog.html` - Blog & Insights
6. `contact.html` - Contact form & info

---

## 🎨 Design Principles

### Color Usage:
- **Primary Red** (#B31B1B): Headers, CTAs, highlights
- **Secondary Red** (#C00404): Hover states, accents  
- **Cornell Brown** (#653819): Cards, badges
- **Seal Brown** (#4E3629): Gradients, borders
- **White** (#FFFFFF): Background, clean space

### Layout Pattern:
```
[Navigation Bar - White bg, shadow]
    ↓
[Hero Section - Red gradient background, white text]
    ↓
[Main Content - White bg, red/brown accents]
    ↓
[CTA Section - Red gradient, white text] (optional)
    ↓
[Footer - Dark gray]
```

---

## 🧩 Common Components

### Navigation (Copy to all pages):
```html
<header class="bg-white shadow-sm sticky top-0 z-50">
<nav class="px-6 py-4">
<div class="max-w-7xl mx-auto flex items-center justify-between">
<a href="vugiatue.html" class="font-script text-2xl text-primary">Gia Tue Vu</a>
<div class="hidden md:flex items-center space-x-6">
<a href="vugiatue.html" class="text-gray-700 hover:text-primary transition-all duration-300 font-medium">Home</a>
<a href="about.html" class="text-gray-700 hover:text-primary transition-all duration-300 font-medium">About Me</a>
<a href="projects.html" class="text-gray-700 hover:text-primary transition-all duration-300 font-medium">Projects</a>
<a href="awards.html" class="text-gray-700 hover:text-primary transition-all duration-300 font-medium">Honors & Awards</a>
<a href="blog.html" class="text-gray-700 hover:text-primary transition-all duration-300 font-medium">Blog</a>
<a href="contact.html" class="text-gray-700 hover:text-primary transition-all duration-300 font-medium">Contact</a>
</div>
</div>
</nav>
</header>
```

### Hero Section Template:
```html
<section class="py-20 bg-gradient-to-br from-primary via-secondary to-primary text-white relative overflow-hidden">
<div class="absolute inset-0 opacity-10">
<div class="absolute top-10 left-10 w-72 h-72 bg-white rounded-full blur-3xl"></div>
<div class="absolute bottom-10 right-10 w-96 h-96 bg-white rounded-full blur-3xl"></div>
</div>
<div class="max-w-7xl mx-auto px-6 relative z-10">
<div class="text-center fade-in">
<h1 class="text-6xl md:text-7xl font-display font-bold mb-6">[PAGE TITLE]</h1>
<p class="text-xl md:text-2xl font-light max-w-3xl mx-auto opacity-90">
[SUBTITLE]
</p>
</div>
</div>
</section>
```

### Card Component:
```html
<div class="bg-white rounded-xl shadow-sm border border-gray-100 p-6 hover:shadow-lg transition-all">
<div class="w-14 h-14 bg-gradient-to-br from-primary to-secondary rounded-full flex items-center justify-center mb-4">
<i class="ri-[icon]-line text-white text-2xl"></i>
</div>
<h3 class="text-xl font-bold mb-2">[Title]</h3>
<p class="text-gray-600">[Description]</p>
</div>
```

---

## 📝 Page-Specific Content

### **awards.html** - Honors & Awards

**Hero Title:** "Honors & Awards"
**Hero Subtitle:** "Recognition for academic excellence and innovation"

**Content Structure:**
1. **Featured Awards** (Top 3-4) - Large cards with icons
2. **Academic Awards** - Grid of achievement cards
3. **Competition Awards** - Timeline or list format
4. **CTA**: "View Projects" or "Contact Me"

**Colors:**
- Gold gradients for medals
- Red for trophies
- Brown for certificates

---

### **blog.html** - Blog & Insights

**Hero Title:** "Blog & Insights"
**Hero Subtitle:** "Thoughts, experiences, and knowledge sharing"

**Content Structure:**
1. **Featured Post** - Large card with image
2. **Recent Posts** - Grid of blog cards (3 columns)
3. **Categories** - Filter badges (Tech, Study Abroad, Life)
4. **CTA**: "Subscribe" or "Contact for collaboration"

**Blog Card Template:**
```html
<article class="bg-white rounded-xl shadow-sm overflow-hidden hover:shadow-lg transition-all">
<div class="h-48 bg-gradient-to-br from-primary to-secondary"></div>
<div class="p-6">
<div class="text-sm text-primary font-medium mb-2">[Category]</div>
<h3 class="text-xl font-bold mb-2">[Title]</h3>
<p class="text-gray-600 mb-4">[Excerpt...]</p>
<a href="#" class="text-primary hover:text-secondary">Read more →</a>
</div>
</article>
```

---

### **contact.html** - Contact Me

**Hero Title:** "Get In Touch"
**Hero Subtitle:** "Let's connect and discuss technology, opportunities, or just say hello!"

**Content Structure:**
1. **Contact Form** - Name, Email, Subject, Message
2. **Contact Info** - Email, Phone, Location with icons
3. **Social Links** - LinkedIn, GitHub, etc.
4. **Map** (optional) - Or decorative element

**Form Template:**
```html
<form class="space-y-6">
<div>
<label class="block text-sm font-medium mb-2">Full Name</label>
<input type="text" class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-primary focus:border-transparent">
</div>
<!-- More fields... -->
<button type="submit" class="w-full bg-primary text-white py-3 px-6 rounded-lg hover:bg-secondary transition-all">
<i class="ri-send-plane-line mr-2"></i>Send Message
</button>
</form>
```

---

## 🖼️ Image Management for GitHub Pages

### Option 1: Local Images (Recommended)
```
Create folder: D:\Personal Website\images\
Add images: profile.jpg, award1.png, etc.
```

In HTML:
```html
<img src="images/profile.jpg" alt="Profile">
<img src="./images/awards/medal.png" alt="Medal">
```

### Option 2: GitHub Raw URLs
1. Push images to GitHub
2. Navigate to image file
3. Click "Raw" button
4. Copy URL: `https://raw.githubusercontent.com/[user]/[repo]/main/images/photo.jpg`

### Option 3: External CDN
```html
<!-- Unsplash, Pexels, or your own CDN -->
<img src="https://images.unsplash.com/photo-..." alt="Image">
```

---

## 🎯 Cornell & Brown Color Combinations

### Recommended Pairings:

**Hero Sections:**
- Background: `bg-gradient-to-br from-primary via-secondary to-primary`
- Text: `text-white`

**Card Headers:**
- Background: `bg-gradient-to-br from-primary to-secondary`
- Icon background: `bg-primary rounded-full`

**Buttons Primary:**
- Background: `bg-primary hover:bg-secondary`
- Text: `text-white`

**Buttons Secondary:**
- Border: `border-2 border-primary`
- Text: `text-primary hover:bg-primary hover:text-white`

**Accents:**
- Borders: `border-primary/20` (20% opacity)
- Backgrounds: `bg-primary/5` or `bg-accent/10`
- Text highlights: `text-primary` or `gradient-text`

---

## 🚀 Quick Start Steps

### To create a new page:

1. **Copy template** from `about.html`
2. **Update title** in `<title>` tag
3. **Change hero** title and subtitle
4. **Replace main content** with page-specific sections
5. **Update active nav link** (add `text-primary font-semibold` class)
6. **Test locally** - open in browser
7. **Commit to GitHub** - push changes

---

## ✅ Checklist for Each Page

- [ ] Correct navigation with all 6 menu items
- [ ] Hero section with Cornell red gradient
- [ ] Active page highlighted in nav
- [ ] Main content with white background
- [ ] Red/brown color accents throughout
- [ ] Responsive design (test on mobile)
- [ ] Smooth scroll animations
- [ ] Footer with copyright
- [ ] No broken links
- [ ] Images load correctly

---

## 💡 Pro Tips

1. **Consistency**: Use same spacing (py-20 for sections)
2. **Icons**: RemixIcon library already loaded
3. **Fonts**: 
   - Headlines: `font-display` (Playfair Display)
   - Body: `font-sans` (Inter)
   - Logo: `font-script` (Pacifico)
4. **Gradients**: Always `from-primary` to `secondary` or `to-accent`
5. **Cards**: `rounded-xl shadow-sm hover:shadow-lg transition-all`

---

## 📱 Testing

Test each page for:
- ✅ Mobile responsiveness (< 768px)
- ✅ Tablet view (768px - 1024px)
- ✅ Desktop (> 1024px)
- ✅ All links work
- ✅ Colors display correctly
- ✅ Animations smooth

---

## 🔄 Update Workflow

When you add a new page:
1. Create HTML file
2. Update navigation in ALL pages
3. Test all links
4. Update README.md
5. Commit to GitHub
6. Test on GitHub Pages

---

**Created by Gia Tue Vu** | Cornell & Brown Color Scheme

