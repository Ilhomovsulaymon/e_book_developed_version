# READORA — Elektron kutubxona (demo MVP)

Readora — O'zbek tilidagi, responsive elektron kutubxona prototipi. Hozirgi implementatsiya vanilla HTML/CSS/JavaScript bo'lib, LocalStorage orqali demo ma'lumotlarni saqlaydi.

## Ishga tushirish

1. ZIP arxivni oching.
2. `index.html`ni brauzerda oching yoki tavsiya etilgan usulda lokal serverni ishga tushiring:
   - Python: `python -m http.server 8000`
   - Brauzerda: `http://localhost:8000`
3. Service worker/PWA offline cache lokal HTTP/HTTPS serverda ishlaydi; `file://` rejimida service worker mavjud emas.

## Demo imkoniyatlari

- 30 ta seed kitob, 12 kategoriya va mualliflar ro'yxati.
- Home, katalog, kategoriyalar, mualliflar, kutubxona, sevimlilar, tarix, profil, sozlamalar, bildirishnomalar, demo auth, admin demo, kitob details, reader routes.
- Katalog: qidiruv, category/author/year/type filtrlari, sort va load-more, grid/list.
- Kitob details, sevimli, share, demo matn export, kitob statusini cycle qilish.
- Reader: original demo sample text, page navigation/progress save, bookmark, reader theme, font-size controls, fullscreen (browser support dependent), mark-read.
- Library statuses (later/reading/read), favorites, recently viewed, reading progress.
- Reviews add/edit/delete (local demo), notifications mark read/delete.
- Profile update, settings/theme, JSON import/export, reset.
- Admin demo: local role flag, add/delete custom demo books.
- Responsive layout, mobile bottom nav, accessible focus styles, reduced-motion support.
- PWA manifest and service-worker shell caching (serve on localhost/HTTPS).

## Muhim cheklovlar / production talablar

- Authentication va admin role faqat browser-local demo state. Bu server-side security emas, production uchun xavfsiz emas.
- Firebase/Supabase backend, server auth, password hashing, email verification, Google OAuth, multi-user database, remote file storage va real admin authorization ulanmagan.
- PDF/EPUB fayl parser/reader, upload storage va haqiqiy kitob fayllari ulanmagan. Reader demo sample text ishlatadi.
- Demo coverlar CSS-generated; real cover image provider/data source qo'shilmagan.
- Reviews lokal demo ma'lumotlari; aggregate rating/distribution va moderatsiya backend darajasida yo'q.
- Admin CRUD hozir custom demo books uchun. Author/category management, uploads, user management, search analytics backend yo'q.
- Notification reminders scheduled push emas; demo notification panel.
- Reading streak, elapsed reading time, page totals from actual document and charts are not fully implemented.
- Search history is saved on Enter, but full autocomplete dropdown/recent-search UX needs further implementation.
- Browser-based automated visual testing could not be run in this environment; headless Chromium startup timed out. Node syntax and mock-DOM functional checks were run instead.

## Test note

Run JavaScript syntax check with `node --check src/js/app.js`. The project has a local test harness in the build process (not shipped in this ZIP) for rendering routes and simulated interactions. Browser tests should be repeated in Chrome/Firefox on a real local server before deployment.
