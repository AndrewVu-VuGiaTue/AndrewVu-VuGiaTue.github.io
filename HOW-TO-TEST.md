# 🧪 How to Test - Language Switcher Feature

## Quick Test Guide / Hướng dẫn Test nhanh

---

## ✅ Testing Checklist

### Test 1: Initial Load (Lần đầu mở trang)
- [ ] Mở file `vugiatue.html` trong trình duyệt
- [ ] **Expected**: Website hiển thị tiếng Anh (English) mặc định
- [ ] Kiểm tra Navigation bar có chữ "Home, About, Skills..." (English)
- [ ] Hero section có text "Greetings from Hanoi, Vietnam!"

### Test 2: Language Switcher UI
- [ ] Tìm icon 🌐 ở góc phải navigation bar
- [ ] Thấy text "EN" bên cạnh icon
- [ ] **Expected**: Icon và text hiển thị rõ ràng

### Test 3: Dropdown Menu
- [ ] Di chuột (hover) vào 🌐 EN
- [ ] **Expected**: Dropdown menu xuất hiện với animation smooth
- [ ] Menu hiển thị 2 options:
  - [ ] 🇺🇸 English (màu đỏ nhạt = active)
  - [ ] 🇻🇳 Tiếng Việt

### Test 4: Switch to Vietnamese
- [ ] Click vào "🇻🇳 Tiếng Việt"
- [ ] **Expected**: 
  - [ ] Text chuyển sang tiếng Việt ngay lập tức
  - [ ] Navigation: "Trang chủ, Giới thiệu, Kỹ năng..."
  - [ ] Hero: "Xin chào từ Hà Nội, Việt Nam!"
  - [ ] Buttons: "Khám phá thêm, Liên hệ ngay"
  - [ ] Icon thay đổi thành "🌐 VI"

### Test 5: Scroll Through Sections (Vietnamese)
- [ ] Scroll xuống section "Giới thiệu về tôi"
- [ ] Check "Kỹ năng & Công nghệ"
- [ ] Check "Dự án nổi bật"
- [ ] Check "Blog & Bài viết"
- [ ] Check "Liên hệ với tôi"
- [ ] **Expected**: Tất cả section titles đều bằng tiếng Việt

### Test 6: Switch Back to English
- [ ] Click vào 🌐 VI
- [ ] Click "🇺🇸 English"
- [ ] **Expected**: Tất cả text chuyển lại sang tiếng Anh
- [ ] Icon thay đổi thành "🌐 EN"

### Test 7: LocalStorage Persistence
- [ ] Chọn ngôn ngữ Tiếng Việt
- [ ] **Đóng tab browser** hoàn toàn
- [ ] Mở lại file `vugiatue.html`
- [ ] **Expected**: Website vẫn hiển thị tiếng Việt (đã lưu preference)

### Test 8: Mobile Responsive
- [ ] Mở Developer Tools (F12)
- [ ] Chuyển sang mobile view (Ctrl + Shift + M)
- [ ] **Expected**: Language switcher vẫn hoạt động bình thường
- [ ] Dropdown vẫn hiển thị đúng vị trí

### Test 9: Multiple Quick Switches
- [ ] Click EN → VI → EN → VI nhanh liên tục
- [ ] **Expected**: Mỗi lần click đều chuyển đổi smooth, không bị lag

### Test 10: All Interactive Elements
- [ ] Chọn tiếng Việt
- [ ] Click các buttons: "Khám phá thêm", "Liên hệ ngay"
- [ ] **Expected**: Text trong buttons đã được dịch
- [ ] Icons (ri-file-text-line, ri-mail-line) vẫn hiển thị

---

## 🎯 Expected Results Summary

| Element | English (EN) | Tiếng Việt (VI) |
|---------|-------------|-----------------|
| Nav - Home | Home | Trang chủ |
| Nav - About | About | Giới thiệu |
| Nav - Skills | Skills | Kỹ năng |
| Nav - Projects | Projects | Dự án |
| Hero Greeting | Greetings from Hanoi, Vietnam! | Xin chào từ Hà Nội, Việt Nam! |
| Explore Button | Explore More | Khám phá thêm |
| Contact Button | Get in Touch | Liên hệ ngay |
| Scroll Down | Scroll Down | Cuộn xuống |
| About Title | About Me | Giới thiệu về tôi |
| Skills Title | Skills & Technologies | Kỹ năng & Công nghệ |
| Projects Title | Featured Projects | Dự án nổi bật |
| Blog Title | Blog & Insights | Blog & Bài viết |
| Contact Title | Get In Touch | Liên hệ với tôi |

---

## 🐛 Common Issues & Solutions

### Issue 1: Dropdown không xuất hiện
**Symptoms**: Hover vào 🌐 nhưng menu không show
**Solution**: 
- Hard refresh: `Ctrl + Shift + R`
- Check Console (F12) xem có lỗi JavaScript không

### Issue 2: Text không chuyển đổi
**Symptoms**: Click vào language nhưng text không thay đổi
**Solution**:
- Kiểm tra Console có lỗi: `Uncaught TypeError`
- Clear cache và reload
- Đảm bảo JavaScript đã load xong

### Issue 3: LocalStorage không lưu
**Symptoms**: Reload trang thì quay lại English
**Solution**:
- Thoát chế độ Incognito/Private browsing
- Check browser settings cho phép localStorage
- Run in normal browser window

### Issue 4: Icons bị mất sau khi switch
**Symptoms**: Buttons thiếu icons (envelope, document icons)
**Solution**:
- This is normal if RemixIcon CDN is slow
- Wait a few seconds và icons sẽ load
- Check internet connection

---

## 💻 Developer Testing (Console Commands)

Mở Console (F12) và test các commands này:

### Test 1: Force Switch Language
```javascript
switchLanguage('vi'); // Switch to Vietnamese
switchLanguage('en'); // Switch to English
```

### Test 2: Check Current Language
```javascript
localStorage.getItem('preferredLanguage'); // Returns: 'en' or 'vi'
```

### Test 3: Check HTML Lang Attribute
```javascript
document.documentElement.lang; // Returns: 'en' or 'vi'
```

### Test 4: List All Translatable Elements
```javascript
document.querySelectorAll('[data-i18n]').length; // Should return ~15+
```

### Test 5: Get Translation Data
```javascript
translations.en.hero.greeting; // English greeting
translations.vi.hero.greeting; // Vietnamese greeting
```

### Test 6: Reset Language Preference
```javascript
localStorage.removeItem('preferredLanguage');
location.reload(); // Resets to default English
```

---

## 📊 Performance Testing

### Load Time Test
1. Open DevTools → Network tab
2. Hard refresh (Ctrl + Shift + R)
3. Check:
   - [ ] DOMContentLoaded < 500ms
   - [ ] Load time < 2s
   - [ ] No failed requests

### Language Switch Speed
1. Open DevTools → Performance tab
2. Start recording
3. Click language switcher
4. Stop recording
5. Check:
   - [ ] Switch happens < 100ms
   - [ ] No layout thrashing
   - [ ] Smooth animation

### Memory Usage
1. Open DevTools → Memory tab
2. Take heap snapshot
3. Switch languages 10 times
4. Take another snapshot
5. Check:
   - [ ] No memory leaks
   - [ ] Memory increase < 1MB

---

## 🎨 Visual/UI Testing

### Desktop (1920x1080)
- [ ] Language dropdown aligns properly
- [ ] Hover effects work smoothly
- [ ] Active state shows correctly
- [ ] Text doesn't overflow

### Tablet (768x1024)
- [ ] Dropdown still accessible
- [ ] Menu position adjusts
- [ ] Touch interactions work

### Mobile (375x667)
- [ ] Icon visible and clickable
- [ ] Dropdown fits screen
- [ ] No horizontal scroll
- [ ] Text readable at all sizes

---

## ✨ User Experience Testing

### Scenario 1: First-time Visitor (Vietnamese speaker)
```
1. Opens website → sees English
2. Notices 🌐 EN in corner
3. Hovers → sees menu with 🇻🇳 flag
4. Clicks Tiếng Việt
5. ✅ Website switches to Vietnamese
6. ✅ Comfortable reading in native language
```

### Scenario 2: Returning Visitor
```
1. Visited yesterday, chose Vietnamese
2. Returns today
3. ✅ Website remembers preference
4. ✅ Shows Vietnamese automatically
5. No need to switch again
```

### Scenario 3: Portfolio Reviewer (English speaker)
```
1. Opens website → sees English (default)
2. ✅ Can immediately understand content
3. Notices language option available
4. ✅ Appreciates professional bilingual setup
```

---

## 📝 Test Report Template

Copy and fill this out after testing:

```
Website: Gia Tue Vu Personal Website
Test Date: ____/____/2025
Tester: _______________
Browser: Chrome / Firefox / Safari / Edge (circle one)
Version: _______________

✅ PASSED TESTS:
- [ ] Initial load (English default)
- [ ] Language switcher visible
- [ ] Dropdown menu works
- [ ] Switch to Vietnamese
- [ ] Switch to English
- [ ] LocalStorage persistence
- [ ] Mobile responsive
- [ ] All sections translated

❌ FAILED TESTS:
(List any issues found)
1. ________________________
2. ________________________

📝 NOTES:
____________________________
____________________________
____________________________

OVERALL: PASS / FAIL (circle one)
```

---

## 🚀 Quick Start Testing (30 seconds)

Chỉ muốn test nhanh? Làm theo 5 bước này:

1. **Open**: Double-click `vugiatue.html`
2. **Check**: Website shows English ✓
3. **Hover**: Mouse over 🌐 EN → menu appears ✓
4. **Click**: Choose 🇻🇳 Tiếng Việt → switches to Vietnamese ✓
5. **Reload**: Refresh page (F5) → still Vietnamese ✓

**If all 5 steps pass → Feature works perfectly! 🎉**

---

## 📞 Report Issues

Found a bug? Report it:
- **Email**: vgt2800@gmail.com
- **Include**: 
  - Browser & version
  - Steps to reproduce
  - Screenshot if possible

---

**Happy Testing! 🧪✨**

