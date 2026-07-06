# html-css-ni-ohrguihrguwurighwrgcard__detai
CSS-da elementlarning joylashuvini (position) boshqarish, ularning qatlamlar tartibi (z-index) va elementlar bir-biriga qanday nisbatda joylashishini tushunish mukammal maketlar yaratishning kalitidir.

1. position Xossasining Farqlari: static, relative, absolute, fixed, sticky
static (Standart): Element sahifaning tabiiy oqimida (normal flow) joylashadi. top, bottom, left, right va z-index xossalari unga ta'sir qilmaydi.

relative (Nisbiy): Element sahifadagi o'zining dastlabki oqimdagi joyiga nisbatan suriladi. top, left kabi xossalar bilan surilganda ham, uning dastlabki o'rni sahifada bo'shliq (joy) sifatida saqlanib qoladi. Ko'pincha ichidagi absolute elementlar uchun poydevor (kapsula) vazifasini o'taydi.

absolute (Mutlaq): Element sahifa oqimidan butkul chiqib ketadi va joy egallamaydi. U o'zidan tepada turgan eng yaqin position qiymati static bo'lmagan (relative, absolute, fixed, sticky) ota-blokiga nisbatan joylashadi. Agar bunday ota-blok bo'lmasa, html (sahifa) ga nisbatan joy oladi.

fixed (Qotirilgan): Element sahifa oqimidan chiqadi va to'g'ridan-to'g'ri brauzer oynasiga (viewport) nisbatan qotiriladi. Sahifa skroll (scroll) qilinganda ham joyidan qimirlamaydi (masalan, chat tugmalari yoki tepada qotib turuvchi navbar).

sticky (Yopishqoq): relative va fixed gibridi. Element skroll ma'lum bir nuqtaga (top: 0 kabi) yetguncha oddiy oqimda (relative kabi) turadi, osha nuqtaga yetganda esa qotib (fixed kabi) qoladi va o'z ota-bloki chegarasidan chiqib ketmaguncha yopishib turadi.

2. Stacking Context (Qatlamlar Muhiti) Yaratuvchi Xususiyatlar
z-index shunchaki butun sahifa bo'yicha elementlarni ustma-ust taxlamaydi. U faqat ma'lum bir Stacking Context (ichki qatlamlar muhiti) ichida ishlaydi. Quyidagi holatlarda yangi Stacking Context hosil bo'ladi:

Element position qiymati absolute yoki relative bo'lib, z-index qiymati auto dan boshqa raqam bo'lganda.

Element position qiymati fixed yoki sticky bo'lganda (bunda z-index shart emas, lekin tartiblash uchun berilishi mumkin).

Element containeri display: flex yoki display: grid bo'lib, bolalariga z-index berilganda.

Elementning shaffofligi opacity qiymati 1 dan kichik bo'lganda (masalan, opacity: 0.9).

transform, filter, perspective, clip-path xossalari none dan boshqa qiymatga ega bo'lganda.

will-change xossasi orqali yuqoridagi effektlar oldindan e'lon qilinganda.

3. z-index Nega Ba'zida Ishlamaydi? (Misollar)
Sabab A: Elementda position e'lon qilinmagan (Yoki static holatda)
z-index xossasi position: static bo'lgan elementlarda mutlaqo ishlamaydi.

Xato kod:

CSS
.box { z-index: 10; } /* Ishlamaydi */
Yechim:

CSS
.box { position: relative; z-index: 10; } /* Ishlaydi */
Sabab B: Ota-bloklarning qatlamlar urushi (Parent Stacking Context)
Agar ikki element alohida ota-bloklar ichida bo'lsa va ota-bloklarning o'zida z-index burchaklari belgilangan bo'lsa, ichidagi bolaning z-indexi qanchalik katta bo'lmasin, ota-blokning qatlamidan o'tib keta olmaydi.

Misol:

HTML
<div class="parent-1" style="position: relative; z-index: 1;">
    <div class="child-1" style="position: absolute; z-index: 9999;">Mening vaznim katta!</div>
</div>
<div class="parent-2" style="position: relative; z-index: 2;">
    <div class="child-2" style="position: absolute; z-index: 1;">Men baribir tepada turaman.</div>
</div>
Tushuntirish: .parent-2 ning z-indexi (2) .parent-1 nikidan (1) katta. Shuning uchun .child-1 ga 9999 berilgani bilan u .parent-2 va uning ichidagi barcha narsalarning ortida qolib ketaveradi.

4. overflow: hidden Xossasining position ga Ta'siri
overflow: hidden ota-blok chegarasidan chiqib ketgan kontentni qirqib (yashirib) qo'yadi. Biroq, bu qoida ichidagi position xossasiga ega elementlarga har doim ham ta'sir qilavermaydi:

Ta'sir qiladigan holat: Agar .parent blokiga overflow: hidden va position: relative berilgan bo'lsa, uning ichidagi position: absolute bo'lgan bola-blok ota-blok chegarasidan tashqariga chiqsa, qirqiladi.

Ta'sir qilmaydigan holat: Agar .parent blokida faqat overflow: hidden bo'lsa (lekin position: static bo'lsa) va uning ichidagi bola position: absolute bo'lsa, u qirqilmaydi! Chunki u ota-blokni chetlab o'tib, o'zining yuqoriroqdagi containing blockini qidirib ketadi.

position: fixed holatida: fixed elementlar har doim brauzer oynasiga bog'langanligi sababli, ularning yuqorisidagi biron bir konteynerda overflow: hidden bo'lishi ularni qirqa olmaydi (agar ota-blokda transform ishlatilmagan bo'lsa).

5. Containing Block Nima va Qanday Aniqlanadi?
Containing Block (Qamrab oluvchi blok) — bu elementning o'lchamlari (width, height, padding) va joylashuvi (top, left va h.k.) qaysi sohaga yoki elementga nisbatan foizda (%) yoki piksellarda hisoblanishini belgilaydigan hududdir.

Elementning position qiymatiga qarab, uning Containing Block-ni aniqlash qoidalari quyidagicha:

position: static yoki relative bo'lsa: Eng yaqin blok darajasidagi (display: block, flex, grid kabi) ota-onasining content-box (kontent maydoni) uning containing block-i hisoblanadi.

position: absolute bo'lsa: O'zidan tepada turgan, position qiymati static bo'lmagan eng yaqin ota-onasining padding-box (padding + kontent maydoni) uning containing block-i bo'ladi.

position: fixed bo'lsa: To'g'ridan-to'g'ri brauzer oynasi (Viewport) uning containing block-i hisoblanadi.

position: sticky bo'lsa: O'zi joylashgan to'g'ridan-to'g'ri ota-konteynerining content-box maydoni uning containing block-i bo'ladi.

Istisno (Exception): Agar ota-bloklardan birortasida transform, perspective yoki filter xossalari (none dan boshqa qiymatda) ishlatilgan bo'lsa, o'sha ota-blok o'z-o'zidan barcha absolute va fixed elementlar uchun Containing Block ga aylanib qoladi.
