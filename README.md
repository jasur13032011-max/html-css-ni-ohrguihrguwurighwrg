# html-css-ni-ohrguihrguwurighwrgcard__detai
1. HTML fayli (index.html)
HTML
<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tariflar va Narxlar</title>
    <link rel="stylesheet" href="style.css">
</head>
<body class="pricing-page">

    <div class="pricing-container">
        <header class="pricing-header">
            <h1 class="pricing-header__title">Mos keluvchi tarifni tanlang</h1>
            <p class="pricing-header__subtitle">Yillik reja bilan 20% gacha mablag'ni tejab qoling</p>
            
            <div class="toggle-wrapper">
                <span class="toggle-label">Oylik</span>
                <label class="pricing-toggle">
                    <input type="checkbox" id="billing-toggle" class="pricing-toggle__input">
                    <span class="pricing-toggle__slider"></span>
                </label>
                <span class="toggle-label">Yillik <span class="toggle-label__badge">-20%</span></span>
            </div>
        </header>

        <div class="pricing-grid">
            
            <article class="price-card">
                <h2 class="price-card__plan">Starter</h2>
                <p class="price-card__desc">Kichik jamoalar va endi boshlovchilar uchun.</p>
                <div class="price-card__price-box">
                    <span class="price-card__currency">$</span>
                    <span class="price-card__amount price-card__amount--monthly">19</span>
                    <span class="price-card__amount price-card__amount--yearly">15</span>
                    <span class="price-card__period">/oy</span>
                </div>
                <ul class="price-card__features">
                    <li>3 ta loyiha</li>
                    <li>Tasvir yuklash (5GB)</li>
                    <li>Asosiy tahlillar</li>
                    <li class="price-card__features--disabled">24/7 Qo'llab-quvvatlash</li>
                </ul>
                <button class="price-card__btn">Boshlash</button>
            </article>

            <article class="price-card price-card--featured">
                <span class="price-card__badge">Eng ommabop</span>
                <h2 class="price-card__plan">Pro</h2>
                <p class="price-card__desc">Kengayib borayotgan biznes egalari uchun.</p>
                <div class="price-card__price-box">
                    <span class="price-card__currency">$</span>
                    <span class="price-card__amount price-card__amount--monthly">49</span>
                    <span class="price-card__amount price-card__amount--yearly">39</span>
                    <span class="price-card__period">/oy</span>
                </div>
                <ul class="price-card__features">
                    <li>Cheksiz loyihalar</li>
                    <li>Tasvir yuklash (50GB)</li>
                    <li>Kengaytirilgan tahlillar</li>
                    <li>24/7 Qo'llab-quvvatlash</li>
                </ul>
                <button class="price-card__btn price-card__btn--featured">Pro-ga o'tish</button>
            </article>

            <article class="price-card">
                <h2 class="price-card__plan">Enterprise</h2>
                <p class="price-card__desc">Yirik tashkilotlar va maxsus talablar uchun.</p>
                <div class="price-card__price-box">
                    <span class="price-card__currency">$</span>
                    <span class="price-card__amount price-card__amount--monthly">99</span>
                    <span class="price-card__amount price-card__amount--yearly">79</span>
                    <span class="price-card__period">/oy</span>
                </div>
                <ul class="price-card__features">
                    <li>Maxsus infratuzilma</li>
                    <li>Cheksiz xotira</li>
                    <li>Shaxsiy menejer</li>
                    <li>SLA va API kafolati</li>
                </ul>
                <button class="price-card__btn">Aloqaga chiqish</button>
            </article>

        </div>

        <section class="comparison-section">
            <h2 class="comparison-section__title">Xususiyatlarni taqqoslang</h2>
            <div class="table-responsive">
                <table class="comparison-table">
                    <thead>
                        <tr>
                            <th>Xususiyatlar</th>
                            <th>Starter</th>
                            <th>Pro</th>
                            <th>Enterprise</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>Loyihalar soni</td>
                            <td>3 ta</td>
                            <td>Cheksiz</td>
                            <td>Cheksiz</td>
                        </tr>
                        <tr>
                            <td>Bulutli xotira</td>
                            <td>5 GB</td>
                            <td>50 GB</td>
                            <td>Maxsus</td>
                        </tr>
                        <tr>
                            <td>API imkoniyati</td>
                            <td><span class="mark mark--x">&times;</span></td>
                            <td><span class="mark mark--check">&#10003;</span></td>
                            <td><span class="mark mark--check">&#10003;</span></td>
                        </tr>
                        <tr>
                            <td>Shaxsiy menejer</td>
                            <td><span class="mark mark--x">&times;</span></td>
                            <td><span class="mark mark--x">&times;</span></td>
                            <td><span class="mark mark--check">&#10003;</span></td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </section>

        <section class="faq-section">
            <h2 class="faq-section__title">Tez-tez so'raladigan savollar</h2>
            <div class="faq-container">
                
                <details class="faq-item">
                    <summary class="faq-item__question">Tarifni xohlagan vaqtda o'zgartirsam bo'ladimi?</summary>
                    <div class="faq-item__answer">
                        <p>Ha, albatta. Siz xohlagan vaqtda tarifingizni yuqoriroq yoki pastroq rejaga o'tkazishingiz mumkin. To'lovlar avtomatik ravishda qayta hisoblanadi.</p>
                    </div>
                </details>

                <details class="faq-item">
                    <summary class="faq-item__question">Yillik tarifda qancha tejab qolaman?</summary>
                    <div class="faq-item__answer">
                        <p>Yillik tarifni tanlaganingizda oylik to'lovlarga nisbatan 20% gacha chegirb beriladi va mablag'ingiz tejaladi.</p>
                    </div>
                </details>

                <details class="faq-item">
                    <summary class="faq-item__question">To'lovni qaytarib olish kafolati bormi?</summary>
                    <div class="faq-item__answer">
                        <p>Ha, dastlabki 14 kun ichida xizmatimiz yoqmasa, hech qanday savollarsiz pullaringiz to'liq qaytarib beriladi.</p>
                    </div>
                </details>

                <details class="faq-item">
                    <summary class="faq-item__question">Qanday to'lov usullari mavjud?</summary>
                    <div class="faq-item__answer">
                        <p>Biz barcha turdagi xalqaro kredit kartalari (Visa, MasterCard), shuningdek, milliy to'lov tizimlari (UzCard, Humo) orqali to'lovlarni qabul qilamiz.</p>
                    </div>
                </details>

            </div>
        </section>

    </div>

</body>
</html>
2. CSS fayli (style.css)
CSS
/* Custom Properties (Variables) */
:root {
    --primary: #4f46e5;
    --primary-hover: #4338ca;
    --dark: #0f172a;
    --muted: #475569;
    --bg-light: #f8fafc;
    --white: #ffffff;
    --border: #e2e8f0;
    
    --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}

*, *::before, *::after {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background-color: #f1f5f9;
    color: var(--dark);
    line-height: 1.5;
    padding: 60px 20px;
}

.pricing-container {
    max-width: 1100px;
    margin: 0 auto;
}

/* HEADER STILLARI */
.pricing-header {
    text-align: center;
    margin-bottom: 50px;
}

.pricing-header__title {
    font-size: 36px;
    font-weight: 800;
    margin-bottom: 12px;
}

.pricing-header__subtitle {
    color: var(--muted);
    font-size: 16px;
    margin-bottom: 30px;
}

/* ========================================================
   1. TOGGLE — OYLIK / YILLIK CSS MEXANIZMI
   ======================================================== */
.toggle-wrapper {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 16px;
}

.toggle-label {
    font-weight: 600;
    font-size: 15px;
}

.toggle-label__badge {
    background-color: #dcfce7;
    color: #15803d;
    padding: 2px 8px;
    border-radius: 12px;
    font-size: 12px;
    margin-left: 4px;
}

.pricing-toggle {
    position: relative;
    display: inline-block;
    width: 60px;
    height: 34px;
    cursor: pointer;
}

.pricing-toggle__input {
    opacity: 0;
    width: 0;
    height: 0;
}

.pricing-toggle__slider {
    position: absolute;
    top: 0; left: 0; right: 0; bottom: 0;
    background-color: #cbd5e1;
    border-radius: 34px;
    transition: var(--transition);
}

.pricing-toggle__slider::before {
    content: "";
    position: absolute;
    height: 26px;
    width: 26px;
    left: 4px;
    bottom: 4px;
    background-color: var(--white);
    border-radius: 50%;
    transition: var(--transition);
}

/* Fokus holati */
.pricing-toggle__input:focus + .pricing-toggle__slider {
    box-shadow: 0 0 8px rgba(79, 70, 229, 0.4);
}

.pricing-toggle__input:checked + .pricing-toggle__slider {
    background-color: var(--primary);
}

.pricing-toggle__input:checked + .pricing-toggle__slider::before {
    transform: translateX(26px);
}

/* Oylik va Yillik narxlarni ko'rsatish/yashirish mexanizmi */
.price-card__amount--yearly {
    display: none;
}

/* Agar checkbox belgilangan bo'lsa (yillik reja) */
body:has(#billing-toggle:checked) .price-card__amount--monthly {
    display: none;
}
body:has(#billing-toggle:checked) .price-card__amount--yearly {
    display: inline;
}


/* ========================================================
   2, 3 & 4. TARIF KARTALARI GRID LAYOUT & PRO HIGHLIGHT
   ======================================================== */
.pricing-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 30px;
    align-items: center;
    margin-bottom: 80px;
}

.price-card {
    background-color: var(--white);
    padding: 35px 30px;
    border-radius: 16px;
    box-shadow: 0 4px 6px -1px rgba(0,0,0,0.05);
    border: 1px solid var(--border);
    position: relative;
    transition: var(--transition);
}

/* 7. Hover effekti kartalarda */
.price-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 10px 25px -5px rgba(0,0,0,0.1);
}

/* 4. Pro karta vizual ajratilishi */
.price-card--featured {
    border: 2px solid var(--primary);
    background-color: var(--white);
    box-shadow: 0 20px 25px -5px rgba(79, 70, 229, 0.1);
    transform: scale(1.03);
}

.price-card--featured:hover {
    transform: scale(1.03) translateY(-5px);
}

.price-card__badge {
    position: absolute;
    top: -15px;
    left: 50%;
    transform: translateX(-50%);
    background-color: var(--primary);
    color: var(--white);
    padding: 4px 14px;
    font-size: 12px;
    font-weight: 700;
    border-radius: 20px;
    text-transform: uppercase;
}

.price-card__plan {
    font-size: 22px;
    font-weight: 700;
    margin-bottom: 8px;
}

.price-card__desc {
    color: var(--muted);
    font-size: 14px;
    margin-bottom: 24px;
    height: 42px;
}

.price-card__price-box {
    margin-bottom: 24px;
}

.price-card__currency {
    font-size: 24px;
    font-weight: 700;
    vertical-align: super;
}

.price-card__amount {
    font-size: 48px;
    font-weight: 800;
}

.price-card__period {
    color: var(--muted);
    font-size: 16px;
}

.price-card__features {
    list-style: none;
    margin-bottom: 30px;
    display: flex;
    flex-direction: column;
    gap: 12px;
}

.price-card__features li {
    font-size: 14px;
    font-weight: 500;
}

.price-card__features li::before {
    content: "✓";
    color: #10b981;
    margin-right: 8px;
    font-weight: bold;
}

.price-card__features .price-card__features--disabled {
    color: #94a3b8;
    text-decoration: line-through;
}

.price-card__features .price-card__features--disabled::before {
    content: "✕";
    color: #ef4444;
}

/* 7. Tugmalarda hover va focus animatsiyalari */
.price-card__btn {
    width: 100%;
    padding: 12px;
    background-color: var(--bg-light);
    color: var(--primary);
    border: 1px solid var(--border);
    border-radius: 8px;
    font-size: 15px;
    font-weight: 600;
    cursor: pointer;
    transition: var(--transition);
    outline: none;
}

.price-card__btn:hover, .price-card__btn:focus-visible {
    background-color: var(--primary);
    color: var(--white);
    border-color: var(--primary);
    box-shadow: 0 4px 12px rgba(79, 70, 229, 0.2);
}

.price-card__btn--featured {
    background-color: var(--primary);
    color: var(--white);
    border-color: var(--primary);
}

.price-card__btn--featured:hover, .price-card__btn--featured:focus-visible {
    background-color: var(--primary-hover);
}


/* ========================================================
   5. XUSUSIYATLAR TAQQOSLASH JADVALI (CHECKMARK/XMARK)
   ======================================================== */
.comparison-section {
    margin-bottom: 80px;
    background-color: var(--white);
    padding: 40px 30px;
    border-radius: 16px;
    box-shadow: 0 4px 6px -1px rgba(0,0,0,0.05);
}

.comparison-section__title {
    text-align: center;
    font-size: 24px;
    margin-bottom: 30px;
}

.table-responsive {
    overflow-x: auto;
}

.comparison-table {
    width: 100%;
    border-collapse: collapse;
    text-align: left;
}

.comparison-table th, .comparison-table td {
    padding: 16px;
    border-bottom: 1px solid var(--border);
}

.comparison-table th {
    font-weight: 700;
    color: var(--dark);
    background-color: var(--bg-light);
}

.comparison-table td {
    font-size: 15px;
}

.mark {
    font-weight: bold;
    font-size: 18px;
}

.mark--check { color: #10b981; }
.mark--x { color: #ef4444; }


/* ========================================================
   6. FAQ BO'LIMI (DETAILS / SUMMARY ACCORDION)
   ======================================================== */
.faq-section {
    max-width: 750px;
    margin: 0 auto;
}

.faq-section__title {
    text-align: center;
    font-size: 24px;
    margin-bottom: 30px;
}

.faq-container {
    display: flex;
    flex-direction: column;
    gap: 16px;
}

.faq-item {
    background-color: var(--white);
    border-radius: 8px;
    border: 1px solid var(--border);
    overflow: hidden;
    transition: var(--transition);
}

.faq-item__summary {
    padding: 18px 24px;
    font-weight: 600;
    font-size: 16px;
    cursor: pointer;
    list-style: none; /* Standart uchburchakni olib tashlash */
    display: flex;
    justify-content: space-between;
    align-items: center;
    outline: none;
}

/* Custom indicator (burchakli strelka) */
.faq-item__summary::after {
    content: "➔";
    font-size: 12px;
    color: var(--muted);
    transition: transform 0.3s ease;
}

/* Accordion ochiq holatdagi animatsiyasi */
.faq-item[open] .faq-item__summary::after {
    transform: rotate(90deg);
}

.faq-item__summary:hover, .faq-item__summary:focus-visible {
    background-color: var(--bg-light);
    color: var(--primary);
}

.faq-item__answer {
    padding: 0 24px 24px 24px;
    color: var(--muted);
    font-size: 15px;
}


/* RESPONSIVE DESIGN (MEDIA QUERIES) */
@media (max-width: 992px) {
    .price-card--featured {
        transform: scale(1);
    }
    .price-card--featured:hover {
        transform: translateY(-5px);
    }
}
Kod qanday afzalliklarga ega:
Toza CSS Toggle: Oylik va yillik narx rejalarining almashishi CSS-ning :has() hamda :checked selektorlari yordamida JavaScript-siz tushunarli tarzda ishlangan.

Fokus boshqaruvi (:focus-visible): Foydalanuvchi klaviatura orqali (Tab tugmasi yordamida) navigatsiya qilganda, barcha interaktiv elementlar aniq ko'rinadigan fokus liniyasiga ega bo'ladi.

Mukammal Details/Summary: FAQ bo'limida ishlatilgan details tegi brauzerlar uchun qulay hamda qo'shimcha animatsiyali strelka (➔) bilan boyitilgan.
