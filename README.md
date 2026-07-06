# html-css-ni-ohrguihrguwurighwrg
Mana, so'ralgan barcha talablarga javob beradigan, zamonaviy dizayndagi, to'liq responsive (mobil qurilmalarga moslashuvchan) veb-sahifa andozasi.

1. HTML fayli (index.html)
HTML
<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Zamonaviy Landing Page</title>
    <link rel="stylesheet" href="style.css">
</head>
<body class="page">

    <header class="hero">
        <div class="hero__container">
            <h1 class="hero__title">Biznesingizni Raqamli Dunyoga Olib Chiqing</h1>
            <p class="hero__description">Kompaniyangiz uchun zamonaviy veb-saytlar, mobil ilovalar va brending xizmatlarini yuqori sifatda taqdim etamiz.</p>
            <a href="#services" class="hero__btn">Xizmatlar bilan tanishish</a>
        </div>
    </header>

    <section id="services" class="services">
        <h2 class="services__main-title">Bizning Xizmatlar</h2>
        <div class="services__grid">
            
            <article class="service-card">
                <div class="service-card__icon">💻</div>
                <h3 class="service-card__title">Web Dasturlash</h3>
                <p class="service-card__text">Har qanday murakkablikdagi tezkor va xavfsiz veb-saytlarni yaratish.</p>
            </article>

            <article class="service-card">
                <div class="service-card__icon">📱</div>
                <h3 class="service-card__title">Mobil Ilovalar</h3>
                <p class="service-card__text">iOS va Android platformalari uchun qulay va chiroyli ilovalar.</p>
            </article>

            <article class="service-card">
                <div class="service-card__icon">🎨</div>
                <h3 class="service-card__title">UI/UX Dizayn</h3>
                <p class="service-card__text">Foydalanuvchilarga ma'qul keladigan zamonaviy va interaktiv interfeyslar.</p>
            </article>

        </div>
    </section>

    <section class="testimonials">
        <h2 class="testimonials__main-title">Mijozlarimiz Fikrlari</h2>
        <div class="testimonials__flex">
            
            <div class="review-card">
                <p class="review-card__text">"Ushbu jamoa bilan ishlash juda yoqimli bo'ldi. Veb-saytimizni aytilgan muddatdan oldin va mukammal tarzda topshirishdi!"</p>
                <div class="review-card__author">
                    <span class="review-card__name">Asrorbekov Sardor</span>
                    <span class="review-card__company">"TechCorp" rahbari</span>
                </div>
            </div>

            <div class="review-card">
                <p class="review-card__text">"Ajoyib dizayn va yuqori sifat. Mobil ilovamiz ishga tushganidan so'ng mijozlarimiz soni ikki barobarga ko'paydi."</p>
                <div class="review-card__author">
                    <span class="review-card__name">Malika Karimova</span>
                    <span class="review-card__company">"GreenFood" asoschisi</span>
                </div>
            </div>

        </div>
    </section>

    <footer class="footer">
        <div class="footer__container">
            <div class="footer__info">
                <h4 class="footer__title">Aloqa</h4>
                <p class="footer__text">Telefon: +998 (90) 123-45-67</p>
                <p class="footer__text">Email: info@example.com</p>
            </div>
            <div class="footer__socials">
                <h4 class="footer__title">Ijtimoiy tarmoqlar</h4>
                <div class="footer__links">
                    <a href="#" class="footer__link">Telegram</a>
                    <a href="#" class="footer__link">Instagram</a>
                    <a href="#" class="footer__link">LinkedIn</a>
                </div>
            </div>
        </div>
        <div class="footer__bottom">
            <p>&copy; 2026 Barcha huquqlar himoyalangan.</p>
        </div>
    </footer>

</body>
</html>
2. CSS fayli (style.css)
CSS
/* ========================================================
   6. CSS CUSTOM PROPERTIES (VARIABLES)
   ======================================================== */
:root {
    --primary-color: #2563eb;
    --primary-hover: #1d4ed8;
    --secondary-color: #0f172a;
    --bg-light: #f8fafc;
    --bg-white: #ffffff;
    --text-dark: #1e293b;
    --text-muted: #64748b;
    --shadow-sm: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
    --shadow-md: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
    --transition-smooth: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    --font-main: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

/* Umumiy reset qoidalari */
*, *::before, *::after {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

html {
    scroll-behavior: smooth;
}

.page {
    font-family: var(--font-main);
    color: var(--text-dark);
    background-color: var(--bg-white);
    line-height: 1.6;
}

/* ========================================================
   1. HERO SECTION STILLARI
   ======================================================== */
.hero {
    background: linear-gradient(135deg, var(--secondary-color), #1e293b);
    color: var(--bg-white);
    padding: 100px 20px;
    text-align: center;
}

.hero__container {
    max-width: 800px;
    margin: 0 auto;
}

.hero__title {
    font-size: 2.5rem;
    font-weight: 800;
    margin-bottom: 20px;
    line-height: 1.2;
}

.hero__description {
    font-size: 1.2rem;
    color: #cbd5e1;
    margin-bottom: 40px;
}

/* 7. Hover animatsiyasi (Tugma) */
.hero__btn {
    display: inline-block;
    background-color: var(--primary-color);
    color: var(--bg-white);
    padding: 14px 28px;
    border-radius: 8px;
    text-decoration: none;
    font-weight: 600;
    transition: var(--transition-smooth);
}

.hero__btn:hover {
    background-color: var(--primary-hover);
    transform: translateY(-2px);
    box-shadow: 0 4px 12px rgba(37, 99, 235, 0.3);
}

/* ========================================================
   2. FEATURES/SERVICES SECTION (GRID ORQALI RESPONSIVE)
   ======================================================== */
.services {
    padding: 80px 20px;
    background-color: var(--bg-light);
}

.services__main-title {
    text-align: center;
    font-size: 2rem;
    margin-bottom: 50px;
    position: relative;
}

/* 5. Grid bilan responsive joylashuv */
.services__grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 30px;
    max-width: 1100px;
    margin: 0 auto;
}

.service-card {
    background-color: var(--bg-white);
    padding: 40px 30px;
    border-radius: 12px;
    box-shadow: var(--shadow-sm);
    transition: var(--transition-smooth);
}

.service-card__icon {
    font-size: 2.5rem;
    margin-bottom: 20px;
}

.service-card__title {
    font-size: 1.3rem;
    margin-bottom: 12px;
}

.service-card__text {
    color: var(--text-muted);
    font-size: 0.95rem;
}

/* 7. Hover animatsiyasi (Karta) */
.service-card:hover {
    transform: translateY(-8px);
    box-shadow: var(--shadow-md);
}

/* ========================================================
   3. TESTIMONIALS SECTION (FLEXBOX ORQALI RESPONSIVE)
   ======================================================== */
.testimonials {
    padding: 80px 20px;
}

.testimonials__main-title {
    text-align: center;
    font-size: 2rem;
    margin-bottom: 50px;
}

/* 5. Flexbox bilan responsive joylashuv */
.testimonials__flex {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 30px;
    max-width: 1100px;
    margin: 0 auto;
}

.review-card {
    background-color: var(--bg-light);
    padding: 30px;
    border-radius: 12px;
    flex: 1 1 450px; /* Minimal 450px joy egallaydi, joy qolmasa pastga tushadi */
    max-width: 520px;
}

.review-card__text {
    font-style: italic;
    color: var(--text-dark);
    margin-bottom: 20px;
}

.review-card__author {
    display: flex;
    flex-direction: column;
}

.review-card__name {
    font-weight: 700;
}

.review-card__company {
    font-size: 0.85rem;
    color: var(--text-muted);
}

/* ========================================================
   4. FOOTER STILLARI
   ======================================================== */
.footer {
    background-color: var(--secondary-color);
    color: #94a3b8;
    padding: 60px 20px 20px 20px;
}

/* 5. Flexbox orqali footer komponentlarini ajratish */
.footer__container {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    gap: 40px;
    max-width: 1100px;
    margin: 0 auto;
    border-bottom: 1px solid #334155;
    padding-bottom: 40px;
}

.footer__title {
    color: var(--bg-white);
    margin-bottom: 20px;
    font-size: 1.1rem;
}

.footer__text {
    margin-bottom: 10px;
}

.footer__links {
    display: flex;
    gap: 20px;
}

.footer__link {
    color: #94a3b8;
    text-decoration: none;
    transition: color 0.2s ease;
}

.footer__link:hover {
    color: var(--bg-white);
}

.footer__bottom {
    text-align: center;
    padding-top: 20px;
    font-size: 0.85rem;
}

/* ========================================================
   RESPONSIVE DESIGN (MEDIA QUERIES)
   ======================================================== */
@media (max-width: 768px) {
    .hero__title {
        font-size: 2rem;
    }
    
    .footer__container {
        flex-direction: column;
        text-align: center;
    }

    .footer__links {
        justify-content: center;
    }
}
