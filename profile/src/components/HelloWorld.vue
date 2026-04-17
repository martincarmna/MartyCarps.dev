<script setup lang="ts">
import { ref, onMounted } from 'vue';
import Magikar from './Magikar.vue';
import Myself from './Myself.vue';
import Banner from './Banner.vue';
import Proyectos from './Proyectos.vue';
import Git from './Git.vue';
import SafariWhatsapp from './SafariWhatsapp.vue';

// --- ESTADOS REACTIVOS ---
const isLoading = ref(true);
const isSidebarOpen = ref(false);
const isSearchOpen = ref(false);
const isLangOpen = ref(false);
const currentLang = ref<'ES' | 'EN'>('ES');
const emailInput = ref('');
const subscribeMessage = ref('');

// --- DICCIONARIO DE TEXTOS ---
const texts = {
  ES: {
    nav: { home: 'Inicio', projects: 'Proyectos', about: 'Sobre mí', cv: 'Mi CV' },
    loading: 'Cargando aventura...',
    searchPlaceholder: 'Buscar...',
    hero: { title: 'Proyectos', button: 'Ir' },
    footer: {
      desc: 'Portafolio personal diseñado para demostrar habilidades frontend y backend. Creativo, guitarrista y apasionado por el código.',
      subscribeTitle: 'Suscríbete al canal',
      subscribeSub: 'Recibe actualizaciones de tutoriales y proyectos.',
      subscribeBtn: 'Unirse',
      thanks: '¡Gracias por unirte, Marty se pondrá en contacto!',
      madeIn: 'Hecho en México.'
    }
  },
  EN: {
    nav: { home: 'Home', projects: 'Projects', about: 'About', cv: 'My CV' },
    loading: 'Loading adventure...',
    searchPlaceholder: 'Search...',
    hero: { title: 'Projects', button: 'Go' },
    footer: {
      desc: 'Personal portfolio designed to demonstrate frontend and backend skills. Creative, guitarist, and passionate about code.',
      subscribeTitle: 'Subscribe to the channel',
      subscribeSub: 'Get updates on tutorials and projects.',
      subscribeBtn: 'Join',
      thanks: 'Thanks for joining, Marty will be in touch!',
      madeIn: 'Made in Mexico.'
    }
  }
};

// --- FUNCIONES ---
onMounted(() => {
  // Simulamos carga de recursos (puedes ajustarlo a 0 si no quieres espera)
  setTimeout(() => {
    isLoading.value = false;
  }, 1800);
});

const toggleSidebar = () => {
  isSidebarOpen.value = !isSidebarOpen.value;
};

const changeLang = (lang: 'ES' | 'EN') => {
  currentLang.value = lang;
  isLangOpen.value = false;
};
</script>

<template>
  <transition name="fade">
    <div v-if="isLoading" class="fixed inset-0 z-[100] bg-black flex flex-col items-center justify-center gap-6">
      <div class="pokeball-container">
        <div class="pokeball-spinner"></div>
        <div class="pokeball-glow"></div>
      </div>
      <p class="text-blue-500 font-black tracking-[0.2em] uppercase animate-pulse text-sm">
        {{ texts[currentLang].loading }}
      </p>
    </div>
  </transition>

  <header class="bg-black flex items-center justify-between px-4 md:px-8 py-3 w-full sticky top-0 z-50 border-b border-gray-900 font-sans">
    <a href="#inicio" class="flex-shrink-0">
      <img src="/Pokemon-Logo.png" alt="Logo Marty Carps" class="w-[100px] md:w-[130px] h-auto object-contain brightness-110">
    </a>

    <nav class="hidden md:flex gap-6 lg:gap-10 text-blue-500 font-bold uppercase tracking-wider text-sm">
      <a href="#inicio" class="hover:text-blue-300 transition-colors">{{ texts[currentLang].nav.home }}</a>
      <a href="#proyectos" class="hover:text-blue-300 transition-colors">{{ texts[currentLang].nav.projects }}</a>
      <a href="#about" class="hover:text-blue-300 transition-colors">{{ texts[currentLang].nav.about }}</a>
      <a href="#cv" class="hover:text-blue-300 transition-colors">{{ texts[currentLang].nav.cv }}</a>
    </nav>

    <div class="flex items-center gap-4 md:gap-6 text-white">
      <div class="relative flex items-center justify-end">
        <transition name="fade-search">
          <input 
            v-if="isSearchOpen" 
            type="text" 
            :placeholder="texts[currentLang].searchPlaceholder" 
            class="absolute right-10 bg-gray-900 border border-blue-500 text-white text-xs rounded-full px-4 py-1.5 w-36 md:w-48 outline-none"
          />
        </transition>
        <span @click="isSearchOpen = !isSearchOpen" class="material-symbols-outlined cursor-pointer hover:text-blue-400 text-[26px] transition-colors">
          search
        </span>
      </div>
      
      <div class="relative flex items-center">
        <span @click="isLangOpen = !isLangOpen" class="material-symbols-outlined cursor-pointer hover:text-blue-400 text-[26px] transition-colors">
          language
        </span>
        <div v-if="isLangOpen" class="absolute right-0 top-full mt-3 w-32 bg-gray-950 border border-gray-800 rounded-lg shadow-2xl overflow-hidden z-50 animate-fade-in">
          <button @click="changeLang('ES')" class="block w-full px-4 py-3 text-[11px] font-bold hover:bg-blue-600 transition-colors text-left border-b border-gray-800">ESPAÑOL</button>
          <button @click="changeLang('EN')" class="block w-full px-4 py-3 text-[11px] font-bold hover:bg-blue-600 transition-colors text-left">ENGLISH</button>
        </div>
      </div>

      <a href="https://www.tiktok.com/@jossmar_carmona" target="_blank" class="hover:text-[#ff0050] transition-all transform hover:scale-110 hidden sm:flex">
        <svg class="w-6 h-6 fill-current" viewBox="0 0 24 24"><path d="M12.525.02c1.31-.02 2.61-.01 3.91-.02.08 1.53.63 3.09 1.75 4.17 1.12 1.11 2.7 1.62 4.24 1.79v4.03c-1.44-.05-2.89-.35-4.2-.97-.57-.26-1.1-.59-1.62-.93-.01 2.92.01 5.84-.02 8.75-.08 1.4-.54 2.79-1.35 3.94-1.31 1.92-3.58 3.17-5.91 3.21-1.43.08-2.86-.31-4.08-1.03-2.02-1.19-3.44-3.37-3.65-5.71-.02-.5-.03-1-.01-1.49.18-1.9 1.12-3.72 2.58-4.96 1.66-1.44 3.98-2.13 6.15-1.72.02 1.48-.04 2.96-.04 4.44-.99-.32-2.15-.23-3.02.37-.63.41-1.11 1.07-1.3 1.8-.23.82-.16 1.71.22 2.47.39.83 1.24 1.43 2.12 1.6 1.25.26 2.62-.1 3.44-1.06.52-.61.81-1.39.86-2.18l.05-11.39z"/></svg>
      </a>

      <button @click="toggleSidebar" class="md:hidden text-blue-500 hover:text-blue-300">
        <span class="material-symbols-outlined text-3xl">menu</span>
      </button>
    </div>
  </header>

  <transition name="slide">
    <div v-if="isSidebarOpen" class="fixed inset-0 z-[60] flex">
      <div @click="isSidebarOpen = false" class="absolute inset-0 bg-black/80 backdrop-blur-sm"></div>
      <aside class="relative w-64 bg-black h-full border-r border-blue-900 p-6 flex flex-col">
        <div class="flex justify-between items-center mb-10">
          <img src="/Pokemon-Logo.png" class="w-24" alt="Logo">
          <span @click="isSidebarOpen = false" class="material-symbols-outlined text-white cursor-pointer">close</span>
        </div>
        <nav class="flex flex-col gap-6 text-blue-500 font-bold uppercase tracking-widest text-lg">
          <a href="#inicio" @click="isSidebarOpen = false">{{ texts[currentLang].nav.home }}</a>
          <a href="#proyectos" @click="isSidebarOpen = false">{{ texts[currentLang].nav.projects }}</a>
          <a href="#about" @click="isSidebarOpen = false">{{ texts[currentLang].nav.about }}</a>
          <a href="#cv" @click="isSidebarOpen = false">{{ texts[currentLang].nav.cv }}</a>
        </nav>
      </aside>
    </div>
  </transition>

  <main>
    <SafariWhatsapp/>
    
    <section id="inicio" class="bg-[url('/fondo1.1.webp')] bg-cover bg-center bg-no-repeat h-screen w-full relative flex flex-col items-center justify-center gap-12 px-4">
      <div class="absolute inset-0 bg-black/20"></div>
      <h1 class="relative text-white text-6xl md:text-8xl font-black drop-shadow-2xl uppercase tracking-tighter text-center italic">
        Marty Carps
      </h1>

      <div class="relative inline-flex flex-col sm:flex-row items-center bg-white border border-gray-100 rounded-2xl sm:rounded-full shadow-2xl p-2 max-w-sm w-full transform hover:scale-105 transition-transform">
        <div class="flex items-center gap-3 px-6 text-gray-700 py-2 sm:py-0">
          <span class="material-symbols-outlined text-gray-400">home_repair_service</span>
          <span class="text-xl font-semibold tracking-tight">{{ texts[currentLang].hero.title }}</span>
        </div>
        <a href="#proyectos" class="w-full sm:w-auto">
          <button class="w-full flex items-center justify-center gap-2.5 bg-yellow-500 text-gray-900 font-bold py-4 px-10 rounded-xl sm:rounded-full hover:bg-yellow-400 transition-all active:scale-95 shadow-md">
            <span class="text-xl">{{ texts[currentLang].hero.button }}</span>
            <span class="material-symbols-outlined">arrow_forward</span>
          </button>
        </a>
      </div>
    </section>

    <Banner :currentLang="currentLang" />
    <Proyectos id="proyectos" :currentLang="currentLang" />
    <Git :currentLang="currentLang" />
    <Myself id="about" :currentLang="currentLang" />
    <Magikar id="cv" :currentLang="currentLang" />
  </main>

  <footer class="bg-black text-white py-12 px-8 md:px-20 border-t border-gray-800">
    <div class="max-w-7xl mx-auto flex flex-col md:flex-row justify-between gap-12">
      <div class="flex-1 space-y-6">
        <a href="#inicio"><img src="/Pokemon-Logo.png" alt="logo" class="w-32 brightness-110"></a>
        <p class="text-gray-400 text-sm leading-relaxed max-w-md">{{ texts[currentLang].footer.desc }}</p>
      </div>

      <div class="flex-1 space-y-4">
        <h3 class="text-xl font-bold text-red-600 uppercase italic">¡Visita mi Canal!</h3>
        <p class="text-gray-400 text-sm">Suscríbete para aperturas de cartas Pokémon y tutoriales dev.</p>
        <a href="https://www.youtube.com/@JossMar_Carmona" target="_blank" class="inline-flex items-center gap-2 bg-red-600 hover:bg-red-700 text-white font-bold px-8 py-3 rounded-lg transition-all transform hover:scale-105 shadow-lg shadow-red-900/20">
          <svg class="w-6 h-6 fill-current" viewBox="0 0 24 24"><path d="M23.498 6.186a3.016 3.016 0 0 0-2.122-2.136C19.505 3.545 12 3.545 12 3.545s-7.505 0-9.377.505A3.017 3.017 0 0 0 .502 6.186C0 8.07 0 12 0 12s0 3.93.502 5.814a3.016 3.016 0 0 0 2.122 2.136c1.871.505 9.376.505 9.376.505s7.505 0 9.377-.505a3.015 3.015 0 0 0 2.122-2.136C24 15.93 24 12 24 12s0-3.93-.502-5.814zM9.545 15.568V8.432L15.818 12l-6.273 3.568z"/></svg>
          IR AL CANAL
        </a>
      </div>
    </div>

    <div class="max-w-7xl mx-auto mt-12 pt-8 border-t border-gray-900 flex flex-col md:flex-row justify-between items-center text-gray-500 text-xs gap-4">
      <p>© 2026 Marty Carps. {{ texts[currentLang].footer.madeIn }}</p>
      <div class="flex gap-6">
        <a href="https://www.youtube.com/@JossMar_Carmona" target="_blank" class="hover:text-red-500 transition">YouTube</a>
        <a href="https://github.com/martincarmna" target="_blank" class="hover:text-blue-500 transition">GitHub</a>
      </div>
    </div>
  </footer>
</template>

<style>
/* --- ESTILOS GLOBALES --- */
html { scroll-behavior: smooth; }
section[id], div[id] { scroll-margin-top: 80px; }

/* --- SPINNER POKEBOLA --- */
.pokeball-container {
  position: relative;
  width: 80px;
  height: 80px;
}

.pokeball-spinner {
  width: 80px;
  height: 80px;
  background: #fff;
  border: 4px solid #000;
  border-radius: 50%;
  position: relative;
  overflow: hidden;
  animation: spin 1s linear infinite;
  z-index: 2;
}

.pokeball-spinner::before {
  content: "";
  position: absolute;
  top: 0; left: 0;
  width: 100%; height: 50%;
  background: #ff0000;
  border-bottom: 4px solid #000;
}

.pokeball-spinner::after {
  content: "";
  position: absolute;
  top: 50%; left: 50%;
  width: 18px; height: 18px;
  background: #fff;
  border: 4px solid #000;
  border-radius: 50%;
  transform: translate(-50%, -50%);
  z-index: 10;
}

.pokeball-glow {
  position: absolute;
  top: -10px; left: -10px;
  width: 100px; height: 100px;
  background: radial-gradient(circle, rgba(59,130,246,0.4) 0%, transparent 70%);
  border-radius: 50%;
  animation: pulse-glow 2s ease-in-out infinite;
}

/* --- ANIMACIONES --- */
@keyframes spin { from { transform: rotate(0deg); } to { transform: rotate(360deg); } }
@keyframes pulse-glow { 0%, 100% { transform: scale(1); opacity: 0.5; } 50% { transform: scale(1.2); opacity: 0.8; } }

.fade-enter-active, .fade-leave-active { transition: opacity 0.5s ease; }
.fade-enter-from, .fade-leave-to { opacity: 0; }

.slide-enter-active, .slide-leave-active { transition: transform 0.3s ease; }
.slide-enter-from, .slide-leave-to { transform: translateX(-100%); }

.fade-search-enter-active { animation: search-in 0.3s ease-out; }
@keyframes search-in { from { opacity: 0; transform: translateX(20px); } to { opacity: 1; transform: translateX(0); } }
</style>