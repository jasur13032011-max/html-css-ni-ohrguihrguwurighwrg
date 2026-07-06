# html-css-ni-ohrguihrguwurighwrg
CSS
/* ========================================================
   4. ::before bilan custom list marker (standart bullet yo'q)
   ======================================================== */
ul {
    list-style: none; /* Standart nuqtalarni olib tashlaymiz */
    padding-left: 20px;
}

ul li {
    position: relative;
    margin-bottom: 10px;
    padding-left: 25px; /* Marker uchun joy ajratamiz */
    color: #333;
}

ul li::before {
    content: "✦"; /* Custom marker shakli (xohlagan belgi yoki emoji bo'lishi mumkin) */
    position: absolute;
    left: 0;
    top: 0;
    color: #3498db; /* Marker rangi */
    font-weight: bold;
}


/* ========================================================
   5. ::after yoki ::before bilan blockquote tirnoq bezagi
   ======================================================== */
blockquote {
    position: relative;
    font-style: italic;
    font-size: 18px;
    color: #555;
    padding: 20px 40px;
    margin: 20px auto;
    max-width: 500px;
    background: #fff;
    border-left: 5px solid #e74c3c; /* Chap tomondagi rangli chiziq */
}

/* Ochuvchi tirnoq */
blockquote::before {
    content: "“";
    position: absolute;
    left: 10px;
    top: -10px;
    font-size: 60px;
    color: #e74c3c;
    opacity: 0.3; /* Tirnoq orqafonda xira ko'rinishi uchun */
    font-family: Georgia, serif;
}

/* Yopuvchi tirnoq */
blockquote::after {
    content: "”";
    position: absolute;
    right: 10px;
    bottom: -30px;
    font-size: 60px;
    color: #e74c3c;
    opacity: 0.3;
    font-family: Georgia, serif;
}


/* ========================================================
   6. :nth-child bilan jadval qatorlari almashinib ranglanishi
   ======================================================== */
table {
    width: 100%;
    max-width: 600px;
    border-collapse: collapse;
    margin-top: 20px;
    background-color: white;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
}

th, td {
    padding: 12px 15px;
    text-align: left;
    border-bottom: 1px solid #e0e0e0;
}

th {
    background-color: #34495e;
    color: white;
}

/* Juft oʻrindagi qatorlar (2, 4, 6...) uchun och kulrang fon */
table tbody tr:nth-child(even) {
    background-color: #f8f9fa;
}

/* Toq oʻrindagi qatorlar (1, 3, 5...) uchun oq fon */
table tbody tr:nth-child(odd) {
    background-color: #ffffff;
}

/* Sichqoncha qator ustiga kelganda ajralib turishi uchun hover effekti */
table tbody tr:hover {
    background-color: #f1f2f6;
    transition: background-color 0.2s ease;
}
Bu qanday ishlaydi?
Custom List: list-style: none orqali standart brauzer nuqtalari oʻchiriladi va ::before psevdo-elementi yordamida har bir li elementining oldiga mutlaq koordinata (position: absolute) bilan maxsus belgi qoʻyiladi.

Blockquote: Matnning ustiga chiqib ketmasligi uchun katta oʻlchamdagi tirnoqlarga opacity: 0.3 (shaffoflik) berildi.

Jadval: :nth-child(even) selektori jadvaldagi faqat juft qatorlarni tanlab oladi va ularga alohida rang beradi,
