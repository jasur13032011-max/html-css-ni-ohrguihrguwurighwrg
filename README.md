# html-css-ni-ohrguihrguwurighwrgcard__detai
1. CSS Box Model Diagrammasi va Qatlamlar
CSS-da har bir HTML elementi to'rtburchak quti (box) sifatida qaraladi. Bu tuzilish Box Model deb ataladi.

Box model 4 ta qatlamdan iborat:

Content (Tarkib): Elementning haqiqiy matni, rasmi yoki boshqa kontenti joylashadigan joy. Uning o'lchami width va height orqali boshqariladi.

Padding (Ichki masofa): Kontent va uning chegarasi (border) orasidagi bo'shliq. Fon rangi (background-color) padding maydoniga ham ta'sir qiladi.

Border (Chegara): Padding va kontentni o'rab turuvchi chiziq. Uning qalinligi, turi va rangi bo'ladi (masalan: 1px solid black).

Margin (Tashqi masofa): Elementning chegarasidan tashqaridagi bo'shliq. U ushbu elementni boshqa qo'shni elementlardan uzoqlashtirish (ajratish) uchun ishlatiladi. Margin mutlaqo shaffof bo'ladi va fon rangiga ega bo'lmaydi.

2. box-sizing: content-box va border-box farqi
Bu xossa elementning umumiy kengligi (width) va balandligi (height) qanday hisoblanishini belgilaydi.

Xossa qiymati	Hisoblash usuli	Elementning haqiqiy umumiy kengligi
content-box (Standart)	width faqat kontentga beriladi. Padding va Border unga qo'shiladi.	width + padding + border
border-box (Tavsiya etiladi)	width ichiga padding va border ham kirib ketadi.	Faqat berilgan width ga teng
Kod misolida tushuntirish:
Aytaylik, bizda quyidagi stillarga ega element bor:

CSS
.box {
    width: 300px;
    padding: 20px;
    border: 5px solid black;
}
box-sizing: content-box bo'lsa: Elementning brauzerdagi umumiy kengligi 300+20(chap)+20(o’ng)+5(chap)+5(o’ng)=350px bo'lib ketadi. Bu tartib maket chizishda ko'p chalkashliklar keltirib chiqaradi.

box-sizing: border-box bo'lsa: Elementning umumiy kengligi qat'iy 300px ligicha qoladi. Kontent uchun ajratilgan joy esa ichkaridan qisqarib, 250px ga aylanadi (300−40−10). Maket buzilib ketmasligi uchun barcha loyihalarda eng tepada ushbu qoida ishlatiladi.

3. CSS Specificity (Kalkulyatsiya)
Specificity — qaysi CSS qoidasi elementga nisbatan kuchliroq ekanini aniqlaydigan vazn (reyting) tizimidir. Uni 3 ta raqam ko'rinishida hisoblash qulay: (ID, Class, Tag).

ID selektorlar = 1, 0, 0 (Eng kuchli)

Class, Psevdo-klasslar (:hover), Atributlar = 0, 1, 0

Tag (Teg) va Psevdo-elementlar (::before) = 0, 0, 1

Universal selektor (*) va Kombinatorlar (+, >, ~) = 0, 0, 0 (Vazni yo'q)

5 ta Misol:
div p

Tahlil: 2 ta teg selektori (div va p).

Vazni: 0, 0, 2

.card .title

Tahlil: 2 ta klass selektori (.card va .title).

Vazni: 0, 2, 0

#main-nav li a

Tahlil: 1 ta ID (#main-nav) va 2 ta teg (li, a).

Vazni: 1, 0, 2

header nav.menu a:hover

Tahlil: 2 ta teg (header, nav), 1 ta klass (.menu), 1 ta teg (a), 1 ta psevdo-klass (:hover).

Jami: 3 ta teg, 2 ta klass.

Vazni: 0, 2, 3

#sidebar div.profile::before

Tahlil: 1 ta ID (#sidebar), 1 ta teg (div), 1 ta klass (.profile), 1 ta psevdo-element (::before).

Jami: 1 ta ID, 1 ta klass, 2 ta teg.

Vazni: 1, 1, 2

Qoida: 0, 2, 0 vazni har doim 0, 0, 99 vaznidan ustun turadi. Ya'ni bitta klass selektori yuzta teg selektoridan kuchliroqdir.

4. display: none vs visibility: hidden vs opacity: 0
Ushbu uchta xossa ham elementni sahifada ko'rinmas qilish uchun ishlatiladi, lekin ularning ishlash mexanizmi butkul farq qiladi:

Xossa	Element joy egallaydimi?	DOM-da saqlanib qoladimi?	Klik (Click) hodisasini qabul qiladimi?
display: none	Yo'q, element sahifadan butkul o'chgandek bo'ladi.	Ha	Yo'q
visibility: hidden	Ha, element ko'rinmaydi, lekin o'z o'rnini (bo'shliqni) saqlab qoladi.	Ha	Yo'q
opacity: 0	Ha, element joyini egallab turadi, shunchaki 100% shaffof bo'ladi.	Ha	Ha, ko'rinmas bo'lsa ham uni bosish mumkin.
display: none animatsiya (transition) bilan ishlamaydi.

opacity: 0 xossasini transition: opacity 0.3s yordamida chiroyli silliq paydo bo'ladigan elementlar yaratishda keng qo'llash mumkin.

5. !important qoidasi: Qachon ishlatish kerak va kerak emas?
!important har qanday CSS specificity (vazn) qoidalarini chetlab o'tib, o'sha stilni majburlab birinchi o'ringa olib chiqadigan buyruqdir.

❌ Qachon ishlatish KERAK EMAS (Yomon amaliyot):
Klass yoki ID selektorlar bilan ishlashga eringanda: Agar yozgan stilingiz ishlamasa, unga !important yopishtirish o'rniga, selektorning vaznini (specificity) to'g'rilash kerak.

Butun loyihani tartibsiz qilishda: Agar CSS faylingiz !important larga to'lib ketsa, keyinchalik biron bir elementning rangini o'zgartirish juda qiyin bo'lib qoladi.

Qachon ishlatish KERAK (To'g'ri amaliyot):
Utility (Yordamchi) klasslar yaratganda: Masalan, loyihangizda har qanday holatda ham element fonini qizil yoki matnni o'ngga suradigan tayyor klasslar bo'lsa:

CSS
.text-center { text-align: center !important; }
.bg-red { background-color: red !important; }
Tashqi CSS kutubxonalar (Bootstrap, Tailwind yoki uchinchi tomon plaginlari) stillarini majburlab o'zgartirish (override) kerak bo'lganda. Agar kutubxona kodi sizga bo'ysunmasa, uni sindirish uchun !important dan foydalanish asosli hisoblanadi.
