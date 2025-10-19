# 🏆 Hướng dẫn Thêm Ảnh Giấy Chứng nhận vào Awards Page

## 📋 Danh sách Awards đã chọn

Từ [folder Google Drive](https://drive.google.com/drive/folders/1x792SYsuOmcz8lVm_yYfSM7-zJj85l1-?usp=drive_link), các giấy chứng nhận sau sẽ được hiển thị:

### 🏆 **Top 3 Featured Awards:**
1. **Grand Prix Award** - Advanced Innovation Global Competition 2025, Singapore
2. **Gold Medal** - 1 IDEA 1 WORLD 2025, Turkey  
3. **Gold Medal** - Hong Kong International Computational Olympiad - International Round

### 🥇 **Gold Medals:**
4. **Gold Medal** - Hong Kong International Computational Olympiad - National Round
5. **Gold Medal** - Hong Kong International Mathematical Olympiad - National Round
6. **Gold Medal** - Cambodia International Mathematical Olympiad Champion - National Round

### 🥈 **Other Awards:**
7. **Silver Medal** - Copernicus International Mathematical Olympiad - National Round
8. **Third Prize** - Excellent Students Mathematics Competition - District Level
9. **Third Prize** - Exploration and Creativity Contest in Mathematics 2024

---

## 🔑 Bước 1: Lấy File IDs từ Google Drive Folder

### Vấn đề:

Folder link (`https://drive.google.com/drive/folders/...`) không thể dùng trực tiếp. Cần lấy File ID riêng cho **MỖI** file PDF.

### Cách lấy File ID:

**Option A: Từ Folder (Khuyên dùng)**

1. Mở folder: https://drive.google.com/drive/folders/1x792SYsuOmcz8lVm_yYfSM7-zJj85l1-
2. Right-click vào file PDF → **"Get link"** hoặc **"Share"**
3. Click "Copy link"
4. Link sẽ có dạng:
   ```
   https://drive.google.com/file/d/ABC123XYZ456/view?usp=sharing
   ```
5. File ID là phần giữa `/d/` và `/view`:
   ```
   ABC123XYZ456
   ```

**Option B: Mở file rồi lấy từ URL**

1. Click vào file PDF trong folder
2. File mở trong viewer
3. Look at address bar, URL dạng:
   ```
   https://drive.google.com/file/d/ABC123XYZ456/view
   ```
4. Copy phần `ABC123XYZ456`

### Lặp lại cho TẤT CẢ 9 files!

---

## 📝 Bước 2: Tạo danh sách File IDs

Tạo file `award-file-ids.txt` để track (QUAN TRỌNG!):

```
Grand Prix AIGC Singapore: [PASTE_FILE_ID_HERE]
Gold Medal 1I1W Turkey: [PASTE_FILE_ID_HERE]
Gold Medal HKICO International: [PASTE_FILE_ID_HERE]
Gold Medal HKICO National: [PASTE_FILE_ID_HERE]
Gold Medal HKIMO National: [PASTE_FILE_ID_HERE]
Gold Medal Cambodia IMO: [PASTE_FILE_ID_HERE]
Silver Medal Copernicus IMO: [PASTE_FILE_ID_HERE]
Third Prize District Math: [PASTE_FILE_ID_HERE]
Third Prize Exploration Math: [PASTE_FILE_ID_HERE]
```

**Điền vào từng dòng với File IDs đã copy!**

---

## 🖼️ Bước 3: Convert File IDs sang Direct Links

Với mỗi File ID, tạo direct link theo format:

```
https://drive.google.com/uc?export=view&id=FILE_ID
```

**Ví dụ:**

File ID: `ABC123XYZ456`  
Direct Link: `https://drive.google.com/uc?export=view&id=ABC123XYZ456`

**Test link:** Paste direct link vào browser → PDF/Image phải hiển thị trực tiếp (không redirect đến Google Drive page)

---

## 🎨 Bước 4: Update `awards.html`

### Option 1: Embed PDF Viewer (Khuyên dùng cho certificates)

Mở `awards.html`, tìm phần **Grand Prix Award** (~line 77):

**HIỆN TẠI:**
```html
<div class="bg-gradient-to-br from-yellow-50 to-orange-50 rounded-2xl p-8 border-4 border-yellow-400 relative overflow-hidden">
  <div class="absolute top-0 right-0 w-32 h-32 bg-yellow-400 rounded-full -mr-16 -mt-16 opacity-20"></div>
  <div class="relative z-10">
    <div class="w-20 h-20 bg-gradient-to-br from-yellow-400 to-orange-500 rounded-full flex items-center justify-center mb-6 shadow-lg">
      <i class="ri-trophy-fill text-white text-3xl"></i>
    </div>
    <h3 class="text-2xl font-bold mb-3 text-gray-900">Grand Prix Award</h3>
```

**THÊM DÒNG SAU** (ngay trước icon/title):

```html
<div class="bg-gradient-to-br from-yellow-50 to-orange-50 rounded-2xl p-8 border-4 border-yellow-400 relative overflow-hidden">
  <div class="absolute top-0 right-0 w-32 h-32 bg-yellow-400 rounded-full -mr-16 -mt-16 opacity-20"></div>
  
  <!-- ===== THÊM PHẦN NÀY ===== -->
  <div class="mb-6 rounded-lg overflow-hidden shadow-2xl bg-white">
    <iframe 
      src="https://drive.google.com/file/d/YOUR_GRAND_PRIX_FILE_ID/preview" 
      width="100%" 
      height="400" 
      allow="autoplay"
      class="border-0">
    </iframe>
  </div>
  <!-- ===== HẾT PHẦN THÊM ===== -->
  
  <div class="relative z-10">
    <div class="w-20 h-20 bg-gradient-to-br from-yellow-400 to-orange-500 rounded-full flex items-center justify-center mb-6 shadow-lg">
      <i class="ri-trophy-fill text-white text-3xl"></i>
    </div>
    <h3 class="text-2xl font-bold mb-3 text-gray-900">Grand Prix Award</h3>
```

**Thay `YOUR_GRAND_PRIX_FILE_ID`** bằng File ID thật!

### Option 2: Show as Image (Nếu convert PDF → Image trước)

```html
<div class="mb-6 rounded-lg overflow-hidden shadow-2xl">
  <img 
    src="https://drive.google.com/uc?export=view&id=YOUR_FILE_ID" 
    alt="Grand Prix Certificate" 
    class="w-full h-auto object-contain bg-white p-4"
    loading="lazy">
</div>
```

---

## 📋 Template Cho TẤT CẢ Awards

### Featured Awards (Top 3) - Với PDF Viewer:

```html
<!-- Grand Prix Award -->
<div class="...card classes...">
  <!-- PDF VIEWER -->
  <div class="mb-6 rounded-lg overflow-hidden shadow-2xl bg-white">
    <iframe 
      src="https://drive.google.com/file/d/GRAND_PRIX_FILE_ID/preview" 
      width="100%" 
      height="400" 
      allow="autoplay"
      class="border-0">
    </iframe>
  </div>
  
  <!-- Existing icon and text... -->
</div>

<!-- Gold Medal 1I1W -->
<div class="...card classes...">
  <div class="mb-6 rounded-lg overflow-hidden shadow-2xl bg-white">
    <iframe 
      src="https://drive.google.com/file/d/1I1W_FILE_ID/preview" 
      width="100%" 
      height="400" 
      allow="autoplay"
      class="border-0">
    </iframe>
  </div>
  
  <!-- Existing content... -->
</div>
```

### Competition Awards Section - Thêm thumbnail:

Trong phần "Competition Awards" list (~line 145), có thể thêm small thumbnail:

```html
<div class="bg-white rounded-xl shadow-sm border border-gray-200 p-6 hover:shadow-lg transition-all">
  <div class="flex items-start gap-4">
    <!-- THUMBNAIL (optional) -->
    <div class="w-24 h-24 flex-shrink-0 rounded-lg overflow-hidden shadow">
      <img 
        src="https://drive.google.com/uc?export=view&id=FILE_ID" 
        alt="Certificate Thumbnail"
        class="w-full h-full object-cover">
    </div>
    
    <!-- Text content -->
    <div class="flex-1">
      <h3 class="text-xl font-bold mb-2">Grand Prix Award</h3>
      <p class="text-primary font-semibold mb-1">Advanced Innovation Global Competition (AIGC)</p>
      <!-- ... rest of content ... -->
    </div>
  </div>
</div>
```

---

## 🎨 Option 3: Gallery Section (Khuyên dùng!)

Thêm section mới vào `awards.html` (trước CTA section, ~line 250):

```html
<!-- Awards Gallery -->
<section class="mb-20 scroll-reveal">
  <div class="max-w-7xl mx-auto px-6">
    <h2 class="text-4xl font-display font-bold mb-12 gradient-text text-center">Certificates Gallery</h2>
    
    <div class="grid md:grid-cols-3 gap-6">
      <!-- Certificate 1 -->
      <div class="rounded-xl overflow-hidden shadow-lg hover:shadow-2xl transition-all group">
        <div class="aspect-[4/3] overflow-hidden bg-gray-100">
          <iframe 
            src="https://drive.google.com/file/d/FILE_ID_1/preview" 
            width="100%" 
            height="100%" 
            class="border-0 group-hover:scale-105 transition-transform">
          </iframe>
        </div>
        <div class="p-4 bg-white">
          <h4 class="font-bold text-sm mb-1">Grand Prix Award</h4>
          <p class="text-xs text-gray-600">AIGC 2025 - Singapore</p>
        </div>
      </div>
      
      <!-- Certificate 2 -->
      <div class="rounded-xl overflow-hidden shadow-lg hover:shadow-2xl transition-all group">
        <div class="aspect-[4/3] overflow-hidden bg-gray-100">
          <iframe 
            src="https://drive.google.com/file/d/FILE_ID_2/preview" 
            width="100%" 
            height="100%" 
            class="border-0 group-hover:scale-105 transition-transform">
          </iframe>
        </div>
        <div class="p-4 bg-white">
          <h4 class="font-bold text-sm mb-1">Gold Medal - 1I1W</h4>
          <p class="text-xs text-gray-600">Turkey 2025</p>
        </div>
      </div>
      
      <!-- Certificate 3 -->
      <div class="rounded-xl overflow-hidden shadow-lg hover:shadow-2xl transition-all group">
        <div class="aspect-[4/3] overflow-hidden bg-gray-100">
          <iframe 
            src="https://drive.google.com/file/d/FILE_ID_3/preview" 
            width="100%" 
            height="100%" 
            class="border-0 group-hover:scale-105 transition-transform">
          </iframe>
        </div>
        <div class="p-4 bg-white">
          <h4 class="font-bold text-sm mb-1">Gold Medal - HKICO</h4>
          <p class="text-xs text-gray-600">International Round 2025</p>
        </div>
      </div>
      
      <!-- Repeat for all 9 certificates... -->
    </div>
  </div>
</section>
```

**Thay ALL `FILE_ID_X` bằng File IDs thật từ danh sách của bạn!**

---

## ✅ Checklist

- [ ] Đã mở folder Drive
- [ ] Đã lấy File ID cho tất cả 9 awards
- [ ] Đã tạo file `award-file-ids.txt` với danh sách
- [ ] Đã test ít nhất 1 direct link trong browser
- [ ] Đã update `awards.html` với File IDs
- [ ] Đã test website locally
- [ ] PDF viewers hiển thị đúng
- [ ] Responsive trên mobile

---

## 🎯 Quick Start (TL;DR)

1. **Lấy File IDs:**
   - Open mỗi PDF trong folder
   - Right-click → Get link
   - Copy ID từ URL

2. **Tạo danh sách:**
   ```
   Grand Prix: ABC123
   Gold 1I1W: DEF456
   Gold HKICO Int: GHI789
   ...
   ```

3. **Update awards.html:**
   - Option A: Add iframe với `src="...file/d/FILE_ID/preview"`
   - Option B: Add Gallery section (code ở trên)
   - Thay FILE_IDs

4. **Test:**
   - Open `awards.html` in browser
   - Check PDFs load correctly

---

## ⚠️ Troubleshooting

### PDF không hiển thị?

**Check:**
1. ✅ File có được share "Anyone with link can view"?
2. ✅ File ID đúng không? (không có dấu space/newline)
3. ✅ URL format đúng? 
   - Iframe: `https://drive.google.com/file/d/ID/preview`
   - Image: `https://drive.google.com/uc?export=view&id=ID`

### PDF hiển thị nhỏ/blur?

- ✅ Tăng `height` của iframe (400 → 500 hoặc 600)
- ✅ Hoặc convert PDF sang high-res image trước

### Loading chậm?

- ✅ Add `loading="lazy"` cho images
- ✅ Reduce số PDFs hiển thị cùng lúc
- ✅ Consider thumbnails thay vì full PDFs

---

## 💡 Pro Tips

1. **Priority hiển thị:**
   - Top 3 Featured: Full PDF viewer (height 400-500px)
   - Others: Thumbnails or gallery với smaller viewers

2. **Mobile optimization:**
   - Trên mobile, PDFs có thể không hiển thị tốt
   - Consider show "View Certificate" button instead

3. **Alternative:**
   - Upload PDFs lên Imgur as images
   - Hoặc convert PDF → PNG locally rồi upload

4. **Organization:**
   - Keep `award-file-ids.txt` file
   - Easy to update/change later

---

## 📞 Cần trợ giúp?

Nếu gặp vấn đề:
1. Check file permissions trên Drive
2. Verify File IDs (không có typos)
3. Test links trong incognito browser
4. Try với 1 file trước, rồi áp dụng cho tất cả

---

**Done! Your awards will look AMAZING! 🏆✨**

