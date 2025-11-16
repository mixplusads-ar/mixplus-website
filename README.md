# 🌟 MixPlus Website - وب‌سایت میکس‌پلاس

یک وب‌سایت کامل دوزبانه (فارسی/انگلیسی) برای شرکت میکس‌پلاس، تولیدکننده محصولات آشپزخانه با کیفیت و طراحی ایتالیایی.

---

## ✨ ویژگی‌های کلیدی

### 🌐 دوزبانه بدون Reload
- تغییر لحظه‌ای بین **فارسی (RTL)** و **انگلیسی (LTR)**
- ذخیره زبان انتخابی در localStorage
- تغییر خودکار ترتیب هدر بر اساس زبان
- تغییر محتوای ویدیو (Aparat برای فارسی، YouTube برای انگلیسی)

### 🎨 تم روشن/تیره
- دو تم کامل Light و Dark
- ذخیره تم در localStorage
- تغییر تمام رنگ‌ها و آیکون‌ها
- انیمیشن نرم در تغییر تم

### 📱 ریسپانسیو کامل
- طراحی Mobile-First
- Breakpoints: 480px, 768px, 968px, 1200px
- منوی موبایل (Hamburger) کاملاً کاربردی
- Grid های تطبیقی (4 → 2 → 1 ستون)

### 🎯 مگامنوهای پیشرفته
- منوی محصولات با 4 دسته + زیردسته‌های داینامیک
- منوی خدمات پس از فروش
- منوی شبکه‌های اجتماعی (با Hover)
- Hover-intent با تاخیر 250ms
- انیمیشن‌های نرم

### 🎬 هیرو داینامیک
- ویدیوهای رندوم (4 ویدیو)
- Fallback خودکار به تصویر
- تیترهای متناوب (10 پیام) هر 5 ثانیه
- فلش اسکرول انیمیت شده

---

## 📁 ساختار فایل

```
mixplus-website/
├── index.html          # فایل اصلی سایت
└── README.md          # این فایل
```

---

## 🚀 نحوه استفاده

### روش 1: باز کردن مستقیم
فقط فایل `index.html` را در مرورگر باز کنید.

### روش 2: دیپلوی روی GitHub Pages

#### گام 1: ایجاد Repository در GitHub
```bash
# در ترمینال:
git init
git add .
git commit -m "Initial commit: MixPlus website"
```

#### گام 2: اتصال به GitHub
```bash
# ریپوی جدید در GitHub بسازید (مثلاً mixplus-website)
git remote add origin https://github.com/YOUR_USERNAME/mixplus-website.git
git branch -M main
git push -u origin main
```

#### گام 3: فعال‌سازی GitHub Pages
1. در GitHub به **Settings** بروید
2. از منوی سمت چپ **Pages** را انتخاب کنید
3. در بخش **Source**:
   - Branch: `main`
   - Folder: `/ (root)`
4. روی **Save** کلیک کنید
5. بعد از چند دقیقه، سایت شما در این آدرس Live می‌شود:
   ```
   https://YOUR_USERNAME.github.io/mixplus-website/
   ```

### روش 3: دیپلوی روی Netlify

#### با رابط کاربری:
1. به [netlify.com](https://netlify.com) بروید
2. فایل `index.html` را Drag & Drop کنید
3. سایت شما Live می‌شود!

#### با Git:
1. ریپوی GitHub را به Netlify متصل کنید
2. Build Settings:
   - Build Command: (خالی بگذارید)
   - Publish Directory: `/`
3. Deploy!

---

## 🖼️ جایگزینی تصاویر و ویدیوها

### ویدیوهای Hero:
```html
<!-- در خط 1230 فایل index.html: -->
const videos = [
  '/videos/hero-01.mp4',  // ویدیوی شما
  '/videos/hero-02.mp4',
  '/videos/hero-03.mp4',
  '/videos/hero-04.mp4'
];
```

### تصاویر Fallback Hero:
```html
<!-- خط 991: -->
<img src="/images/hero-fallback.jpg" ...>
```

### تصاویر کارت‌های محصولات:
```html
<!-- خطوط 1041-1072: -->
<img src="/images/products/hob.jpg" ...>
<img src="/images/products/sink.jpg" ...>
<img src="/images/products/oven.jpg" ...>
<img src="/images/products/hood.jpg" ...>
```

### بنرهای Full-bleed:
```html
<!-- خطوط 1081، 1110، 1124، 1186: -->
<img src="/images/banners/fullbleed-01.jpg" ...>
<img src="/images/banners/fullbleed-02.jpg" ...>
<img src="/images/banners/fullbleed-03.jpg" ...>
<img src="/images/banners/fullbleed-04.jpg" ...>
```

### کارت‌های میانبر:
```html
<!-- خطوط 1149-1180: -->
<img src="/images/shortcuts/products.jpg" ...>
<img src="/images/shortcuts/events.jpg" ...>
<img src="/images/shortcuts/services.jpg" ...>
<img src="/images/shortcuts/training.jpg" ...>
```

### ویدیو کارخانه:
```javascript
// خط 792 (فارسی):
document.getElementById('factory-video').src = 'https://www.aparat.com/v/YOUR_VIDEO_ID';

// خط 801 (انگلیسی):
document.getElementById('factory-video').src = 'https://www.youtube.com/embed/YOUR_VIDEO_ID';
```

---

## 🎨 سفارشی‌سازی رنگ برند

در فایل CSS (خط 23):
```css
:root {
  --brand: #0fa99c;  /* رنگ اصلی برند */
}
```

---

## 📝 افزودن محتوای جدید

### اضافه کردن دسته محصول جدید:
```javascript
// خط 666 در JavaScript:
const categories = {
  // ... دسته‌های فعلی
  
  newCategory: {
    fa: [
      { name: 'زیردسته ۱', slug: 'sub1' },
      { name: 'زیردسته ۲', slug: 'sub2' }
    ],
    en: [
      { name: 'Subcategory 1', slug: 'sub1' },
      { name: 'Subcategory 2', slug: 'sub2' }
    ]
  }
};
```

### اضافه کردن تیتر Hero:
```javascript
// خط 690:
const heroMessages = {
  fa: [
    // ... پیام‌های فعلی
    { title: 'تیتر جدید', subtitle: 'ساب‌تیتر جدید' }
  ],
  en: [
    // ... پیام‌های فعلی
    { title: 'New Title', subtitle: 'New Subtitle' }
  ]
};
```

---

## 🔧 تنظیمات پیشرفته

### تغییر مدت نمایش تیترها:
```javascript
// خط 1278:
window.heroMessageInterval = setInterval(showNextMessage, 5000);
// 5000 = 5 ثانیه، می‌توانید تغییر دهید
```

### تغییر تاخیر Hover-intent:
```javascript
// خطوط 863، 871، 890، 898، 915، 923، 936، 944:
setTimeout(() => { ... }, 250);
// 250 = 250 میلی‌ثانیه
```

---

## 🌍 لینک‌های مهم

### فونت‌ها:
- **Vazirmatn**: [GitHub](https://github.com/rastikerdar/vazirmatn)
- **Montserrat**: [Google Fonts](https://fonts.google.com/specimen/Montserrat)

### تصاویر Placeholder:
- [Unsplash](https://unsplash.com)
- [Pexels](https://pexels.com)

### آیکون‌ها:
- [Heroicons](https://heroicons.com)
- [Feather Icons](https://feathericons.com)

---

## 📱 پشتیبانی مرورگرها

✅ Chrome, Edge, Firefox, Safari  
✅ موبایل: iOS Safari, Chrome Android  
✅ Tablet ها  

---

## 🐛 رفع مشکلات رایج

### ویدیو پخش نمی‌شود:
- مطمئن شوید فایل ویدیو کوچک است (< 5MB)
- ویدیو حتماً باید Muted باشد
- فرمت MP4 استفاده کنید

### منوی موبایل کار نمی‌کند:
- Ctrl+Shift+R را بزنید (Hard Refresh)
- Cache مرورگر را پاک کنید

### فونت‌ها درست نمایش داده نمی‌شوند:
- اتصال اینترنت را چک کنید (فونت‌ها از CDN بارگذاری می‌شوند)
- یا فونت‌های محلی اضافه کنید

---

## 📞 پشتیبانی

برای سوالات و مشکلات:
- 📧 Email: support@mixplus.ir
- 🌐 Website: www.mixplus.ir
- 📱 Instagram: @mixplus_official

---

## 📜 مجوز

© 2024 MixPlus. All rights reserved.

این کد برای استفاده در پروژه MixPlus طراحی شده است.

---

## 🎉 نکات نهایی

1. **SEO**: عناوین صفحات را در `<title>` تغییر دهید
2. **آنالیتیکس**: کد Google Analytics را اضافه کنید
3. **فاویکون**: فایل `favicon.ico` اضافه کنید
4. **Sitemap**: برای سئو بهتر sitemap.xml بسازید
5. **Performance**: تصاویر را بهینه کنید (WebP)

---

**ساخته شده با ❤️ برای MixPlus**
