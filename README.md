# html-css-ni-ohrguihrguwurighwrgcard__detai
CSS-da o'lchov birliklari, joylashuv tizimlari va animatsiyalarni to'g'ri tanlash kodning moslashuvchanligi (responsiveness) va tozaligini ta'minlaydi. Quyida so'ralgan barcha tushunchalarning qisqa va lo'nda tahlili keltirilgan.1. em, rem, %, vw Birliklari FarqiUshbu birliklar dinamik (nisbiy) o'lchov birliklari hisoblanadi:BirlikNimaga nisbatan hisoblanadi?Eng ko'p ishlatiladigan o'rinlaremO'zi joylashgan elementning (yoki otasining) font-size qiymatiga nisbatan.padding, margin va ichki komponent o'lchamlarida.remFaqat va faqat asosiy HTML (root) elementining font-size qiymatiga nisbatan (odatda $1\text{rem} = 16\text{px}$).Global matnlar o'lchami (font-size), sayt strukturasidagi masofalarda.%To'g'ridan-to'g'ri ota-blokining mos o'lchamiga (kenglik/balandlik) nisbatan.Bloklar kengligi (width), responsive maket qurishda.vwEkran (Viewport) kengligining $1\%$ qismiga nisbatan ($100\vw$ = to'liq ekran kengligi).Katta hero-bannerlar, to'liq ekranli sahifalar yoki ekranga moslashuvchan matnlarda.2. Flexbox vs CSS Grid: Qachon qaysinisini ishlatish kerak?Ikkalasi ham joylashuvni boshqarish uchun xizmat qilsa-da, ularning o'z maqsadlari bor:Flexbox (1 o'lchamli - 1D): Elementlarni faqat bitta yo'nalish bo'yicha (yoki faqat qator, yoki faqat ustun) joylashtirish uchun mo'ljallangan.Qachon ishlatiladi: Navigatsiya paneli (Navbar), tugmalar qatori, elementlarni komponent ichida shunchaki yonma-yon yoki ustma-ust tartiblashda.CSS Grid (2 o'lchamli - 2D): Elementlarni bir vaqtning o'zida ham qator, ham ustunlar (to'r) bo'yicha mukammal boshqarish uchun mo'ljallangan.Qachon ishlatiladi: Butun sahifa maketi (Layout), loyihalar galereyasi, dashboard panellari va murakkab jadvalli tuzilmalarda.3. Pseudo-element (::) va Pseudo-class (:) FarqiPseudo-class (Psevdo-klass — :): Elementning ma'lum bir holatini (state) aniqlash uchun ishlatiladi. HTML-ni o'zgartirmaydi.Misollar: :hover (sichqoncha ustiga kelganda), :focus (element tanlanganda), :nth-child(2) (ikkinchi bola element).Pseudo-element (Psevdo-element — ::): Elementning ma'lum bir qismini stillash yoki DOM-da yo'q bo'lgan yangi virtual kontent qo'shish uchun ishlatiladi.Misollar: ::before (element ichidan eng boshiga), ::after (element ichidan eng oxiriga kontent qo'shish), ::placeholder (input ichidagi och matn).4. CSS Transitions va Animations FarqiTransitions (O'tish effektlari): Elementning bitta holatdan ikkinchi holatga (masalan, oddiy holatdan :hover holatiga) silliq o'tishini ta'minlaydi. Ishlashi uchun trigger (sichqoncha kelishi, klik bo'lishi) kerak. Ularda faqat ikkita nuqta bor: boshlanish va tugash.Animations (Animatsiyalar): @keyframes qoidalari orqali boshqariladi. Hech qanday foydalanuvchi harakatisiz ham sahifa yuklanganda o'zi mustaqil ishlay oladi va cheksiz (infinite) aylanishi mumkin. U yerda o'tish jarayonini foizlar (0%, 50%, 100%) orqali ko'p bosqichli qilish mumkin.5. CSS Custom Properties (Variables) Misollar bilanCSS o'zgaruvchilari qiymatlarni bitta joyda saqlab, butun loyiha bo'ylab qayta-qayta ishlatish imkonini beradi. Bu ayniqsa saytga Dark Mode (tungi rejim) qo'shishda juda asqotadi.Kod misoli:CSS/* Global o'zgaruvchilarni e'lon qilish */
:root {
    --primary-color: #3b82f6;
    --text-color: #1e293b;
    --padding-base: 16px;
}

/* O'zgaruvchilarni elementlarda qo'llash */
.card {
    padding: var(--padding-base);
    border: 1px solid var(--primary-color);
}

.card__title {
    color: var(--text-color);
}

/* Tungi rejim uchun qiymatlarni bitta joyda almashtirish */
@media (prefers-color-scheme: dark) {
    :root {
        --text-color: #f8fafc; /* Avtomatik ravishda barcha matnlar rangi o'zgaradi */
    }
}
