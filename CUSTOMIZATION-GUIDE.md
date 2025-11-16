# 📚 راهنمای کامل جایگزینی Asset ها و سفارشی‌سازی - MixPlus

این راهنما به شما کمک می‌کند تمام تصاویر، ویدیوها، فونت‌ها، لوگوها و متن‌های سایت را به راحتی جایگزین کنید.

---

## 📁 ساختار فولدرها

```
mixplus-website/
├── index.html              ← فایل اصلی سایت
├── fonts/                  ← فونت‌های فارسی و انگلیسی
│   ├── KALAMEH-REGULAR.woff2
│   ├── KALAMEH-BOLD.woff2
│   ├── KALAMEH-BLACK.woff2
│   ├── Montserrat-Regular.woff2
│   ├── Montserrat-Medium.woff2
│   ├── Montserrat-Bold.woff2
│   └── Montserrat-Black.woff2
├── logos/                  ← لوگوهای سایت
│   ├── logo-light.svg      ← لوگو برای تم روشن (تیره رنگ)
│   └── logo-dark.svg       ← لوگو برای تم تاریک (روشن رنگ)
├── videos/                 ← ویدیوهای هیرو
│   ├── hero-01.mp4
│   ├── hero-02.mp4
│   ├── hero-03.mp4
│   └── hero-04.mp4
├── images/                 ← تصاویر سایت
│   ├── banners/            ← بنرهای تمام‌صفحه
│   │   ├── fullbleed-01.jpg
│   │   ├── fullbleed-02.jpg
│   │   └── fullbleed-03.jpg
│   ├── categories/         ← کارت‌های محصولات
│   │   ├── hob.jpg
│   │   ├── sink.jpg
│   │   ├── oven.jpg
│   │   └── hood.jpg
│   └── shortcuts/          ← کارت‌های میانبر
│       ├── products.jpg
│       ├── events.jpg
│       ├── services.jpg
│       └── training.jpg
└── docs/                   ← فایل‌های PDF کاتالوگ
    ├── catalog-fa.pdf
    └── catalog-en.pdf
```

---

## 🎨 1. جایگزینی فونت‌ها

### مرحله 1: دانلود فونت‌ها

**فونت Kalameh (فارسی):**
- از [این لینک](https://github.com/Goudarz/kalameh-font) دانلود کنید
- فایل‌های `KALAMEH-REGULAR.woff2`، `KALAMEH-BOLD.woff2` و `KALAMEH-BLACK.woff2` را استخراج کنید

**فونت Montserrat (انگلیسی):**
- از [Google Fonts](https://fonts.google.com/specimen/Montserrat) دانلود کنید
- یا از [این لینک](https://gwfh.mranftl.com/fonts/montserrat) نسخه woff2 بگیرید
- فایل‌های `Regular`, `Medium`, `Bold` و `Black` را دانلود کنید

### مرحله 2: قرار دادن فونت‌ها

1. فولدر `fonts/` در کنار فایل `index.html` بسازید
2. تمام فایل‌های `.woff2` را در آن قرار دهید

### ✅ فایل‌های مورد نیاز:
```
fonts/
├── KALAMEH-REGULAR.woff2
├── KALAMEH-BOLD.woff2
├── KALAMEH-BLACK.woff2
├── Montserrat-Regular.woff2
├── Montserrat-Medium.woff2
├── Montserrat-Bold.woff2
└── Montserrat-Black.woff2
```

**نکته**: اگر فونت Kalameh در دسترس نیست، فعلاً همان Vazirmatn از Google Fonts استفاده می‌شود.

---

## 🖼️ 2. جایگزینی لوگو

### لوگوها باید SVG باشند

شما به **دو فایل SVG** نیاز دارید:

1. **`logo-light.svg`**: لوگوی **تیره** برای تم روشن
2. **`logo-dark.svg`**: لوگوی **روشن** برای تم تیره

### مرحله 1: ساخت لوگو در Figma/Illustrator

- لوگو را طراحی کنید
- Export به SVG
- **مهم**: سایز توصیه شده: 120×40 پیکسل

### مرحله 2: قرار دادن لوگوها

```
logos/
├── logo-light.svg    ← رنگ تیره (مثلاً #111111)
└── logo-dark.svg     ← رنگ روشن (مثلاً #f9fafb)
```

### مکان در کد (خط ~1065):
```html
<a href="#" class="mix-header__logo">
  <img src="/logos/logo-light.svg" alt="MixPlus Logo" class="logo-light">
  <img src="/logos/logo-dark.svg" alt="MixPlus Logo" class="logo-dark hidden">
</a>
```

**نکته**: در JavaScript، لوگو بر اساس تم خودکار تغییر می‌کند!

---

## 🎬 3. جایگزینی ویدیوهای Hero

### مرحله 1: آماده‌سازی ویدیوها

**الزامات ویدیو:**
- فرمت: **MP4** (H.264 codec)
- سایز: **کمتر از 5MB** (برای سرعت بالا)
- وضوح: **1920×1080** یا **1280×720**
- مدت: **5-15 ثانیه**
- **بدون صدا** (muted) - برای autoplay

**نکته**: از [HandBrake](https://handbrake.fr/) برای فشرده‌سازی استفاده کنید.

### مرحله 2: قرار دادن ویدیوها

```
videos/
├── hero-01.mp4
├── hero-02.mp4
├── hero-03.mp4
└── hero-04.mp4
```

### مکان در کد (خط ~1335):
```html
<video class="mix-hero__video" id="hero-video" autoplay muted playsinline loop>
  <source src="https://www.w3schools.com/html/mov_bbb.mp4" type="video/mp4">
</video>
```

**جایگزین کنید با:**
```html
<source src="/videos/hero-01.mp4" type="video/mp4">
```

**و در JavaScript (خط تقریبی ~1800):**
```javascript
// فعلاً:
const videos = [
  'https://www.w3schools.com/html/mov_bbb.mp4',
  ...
];

// تبدیل به:
const videos = [
  '/videos/hero-01.mp4',
  '/videos/hero-02.mp4',
  '/videos/hero-03.mp4',
  '/videos/hero-04.mp4'
];
```

---

## 🖼️ 4. جایگزینی تصاویر

### الف) بنرهای Full-bleed (بنرهای تمام‌صفحه)

**الزامات:**
- سایز: **1920×1080** پیکسل
- فرمت: **JPG** (بهینه شده) یا **WebP**
- کیفیت: 80-85%

**مکان‌ها در کد:**

1. **بنر 1** (خط ~1410):
```html
<img src="https://images.unsplash.com/photo-1556911220...">
```
جایگزین: `/images/banners/fullbleed-01.jpg`

2. **بنر 2** (خط ~1439):
```html
<img src="https://images.unsplash.com/photo-1556909172...">
```
جایگزین: `/images/banners/fullbleed-02.jpg`

3. **بنر 3** (خط ~1490):
```html
<img src="https://images.unsplash.com/photo-1556909114...">
```
جایگزین: `/images/banners/fullbleed-03.jpg`

### ب) کارت‌های محصولات (4 عدد)

**الزامات:**
- سایز: **400×533** پیکسل (نسبت 3:4)
- فرمت: **JPG** بهینه شده

**مکان‌ها** (خطوط ~1370-1406):
```html
<!-- اجاق گاز -->
<img src="..." alt="Hob">
<!-- سینک -->
<img src="..." alt="Sink">
<!-- فر -->
<img src="..." alt="Oven">
<!-- هود -->
<img src="..." alt="Hood">
```

جایگزین:
```html
<img src="/images/categories/hob.jpg" alt="Hob">
<img src="/images/categories/sink.jpg" alt="Sink">
<img src="/images/categories/oven.jpg" alt="Oven">
<img src="/images/categories/hood.jpg" alt="Hood">
```

### ج) کارت‌های میانبر (4 عدد مربعی)

**الزامات:**
- سایز: **400×400** پیکسل (مربع)
- فرمت: **JPG** بهینه شده

**مکان‌ها** (خطوط ~1450-1486):
```html
<img src="..." alt="Products">
<img src="..." alt="Events">
<img src="..." alt="Services">
<img src="..." alt="Training">
```

جایگزین:
```html
<img src="/images/shortcuts/products.jpg" alt="Products">
<img src="/images/shortcuts/events.jpg" alt="Events">
<img src="/images/shortcuts/services.jpg" alt="Services">
<img src="/images/shortcuts/training.jpg" alt="Training">
```

---

## 📺 5. جایگزینی ویدیوی کارخانه (Aparat/YouTube)

### برای فارسی (Aparat):

1. ویدیو را در Aparat آپلود کنید
2. روی "اشتراک‌گذاری" کلیک کنید
3. کد Embed را کپی کنید
4. از URL بخش `src` را بردارید

مثال:
```
https://www.aparat.com/video/video/embed/videohash/YOUR_VIDEO_ID/vt/frame
```

**مکان در کد** (خط ~1427):
```html
<iframe id="factory-video" src="https://www.aparat.com/video/video/embed/videohash/sample/vt/frame"></iframe>
```

جایگزین: `sample` را با ID ویدیوی خودتان عوض کنید.

### برای انگلیسی (YouTube):

1. ویدیو را در YouTube آپلود کنید
2. روی Share → Embed کلیک کنید
3. URL را کپی کنید

مثال:
```
https://www.youtube.com/embed/YOUR_VIDEO_ID
```

**در JavaScript** (خط ~1721):
```javascript
document.getElementById('factory-video').src = currentLang === 'fa' 
  ? 'https://www.aparat.com/video/video/embed/videohash/YOUR_ID/vt/frame' 
  : 'https://www.youtube.com/embed/YOUR_YOUTUBE_ID';
```

---

## 🎨 6. جایگزینی آیکون‌های SVG شبکه‌های اجتماعی

### مکان در کد (خطوط ~1500-1547):

```html
<section class="mix-social-strip">
  <a href="https://linkedin.com" target="_blank" class="mix-social-icon">
    <svg viewBox="0 0 24 24">
      <path d="..."/>  ← کد SVG آیکون LinkedIn
    </svg>
  </a>
  <!-- Instagram, YouTube, Aparat, Telegram -->
</section>
```

### چطوری آیکون‌ها را جایگزین کنیم؟

**روش 1: از Heroicons استفاده کنید**
1. به [heroicons.com](https://heroicons.com) بروید
2. آیکون مورد نظر را جستجو کنید
3. SVG Code را کپی کنید
4. داخل تگ `<svg>` قرار دهید

**روش 2: از Font Awesome**
1. به [fontawesome.com](https://fontawesome.com/icons) بروید
2. آیکون را انتخاب کنید
3. SVG را دانلود و محتوای `<path>` را کپی کنید

**نکته**: حتماً `viewBox="0 0 24 24"` را حفظ کنید!

---

## ✏️ 7. تغییر متن‌ها

### الف) تیترهای Hero (متن‌های چرخشی)

**مکان در JavaScript** (خط ~1646):
```javascript
const heroMessages = {
  fa: [
    { title: 'کیفیت برتر با طراحی ایتالیایی', subtitle: 'محصولات آشپزخانه...' },
    { title: 'نوآوری در هر جزئیات', subtitle: 'تکنولوژی پیشرفته...' },
    { title: 'زیبایی که ماندگار است', subtitle: 'طراحی‌هایی که...' }
  ],
  en: [
    { title: 'Premium Quality...', subtitle: 'Kitchen products...' },
    // ...
  ]
};
```

**چطوری اضافه کنیم؟**
```javascript
fa: [
  // پیام‌های فعلی...
  { title: 'متن جدید شما', subtitle: 'زیرمتن جدید شما' }
],
```

### ب) عناوین سکشن‌ها

**مکان** (مثلاً خط ~1345):
```html
<h2>
  <span class="text-fa">میکس‌پلاس؛ کیفیت و زیبایی...</span>
  <span class="text-en hidden">MixPlus: Quality...</span>
</h2>
```

فقط متن داخل `<span>` را تغییر دهید.

### ج) تغییر لینک‌های شبکه‌های اجتماعی

**مکان** (خط ~1080 - در منوی هدر):
```html
<div class="mix-dropdown" id="social-dropdown">
  <a href="https://instagram.com" target="_blank">Instagram</a>
  <a href="https://aparat.com" target="_blank">Aparat</a>
  <a href="https://youtube.com" target="_blank">YouTube</a>
  <a href="https://linkedin.com" target="_blank">LinkedIn</a>
  <a href="https://t.me" target="_blank">Telegram</a>
</div>
```

لینک‌ها را با URL واقعی خودتان جایگزین کنید:
```html
<a href="https://instagram.com/mixplus_official" target="_blank">Instagram</a>
```

همین کار را در **Social Strip** هم انجام دهید (خط ~1500).

---

## 🎨 8. تغییر رنگ برند

**مکان در CSS** (خط ~67):
```css
:root {
  --brand: #0fa99c;  ← رنگ اصلی سبز
}
```

برای تغییر:
```css
--brand: #FF5733;  ← رنگ جدید (مثلاً نارنجی)
```

این رنگ در تمام سایت (دکمه‌ها، hover ها، لوگو فوتر) اعمال می‌شود.

---

## 🚀 9. دیپلوی روی GitHub Pages

### مرحله 1: ایجاد Repository

```bash
# در ترمینال:
cd mixplus-website
git init
git add .
git commit -m "Initial commit: MixPlus website"
```

### مرحله 2: اتصال به GitHub

1. به [github.com](https://github.com) بروید
2. یک Repository جدید بسازید (مثلاً `mixplus`)
3. در ترمینال:

```bash
git remote add origin https://github.com/YOUR_USERNAME/mixplus.git
git branch -M main
git push -u origin main
```

### مرحله 3: فعال‌سازی GitHub Pages

1. به **Settings** بروید
2. از منوی چپ **Pages** را کلیک کنید
3. در بخش **Source**:
   - Branch: `main`
   - Folder: `/ (root)`
4. **Save** را بزنید

### ✅ سایت شما Live می‌شود:
```
https://YOUR_USERNAME.github.io/mixplus/
```

**نکته**: بعد از push، 2-3 دقیقه صبر کنید تا سایت آماده شود.

---

## 📝 10. نکات نهایی

### ✅ چک‌لیست قبل از دیپلوی:

- [ ] تمام فونت‌ها جایگزین شدند
- [ ] لوگوهای light و dark در `/logos/` قرار گرفتند
- [ ] ویدیوهای Hero آپلود شدند (< 5MB)
- [ ] تصاویر بنرها (1920×1080) بهینه شدند
- [ ] تصاویر کارت‌های محصولات (400×533) اضافه شدند
- [ ] تصاویر کارت‌های میانبر (400×400) قرار گرفتند
- [ ] لینک ویدیوی Aparat/YouTube جایگزین شد
- [ ] لینک‌های شبکه‌های اجتماعی به‌روز شدند
- [ ] فایل‌های PDF کاتالوگ (`catalog-fa.pdf` و `catalog-en.pdf`) آپلود شدند
- [ ] متن‌های تیترها و زیرمتن‌ها بررسی شدند

### 🔧 رفع مشکلات رایج:

**فونت‌ها نمایش داده نمی‌شوند:**
- مطمئن شوید مسیر `/fonts/` درست است
- فایل‌ها باید حتماً `.woff2` باشند
- در DevTools (F12) → Network چک کنید فایل‌ها لود می‌شوند

**لوگو تغییر نمی‌کند:**
- Ctrl+Shift+R (Hard Refresh) بزنید
- مطمئن شوید هر دو لوگو در `/logos/` هستند

**ویدیوها پخش نمی‌شوند:**
- فایل باید < 5MB باشد
- فرمت MP4 (H.264)
- حتماً `muted` باشد
- اگر در GitHub Pages دیپلوی کرده‌اید، مسیر را چک کنید

---

## 📞 پشتیبانی

برای سوالات:
- 📧 Email: support@mixplus.ir
- 🌐 Website: www.mixplus.ir

---

**ساخته شده با ❤️ برای MixPlus**

© 2024 MixPlus. All rights reserved.
