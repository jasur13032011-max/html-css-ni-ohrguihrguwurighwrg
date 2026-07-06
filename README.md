# html-css-ni-ohrguihrguwurighwrg
Mana, so'ralgan talablar asosida tayyorlangan chiroyli va interaktiv forma uchun HTML va CSS kodlari.

1. HTML fayli (index.html)
HTML
<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interaktiv Aloqa Formasi</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <div class="form-container">
        <h2>Biz bilan aloqa</h2>
        <form action="#" method="POST">
            
            <div class="form-group">
                <label for="name">Ismingiz</label>
                <input type="text" id="name" placeholder="Masalan: Ali" required minlength="3">
                <span class="validation-msg">Kamida 3 ta harf kiriting</span>
            </div>

            <div class="form-group">
                <label for="email">Email manzilingiz</label>
                <input type="email" id="email" placeholder="example@mail.com" required>
                <span class="validation-msg">To'g'ri email kiriting (ism@domen.com)</span>
            </div>

            <div class="form-group">
                <label for="message">Xabaringiz</label>
                <textarea id="message" rows="4" placeholder="Xabaringizni shu yerga yozing..." required minlength="10"></textarea>
                <span class="validation-msg">Xabar juda qisqa</span>
            </div>

            <div class="checkbox-group">
                <label class="custom-checkbox-label">
                    <input type="checkbox" class="real-checkbox" required>
                    <span class="custom-checkbox"></span>
                    Shartlarga roziman
                </label>
            </div>

            <button type="submit" class="submit-btn">Yuborish</button>
        </form>
    </div>

</body>
</html>
2. CSS fayli (style.css)
CSS
/* Sahifani markazlashtirish uchun umumiy stillar */
body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background-color: #f0f4f8;
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    margin: 0;
}

/* Forma konteyneri */
.form-container {
    background-color: white;
    padding: 30px;
    border-radius: 12px;
    box-shadow: 0 8px 24px rgba(0, 0, 0, 0.1);
    width: 100%;
    max-width: 400px;
}

h2 {
    margin-top: 0;
    margin-bottom: 20px;
    color: #2c3e50;
    text-align: center;
}

.form-group {
    margin-bottom: 20px;
    position: relative;
}

label {
    display: block;
    margin-bottom: 8px;
    font-weight: 600;
    color: #34495e;
    font-size: 14px;
}

/* Input va Textarea umumiy stillari */
input[type="text"],
input[type="email"],
textarea {
    width: 100%;
    padding: 12px;
    border: 2px solid #bdc3c7;
    border-radius: 6px;
    font-size: 15px;
    color: #2c3e50;
    box-sizing: border-box;
    outline: none;
    /* Silliq o'tish effektlari */
    transition: border-color 0.3s ease, box-shadow 0.3s ease;
}

/* ========================================================
   1. ::placeholder rangi o'zgartirilgan
   ======================================================== */
input::placeholder,
textarea::placeholder {
    color: #a0aec0;
    font-style: italic;
    opacity: 1; /* Brauzer standart shaffofligini toirlash */
}

/* ========================================================
   2. :focus paytida border rangi o'zgarishi
   ======================================================== */
input:focus,
textarea:focus {
    border-color: #3498db;
    box-shadow: 0 0 8px rgba(52, 152, 219, 0.2);
}

/* ========================================================
   3. :valid / :invalid bilan validatsiya ko'rsatilishi
   ======================================================== */
/* Foydalanuvchi yozishni boshlaganda (yoki qiymat bo'lganda) va u xato bo'lsa */
input:placeholder-shown:invalid,
textarea:placeholder-shown:invalid {
    border-color: #bdc3c7; /* Bo'sh turganda xato deb ko'rsatmaydi */
}

input:not(:placeholder-shown):invalid,
textarea:not(:placeholder-shown):invalid {
    border-color: #e74c3c;
    background-color: #fdf2f2;
}

input:not(:placeholder-shown):valid,
textarea:not(:placeholder-shown):valid {
    border-color: #2ecc71;
    background-color: #f4fbf7;
}

/* Validatsiya xabarlarini boshqarish */
.validation-msg {
    font-size: 12px;
    color: #e74c3c;
    display: none;
    margin-top: 5px;
}

input:not(:placeholder-shown):invalid ~ .validation-msg,
textarea:not(:placeholder-shown):invalid ~ .validation-msg {
    display: block;
}


/* ========================================================
   4. Custom CSS checkbox (standart checkbox yashiriladi)
   ======================================================== */
.checkbox-group {
    margin-bottom: 25px;
}

.custom-checkbox-label {
    display: flex;
    align-items: center;
    cursor: pointer;
    font-size: 14px;
    color: #555;
    user-select: none;
}

/* Standart brauzer checkboxini butkul yashiramiz */
.real-checkbox {
    position: absolute;
    opacity: 0;
    cursor: pointer;
    height: 0;
    width: 0;
}

/* Yangi dizayndagi checkboxning tashqi ko'rinishi */
.custom-checkbox {
    position: relative;
    display: inline-block;
    width: 20px;
    height: 20px;
    border: 2px solid #bdc3c7;
    border-radius: 4px;
    margin-right: 10px;
    background-color: white;
    transition: all 0.2s ease;
}

/* Checkbox bosilgandagi (checked) holati */
.real-checkbox:checked ~ .custom-checkbox {
    background-color: #3498db;
    border-color: #3498db;
}

/* Checkbox ichidagi "belgi" (checkmark) - boshlang'ich yashirin holat */
.custom-checkbox::after {
    content: "";
    position: absolute;
    display: none;
    left: 6px;
    top: 2px;
    width: 5px;
    height: 10px;
    border: solid white;
    border-width: 0 2px 2px 0;
    transform: rotate(45deg);
}

/* Checkbox bosilganda belgini ko'rsatish */
.real-checkbox:checked ~ .custom-checkbox::after {
    display: block;
}

/* Custom checkbox validatsiyasi */
.real-checkbox:focus ~ .custom-checkbox {
    box-shadow: 0 0 5px rgba(52, 152, 219, 0.5);
}


/* Yuborish tugmasi stili */
.submit-btn {
    width: 100%;
    padding: 12px;
    background-color: #3498db;
    color: white;
    border: none;
    border-radius: 6px;
    font-size: 16px;
    font-weight: bold;
    cursor: pointer;
    transition: background-color 0.2s ease;
}

.submit-btn:hover {
    background-color: #2980b9;
}
Kodning o'ziga xosliklari:
Silliq Validatsiya (:not(:placeholder-shown)): Forma yuklanishi bilanoq birdan qizil (xato) bo'lib qolmaydi. Foydalanuvchi ma'lumot yozishni boshlaganidan keyingina validatsiya ishga tushadi.

Custom Checkbox: input[type="checkbox"] mutlaqo yashirilib, uning o'rniga CSS ::after hamda :checked selektorlari yordamida chiroyli zamonaviy checkbox yaratildi.

Fokus holati:
