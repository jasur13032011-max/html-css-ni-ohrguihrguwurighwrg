# html-css-ni-ohrguihrguwurighwrg
Mana, so'ralgan talablar asosida tayyorlangan HTML va CSS kodlari. Loyihangizda tushunarli bo'lishi uchun kodlar alohida bloklarga ajratilgan.

1. HTML fayli (index.html)
HTML
<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Effektlar</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <div class="container">
        <button class="animated-button">Bosing</button>

        <div class="spinner"></div>

        <div class="card">
            <h3>Interaktiv Karta</h3>
            <p>Sichqonchani ustiga olib kelsangiz, bu karta silliq ko'tariladi va soyasi kengayadi.</p>
        </div>
    </div>

</body>
</html>
2. CSS fayli (style.css)
CSS
/* Umumiy stillar (sahifani markazlashtirish uchun) */
body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background-color: #f4f7f6;
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    margin: 0;
}

.container {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 40px;
}

/* ========================================================
   1. Hover effektli tugma (rang va o'lcham silliq o'zgaradi)
   ======================================================== */
.animated-button {
    padding: 12px 28px;
    font-size: 16px;
    font-weight: bold;
    color: white;
    background-color: #3498db;
    border: none;
    border-radius: 25px;
    cursor: pointer;
    /* Silliq o'tish effekti: barcha o'zgarishlar 0.3 soniya davom etadi */
    transition: background-color 0.3s ease, transform 0.3s ease;
}

.animated-button:hover {
    background-color: #2980b9; /* Rang o'zgarishi */
    transform: scale(1.1);       /* O'lchamning kattalashishi */
}

/* ========================================================
   2. @keyframes bilan cheksiz aylanadigan spinner
   ======================================================== */
.spinner {
    width: 50px;
    height: 50px;
    border: 5px solid #e0e0e0;
    border-top: 5px solid #e74c3c; /* Spinnerning rangli qismi */
    border-radius: 50%;
    /* spin animatsiyasi: 1 soniya, bir tekis (linear) va cheksiz (infinite) */
    animation: spin 1s linear infinite;
}

@keyframes spin {
    0% {
        transform: rotate(0deg);
    }
    100% {
        transform: rotate(360deg);
    }
}

/* ========================================================
   3. Kartaga hover ko'tarilish effekti (translateY + box-shadow)
   ======================================================== */
.card {
    width: 280px;
    padding: 20px;
    background-color: white;
    border-radius: 10px;
    text-align: center;
    /* Standart holatdagi yengil soya */
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    /* Transformatsiya va soya o'zgarishi silliq bo'lishi uchun */
    transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.card h3 {
    margin-top: 0;
    color: #333;
}

.card p {
    color: #666;
    font-size: 14px;
}

.card:hover {
    transform: translateY(-10px); /* Yuqoriga ko'tarilish */
    box-shadow: 0 12px 24px rgba(0, 0, 0, 0.2); /* Soya kuchayishi */
}
Eslatma: Effektlar to'g'ri ishlashi uchun har ikkala faylni bitta papkaga joylashtiring va brauzerda index.html faylini oching.
