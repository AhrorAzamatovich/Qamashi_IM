# Qamashi IM — Professional School Portal

Qamashi tumani ixtisoslashtirilgan maktabi uchun GitHub Pages + Supabase asosidagi zamonaviy axborot portali.

## Imkoniyatlar

- Responsive professional dizayn
- Bosh sahifa, yangiliklar, tadbirlar, maktab haqida, aloqa
- Email/parol orqali ro‘yxatdan o‘tish va kirish
- Shaxsiy kabinet
- Foydalanuvchi post yuborishi
- Rasm yuklash
- Moderator tasdig‘i
- Admin/moderator paneli
- Kategoriyalar
- Qidiruv va filtr
- Post ko‘rishlar soni
- SEO meta teglar
- GitHub Pages bilan ishlash
- Supabase PostgreSQL + Auth + Storage

## 1. GitHub

Yangi repository yarating, masalan:

`QamashiIM`

ZIP ichidagi barcha fayllarni repository root'iga yuklang.

## 2. Supabase

Supabase'da yangi project yarating.

SQL Editor'ni oching va:

`sql/schema.sql`

faylidagi SQL kodni to‘liq ishga tushiring.

## 3. Supabase API

Supabase:

Project Settings → API

bo‘limidan:

- Project URL
- Publishable/Anon key

ni oling.

`js/config.js` faylini ochib:

```js
window.QAMASHI_CONFIG = {
  SUPABASE_URL: "https://YOUR-PROJECT.supabase.co",
  SUPABASE_ANON_KEY: "YOUR-PUBLISHABLE-OR-ANON-KEY"
};
```

joylarini o‘zingiznikiga almashtiring.

**Service role / secret keyni frontendga yozmang.**

## 4. Auth URL

Supabase:

Authentication → URL Configuration

ichida GitHub Pages manzilingizni Site URL sifatida qo‘ying.

Masalan:

`https://USERNAME.github.io/QamashiIM/`

Redirect URLsga ham shu manzilni qo‘shing.

## 5. Birinchi administrator

Oddiy foydalanuvchi sifatida register.html orqali akkaunt yarating.

Supabase:

Table Editor → profiles

ga kirib o‘sha foydalanuvchining `role` qiymatini:

`admin`

qiling.

Shundan keyin:

`/admin/`

orqali moderator paneliga kirishingiz mumkin.

## 6. GitHub Pages

Repository:

Settings → Pages

Source:

`Deploy from a branch`

Branch:

`main`

Folder:

`/ (root)`

Save.

## 7. Muhim

GitHub Pages faqat frontendni hosting qiladi. Foydalanuvchilar, login, postlar va rasmlar Supabase orqali saqlanadi.

## Tavsiya etiladigan keyingi bosqichlar

- Google/Yandex Search Console
- sitemap.xml va robots.txt
- Telegram bot orqali yangi post xabari
- Google Analytics
- CAPTCHA / anti-spam
- foydalanuvchi profil rasmi
- post tahrirlash
- admin foydalanuvchilar boshqaruvi
- rasm galereyasi
- video galereya
- maktab hujjatlari bo‘limi
