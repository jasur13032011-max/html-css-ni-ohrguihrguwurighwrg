# html-css-ni-ohrguihrguwurighwrg
1. HTML fayli (index.html)
HTML
<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BEM Metodologiyasi Bo'yicha Kartalar</title>
    <link rel="stylesheet" href="style.css">
</head>
<body class="page-body">

    <div class="card-grid">
        
        <article class="card">
            <div class="card__image-container">
                <img class="card__image" src="https://picsum.photos/300/200?random=1" alt="Mahsulot rasmi">
            </div>
            <div class="card__content">
                <h3 class="card__title">Zamonaviy Krossovka</h3>
                <p class="card__description">Kundalik kiyish va sport bilan shug'ullanish uchun juda qulay va yengil krossovka.</p>
                <div class="card__price-box">
                    <span class="card__price">450,000 so'm</span>
                </div>
                <button class="card__button">Sotib olish</button>
            </div>
        </article>

        <article class="card card--sale">
            <div class="card__image-container">
                <span class="card__badge card__badge--sale">Chegirma</span>
                <img class="card__image" src="https://picsum.photos/300/200?random=2" alt="Mahsulot rasmi">
            </div>
            <div class="card__content">
                <h3 class="card__title">Aqlli Soat Pro</h3>
                <p class="card__description">Yurak urishi, uyqu va sport faolligini kuzatuvchi eng so'nggi modeldagi aqlli soat.</p>
                <div class="card__price-box">
                    <span class="card__price card__price--old">800,000 so'm</span>
                    <span class="card__price card__price--current">599,000 so'm</span>
                </div>
                <button class="card__button">Sotib olish</button>
            </div>
        </article>

        <article class="card card--new">
            <div class="card__image-container">
                <span class="card__badge card__badge--new">Yangi</span>
                <img class="card__image" src="https://picsum.photos/300/200?random=3" alt="Mahsulot rasmi">
            </div>
            <div class="card__content">
                <h3 class="card__title">Simsiz Quloqchinlar</h3>
                <p class="card__description">Yuqori sifatli ovoz va shovqinni to'suvchi (ANC) tizimiga ega simsiz quloqchin.</p>
                <div class="card__price-box">
                    <span class="card__price">350,000 so'm</span>
                </div>
                <button class="card__button">Sotib olish</button>
            </div>
        </article>

    </div>

</body>
</html>
2. CSS fayli (style.css)
CSS
/* Sahifa uchun umumiy BEM stillari */
.page-body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background-color: #f5f7fa;
    margin: 0;
    padding: 40px 20px;
}

.card-grid {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 30px;
    max-width: 1200px;
    margin: 0 auto;
}

/* ========================================================
   BEM: BLOCK (Karta asosiy bloki)
   ======================================================== */
.card {
    background-color: #ffffff;
    border-radius: 12px;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.05);
    width: 300px;
    overflow: hidden;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    border: 1px solid #e1e8ed;
}

.card:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 25px rgba(0, 0, 0, 0.1);
}

/* ========================================================
   BEM: MODIFIERS (Blok darajasidagi modifikatorlar)
   ======================================================== */
/* Aksiyadagi karta uchun maxsus chegirma foni yoki burchak rangi */
.card--sale {
    border: 1px solid #ff4d4f;
    background-color: #fff1f0;
}

/* Yangi mahsulot kartasi uchun maxsus yashil tusli jilo */
.card--new {
    border: 1px solid #73d13d;
    background-color: #f6ffed;
}

/* ========================================================
   BEM: ELEMENTS (Blok ichidagi elementlar)
   ======================================================== */
.card__image-container {
    position: relative;
    width: 100%;
    height: 200px;
    background-color: #eaeff2;
}

.card__image {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.card__content {
    padding: 20px;
}

.card__title {
    margin: 0 0 10px 0;
    font-size: 20px;
    color: #1f2937;
    font-weight: 600;
}

.card__description {
    margin: 0 0 20px 0;
    font-size: 14px;
    color: #4b5563;
    line-height: 1.5;
    height: 63px; /* Matnlar bir xil tekislikda turishi uchun fixed balandlik */
    overflow: hidden;
}

.card__price-box {
    margin-bottom: 20px;
    display: flex;
    align-items: center;
    gap: 10px;
}

.card__price {
    font-size: 18px;
    font-weight: 700;
    color: #1f2937;
}

/* Element ichidagi modifikatorlar (E__A--B) */
.card__price--old {
    font-size: 14px;
    color: #9ca3af;
    text-decoration: line-through;
    font-weight: 400;
}

.card__price--current {
    color: #ff4d4f;
    font-size: 20px;
}

.card__badge {
    position: absolute;
    top: 12px;
    left: 12px;
    padding: 4px 10px;
    font-size: 12px;
    font-weight: bold;
    color: #ffffff;
    border-radius: 4px;
    z-index: 1;
}

.card__badge--sale {
    background-color: #ff4d4f;
}

.card__badge--new {
    background-color: #73d13d;
}

.card__button {
    width: 100%;
    padding: 10px 0;
    background-color: #2f54eb;
    color: #ffffff;
    border: none;
    border-radius: 6px;
    font-size: 15px;
    font-weight: 600;
    cursor: pointer;
    transition: background-color 0.2s ease;
}

.card__button:hover {
    background-color: #1d39c4;
}

/* Modifikatorli kartalarning ichidagi tugma ranglarini moslash */
.card--sale .card__button {
    background-color: #ff4d4f;
}

.card--sale .card__button:hover {
    background-color: #d9363e;
}

.card--new .card__button {
    background-color: #73d13d;
}

.card--new .card__button:hover {
    background-color: #52c41a;
}
BEM qoidalariga rioya etilishi tahlili:
Blok (.card): Mustaqil komponent bo'lib, o'z funksiyasiga ega.

Elementlar (.card__image, .card__title, .card__button): Faqat blok ichida ma'noga ega bo'lgan va blok nomiga ikki tag-chiziq (__) bilan yopishgan elementlar.

Modifikatorlar (.card--sale, .card--new, .card__badge--sale): Blok yoki elementning holati yoki ko'rinishini o'zgartirish uchun ikki chiziq (--) bilan qo'shilgan klasslar.

Teg selektorlarisiz: CSS-da birorta ham div, img, h3,
