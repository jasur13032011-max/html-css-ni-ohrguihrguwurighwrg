# html-css-ni-ohrguihrguwurighwrg
Mana, so'ralgan barcha 7 ta bandni o'z ichiga olgan, to'liq moslashuvchan (responsive) va zamonaviy veb-sahifa kodi.

Bu kodda mobil qurilmalar uchun burger menyu, chiroyli gradientlar, grid tizimi va barcha elementlarning desktop hamda mobil ko'rinishlari mukammal sozlangan.

HTML
<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mukammal Landing Page - Tailwind CSS</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        // Mobil menyuni yoqib-ochirish funksiyasi
        function toggleMenu() {
            const menu = document.getElementById('mobile-menu');
            menu.classList.toggle('hidden');
        }
    </script>
</head>
<body class="bg-gray-50 text-gray-900 font-sans antialiased">

    <nav class="bg-white/80 backdrop-blur-md sticky top-0 z-50 border-b border-gray-100 transition-all duration-300">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between h-16 items-center">
                <div class="flex-shrink-0 flex items-center">
                    <span class="text-2xl font-bold bg-gradient-to-r from-blue-600 to-indigo-600 bg-clip-text text-transparent">BrandLogo</span>
                </div>
                
                <div class="hidden md:flex space-x-8 font-medium text-gray-600">
                    <a href="#hero" class="hover:text-blue-600 transition-colors duration-200">Asosiy</a>
                    <a href="#features" class="hover:text-blue-600 transition-colors duration-200">Xizmatlar</a>
                    <a href="#pricing" class="hover:text-blue-600 transition-colors duration-200">Tariflar</a>
                    <a href="#testimonials" class="hover:text-blue-600 transition-colors duration-200">Izohlar</a>
                </div>

                <div class="hidden md:block">
                    <a href="#pricing" class="px-5 py-2 bg-blue-600 text-white font-medium rounded-lg shadow-md hover:bg-blue-700 hover:shadow-lg transition-all duration-300">Boshlash</a>
                </div>

                <div class="md:hidden flex items-center">
                    <button onclick="toggleMenu()" class="text-gray-600 hover:text-gray-900 focus:outline-none">
                        <svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"/>
                        </svg>
                    </button>
                </div>
            </div>
        </div>

        <div id="mobile-menu" class="hidden md:hidden bg-white border-b border-gray-200 px-4 pt-2 pb-4 space-y-2">
            <a href="#hero" class="block px-3 py-2 rounded-md text-gray-700 hover:bg-gray-50">Asosiy</a>
            <a href="#features" class="block px-3 py-2 rounded-md text-gray-700 hover:bg-gray-50">Xizmatlar</a>
            <a href="#pricing" class="block px-3 py-2 rounded-md text-gray-700 hover:bg-gray-50">Tariflar</a>
            <a href="#testimonials" class="block px-3 py-2 rounded-md text-gray-700 hover:bg-gray-50">Izohlar</a>
            <a href="#pricing" class="block w-full text-center px-3 py-2.5 bg-blue-600 text-white font-medium rounded-md">Boshlash</a>
        </div>
    </nav>

    <section id="hero" class="relative bg-gradient-to-br from-blue-50 via-indigo-50 to-white pt-20 pb-16 lg:pt-32 lg:pb-24 overflow-hidden">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center relative z-10">
            <h1 class="text-4xl sm:text-5xl lg:text-6xl font-extrabold tracking-tight text-gray-900 max-w-4xl mx-auto leading-tight">
                Biznesingizni <span class="bg-gradient-to-r from-blue-600 to-indigo-600 bg-clip-text text-transparent">Raqamli Dunyoga</span> Olib Chiqing
            </h1>
            <p class="mt-6 text-lg sm:text-xl text-gray-600 max-w-2xl mx-auto">
                Zamonaviy texnologiyalar va mukammal dizayn yordamida loyihalaringizni tezroq va samaraliroq rivojlantiring.
            </p>
            
            <div class="mt-10 flex flex-wrap justify-center gap-4">
                <a href="#pricing" class="px-8 py-3.5 bg-blue-600 text-white font-semibold rounded-xl shadow-lg hover:bg-blue-700 hover:-translate-y-0.5 transition-all duration-300">Hozir boshlang</a>
                <a href="#features" class="px-8 py-3.5 bg-white text-gray-700 font-semibold rounded-xl shadow-md border border-gray-200 hover:bg-gray-50 hover:-translate-y-0.5 transition-all duration-300">Batafsil ma'lumot</a>
            </div>

            <div class="mt-20 border-t border-gray-200/60 pt-10 max-w-4xl mx-auto">
                <dl class="grid grid-cols-2 md:grid-cols-4 gap-8">
                    <div>
                        <dt class="text-sm font-medium text-gray-500 uppercase">Aktiv foydalanuvchilar</dt>
                        <dd class="mt-1 text-3xl font-extrabold text-blue-600">50K+</dd>
                    </div>
                    <div>
                        <dt class="text-sm font-medium text-gray-500 uppercase">Yuklab olingan</dt>
                        <dd class="mt-1 text-3xl font-extrabold text-blue-600">100K+</dd>
                    </div>
                    <div>
                        <dt class="text-sm font-medium text-gray-500 uppercase">Ijobiy baholar</dt>
                        <dd class="mt-1 text-3xl font-extrabold text-blue-600">4.9/5</dd>
                    </div>
                    <div>
                        <dt class="text-sm font-medium text-gray-500 uppercase">Hamkorlarimiz</dt>
                        <dd class="mt-1 text-3xl font-extrabold text-blue-600">120+</dd>
                    </div>
                </dl>
            </div>
        </div>
    </section>

    <section id="features" class="py-20 lg:py-28 bg-white">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto mb-16">
                <h2 class="text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl">Keng qamrovli xizmatlarimiz</h2>
                <p class="mt-4 text-lg text-gray-600">Sizning muvaffaqiyatingiz uchun kerak bo'ladigan barcha vositalar bir joyda jamlangan.</p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                <div class="p-8 border border-gray-100 rounded-2xl bg-gray-50/50 hover:bg-white hover:shadow-xl hover:-translate-y-1 transition-all duration-300">
                    <div class="w-12 h-12 bg-blue-100 text-blue-600 rounded-xl flex items-center justify-center font-bold text-xl mb-6">⚡</div>
                    <h3 class="text-xl font-bold text-gray-900">Yuqori Tezlik</h3>
                    <p class="mt-3 text-gray-600 text-sm leading-relaxed">Bizning tizim eng so'nggi texnologiyalar bilan jihozlangan va maksimal tezlikda ishlaydi.</p>
                </div>
                <div class="p-8 border border-gray-100 rounded-2xl bg-gray-50/50 hover:bg-white hover:shadow-xl hover:-translate-y-1 transition-all duration-300">
                    <div class="w-12 h-12 bg-indigo-100 text-indigo-600 rounded-xl flex items-center justify-center font-bold text-xl mb-6">🔒</div>
                    <h3 class="text-xl font-bold text-gray-900">Xavfsizlik</h3>
                    <p class="mt-3 text-gray-600 text-sm leading-relaxed">Ma'lumotlaringiz to'liq shifrlangan va xalqaro xavfsizlik standartlariga mos himoyalangan.</p>
                </div>
                <div class="p-8 border border-gray-100 rounded-2xl bg-gray-50/50 hover:bg-white hover:shadow-xl hover:-translate-y-1 transition-all duration-300">
                    <div class="w-12 h-12 bg-purple-100 text-purple-600 rounded-xl flex items-center justify-center font-bold text-xl mb-6">📊</div>
                    <h3 class="text-xl font-bold text-gray-900">Chuqur Analitika</h3>
                    <p class="mt-3 text-gray-600 text-sm leading-relaxed">Biznesingiz o'sishini real vaqt rejimida kuzatib borish uchun qulay boshqaruv paneli.</p>
                </div>
                <div class="p-8 border border-gray-100 rounded-2xl bg-gray-50/50 hover:bg-white hover:shadow-xl hover:-translate-y-1 transition-all duration-300">
                    <div class="w-12 h-12 bg-emerald-100 text-emerald-600 rounded-xl flex items-center justify-center font-bold text-xl mb-6">🎨</div>
                    <h3 class="text-xl font-bold text-gray-900">Moslashuvchan Dizayn</h3>
                    <p class="mt-3 text-gray-600 text-sm leading-relaxed">Istalgan turdagi qurilma va ekranga moslashuvchi zamonaviy UI/UX yechimlar.</p>
                </div>
                <div class="p-8 border border-gray-100 rounded-2xl bg-gray-50/50 hover:bg-white hover:shadow-xl hover:-translate-y-1 transition-all duration-300">
                    <div class="w-12 h-12 bg-rose-100 text-rose-600 rounded-xl flex items-center justify-center font-bold text-xl mb-6">🛠️</div>
                    <h3 class="text-xl font-bold text-gray-900">24/7 Qo'llab-quvvatlash</h3>
                    <p class="mt-3 text-gray-600 text-sm leading-relaxed">Mutaxassislarimiz har qanday texnik muammoni hal qilishda yordam berishga tayyor.</p>
                </div>
                <div class="p-8 border border-gray-100 rounded-2xl bg-gray-50/50 hover:bg-white hover:shadow-xl hover:-translate-y-1 transition-all duration-300">
                    <div class="w-12 h-12 bg-amber-100 text-amber-600 rounded-xl flex items-center justify-center font-bold text-xl mb-6">☁️</div>
                    <h3 class="text-xl font-bold text-gray-900">Bulutli Tizim</h3>
                    <p class="mt-3 text-gray-600 text-sm leading-relaxed">Fayllaringiz va loyihalaringiz dunyoning istalgan nuqtasidan muammosiz ochiladi.</p>
                </div>
            </div>
        </div>
    </section>

    <section id="pricing" class="py-20 lg:py-28 bg-gray-50">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto mb-16">
                <h2 class="text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl">Sizga mos keluvchi reja</h2>
                <p class="mt-4 text-lg text-gray-600">Yashirin to'lovlarsiz shaffof narxlar.</p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-8 items-center">
                <div class="bg-white p-8 border border-gray-200 rounded-2xl shadow-sm hover:shadow-md transition-all duration-300">
                    <h3 class="text-xl font-bold text-gray-900">Basic</h3>
                    <p class="mt-2 text-sm text-gray-500">Kichik yoki shaxsiy loyihalar uchun.</p>
                    <div class="mt-6 flex items-baseline">
                        <span class="text-4xl font-extrabold text-gray-900">$19</span>
                        <span class="ml-1 text-sm text-gray-500">/oyiga</span>
                    </div>
                    <ul class="mt-6 space-y-4 text-sm text-gray-600">
                        <li>✓ 3 ta loyiha qo'shish</li>
                        <li>✓ 5GB Bulutli xotira</li>
                        <li>✓ Jamiyat yordami</li>
                    </ul>
                    <button class="mt-8 w-full py-3 px-4 bg-gray-100 hover:bg-gray-200 text-gray-900 font-semibold rounded-xl transition-all duration-200">Boshlash</button>
                </div>

                <div class="bg-white p-8 border-2 border-blue-600 rounded-2xl shadow-xl relative scale-105 z-10">
                    <span class="absolute top-0 right-6 transform -translate-y-1/2 bg-blue-600 text-white text-xs font-bold uppercase tracking-wider px-3 py-1 rounded-full">Ommabop</span>
                    <h3 class="text-xl font-bold text-gray-900">Pro</h3>
                    <p class="mt-2 text-sm text-gray-500">Rivojlanayotgan bizneslar uchun.</p>
                    <div class="mt-6 flex items-baseline">
                        <span class="text-4xl font-extrabold text-gray-900">$49</span>
                        <span class="ml-1 text-sm text-gray-500">/oyiga</span>
                    </div>
                    <ul class="mt-6 space-y-4 text-sm text-gray-600">
                        <li>✓ Cheksiz loyihalar</li>
                        <li>✓ 50GB Bulutli xotira</li>
                        <li>✓ 24/7 Qo'llab-quvvatlash</li>
                        <li>✓ Premium Analitika</li>
                    </ul>
                    <button class="mt-8 w-full py-3 px-4 bg-blue-600 hover:bg-blue-700 text-white font-semibold rounded-xl shadow-md transition-all duration-200">Sotib olish</button>
                </div>

                <div class="bg-white p-8 border border-gray-200 rounded-2xl shadow-sm hover:shadow-md transition-all duration-300">
                    <h3 class="text-xl font-bold text-gray-900">Enterprise</h3>
                    <p class="mt-2 text-sm text-gray-500">Katta tashkilot va jamoalar uchun.</p>
                    <div class="mt-6 flex items-baseline">
                        <span class="text-4xl font-extrabold text-gray-900">$99</span>
                        <span class="ml-1 text-sm text-gray-500">/oyiga</span>
                    </div>
                    <ul class="mt-6 space-y-4 text-sm text-gray-600">
                        <li>✓ Maxsus xususiyatlar</li>
                        <li>✓ Cheksiz xotira hajmi</li>
                        <li>✓ Shaxsiy menejer</li>
                        <li>✓ SLA kafolati</li>
                    </ul>
                    <button class="mt-8 w-full py-3 px-4 bg-gray-100 hover:bg-gray-200 text-gray-900 font-semibold rounded-xl transition-all duration-200">Bog'lanish</button>
                </div>
            </div>
        </div>
    </section>

    <section id="testimonials" class="py-20 lg:py-28 bg-white">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto mb-16">
                <h2 class="text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl">Mijozlarimiz fikri</h2>
                <p class="mt-4 text-lg text-gray-600">Biz bilan birga o'sayotgan jamoalarning samimiy fikrlari.</p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <div class="p-8 border border-gray-200 rounded-2xl bg-white shadow-sm hover:shadow-md transition-shadow duration-300">
                    <p class="text-gray-600 italic">"Ushbu platforma yordamida biz ishimiz samaradorligini ikki barobarga oshirdik. Dizayn ham, tezlik ham ajoyib!"</p>
                    <div class="mt-6 flex items-center gap-4">
                        <div class="w-11 h-11 bg-blue-600 text-white rounded-full font-bold flex items-center justify-center">AK</div>
                        <div>
                            <h4 class="font-bold text-gray-900 text-sm">Asror Karimov</h4>
                            <p class="text-xs text-gray-500">TechCorp — CEO</p>
                        </div>
                    </div>
                </div>

                <div class="p-8 border border-gray-200 rounded-2xl bg-white shadow-sm hover:shadow-md transition-shadow duration-300">
                    <p class="text-gray-600 italic">"Texnik qo'llab-quvvatlash jamoasi shunchaki super. Muammolar bir necha daqiqa ichida hal qilinadi."</p>
                    <div class="mt-6 flex items-center gap-4">
                        <div class="w-11 h-11 bg-indigo-600 text-white rounded-full font-bold flex items-center justify-center">MN</div>
                        <div>
                            <h4 class="font-bold text-gray-900 text-sm">Malika Nosirova</h4>
                            <p class="text-xs text-gray-500">DesignStudio — Art Director</p>
                        </div>
                    </div>
                </div>

                <div class="p-8 border border-gray-200 rounded-2xl bg-white shadow-sm hover:shadow-md transition-shadow duration-300">
                    <p class="text-gray-600 italic">"Narx va sifat nisbati juda yaxshi sozlangan. Har qanday startap uchun juda ham mos yechim."</p>
                    <div class="mt-6 flex items-center gap-4">
                        <div class="w-11 h-11 bg-purple-600 text-white rounded-full font-bold flex items-center justify-center">JS</div>
                        <div>
                            <h4 class="font-bold text-gray-900 text-sm">Jamshid Sultanov</h4>
                            <p class="text-xs text-gray-500">Freelancer — Dasturchi</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <footer class="bg-gray-900 text-gray-400 py-12 border-t border-gray-800">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 grid grid-cols-1 md:grid-cols-4 gap-8">
            <div class="space-y-4">
                <span class="text-2xl font-bold text-white">BrandLogo</span>
                <p class="text-sm">Kelajak raqamli texnologiyalarini bugun yaratamiz.</p>
            </div>

            <div>
                <h4 class="text-sm font-semibold text-white tracking-wider uppercase mb-4">Kompaniya</h4>
                <ul class="space-y-2 text-sm">
                    <li><a href="#" class="hover:text-white transition-colors">Biz haqimizda</a></li>
                    <li><a href="#" class="hover:text-white transition-colors">Vakansiyalar</a></li>
                    <li><a href="#" class="hover:text-white transition-colors">Yangiliklar</a></li>
                </ul>
            </div>

            <div>
                <h4 class="text-sm font-semibold text-white tracking-wider uppercase mb-4">Huquqiy</h4>
                <ul class="space-y-2 text-sm">
                    <li><a href="#" class="hover:text-white transition-colors">Maxfiylik siyosati</a></li>
                    <li><a href="#" class="hover:text-white transition-colors">Foydalanish shartlari</a></li>
                </ul>
            </div>

            <div>
                <h4 class="text-sm font-semibold text-white tracking-wider uppercase mb-4">Bizni kuzating</h4>
                <div class="flex space-x-4 text-xl">
                    <a href="#" class="hover:text-white transition-colors">🔵 Telegram</a>
                    <a href="#" class="hover:text-white transition-colors">📸 Insta</a>
                </div>
            </div>
        </div>

        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 mt-12 pt-8 border-t border-gray-800 text-center text-xs">
            <p>&copy; 2026 BrandLogo OAJ. Barcha huquqlar himoyalangan.</p>
        </div>
    </footer>

</body>
</html>
