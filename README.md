# html-css-ni-ohrguihrguwurighwrgcard__detai
CSS-da elementlarni to'g'ri joylashtirish va maket (layout) yaratish — veb-dasturlashning eng asosiy poydevorlaridan biridir. Quyida so'ralgan barcha tartiblar va ularning eng zamonaviy yechimlari keltirilgan.

1. Elementni (Div) markazlashtirishning 5 xil usuli
Ota-blok (.parent) ichidagi bola-blokni (.child) ham gorizontal, ham vertikal markazga keltirish usullari:

Usul 1: Flexbox (Eng mashhur va oson usul)
CSS
.parent {
    display: flex;
    justify-content: center; /* Gorizontal */
    align-items: center;     /* Vertikal */
}
Usul 2: CSS Grid (place-items)
Atigi ikki qator kod bilan mukammal markazlashtirish:

CSS
.parent {
    display: grid;
    place-items: center;
}
Usul 3: Absolute va CSS Transform
Bola-blok o'lchamlari aniq bo'lmagan holatlar uchun juda mos keladi:

CSS
.parent {
    position: relative;
}
.child {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}
Usul 4: Flexbox + margin: auto
Flex-konteyner ichidagi elementga margin: auto berilsa, u barcha bo'sh joyni teng bo'lib oladi:

CSS
.parent {
    display: flex;
}
.child {
    margin: auto;
}
Usul 5: Absolute + Margin auto (O'lchamlari aniq bloklar uchun)
Agar .child blokning width va height qiymatlari aniq bo'lsa:

CSS
.parent {
    position: relative;
}
.child {
    position: absolute;
    top: 0; bottom: 0; left: 0; right: 0;
    margin: auto;
    width: 200px;  /* Majburiy */
    height: 100px; /* Majburiy */
}
2. Sticky Footer (Sahifa pastida qoluvchi footer)
Agar sahifada kontent juda kam bo'lsa, footer sahifa o'rtasiga ko'tarilib qoladi. Buni oldini olish va kontent kam bo'lsa ham footerni ekran tubiga "yopishtirib" qo'yish uchun Flexbox eng yaxshi yechimdir:

HTML
<body class="site-wrapper">
    <header>Header</header>
    <main class="main-content">Kontent kam bo'lsa ham...</main>
    <footer>Footer har doim pastda</footer>
</body>
CSS
.site-wrapper {
    display: flex;
    flex-direction: column;
    min-height: 100vh; /* Butun ekran balandligi */
}

.main-content {
    flex-grow: 1; /* Barcha bo'sh joyni egallab, footerni pastga suradi */
}
3. Holy Grail Layout
Bu klassik veb-maket tuzilishi bo'lib, u Header, Chap Sidebar, Asosiy Kontent, O'ng Sidebar va Footerdan tashkil topadi. CSS Grid yordamida uni responsive qilish juda oson:

HTML
<div class="holy-grail">
    <header class="hg-header">Header</header>
    <aside class="hg-left">Chap Sidebar</aside>
    <main class="hg-main">Asosiy Kontent</main>
    <aside class="hg-right">O'ng Sidebar</aside>
    <footer class="hg-footer">Footer</footer>
</div>
CSS
.holy-grail {
    display: grid;
    grid-template-columns: 200px 1fr 200px;
    grid-template-rows: auto 1fr auto;
    min-height: 100vh;
}

.hg-header { grid-column: 1 / -1; } /* 1-chiziqdan oxirigacha */
.hg-footer { grid-column: 1 / -1; }

/* Mobil qurilmalar uchun moslashtirish (Media query) */
@media (max-width: 768px) {
    .holy-grail {
        grid-template-columns: 1fr;
        grid-template-rows: auto auto auto auto auto;
    }
    .hg-header, .hg-left, .hg-main, .hg-right, .hg-footer {
        grid-column: auto;
    }
}
4. Teng balandlikdagi ustunlar (Equal Height Columns)
Eski CSS-da ustunlar ichidagi matn hajmiga qarab biri kalta, biri uzun bo'lib qolardi. Flexbox va Grid tizimlarida avtomatik ravishda barcha qo'shni ustunlar eng uzun element balandligiga tenglashadi.

CSS
/* Usul 1: Flexbox bilan */
.columns-container-flex {
    display: flex;
    align-items: stretch; /* Standart qiymat, ustunlarni tenglashtiradi */
}

/* Usul 2: Grid bilan */
.columns-container-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr); /* 3 ta teng ustun */
}
5. Fixed Header bilan to'liq sahifa layout
Header sahifaning eng yuqorisida qotib turadi (fixed), qolgan kontent esa uning tagidan scroll bo'ladi. Bu tartibda kontent header ortiga yashirinib qolmasligi uchun padding-top ishlatiladi.

HTML
<header class="fixed-header">Navigatsiya paneli</header>
<main class="page-body">Sahifa asosiy kontenti shu yerda...</main>
CSS
*, *::before, *::after {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

.fixed-header {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 70px; /* Header aniq balandligi */
    background-color: #1e293b;
    color: white;
    z-index: 1000; /* Barcha elementlardan ustida turishi uchun */
}

.page-body {
    padding-top: 70px; /* Header balandligi bilan bir xil bo'lishi shart */
    min-height: 100vh;
    background-color: #f1f5f9;
}
