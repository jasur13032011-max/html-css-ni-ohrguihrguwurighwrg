# html-css-ni-ohrguihrguwurighwrgcard__detai
Elektron tijorat (E-commerce) tizimlari uchun eng ko'p ishlatiladigan interaktiv mahsulot sahifasining (Product Detail Page) HTML va CSS kodlari. Dizayn to'liq responsive bo'lib, o'ng tomondagi ma'lumotlar qismi Flexbox yordamida joylashtirilgan.

1. HTML fayli (index.html)
HTML
<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mahsulot Sahifasi</title>
    <link rel="stylesheet" href="style.css">
</head>
<body class="product-page">

    <div class="product-container">
        
        <section class="product-gallery">
            <div class="product-gallery__main-wrapper">
                <img class="product-gallery__main" src="https://picsum.photos/600/600?random=10" alt="Asosiy mahsulot rasmi">
            </div>
            <div class="product-gallery__thumbnails">
                <img class="product-gallery__thumb product-gallery__thumb--active" src="https://picsum.photos/600/600?random=10" alt="Thumbnail 1">
                <img class="product-gallery__thumb" src="https://picsum.photos/600/600?random=11" alt="Thumbnail 2">
                <img class="product-gallery__thumb" src="https://picsum.photos/600/600?random=12" alt="Thumbnail 3">
                <img class="product-gallery__thumb" src="https://picsum.photos/600/600?random=13" alt="Thumbnail 4">
            </div>
        </section>

        <section class="product-details">
            <h1 class="product-details__title">Premium Charm Krossovka</h1>
            
            <div class="product-details__rating">
                <span class="product-details__stars">★★★★☆</span>
                <span class="product-details__reviews">(4.8 / 120 ta sharh)</span>
            </div>

            <div class="product-details__price-box">
                <span class="product-details__price">850,000 so'm</span>
                <span class="product-details__old-price">1,100,000 so'm</span>
            </div>

            <p class="product-details__description">
                Yuqori sifatli tabiiy charm va qulay ortopedik taglikka ega bo'lgan ushbu krossovka kundalik kiyish hamda faol hayot tarzi uchun maxsus ishlab chiqilgan.
            </p>

            <hr class="product-details__divider">

            <div class="product-option">
                <span class="product-option__title">Rang:</span>
                <div class="product-option__swatches">
                    <label class="color-swatch">
                        <input type="radio" name="color" checked>
                        <span class="color-swatch__visual color-swatch__visual--black"></span>
                    </label>
                    <label class="color-swatch">
                        <input type="radio" name="color">
                        <span class="color-swatch__visual color-swatch__visual--blue"></span>
                    </label>
                    <label class="color-swatch">
                        <input type="radio" name="color">
                        <span class="color-swatch__visual color-swatch__visual--brown"></span>
                    </label>
                </div>
            </div>

            <div class="product-option">
                <span class="product-option__title">O'lcham:</span>
                <div class="product-option__swatches">
                    <label class="size-swatch">
                        <input type="radio" name="size">
                        <span class="size-swatch__visual">40</span>
                    </label>
                    <label class="size-swatch">
                        <input type="radio" name="size" checked>
                        <span class="size-swatch__visual">41</span>
                    </label>
                    <label class="size-swatch">
                        <input type="radio" name="size">
                        <span class="size-swatch__visual">42</span>
                    </label>
                    <label class="size-swatch">
                        <input type="radio" name="size">
                        <span class="size-swatch__visual">43</span>
                    </label>
                </div>
            </div>

            <div class="product-actions">
                <div class="quantity-selector">
                    <button class="quantity-selector__btn" type="button">−</button>
                    <input class="quantity-selector__input" type="number" value="1" min="1">
                    <button class="quantity-selector__btn" type="button">+</button>
                </div>
                <button class="product-actions__cart-btn" type="button">Savatga qo'shish</button>
            </div>

            <hr class="product-details__divider">

            <div class="product-specs">
                <h3 class="product-specs__title">Xususiyatlari:</h3>
                <ul class="product-specs__list">
                    <li class="product-specs__item"><strong>Material:</strong> 100% Tabiiy charm</li>
                    <li class="product-specs__item"><strong>Taglik:</strong> EVA (Yengil va yumshoq)</li>
                    <li class="product-specs__item"><strong>Ishlab chiqarilgan:</strong> O'zbekiston</li>
                </ul>
            </div>
        </section>

    </div>

</body>
</html>
2. CSS fayli (style.css)
CSS
/* Custom Variables */
:root {
    --primary: #2563eb;
    --primary-hover: #1d4ed8;
    --text-dark: #1e293b;
    --text-muted: #64748b;
    --border: #cbd5e1;
    --bg-light: #f8fafc;
    --white: #ffffff;
}

*, *::before, *::after {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background-color: #f1f5f9;
    color: var(--text-dark);
    padding: 40px 20px;
    line-height: 1.5;
}

/* ========================================================
   6. FLEXBOX BILAN 2 USTUNLI LAYOUT
   ======================================================== */
.product-container {
    display: flex;
    flex-wrap: wrap;
    gap: 40px;
    max-width: 1100px;
    margin: 0 auto;
    background-color: var(--white);
    padding: 30px;
    border-radius: 16px;
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.05);
}

.product-gallery,
.product-details {
    flex: 1 1 480px; /* Ekranga qarab kengayadi yoki mobilga yiqiladi */
}

/* ========================================================
   1. RASM GALEREYASI
   ======================================================== */
.product-gallery__main-wrapper {
    width: 100%;
    background-color: var(--bg-light);
    border-radius: 12px;
    overflow: hidden;
    margin-bottom: 16px;
    border: 1px solid var(--border);
}

.product-gallery__main {
    width: 100%;
    height: auto;
    display: block;
    object-fit: cover;
}

.product-gallery__thumbnails {
    display: flex;
    gap: 12px;
}

/* 7. Thumbnaillarda hover effekti */
.product-gallery__thumb {
    width: calc(25% - 9px);
    aspect-ratio: 1;
    border: 2px solid transparent;
    border-radius: 8px;
    cursor: pointer;
    object-fit: cover;
    transition: all 0.2s ease;
}

.product-gallery__thumb:hover,
.product-gallery__thumb--active {
    border-color: var(--primary);
    opacity: 0.8;
    transform: scale(1.03);
}

/* ========================================================
   2 & 5. MAHSULOT DETALLARI VA TAVSIFI
   ======================================================== */
.product-details__title {
    font-size: 28px;
    font-weight: 700;
    margin-bottom: 12px;
}

.product-details__rating {
    display: flex;
    align-items: center;
    gap: 8px;
    margin-bottom: 16px;
}

.product-details__stars {
    color: #f59e0b;
    font-size: 18px;
}

.product-details__reviews {
    color: var(--text-muted);
    font-size: 14px;
}

.product-details__price-box {
    display: flex;
    align-items: baseline;
    gap: 12px;
    margin-bottom: 20px;
}

.product-details__price {
    font-size: 24px;
    font-weight: 700;
    color: var(--primary);
}

.product-details__old-price {
    font-size: 16px;
    color: var(--text-muted);
    text-decoration: line-through;
}

.product-details__description {
    color: #475569;
    margin-bottom: 24px;
}

.product-details__divider {
    border: 0;
    border-top: 1px solid var(--border);
    margin: 20px 0;
}

/* ========================================================
   3. RANG VA O'LCHAM TANLASH (SWATCHES)
   ======================================================== */
.product-option {
    margin-bottom: 20px;
}

.product-option__title {
    display: block;
    font-weight: 600;
    margin-bottom: 8px;
}

.product-option__swatches {
    display: flex;
    gap: 12px;
}

/* Radio inputni yashirish */
.color-swatch input,
.size-swatch input {
    position: absolute;
    opacity: 0;
    width: 0;
    height: 0;
}

/* Color Swatch vizuali */
.color-swatch__visual {
    display: block;
    width: 32px;
    height: 32px;
    border-radius: 50%;
    cursor: pointer;
    border: 2px solid var(--white);
    outline: 2px solid var(--border);
    transition: all 0.2s ease;
}

.color-swatch__visual--black { background-color: #1e293b; }
.color-swatch__visual--blue { background-color: #1d4ed8; }
.color-swatch__visual--brown { background-color: #78350f; }

.color-swatch input:checked + .color-swatch__visual {
    outline-color: var(--primary);
    transform: scale(1.1);
}

/* Size Swatch vizuali */
.size-swatch__visual {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 44px;
    height: 44px;
    border: 1px solid var(--border);
    border-radius: 8px;
    cursor: pointer;
    font-weight: 600;
    transition: all 0.2s ease;
}

.size-swatch__visual:hover {
    border-color: var(--primary);
    background-color: var(--bg-light);
}

.size-swatch input:checked + .size-swatch__visual {
    border-color: var(--primary);
    background-color: var(--primary);
    color: var(--white);
}

/* ========================================================
   4 & 7. MIQDOR VA AMALLAR TUGMALARI
   ======================================================== */
.product-actions {
    display: flex;
    gap: 16px;
    margin-top: 24px;
}

/* +/- Miqdor qismi */
.quantity-selector {
    display: flex;
    border: 1px solid var(--border);
    border-radius: 8px;
    overflow: hidden;
}

.quantity-selector__btn {
    background-color: var(--bg-light);
    border: none;
    width: 40px;
    font-size: 18px;
    font-weight: bold;
    cursor: pointer;
    transition: background-color 0.2s ease;
}

.quantity-selector__btn:hover {
    background-color: #cbd5e1;
}

.quantity-selector__input {
    width: 50px;
    border: none;
    border-left: 1px solid var(--border);
    border-right: 1px solid var(--border);
    text-align: center;
    font-size: 16px;
    font-weight: 600;
    outline: none;
    -moz-appearance: textfield;
}

.quantity-selector__input::-webkit-outer-spin-button,
.quantity-selector__input::-webkit-inner-spin-button {
    -webkit-appearance: none;
    margin: 0;
}

/* Savatga qo'shish tugmasi */
.product-actions__cart-btn {
    flex-grow: 1;
    background-color: var(--primary);
    color: var(--white);
    border: none;
    border-radius: 8px;
    font-size: 16px;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.2s ease;
}

.product-actions__cart-btn:hover {
    background-color: var(--primary-hover);
    box-shadow: 0 4px 12px rgba(37, 99, 235, 0.2);
}

/* 5. Xususiyatlari */
.product-specs__title {
    font-size: 16px;
    margin-bottom: 10px;
}

.product-specs__list {
    list-style-type: none;
}

.product-specs__item {
    margin-bottom: 6px;
    font-size: 14px;
    color: #475569;
}
