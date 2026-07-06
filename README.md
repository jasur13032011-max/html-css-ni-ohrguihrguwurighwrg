# html-css-ni-ohrguihrguwurighwrgcard__detai
1. Render-blocking CSS nima va uni qanday hal qilish kerak?
Brauzer HTML sahifani o'qiyotganda, barcha tashqi CSS fayllari (<link rel="stylesheet">) to'liq yuklab olinmaguncha va tahlil qilinmaguncha sahifani ekranga chizishni (renderlashni) to'xtatib turadi. Bu Render-blocking CSS deb ataladi. Brauzer buni sayt xunuk, stillarsiz holatda ko'rinib qolmasligi (FOUC — Flash of Unstyled Content) uchun qiladi.

Muammoni hal qilish usullari:
Critical CSS (Eng muhim CSS): Sahifaning birinchi ekranga yuklanadigan qismi (Above-the-fold — masalan, navbar va hero section) uchun stillarni alohida ajratib, ularni HTML-ning <head> qismiga <style> tegi ichida to'g'ridan-to'g'ri (inline) yozish.

Asinxron CSS yuklash: Muhim bo'lmagan, pastroqdagi (Below-the-fold) stillarni yuklashni kechiktirish. Buning uchun media atributidan foydalanish keng tarqalgan:

HTML
<link rel="stylesheet" href="styles.css" media="print" onload="this.media='all'">
2. Samarali (Efficient) va Samarasiz (Inefficient) Selektorlar
Brauzer CSS selektorlarini o'ngdan chapga qarab o'qiydi (Right-to-Left). Shuning uchun eng oxirgi yozilgan selektor juda umumiy bo'lsa, brauzer ortiqcha energiya sarflaydi.

❌ Samarasiz selektorlar (Yomon amaliyot):
CSS
/* 1. Brauzer avval sahifadagi barcha 'a' teglarini topadi, keyin ulardan qaysi biri '.nav' ichidaligini qidiradi */
.nav li a { color: blue; } 

/* 2. Juda uzun va og'ir zanjir (Vazni ham oshib ketadi) */
body div.container main article.card .card__title { font-size: 20px; }

/* 3. Universal selektor bilan qo'shib yozish (eng yomoni) */
.sidebar * { box-sizing: border-box; }
Samarali selektorlar (Yaxshi amaliyot):
CSS
/* 1. To'g'ridan-to'g'ri klassga murojaat (Tezkor va aniq) */
.nav__link { color: blue; }

/* 2. BEM metodologiyasi bo'yicha qisqa klass (Zanjirsiz) */
.card__title { font-size: 20px; }
3. will-change Xossasini To'g'ri va Noto'g'ri Ishlatish
will-change brauzerga qaysi element yaqin orada animatsiyaga kirishishini oldindan aytadi. Bu brauzerga o'sha element uchun GPU (grafik karta) xotirasidan alohida qatlam (layer) ajratib, tayyorgarlik ko'rishga imkon beradi.

❌ Noto'g'ri ishlatish (Aqliy va resurs jihatdan zarar):
CSS
/* 1. Barcha elementlarga birdaniga berish GPU xotirasini to'ldirib, saytni qotiradigan qiladi */
* { will-change: transform, opacity; }

/* 2. Animatsiya paytida yoki undan keyin ham qolib ketishi (Doimiy resurs yeydi) */
.box { will-change: transform; transform: scale(1.1); }
To'g'ri ishlatish:
Faqat haqiqatdan ham og'ir yuklanadigan, foydalanuvchi ta'sir o'tkazadigan elementlarga va faqat kerakli vaqtda qo'llash lozim:

CSS
/* Ota-blok hover bo'lganda, bola-blok o'zgarishga tayyorlanadi */
.card:hover .card__image {
    will-change: transform;
}
.card__image {
    transition: transform 0.3s;
}
.card__image:hover {
    transform: scale(1.05);
}
Eslatma: JavaScript orqali animatsiya boshlanishidan biroz oldin will-change qo'shib, animatsiya tugagach uni olib tashlash eng ideal yo'ldir.

4. content-visibility: auto Qachon Qo'llaniladi?
content-visibility: auto — bu sahifa unumdorligini oshiruvchi juda kuchli zamonaviy xossadir. U element ekranga yaqinlashmaguncha (Viewport-ga kirmaguncha) uning ichki kontentini renderlash va hisoblash ishlarini kechiktiradi (to'xtatib turadi).

Qachon qo'llash kerak?
Uzun skrolli sahifalarda: Masalan, blog postlar ro'yxati, yangiliklar tasmasi (Feed) yoki sharhlar ko'p bo'lgan sahifalarda.

Saytning pastki qismidagi og'ir bloklarda: Footer yoki murakkab taqqoslash jadvallarida.

CSS
.long-feed__item {
    content-visibility: auto;
    contain-intrinsic-size: 0 500px; /* Skroll sakrab ketmasligi uchun elementning taxminiy balandligi beriladi */
}
5. Repaint va Reflow (Layout) Qiluvchi Xususiyatlar Ro'yxati
Brauzer sahifani chizishda ikki bosqichdan o'tadi: Reflow (elementlar joylashuvi va o'lchamini hisoblash) va Repaint (ranglar, soyalar va vizual ko'rinishni chizish). Reflow eng og'ir operatsiya hisoblanadi, chunki u bitta element o'zgarganda butun sahifa tartibini qayta hisoblashga majbur qilishi mumkin.

⚠️ Reflow keltirib chiqaradigan xossalar (Eng og'ir):
Ushbu xossalar o'zgarganda brauzer element joyini qayta hisoblaydi va ketidan majburan Repaint ham qiladi:

width, height

padding, margin

top, bottom, left, right

font-size, font-family, line-height

display, border-width

Repaint keltirib chiqaradigan xossalar (O'rtacha og'irlikda):
Geometrik joylashuv o'zgarmaydi, faqat piksel ranglari yangilanadi:

color, background-color

visibility

box-shadow, text-shadow

border-style, border-radius

⚡ Faqat Composite (Eng yengil va tezkor):
GPU darajasida bajariladi, Reflow ham, Repaint ham sodir bo'lmaydi. Animatsiyalarni faqat shu ikki xossa bilan qilish tavsiya etiladi:

transform (translate, scale, rotate)

opacity
