# 📸 Hướng dẫn Thêm Ảnh cho GitHub Pages

## Tổng quan

Khi deploy website lên GitHub Pages, bạn có 3 cách chính để thêm ảnh vào website.

---

## ✅ Cách 1: Ảnh Local trong Repo (KHUYÊN DÙNG)

### Ưu điểm:
- ✅ Nhanh nhất
- ✅ Kiểm soát hoàn toàn
- ✅ Không phụ thuộc service bên ngoài
- ✅ Hoạt động offline khi dev

### Các bước:

#### Bước 1: Tạo thư mục `images`

```
D:\Personal Website\
├── images/
│   ├── profile.jpg           # Ảnh profile
│   ├── about-hero.jpg        # Hero image cho About page
│   ├── projects/
│   │   ├── project1.jpg
│   │   ├── project2.jpg
│   │   └── project3.jpg
│   └── awards/
│       ├── trophy.png
│       └── medal.png
├── vugiatue.html
├── about.html
└── ...
```

#### Bước 2: Đặt ảnh vào thư mục

- Copy ảnh profile của bạn vào `images/profile.jpg`
- Copy ảnh projects vào `images/projects/`
- Copy icons/awards vào `images/awards/`

#### Bước 3: Update HTML

**Ví dụ trong `about.html`:**

Tìm dòng:
```html
<img src="https://static.readdy.ai/image/463e20087823e41977ed319075af2fbf/41a55e653710a7f0fda8e5db4410f3cb.png" alt="Gia Tue Vu">
```

Thay bằng:
```html
<img src="images/profile.jpg" alt="Gia Tue Vu">
```

**Ví dụ trong `projects.html`:**

Tìm:
```html
<img src="https://readdy.ai/api/search-image?query=..." alt="Project">
```

Thay bằng:
```html
<img src="images/projects/project1.jpg" alt="E-commerce Platform">
```

#### Bước 4: Push lên GitHub

```bash
git add images/
git add *.html
git commit -m "Add local images"
git push origin main
```

✅ **Done!** Ảnh sẽ tự động load từ repo của bạn.

---

## 📌 Cách 2: GitHub Raw URLs

### Ưu điểm:
- ✅ Đơn giản
- ✅ Sử dụng chính repo làm CDN
- ✅ Không cần service bên ngoài

### Các bước:

#### Bước 1: Upload ảnh lên GitHub

1. Tạo thư mục `images` trong repo
2. Upload ảnh lên GitHub (qua web interface hoặc git)

#### Bước 2: Lấy Raw URL

1. Vào repo trên GitHub
2. Navigate đến file ảnh (vd: `images/profile.jpg`)
3. Click nút **"Raw"** ở góc phải
4. Copy URL trong address bar

URL sẽ có dạng:
```
https://raw.githubusercontent.com/YOUR-USERNAME/YOUR-REPO/main/images/profile.jpg
```

#### Bước 3: Sử dụng trong HTML

```html
<img src="https://raw.githubusercontent.com/YOUR-USERNAME/YOUR-REPO/main/images/profile.jpg" alt="Profile">
```

**Ví dụ cụ thể:**
```html
<!-- Nếu username là "johndoe" và repo là "my-website" -->
<img src="https://raw.githubusercontent.com/johndoe/my-website/main/images/profile.jpg" alt="Profile">
```

---

## 🌐 Cách 3: External CDN / Image Hosting

### Option A: Imgur

#### Bước 1: Upload lên Imgur
1. Vào [imgur.com](https://imgur.com)
2. Click "New post"
3. Upload ảnh
4. Click vào ảnh đã upload
5. Right-click → "Copy image address"

#### Bước 2: Sử dụng URL
```html
<img src="https://i.imgur.com/ABC123.jpg" alt="Image">
```

### Option B: imgbb

1. Vào [imgbb.com](https://imgbb.com)
2. Upload ảnh
3. Copy "Direct link"
4. Paste vào `src`

### Option C: Cloudinary

1. Đăng ký [cloudinary.com](https://cloudinary.com)
2. Upload ảnh
3. Copy URL
4. Sử dụng trong HTML

### Option D: GitHub Issues Trick

**Cách làm:**

1. Vào repo của bạn trên GitHub
2. Click tab "Issues"
3. Click "New issue"
4. **KHÔNG** submit issue, chỉ drag & drop ảnh vào text box
5. GitHub sẽ tự động upload và generate URL
6. Copy URL đó (dạng: `https://user-images.githubusercontent.com/...`)
7. Dán vào HTML

**Lưu ý:** Có thể close issue sau khi lấy URL

---

## 📝 Checklist Thay Thế Ảnh

Đây là các vị trí cần thay ảnh trong website của bạn:

### `about.html`
- [ ] Line ~69: Profile photo (trong card)
```html
<img src="images/profile.jpg" alt="Gia Tue Vu">
```

### `projects.html`
- [ ] Project 1 image (E-commerce)
- [ ] Project 2 image (AI Chatbot)
- [ ] Project 3 image (Task Manager)

```html
<img src="images/projects/ecommerce.jpg" alt="E-commerce Platform">
<img src="images/projects/chatbot.jpg" alt="AI Chatbot">
<img src="images/projects/taskmanager.jpg" alt="Task Manager">
```

### `blog.html`
- [ ] Featured post image
- [ ] Blog post 1-6 images

```html
<div class="h-48 bg-gradient-to-br from-blue-500 to-cyan-600">
  <!-- Có thể giữ gradient hoặc thay bằng ảnh -->
  <img src="images/blog/post1.jpg" alt="Blog Post" class="w-full h-full object-cover">
</div>
```

### `vugiatue.html`
- [ ] Hero background (parallax)
```html
<section id="home" ... style="background-image: url('images/hero-background.jpg');">
```

---

## 🎨 Tối Ưu Ảnh

### Kích thước khuyến nghị:

| Vị trí | Kích thước | Format |
|--------|-----------|--------|
| Profile photo | 400x400px | JPG |
| Hero background | 1920x1080px | JPG |
| Project cards | 800x600px | JPG/PNG |
| Blog thumbnails | 600x400px | JPG |
| Icons/Awards | 256x256px | PNG/SVG |

### Tools để resize:

- **Online:** 
  - [TinyPNG](https://tinypng.com) - Nén ảnh
  - [Squoosh](https://squoosh.app) - Resize & compress
  - [ResizeImage](https://resizeimage.net)

- **Desktop:**
  - Photoshop
  - GIMP (free)
  - Paint.NET (Windows, free)

### Tips:
- ✅ Nén ảnh trước khi upload (giảm dung lượng)
- ✅ Sử dụng format phù hợp (JPG cho photos, PNG cho logos)
- ✅ Đặt tên file có ý nghĩa (`profile.jpg` thay vì `IMG_1234.jpg`)
- ✅ Sử dụng chữ thường và dấu gạch ngang (`my-project.jpg`)

---

## 🚀 Quick Start - Thay Ảnh Profile

### Bước nhanh nhất:

1. **Chuẩn bị ảnh:**
   - Ảnh profile của bạn
   - Resize về 400x400px
   - Đặt tên `profile.jpg`

2. **Tạo thư mục:**
```bash
cd "D:\Personal Website"
mkdir images
```

3. **Copy ảnh:**
   - Copy `profile.jpg` vào `D:\Personal Website\images\`

4. **Update `about.html`:**
   - Mở file `about.html`
   - Tìm line ~69
   - Thay URL thành: `images/profile.jpg`

5. **Test local:**
   - Mở `about.html` trong browser
   - Check ảnh có hiển thị không

6. **Push lên GitHub:**
```bash
git add images/profile.jpg
git add about.html
git commit -m "Add profile photo"
git push origin main
```

✅ **Done!**

---

## ❓ Troubleshooting

### Ảnh không hiển thị trên GitHub Pages?

**Kiểm tra:**

1. **Đường dẫn đúng không?**
   ```html
   <!-- Đúng -->
   <img src="images/profile.jpg">
   <img src="./images/profile.jpg">
   
   <!-- Sai -->
   <img src="/images/profile.jpg">  <!-- Thiếu . -->
   <img src="Images/profile.jpg">   <!-- Viết hoa I -->
   ```

2. **File có tồn tại không?**
   - Check trong repo GitHub
   - Đảm bảo đã commit & push

3. **Tên file chính xác không?**
   - Case-sensitive trên Linux/GitHub
   - `Profile.jpg` ≠ `profile.jpg`

4. **Cache browser?**
   - Thử Ctrl+F5 để hard refresh
   - Mở incognito window

5. **Path từ root đúng không?**
   ```
   about.html  →  images/profile.jpg  ✅
   pages/about.html  →  ../images/profile.jpg  ✅
   ```

---

## 💡 Best Practices

### DO ✅

- ✅ Sử dụng relative paths (`images/photo.jpg`)
- ✅ Optimize ảnh trước khi upload
- ✅ Đặt tên file có ý nghĩa
- ✅ Tổ chức ảnh theo folders (projects/, awards/, blog/)
- ✅ Sử dụng `alt` text cho accessibility
- ✅ Test trên mobile devices

### DON'T ❌

- ❌ Dùng ảnh quá nặng (> 1MB mỗi file)
- ❌ Dùng absolute paths (`C:\Users\...`)
- ❌ Upload ảnh không cần thiết
- ❌ Để ảnh personal/sensitive public
- ❌ Quên commit ảnh vào repo

---

## 📚 Resources

### Free Stock Photos:
- [Unsplash](https://unsplash.com)
- [Pexels](https://pexels.com)
- [Pixabay](https://pixabay.com)

### Icons:
- [RemixIcon](https://remixicon.com) - đã dùng trong website
- [FontAwesome](https://fontawesome.com)
- [Flaticon](https://flaticon.com)

### Image Tools:
- [TinyPNG](https://tinypng.com) - Compress
- [Squoosh](https://squoosh.app) - Resize
- [Remove.bg](https://remove.bg) - Remove background

---

## 🎯 Summary

**Khuyến nghị:**
- Dùng **Cách 1 (Local images)** cho tất cả ảnh chính
- Dùng **Cách 2 (GitHub Raw)** nếu muốn share ảnh
- Dùng **Cách 3 (CDN)** cho ảnh temporary/testing

**Workflow:**
1. Tạo `images/` folder
2. Tổ chức ảnh theo folders
3. Update HTML với paths
4. Test locally
5. Commit & push
6. Verify trên GitHub Pages

---

**Happy coding! 🚀**

Nếu có vấn đề, check troubleshooting section hoặc liên hệ!

