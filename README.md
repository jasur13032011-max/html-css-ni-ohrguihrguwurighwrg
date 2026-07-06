# html-css-ni-ohrguihrguwurighwrg
HTML
<!DOCTYPE html>
<html lang="uz" class="">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tailwind CSS Amaliyot</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        // Tailwind uchun dark mode konfiguratsiyasi
        tailwind.config = {
            darkMode: 'class',
        }
    </script>
</head>
<body class="bg-gray-50 text-gray-900 dark:bg-gray-900 dark:text-gray-100 min-h-screen p-8 transition-colors duration-300">

    <div class="flex justify-end mb-8">
        <button id="theme-toggle" class="px-4 py-2 rounded-lg bg-gray-200 dark:bg-gray-700 text-sm font-semibold shadow-md hover:opacity-80 transition-all duration-300">
            🌙 Dark Mode / ☀️ Light Mode
        </button>
    </div>

    <div class="max-w-4xl mx-auto space-y-12">
        
        <section class="space-y-4">
            <h2 class="text-xl font-bold border-b pb-2 border-gray-200 dark:border-gray-700">1. Tugmalar (States)</h2>
            <div class="flex flex-wrap gap-4">
                <button class="px-5 py-2.5 bg-blue-600 text-white font-medium rounded-lg shadow-md hover:bg-blue-700 focus:outline-none focus:ring-4 focus:ring-blue-300 active:bg-blue-800 disabled:opacity-50 disabled:pointer-events-none transition-all duration-200">
                    Primary
                </button>

                <button class="px-5 py-2.5 bg-green-600 text-white font-medium rounded-lg shadow-md hover:bg-green-700 focus:outline-none focus:ring-4 focus:ring-green-300 active:bg-green-800 disabled:opacity-50 disabled:pointer-events-none transition-all duration-200">
                    Success
                </button>

                <button class="px-5 py-2.5 bg-red-600 text-white font-medium rounded-lg shadow-md hover:bg-red-700 focus:outline-none focus:ring-4 focus:ring-red-300 active:bg-red-800 disabled:opacity-50 disabled:pointer-events-none transition-all duration-200">
                    Danger
                </button>

                <button class="px-5 py-2.5 bg-yellow-500 text-white font-medium rounded-lg shadow-md hover:bg-yellow-600 focus:outline-none focus:ring-4 focus:ring-yellow-200 active:bg-yellow-700 disabled:opacity-50 disabled:pointer-events-none transition-all duration-200">
                    Warning
                </button>

                <button disabled class="px-5 py-2.5 bg-gray-600 text-white font-medium rounded-lg shadow-md hover:bg-gray-700 focus:outline-none focus:ring-4 focus:ring-gray-300 active:bg-gray-800 disabled:opacity-50 disabled:pointer-events-none transition-all duration-200">
                    Disabled
                </button>
            </div>
        </section>

        <section class="space-y-4">
            <h2 class="text-xl font-bold border-b pb-2 border-gray-200 dark:border-gray-700">2. Group Hover Effekt</h2>
            <div class="group block max-w-sm p-6 bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-xl shadow-md hover:bg-blue-50 dark:hover:bg-blue-950/30 transition-all duration-300 cursor-pointer">
                <h3 class="text-lg font-semibold text-gray-900 dark:text-white group-hover:text-blue-600 dark:group-hover:text-blue-400 transition-colors duration-300">
                    Karta Sarlavhasi
                </h3>
                <p class="mt-2 text-gray-600 dark:text-gray-400 text-sm">
                    Karta ustiga kelganingizda ushbu matn rangi o'zgarmaydi, lekin pastdagi havola o'zgaradi.
                </p>
                <span class="inline-block mt-4 text-sm font-medium text-gray-400 group-hover:text-blue-600 group-hover:translate-x-2 transition-all duration-300">
                    Batafsil ma'lumot &rarr;
                </span>
            </div>
        </section>

        <section class="space-y-4">
            <h2 class="text-xl font-bold border-b pb-2 border-gray-200 dark:border-gray-700">4 & 5. Pricing Karta</h2>
            
            <div class="max-w-sm mx-auto bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700 rounded-2xl shadow-xl overflow-hidden transition-all duration-300 hover:shadow-2xl hover:-translate-y-1">
                <div class="p-6 sm:p-8">
                    <h3 class="text-xl font-bold text-gray-950 dark:text-white transition-colors duration-300">Premium Reja</h3>
                    <p class="mt-2 text-sm text-gray-500 dark:text-gray-400 transition-colors duration-300">Katta hajmdagi loyihalar va jamoalar uchun.</p>
                    
                    <div class="mt-4 flex items-baseline text-gray-950 dark:text-white transition-colors duration-300">
                        <span class="text-3xl font-semibold tracking-tight">$</span>
                        <span class="text-5xl font-bold tracking-tight">49</span>
                        <span class="ml-1 text-sm font-semibold text-gray-500 dark:text-gray-400">/oyiga</span>
                    </div>

                    <ul class="mt-6 space-y-4 text-sm text-gray-600 dark:text-gray-300 transition-colors duration-300">
                        <li class="flex items-center">
                            <span class="text-green-500 mr-2">✓</span> Cheksiz loyihalar
                        </li>
                        <li class="flex items-center">
                            <span class="text-green-500 mr-2">✓</span> 24/7 Qo'llab-quvvatlash
                        </li>
                        <li class="flex items-center">
                            <span class="text-green-500 mr-2">✓</span> Advanced Analitika
                        </li>
                    </ul>

                    <button class="mt-8 w-full py-3 px-4 bg-blue-600 hover:bg-blue-700 text-white font-semibold rounded-xl shadow-md focus:outline-none focus:ring-4 focus:ring-blue-300 active:bg-blue-800 transition-all duration-300">
                        Sotib olish
                    </button>
                </div>
            </div>
        </section>

    </div>

    <script>
        const toggleBtn = document.getElementById('theme-toggle');
        const htmlElement = document.documentElement;

        toggleBtn.addEventListener('click', () => {
            if (htmlElement.classList.contains('dark')) {
                htmlElement.classList.remove('dark');
                localStorage.setItem('theme', 'light');
            } else {
                htmlElement.classList.add('dark');
                localStorage.setItem('theme', 'dark');
            }
        });

        // Sayt yuklanganda foydalanuvchining oldingi tanlovini tekshirish
        if (localStorage.getItem('theme') === 'dark' || (!('theme' in localStorage) && window.matchMedia('(prefers-color-scheme: dark)').matches)) {
            htmlElement.classList.add('dark');
        } else {
            htmlElement.classList.remove('dark');
        }
    </script>
</body>
</html>
Kodning qisqacha tushuntirishi:
Tugmalar holati (1-band): Har bir tugmada hover:, focus:, active:, disabled: klasslari qo'llanilgan. focus:ring-4 orqali fokus holati, active:scale-95 yoki rang o'zgarishi orqali bosilish holati berilgan.

Group Modifikatori (2-band): Tashqi divga group klassi berilgan. Ichki elementda esa group-hover:text-blue-600 va group-hover:translate-x-2 orqali karta ustiga kelganda matn rangi o'zgarishi va o'ngga surilishi ta'minlangan.

Dark Mode Toggle (3-band): JavaScript yordamida html teginga dark klassi qo'shiladi va olib tashlanadi. Foydalanuvchi tanlovi localStorage da saqlanadi.

Dark prefikslari (4-band): Kodda dark:bg-gray-900, dark:text-white, dark:border-gray-700 kabi prefikslar orqali tungi reja uchun ranglar sozlangan.

Pricing Karta (5-band): Light modeda oq fonda, dark modeda esa to'q kulrang fonda chiroyli ko'rinadigan, chekkalari yumaloqlangan zamonaviy karta yaratilgan.

Transition (6-band): Deyarli barcha elementlarda silliq animatsiya uchun transition-all duration-300 yoki transition-colors klasslaridan foydalanilgan.
