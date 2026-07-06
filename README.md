# html-css-ni-ohrguihrguwurighwrg
Mana, 3D chuqurlik effektiga ega va hover bo'lganda 180° silliq ag'dariladigan 3D karta (Flip Card) kodi.

1. HTML fayli (index.html)
HTML
<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>3D Ag'dariluvchi Karta</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <div class="flip-card-container">
        <div class="flip-card">
            
            <div class="card-face card-front">
                <h2>Old Tomon</h2>
                <p>Sichqonchani ustiga olib keling</p>
            </div>
            
            <div class="card-face card-back">
                <h2>Orqa Tomon</h2>
                <p>Muvaffaqiyatli ag'darildi!</p>
            </div>
            
        </div>
    </div>

</body>
</html>
2. CSS fayli (style.css)
CSS
/* Sahifa markazi uchun umumiy stillar */
body {
    font-family: 'Segoe UI', sans-serif;
    background-color: #f0f3f5;
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    margin: 0;
}

/* 1. Karta uchun 3D chuqurlik muhiti */
.flip-card-container {
    width: 300px;
    height: 400px;
    /* perspective 3D chuqurlik hissini beradi. Qiymat qancha kichik bo'lsa, effekt shuncha yaqin ko'rinadi */
    perspective: 1000px; 
}

/* 2. Aylanishni amalga oshiradigan ichki blok */
.flip-card {
    width: 100%;
    height: 100%;
    position: relative;
    /* Ichki elementlar (old/orqa tomonlar) ham 3D fazoda qolishi uchun */
    transform-style: preserve-3d;
    /* Silliq ag'darilish effekti uchun transition */
    transition: transform 0.6s cubic-bezier(0.4, 0, 0.2, 1);
}

/* Hover paytida kartani Y o'qi bo'yicha 180 gradusga buramiz */
.flip-card-container:hover .flip-card {
    transform: rotateY(180deg);
}

/* 3. Kartaning ikkala tomoni uchun umumiy qoidalar */
.card-face {
    position: absolute;
    width: 100%;
    height: 100%;
    border-radius: 15px;
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.15);
    
    /* Ichidagi matnlarni markazlashtirish */
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 20px;
    box-sizing: border-box;

    /* Orqa tomondagi element teskari turganda ko'rinmasligi uchun eng muhim xossa */
    backface-visibility: hidden; 
}

/* 4. Faqat old tomon stili */
.card-front {
    background: linear-gradient(135deg, #3498db, #2980b9);
    color: white;
}

/* 5. Faqat orqa tomon stili */
.card-back {
    background: linear-gradient(135deg, #2ecc71, #27ae60);
    color: white;
    /* Orqa tomon boshlang'ich holatda 180 gradus burilib, old tomonning orqasida tayyor turadi */
    transform: rotateY(180deg);
}
