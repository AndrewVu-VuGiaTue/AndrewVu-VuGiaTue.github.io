# 📸 Hướng dẫn Sử dụng Google Drive cho Ảnh Website

## 🎯 Tổng quan

Bạn có thể dùng Google Drive để host ảnh cho website. Đây là cách chuyển link Google Drive thành direct image link.

---

## 🔄 Cách Convert Google Drive Link

### Bước 1: Share File trên Google Drive

1. Vào [Google Drive](https://drive.google.com)
2. Right-click vào file ảnh → **Share** hoặc **Get link**
3. Chọn **Anyone with the link can view**
4. Click **Copy link**

Link sẽ có dạng:
```
https://drive.google.com/file/d/1A2B3C4D5E6F7G8H9I0J/view?usp=sharing
```

### Bước 2: Lấy File ID

Từ link trên, lấy phần **File ID** (giữa `/d/` và `/view`):

```
1A2B3C4D5E6F7G8H9I0J
```

### Bước 3: Tạo Direct Link

Sử dụng format sau:

```
https://drive.google.com/uc?export=view&id=FILE_ID
```

**Ví dụ:**

Link gốc:
```
https://drive.google.com/file/d/1A2B3C4D5E6F7G8H9I0J/view?usp=sharing
```

Direct link:
```
https://drive.google.com/uc?export=view&id=1A2B3C4D5E6F7G8H9I0J
```

---

## 📝 Cách Sử dụng trong HTML

### Ví dụ 1: Ảnh Profile trong `about.html`

**Tìm dòng (~line 69):**
```html
<img src="https://static.readdy.ai/image/..." alt="Gia Tue Vu">
```

**Thay bằng:**
```html
<img src="https://drive.google.com/uc?export=view&id=YOUR_FILE_ID" alt="Gia Tue Vu" class="w-full h-full object-cover object-top">
```

### Ví dụ 2: Ảnh Awards trong `awards.html`

Bạn có thể thêm ảnh cho featured awards:

**Tìm phần Grand Prix Award (~line 77):**
```html
<div class="bg-gradient-to-br from-yellow-50 to-orange-50 rounded-2xl p-8 border-4 border-yellow-400 relative overflow-hidden">
  <div class="absolute top-0 right-0 w-32 h-32 bg-yellow-400 rounded-full -mr-16 -mt-16 opacity-20"></div>
  <div class="relative z-10">
    <div class="w-20 h-20 bg-gradient-to-br from-yellow-400 to-orange-500 rounded-full flex items-center justify-center mb-6 shadow-lg">
      <i class="ri-trophy-fill text-white text-3xl"></i>
    </div>
```

**Thêm ảnh certificate/award:**
```html
<div class="bg-gradient-to-br from-yellow-50 to-orange-50 rounded-2xl p-8 border-4 border-yellow-400 relative overflow-hidden">
  <!-- Add image at the top -->
  <div class="mb-6 rounded-lg overflow-hidden">
    <img src="https://drive.google.com/uc?export=view&id=YOUR_GRAND_PRIX_ID" alt="Grand Prix Certificate" class="w-full h-48 object-cover">
  </div>
  
  <div class="relative z-10">
    <div class="w-20 h-20 bg-gradient-to-br from-yellow-400 to-orange-500 rounded-full flex items-center justify-center mb-6 shadow-lg">
      <i class="ri-trophy-fill text-white text-3xl"></i>
    </div>
```

---

## 🏆 Ví dụ Cụ thể cho Awards Page

### Tổ chức Ảnh trên Google Drive

Tạo folders:
```
My Drive/
└── Website Images/
    ├── Awards/
    │   ├── grand-prix-aigc.jpg
    │   ├── gold-medal-1i1w.jpg
    │   ├── gold-medal-hkico.jpg
    │   └── gold-medal-hkimo.jpg
    └── Profile/
        └── profile-photo.jpg
```

### Lấy Link cho từng ảnh

1. **Grand Prix AIGC:**
   - Share file `grand-prix-aigc.jpg`
   - Copy link: `https://drive.google.com/file/d/ABC123XYZ/view`
   - File ID: `ABC123XYZ`
   - Direct link: `https://drive.google.com/uc?export=view&id=ABC123XYZ`

2. **Gold Medal 1I1W:**
   - File ID: `DEF456UVW`
   - Direct link: `https://drive.google.com/uc?export=view&id=DEF456UVW`

3. **Và tiếp tục cho các ảnh khác...**

### Update Awards Page HTML

**Option 1: Thêm ảnh vào Featured Awards**

```html
<!-- Grand Prix Award -->
<div class="bg-gradient-to-br from-yellow-50 to-orange-50 rounded-2xl p-8 border-4 border-yellow-400 relative overflow-hidden">
  <!-- Certificate Image -->
  <div class="mb-6 rounded-lg overflow-hidden shadow-lg">
    <img src="https://drive.google.com/uc?export=view&id=ABC123XYZ" 
         alt="Grand Prix AIGC Certificate" 
         class="w-full h-64 object-contain bg-white">
  </div>
  
  <!-- Existing content -->
  <div class="relative z-10">
    <div class="w-20 h-20 bg-gradient-to-br from-yellow-400 to-orange-500 rounded-full flex items-center justify-center mb-6 shadow-lg">
      <i class="ri-trophy-fill text-white text-3xl"></i>
    </div>
    <h3 class="text-2xl font-bold mb-3 text-gray-900">Grand Prix Award</h3>
    <p class="text-lg font-semibold text-primary mb-2">Advanced Innovation Global Competition (AIGC)</p>
    <p class="text-gray-700 mb-4">Singapore 2025</p>
    <div class="flex items-center text-sm text-gray-600">
      <i class="ri-medal-line mr-2 text-yellow-600"></i>
      <span class="font-medium">Highest Achievement - International Level</span>
    </div>
  </div>
</div>
```

**Option 2: Tạo Gallery Section**

Thêm section mới vào `awards.html` (sau phần Competition Awards):

```html
<!-- Awards Gallery -->
<div class="mb-20 scroll-reveal">
  <h2 class="text-4xl font-display font-bold mb-12 gradient-text text-center">Awards Gallery</h2>
  <div class="grid md:grid-cols-3 gap-6">
    <!-- Award Photo 1 -->
    <div class="rounded-xl overflow-hidden shadow-lg hover:shadow-2xl transition-all">
      <img src="https://drive.google.com/uc?export=view&id=ABC123XYZ" 
           alt="Grand Prix AIGC Award Ceremony" 
           class="w-full h-64 object-cover">
      <div class="p-4 bg-white">
        <h4 class="font-bold text-sm">Grand Prix Award - AIGC</h4>
        <p class="text-xs text-gray-600">Singapore 2025</p>
      </div>
    </div>
    
    <!-- Award Photo 2 -->
    <div class="rounded-xl overflow-hidden shadow-lg hover:shadow-2xl transition-all">
      <img src="https://drive.google.com/uc?export=view&id=DEF456UVW" 
           alt="Gold Medal 1I1W Award Ceremony" 
           class="w-full h-64 object-cover">
      <div class="p-4 bg-white">
        <h4 class="font-bold text-sm">Gold Medal - 1I1W</h4>
        <p class="text-xs text-gray-600">International 2025</p>
      </div>
    </div>
    
    <!-- Award Photo 3 -->
    <div class="rounded-xl overflow-hidden shadow-lg hover:shadow-2xl transition-all">
      <img src="https://drive.google.com/uc?export=view&id=GHI789RST" 
           alt="Gold Medal HKICO" 
           class="w-full h-64 object-cover">
      <div class="p-4 bg-white">
        <h4 class="font-bold text-sm">Gold Medal - HKICO</h4>
        <p class="text-xs text-gray-600">Hong Kong 2025</p>
      </div>
    </div>
    
    <!-- Add more photos... -->
  </div>
</div>
```

---

## 🎨 CSS Tips cho Ảnh

### Object Fit Options:

```css
/* Ảnh bằng chứng/certificates - giữ tỉ lệ */
object-fit: contain;

/* Ảnh ceremony/events - crop đẹp */
object-fit: cover;

/* Ảnh profile - center face */
object-fit: cover;
object-position: center top;
```

### Ví dụ HTML với styling:

```html
<!-- Certificate (nằm ngang) -->
<img src="..." class="w-full h-64 object-contain bg-white">

<!-- Award photo (vuông/dọc) -->
<img src="..." class="w-full h-80 object-cover">

<!-- Profile photo -->
<img src="..." class="w-48 h-48 rounded-full object-cover object-top">
```

---

## 🚀 Quick Start - Thêm Ảnh Awards

### Bước 1: Chuẩn bị

1. Upload tất cả ảnh awards lên Google Drive
2. Organize vào folder `Website Images/Awards/`
3. Share từng file và lấy File ID

### Bước 2: Tạo Danh sách Links

Tạo file `image-links.txt` để track:

```
Grand Prix AIGC: ABC123XYZ
Gold Medal 1I1W: DEF456UVW
Gold Medal HKICO: GHI789RST
Gold Medal HKIMO: JKL012MNO
Profile Photo: PQR345STU
```

### Bước 3: Update HTML

Open `awards.html` và thêm ảnh vào các vị trí phù hợp.

### Bước 4: Test

1. Save file
2. Open trong browser
3. Check ảnh có load không
4. Nếu không load, check:
   - File có public không?
   - File ID đúng không?
   - Link format đúng không?

---

## ⚠️ Troubleshooting

### Ảnh không hiển thị?

**Problem 1: "Access denied"**
- ✅ **Fix:** Đảm bảo file được share "Anyone with the link can view"

**Problem 2: Ảnh hiển thị nhỏ/blur**
- ✅ **Fix:** Upload ảnh resolution cao hơn (tối thiểu 1920x1080 cho landscape)

**Problem 3: Google Drive API quota exceeded**
- ✅ **Fix:** Nếu traffic cao, consider move sang Imgur/Cloudinary

**Problem 4: Link không work**
- ✅ **Check format:**
  ```
  ĐÚNG: https://drive.google.com/uc?export=view&id=ABC123
  SAI:  https://drive.google.com/file/d/ABC123/view
  ```

### Test Link

Paste direct link vào browser address bar:
- ✅ **Đúng:** Ảnh hiển thị trực tiếp
- ❌ **Sai:** Redirect đến Google Drive page

---

## 📊 Khuyến nghị Kích thước Ảnh

| Loại ảnh | Kích thước | Format |
|----------|-----------|--------|
| Certificate (ngang) | 1920x1080px | JPG/PNG |
| Award photo (dọc) | 1080x1920px | JPG |
| Trophy/Medal close-up | 1200x1200px | JPG/PNG |
| Profile photo | 800x800px | JPG |
| Gallery thumbnails | 600x600px | JPG |

### Compress ảnh trước khi upload:
- [TinyPNG](https://tinypng.com) - Miễn phí
- [Squoosh](https://squoosh.app) - Google tool
- Target: < 500KB per image

---

## 🎯 Template HTML - Copy & Paste

### Template 1: Featured Award với Ảnh

```html
<div class="bg-gradient-to-br from-yellow-50 to-orange-50 rounded-2xl p-8 border-4 border-yellow-400 relative overflow-hidden">
  <!-- Certificate Image -->
  <div class="mb-6 rounded-lg overflow-hidden shadow-lg">
    <img src="https://drive.google.com/uc?export=view&id=YOUR_FILE_ID" 
         alt="Award Certificate" 
         class="w-full h-64 object-contain bg-white p-4">
  </div>
  
  <!-- Award Info -->
  <div class="relative z-10">
    <div class="w-20 h-20 bg-gradient-to-br from-yellow-400 to-orange-500 rounded-full flex items-center justify-center mb-6 shadow-lg">
      <i class="ri-trophy-fill text-white text-3xl"></i>
    </div>
    <h3 class="text-2xl font-bold mb-3 text-gray-900">Award Title</h3>
    <p class="text-lg font-semibold text-primary mb-2">Competition Name</p>
    <p class="text-gray-700 mb-4">Location Year</p>
    <div class="flex items-center text-sm text-gray-600">
      <i class="ri-medal-line mr-2 text-yellow-600"></i>
      <span class="font-medium">Achievement Level</span>
    </div>
  </div>
</div>
```

### Template 2: Gallery Grid

```html
<div class="grid md:grid-cols-3 gap-6">
  <div class="rounded-xl overflow-hidden shadow-lg hover:shadow-2xl transition-all group">
    <div class="overflow-hidden">
      <img src="https://drive.google.com/uc?export=view&id=YOUR_FILE_ID" 
           alt="Award Photo" 
           class="w-full h-64 object-cover group-hover:scale-110 transition-transform duration-300">
    </div>
    <div class="p-4 bg-white">
      <h4 class="font-bold text-sm">Award Title</h4>
      <p class="text-xs text-gray-600">Location Year</p>
    </div>
  </div>
  <!-- Repeat for more photos -->
</div>
```

---

## 📝 Checklist

Trước khi deploy:

- [ ] Tất cả ảnh đã upload lên Google Drive
- [ ] Tất cả files được set "Anyone with link can view"
- [ ] Đã lấy File ID cho tất cả ảnh
- [ ] Đã convert sang direct links
- [ ] Đã test links trong browser (ảnh hiển thị trực tiếp)
- [ ] Đã update HTML với links
- [ ] Đã test website locally
- [ ] Ảnh hiển thị đúng và đẹp
- [ ] Responsive trên mobile

---

## 💡 Pro Tips

1. **Organize Drive:**
   ```
   Website Images/
   ├── Awards/
   │   ├── International/
   │   ├── National/
   │   └── Local/
   ├── Projects/
   └── Profile/
   ```

2. **Naming Convention:**
   - `award-aigc-grand-prix-2025.jpg`
   - `award-1i1w-gold-medal-2025.jpg`
   - Clear, descriptive names

3. **Backup Links:**
   - Giữ spreadsheet với tất cả links
   - Columns: Award Name | File ID | Direct Link | Status

4. **Version Control:**
   - Nếu update ảnh, upload file mới với tên khác
   - Không delete file cũ ngay, test trước

5. **Loading Optimization:**
   - Add `loading="lazy"` cho ảnh không ở top:
   ```html
   <img src="..." loading="lazy" alt="...">
   ```

---

## 🔄 Alternative: Google Photos

Nếu muốn dùng Google Photos thay vì Drive:

1. Upload ảnh lên Google Photos
2. Right-click → "Copy image address"
3. URL sẽ có dạng: `https://lh3.googleusercontent.com/...`
4. Dùng trực tiếp URL này trong HTML

**Lưu ý:** Google Photos links có thể expire, Drive stable hơn.

---

## 📞 Cần Trợ Giúp?

Nếu gặp vấn đề:

1. Check file permissions trên Drive
2. Test direct link trong incognito browser
3. Verify File ID chính xác
4. Check console log (F12) trong browser
5. Thử với file khác để test

---

**Happy uploading! 🎉**

Ảnh awards của bạn sẽ làm website thêm impressive!

