# html-css-ni-ohrguihrguwurighwrgcard__detai
Mana, shaxsiy portfolioga mo'ljallangan, professional light/dark muvozanatiga ega, to'liq responsive HTML va CSS kodlari. Sahifada bo'limlararo o'tish silliq scroll (scroll-behavior: smooth) orqali amalga oshiriladi.

1. HTML fayli (index.html)
HTML
<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Shaxsiy Portfolio</title>
    <link rel="stylesheet" href="style.css">
</head>
<body class="portfolio">

    <nav class="navbar">
        <div class="navbar__container">
            <a href="#" class="navbar__logo">Portfolio.</a>
            <div class="navbar__links">
                <a href="#hero" class="navbar__link">Asosiy</a>
                <a href="#about" class="navbar__link">Men haqimda</a>
                <a href="#projects" class="navbar__link">Loyihalar</a>
                <a href="#skills" class="navbar__link">Ko'nikmalar</a>
                <a href="#contact" class="navbar__link">Aloqa</a>
            </div>
        </div>
    </nav>

    <header id="hero" class="hero">
        <div class="hero__container">
            <span class="hero__welcome">Assalomu alaykum!</span>
            <h1 class="hero__title">Men <span class="hero__name">Asrorbek</span></h1>
            <h2 class="hero__subtitle">Frontend Dasturchi</h2>
            <p class="hero__description">Zamonaviy, tezkor va foydalanuvchilar uchun qulay veb-interfeyslarni yaratish bilan shug'ullanaman.</p>
            <a href="#" class="hero__cta-btn" download>CV Yuklab Olish</a>
        </div>
    </header>

    <section id="about" class="about">
        <div class="about__container">
            <div class="about__avatar-box">
                <div class="about__avatar">A</div>
            </div>
            <div class="about__content">
                <h2 class="about__title">Men haqimda</h2>
                <p class="about__text">Men veb-dasturlash olamiga qiziqaman va har bir loyihaga ijodiy yondashaman. Kod yozish bilan birga dizaynning mukammal chiqishiga ham katta e'tibor qarataman.</p>
                <div class="about__experience">
                    <span class="about__years">3+</span>
                    <span class="about__exp-text">Yillik amaliy<br>tajriba</span>
                </div>
            </div>
        </div>
    </section>

    <section id="projects" class="projects">
        <h2 class="projects__title">Mening loyihalarim</h2>
        <div class="projects__grid">
            
            <article class="project-card">
                <img class="project-card__image" src="https://picsum.photos/400/250?random=21" alt="Loyiha 1">
                <div class="project-card__content">
                    <h3 class="project-card__name">E-Commerce Sayt</h3>
                    <div class="project-card__tags">
                        <span class="project-card__tag">HTML</span>
                        <span class="project-card__tag">CSS</span>
                        <span class="project-card__tag">JavaScript</span>
                    </div>
                    <a href="#" class="project-card__link">Ko'rish &rarr;</a>
                </div>
            </article>

            <article class="project-card">
                <img class="project-card__image" src="https://picsum.photos/400/250?random=22" alt="Loyiha 2">
                <div class="project-card__content">
                    <h3 class="project-card__name">Dashboard Paneli</h3>
                    <div class="project-card__tags">
                        <span class="project-card__tag">React</span>
                        <span class="project-card__tag">BEM CSS</span>
                    </div>
                    <a href="#" class="project-card__link">Ko'rish &rarr;</a>
                </div>
            </article>

            <article class="project-card">
                <img class="project-card__image" src="https://picsum.photos/400/250?random=23" alt="Loyiha 3">
                <div class="project-card__content">
                    <h3 class="project-card__name">Kripto Hamyon Ilovasi</h3>
                    <div class="project-card__tags">
                        <span class="project-card__tag">Next.js</span>
                        <span class="project-card__tag">Tailwind</span>
                    </div>
                    <a href="#" class="project-card__link">Ko'rish &rarr;</a>
                </div>
            </article>

            <article class="project-card">
                <img class="project-card__image" src="https://picsum.photos/400/250?random=24" alt="Loyiha 4">
                <div class="project-card__content">
                    <h3 class="project-card__name">Ob-havo Platformasi</h3>
                    <div class="project-card__tags">
                        <span class="project-card__tag">API</span>
                        <span class="project-card__tag">Vanilla JS</span>
                    </div>
                    <a href="#" class="project-card__link">Ko'rish &rarr;</a>
                </div>
            </article>

        </div>
    </section>

    <section id="skills" class="skills">
        <h2 class="skills__title">Ko'nikmalar</h2>
        <div class="skills__container">
            
            <div class="skill-progress">
                <div class="skill-progress__info">
                    <span class="skill-progress__name">HTML5 / CSS3</span>
                    <span class="skill-progress__percentage">95%</span>
                </div>
                <div class="skill-progress__bar">
                    <div class="skill-progress__fill" style="width: 95%;"></div>
                </div>
            </div>

            <div class="skill-progress">
                <div class="skill-progress__info">
                    <span class="skill-progress__name">JavaScript</span>
                    <span class="skill-progress__percentage">85%</span>
                </div>
                <div class="skill-progress__bar">
                    <div class="skill-progress__fill" style="width: 85%;"></div>
                </div>
            </div>

            <div class="skill-progress">
                <div class="skill-progress__info">
                    <span class="skill-progress__name">React.js</span>
                    <span class="skill-progress__percentage">80%</span>
                </div>
                <div class="skill-progress__bar">
                    <div class="skill-progress__fill" style="width: 80%;"></div>
                </div>
            </div>

            <div class="skill-progress">
                <div class="skill-progress__info">
                    <span class="skill-progress__name">UI/UX Dizayn</span>
                    <span class="skill-progress__percentage">70%</span>
                </div>
                <div class="skill-progress__bar">
                    <div class="skill-progress__fill" style="width: 70%;"></div>
                </div>
            </div>

        </div>
    </section>

    <section id="contact" class="contact">
        <h2 class="contact__title">Bog'lanish</h2>
        <div class="contact__container">
            <form action="#" class="contact-form">
                <div class="contact-form__group">
                    <label class="contact-form__label">Ismingiz</label>
                    <input type="text" class="contact-form__input" placeholder="Ismingizni kiriting" required>
                </div>
                <div class="contact-form__group">
                    <label class="contact-form__label">Email manzilingiz</label>
                    <input type="email" class="contact-form__input" placeholder="example@mail.com" required>
                </div>
                <div class="contact-form__group">
                    <label class="contact-form__label">Xabaringiz</label>
                    <textarea class="contact-form__input contact-form__input--textarea" rows="5" placeholder="Xabarni yozing..." required></textarea>
                </div>
                <button type="submit" class="contact-form__btn">Xabarni yuborish</button>
            </form>
        </div>
    </section>

    <footer class="footer">
        <p>&copy; 2026. Barcha huquqlar himoyalangan.</p>
    </footer>

</body>
</html>
2. CSS fayli (style.css)
CSS
/* ========================================================
   7. RANG TIZIMI VA PROFESSIONAL LIGHT/DARK SXEMASI
   ======================================================== */
:root {
    --bg-dark: #0f172a;        /* Chuqur quyuq fon */
    --bg-card: #1e293b;        /* Kartalar foni */
    --accent: #38bdf8;         /* Neon ko'k aksent rang */
    --text-white: #f8fafc;     /* Asosiy matn rangi */
    --text-muted: #94a3b8;     /* Ikkinchi darajali matn */
    --border: #334155;
    
    --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}

/* 6. Silliq scroll ta'minlash */
html {
    scroll-behavior: smooth;
    scroll-padding-top: 80px; /* Navbar balandligini hisobga olish */
}

*, *::before, *::after {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background-color: var(--bg-dark);
    color: var(--text-white);
    line-height: 1.6;
}

/* NAVBAR STILLARI */
.navbar {
    position: sticky;
    top: 0;
    background-color: rgba(15, 23, 42, 0.9);
    backdrop-filter: blur(10px);
    border-bottom: 1px solid var(--border);
    z-index: 1000;
}

.navbar__container {
    max-width: 1100px;
    margin: 0 auto;
    padding: 20px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.navbar__logo {
    color: var(--text-white);
    text-decoration: none;
    font-size: 22px;
    font-weight: 700;
}

.navbar__links {
    display: flex;
    gap: 24px;
}

.navbar__link {
    color: var(--text-muted);
    text-decoration: none;
    font-weight: 500;
    transition: var(--transition);
}

.navbar__link:hover {
    color: var(--accent);
}

/* ========================================================
   1. HERO SECTION
   ======================================================== */
.hero {
    min-height: calc(100vh - 80px);
    display: flex;
    align-items: center;
    max-width: 1100px;
    margin: 0 auto;
    padding: 40px 20px;
}

.hero__welcome {
    color: var(--accent);
    font-weight: 600;
    font-size: 18px;
    display: block;
    margin-bottom: 8px;
}

.hero__title {
    font-size: 48px;
    font-weight: 800;
    line-height: 1.2;
}

.hero__name {
    color: var(--accent);
}

.hero__subtitle {
    font-size: 32px;
    color: var(--text-muted);
    margin-bottom: 20px;
}

.hero__description {
    max-width: 600px;
    color: var(--text-muted);
    font-size: 16px;
    margin-bottom: 40px;
}

.hero__cta-btn {
    display: inline-block;
    background-color: transparent;
    color: var(--accent);
    border: 2px solid var(--accent);
    padding: 12px 28px;
    border-radius: 8px;
    text-decoration: none;
    font-weight: 600;
    transition: var(--transition);
}

.hero__cta-btn:hover {
    background-color: var(--accent);
    color: var(--bg-dark);
    box-shadow: 0 0 20px rgba(56, 189, 248, 0.4);
}

/* ========================================================
   2. ABOUT SECTION
   ======================================================== */
.about {
    padding: 100px 20px;
    border-top: 1px solid var(--border);
}

.about__container {
    max-width: 1100px;
    margin: 0 auto;
    display: flex;
    flex-wrap: wrap;
    gap: 50px;
    align-items: center;
}

.about__avatar-box, .about__content {
    flex: 1 1 400px;
}

.about__avatar {
    width: 200px;
    height: 200px;
    background-color: var(--bg-card);
    border: 4px solid var(--border);
    border-radius: 50%;
    margin: 0 auto;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 72px;
    font-weight: bold;
    color: var(--accent);
}

.about__title {
    font-size: 32px;
    margin-bottom: 20px;
}

.about__text {
    color: var(--text-muted);
    margin-bottom: 30px;
}

.about__experience {
    display: flex;
    align-items: center;
    gap: 16px;
}

.about__years {
    font-size: 44px;
    font-weight: 800;
    color: var(--accent);
}

.about__exp-text {
    font-size: 14px;
    color: var(--text-white);
    font-weight: 500;
}

/* ========================================================
   3. LOYIHALAR GRID
   ======================================================== */
.projects {
    padding: 100px 20px;
    background-color: rgba(30, 41, 59, 0.3);
}

.projects__title {
    text-align: center;
    font-size: 32px;
    margin-bottom: 60px;
}

.projects__grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 30px;
    max-width: 1100px;
    margin: 0 auto;
}

.project-card {
    background-color: var(--bg-card);
    border-radius: 12px;
    overflow: hidden;
    border: 1px solid var(--border);
    transition: var(--transition);
}

.project-card:hover {
    transform: translateY(-6px);
    border-color: var(--accent);
}

.project-card__image {
    width: 100%;
    height: 200px;
    object-fit: cover;
}

.project-card__content {
    padding: 20px;
}

.project-card__name {
    font-size: 20px;
    margin-bottom: 12px;
}

.project-card__tags {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-bottom: 20px;
}

.project-card__tag {
    background-color: var(--bg-dark);
    color: var(--accent);
    padding: 4px 10px;
    font-size: 12px;
    border-radius: 6px;
    font-weight: 500;
}

.project-card__link {
    color: var(--text-white);
    text-decoration: none;
    font-weight: 600;
    font-size: 14px;
    transition: var(--transition);
}

.project-card:hover .project-card__link {
    color: var(--accent);
}

/* ========================================================
   4. KO'NIKMALAR (PROGRESS BAR KO'RINISHIDA)
   ======================================================== */
.skills {
    padding: 100px 20px;
}

.skills__title {
    text-align: center;
    font-size: 32px;
    margin-bottom: 60px;
}

.skills__container {
    max-width: 700px;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    gap: 24px;
}

.skill-progress__info {
    display: flex;
    justify-content: space-between;
    margin-bottom: 8px;
    font-weight: 500;
}

.skill-progress__percentage {
    color: var(--accent);
}

.skill-progress__bar {
    width: 100%;
    height: 8px;
    background-color: var(--bg-card);
    border-radius: 4px;
    overflow: hidden;
}

.skill-progress__fill {
    height: 100%;
    background-color: var(--accent);
    border-radius: 4px;
    box-shadow: 0 0 10px rgba(56, 189, 248, 0.5);
}

/* ========================================================
   5. ALOQA SHAKLI (CONTACT FORM)
   ======================================================== */
.contact {
    padding: 100px 20px;
    border-top: 1px solid var(--border);
}

.contact__title {
    text-align: center;
    font-size: 32px;
    margin-bottom: 60px;
}

.contact__container {
    max-width: 600px;
    margin: 0 auto;
}

.contact-form {
    background-color: var(--bg-card);
    padding: 40px;
    border-radius: 16px;
    border: 1px solid var(--border);
}

.contact-form__group {
    margin-bottom: 24px;
}

.contact-form__label {
    display: block;
    margin-bottom: 8px;
    font-size: 14px;
    color: var(--text-muted);
}

.contact-form__input {
    width: 100%;
    padding: 12px 16px;
    background-color: var(--bg-dark);
    border: 1px solid var(--border);
    border-radius: 8px;
    color: var(--text-white);
    outline: none;
    font-size: 16px;
    transition: var(--transition);
}

.contact-form__input:focus {
    border-color: var(--accent);
    box-shadow: 0 0 8px rgba(56, 189, 248, 0.2);
}

.contact-form__input--textarea {
    resize: none;
}

.contact-form__btn {
    width: 100%;
    padding: 14px;
    background-color: var(--accent);
    color: var(--bg-dark);
    border: none;
    border-radius: 8px;
    font-size: 16px;
    font-weight: 700;
    cursor: pointer;
    transition: var(--transition);
}

.contact-form__btn:hover {
    transform: translateY(-2px);
    box-shadow: 0 4px 15px rgba(56, 189, 248, 0.4);
}

.footer {
    text-align: center;
    padding: 40px 20px;
    color: var(--text-muted);
    font-size: 14px;
    border-top: 1px solid var(--border);
}

/* MEDIA SOZLAMALARI (RESPONSIVE DESIGN) */
@media (max-width: 768px) {
    .navbar__links {
        display: none; /* Mobil menyu soddaligi uchun yashirildi */
    }
    
    .hero__title {
        font-size: 36px;
    }
    
    .hero__subtitle {
        font-size: 24px;
    }
    
    .contact-form {
        padding: 24px;
    }
}
