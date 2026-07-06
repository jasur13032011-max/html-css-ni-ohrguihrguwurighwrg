# html-css-ni-ohrguihrguwurighwrg
Tailwind CSS-da maxsus dizayn tizimini (ranglar, shriftlar) sozlash va @apply direktivasi yordamida qayta ishlatiluvchi komponentlar yaratish bo'yicha so'ralgan barcha sozlamalar va kodlar konfiguratsiyasi:

1. tailwind.config.js konfiguratsiyasi
Loyihangizning brand ranglari va maxsus shrift o'lchamlarini tailwind.config.js faylining theme.extend qismiga quyidagicha qo'shasiz:

JavaScript
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./src/**/*.{html,js}"],
  theme: {
    extend: {
      // 1. Brand ranglari konfiguratsiyasi
      colors: {
        brand: {
          primary: {
            DEFAULT: '#1e40af', // Asosiy ko'k
            dark: '#1e3a8a',
          },
          secondary: {
            DEFAULT: '#0d9488', // Yordamchi yashil-ko'k
            dark: '#0f766e',
          },
          accent: {
            DEFAULT: '#f59e0b', // Urg'u beruvchi sariq/olovrang
            dark: '#d97706',
          }
        }
      },
      // 2. Custom shrift o'lchamlari
      fontSize: {
        'display': ['3.5rem', { lineHeight: '1.2', fontWeight: '800' }],  // Katta sarlavhalar uchun
        'caption': ['0.75rem', { lineHeight: '1.4', fontWeight: '400' }], // Kichik izohlar uchun
      }
    },
  },
  plugins: [],
}
2. Global CSS fayli (src/input.css)
@apply yordamida komponentlarni yaratish hamda ularga hover, focus va transition effektlarini qo'shish:

CSS
@tailwind base;
@tailwind components;
@tailwind utilities;

@layer components {
  
  /* 3. Tugma komponentlari (+ 5-6-band: hover, focus, transition) */
  .btn-primary {
    @apply px-5 py-2.5 bg-brand-primary text-white font-medium rounded-lg 
           shadow-md hover:bg-brand-primary-dark focus:outline-none focus:ring-4 
           focus:ring-brand-primary/30 active:scale-[0.98] 
           transition-all duration-300 ease-in-out;
  }

  .btn-secondary {
    @apply px-5 py-2.5 bg-brand-secondary text-white font-medium rounded-lg 
           shadow-md hover:bg-brand-secondary-dark focus:outline-none focus:ring-4 
           focus:ring-brand-secondary/30 active:scale-[0.98] 
           transition-all duration-300 ease-in-out;
  }

  .btn-outline {
    @apply px-5 py-2.5 bg-transparent text-brand-primary font-medium rounded-lg 
           border-2 border-brand-primary hover:bg-brand-primary hover:text-white 
           focus:outline-none focus:ring-4 focus:ring-brand-primary/30 active:scale-[0.98] 
           transition-all duration-300 ease-in-out;
  }

  /* 4. .card komponenti (+ 5-6-band: hover, transition) */
  .card {
    @apply p-6 bg-white border border-gray-200 rounded-2xl shadow-sm 
           hover:shadow-xl hover:-translate-y-1 focus-within:ring-2 focus-within:ring-brand-primary/50
           transition-all duration-300 ease-in-out;
  }

  /* 4. .input komponenti (+ 5-6-band: hover, focus, transition) */
  .input {
    @apply w-full px-4 py-2.5 bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg 
           hover:border-gray-400 focus:bg-white focus:border-brand-primary focus:ring-4 
           focus:ring-brand-primary/20 focus:outline-none 
           transition-all duration-300 ease-in-out;
  }
}
3. HTML-da ishlatilish namunasi
Yuqoridagi klasslarni HTML strukturangizda quyidagicha toza holatda ishlatishingiz mumkin:

HTML
<div class="p-8 max-w-xl mx-auto space-y-6">

  <div>
    <h1 class="text-display text-gray-900">Katta Sarlavha</h1>
    <span class="text-caption text-gray-500">Bu rasm ostidagi kichik izoh matni.</span>
  </div>

  <div class="card">
    <h3 class="text-lg font-semibold mb-4 text-brand-accent">Tizimga kirish</h3>
    
    <div class="space-y-4">
      <input type="email" placeholder="Email manzilingiz" class="input" />
      <input type="password" placeholder="Parol" class="input" />
    </div>

    <div class="mt-6 flex flex-wrap gap-3">
      <button class="btn-primary">Kirish</button>
      <button class="btn-secondary">Ro'yxatdan o'tish</button>
      <button class="btn-outline">Bekor qilish</button>
    </div>
  </div>

</div>
