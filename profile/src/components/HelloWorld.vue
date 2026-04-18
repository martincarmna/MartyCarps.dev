<script setup lang="ts">
import { ref, onMounted } from 'vue';
import Magikar from './Magikar.vue';
import Myself from './Myself.vue';
import Proyectos from './Proyectos.vue';
import Git from './Git.vue';

const isLoading = ref(true);
const isSidebarOpen = ref(false);
const isSearchOpen = ref(false);
const isLangOpen = ref(false);
const currentLang = ref<'ES' | 'EN'>('ES');

const logos = {
  django: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/django/django-plain.svg' // Ejemplo
};

const texts = {
  ES: {
    nav: [
      { label: 'Inicio',    href: '#inicio' },
      { label: 'Proyectos', href: '#proyectos' },
      { label: 'Sobre mí',  href: '#about' },
      { label: 'Mi CV',     href: '#cv' },
    ],
    loading: 'Capturando aventura...',
    searchPlaceholder: 'Buscar proyecto...',
    hero: { title: 'Proyectos Seleccionados', button: 'Explorar' },
    footer: {
      desc: 'Desarrollador enfocado en crear experiencias visuales de alto impacto. Combinando lógica de backend con estética frontend.',
      madeIn: 'Marty Carps Hecho en México.'
    }
  },
  EN: {
    nav: [
      { label: 'Home',      href: '#inicio' },
      { label: 'Projects', href: '#proyectos' },
      { label: 'About',    href: '#about' },
      { label: 'My CV',    href: '#cv' },
    ],
    loading: 'Catching adventure...',
    searchPlaceholder: 'Search project...',
    hero: { title: 'Selected Projects', button: 'Explore' },
    footer: {
      desc: 'Developer focused on creating high-impact visual experiences. Combining backend logic with frontend aesthetics.',
      madeIn: 'Marty Carps Made in Mexico.'
    }
  }
};

onMounted(() => {
  setTimeout(() => { isLoading.value = false; }, 2200);
});

const toggleSidebar = () => { isSidebarOpen.value = !isSidebarOpen.value; };
const changeLang = (lang: 'ES' | 'EN') => { currentLang.value = lang; isLangOpen.value = false; };
</script>

<template>
  <transition name="fade">
    <div v-if="isLoading" class="fixed inset-0 z-[100] bg-gray-950 flex flex-col items-center justify-center gap-8">
      <div class="pokeball-container">
        <div class="pokeball-spinner pokeball-catching">
          <div class="pokeball-spinner-reflect"></div>
        </div>
        <div class="pokeball-glow"></div>
      </div>
      <div class="text-center space-y-2">
        <p class="text-white font-black tracking-[0.3em] uppercase text-[10px] font-mono animate-pulse">
          {{ texts[currentLang].loading }}
        </p>
        <div class="w-32 h-[1px] bg-gradient-to-r from-transparent via-gray-700 to-transparent mx-auto"></div>
      </div>
    </div>
  </transition>

  <header class="bg-black/90 backdrop-blur-lg flex items-center justify-between px-6 md:px-12 py-5 w-full sticky top-0 z-50 border-b border-gray-900">
    <a href="#inicio" class="group">
      <h1 class="text-white text-xl font-black uppercase tracking-tighter italic group-hover:text-red-500 transition-colors">
        Marty Carps<span class="text-red-600">.</span>
      </h1>
    </a>

    <nav class="hidden md:flex gap-10 text-gray-400 font-bold uppercase tracking-widest text-[10px]">
      <a v-for="item in texts[currentLang].nav" :key="item.href" :href="item.href"
        class="relative hover:text-white transition-colors after:content-[''] after:absolute after:-bottom-1 after:left-0 after:w-0 after:h-[2px] after:bg-red-600 hover:after:w-full after:transition-all after:duration-300">
        {{ item.label }}
      </a>
    </nav>

    <div class="hidden md:flex items-center gap-6 text-gray-400">
      <div class="relative flex items-center justify-end">
        <transition name="fade-search">
          <input v-if="isSearchOpen" type="text" :placeholder="texts[currentLang].searchPlaceholder"
            class="absolute right-10 bg-gray-900 border border-gray-800 text-white text-[10px] font-mono rounded-sm px-4 py-2 w-56 outline-none focus:border-red-900/50 transition-all shadow-2xl" />
        </transition>
        <span @click="isSearchOpen = !isSearchOpen" class="material-symbols-outlined cursor-pointer hover:text-white text-[20px]">search</span>
      </div>

      <div class="relative">
        <span @click="isLangOpen = !isLangOpen" class="material-symbols-outlined cursor-pointer hover:text-white text-[20px]">language</span>
        <div v-if="isLangOpen" class="absolute right-0 top-full mt-5 w-32 bg-gray-950 border border-gray-800 rounded-sm shadow-2xl overflow-hidden z-50">
          <button @click="changeLang('ES')" class="block w-full px-4 py-3 text-[10px] font-black hover:bg-red-600 hover:text-white transition-colors text-left border-b border-gray-900 text-gray-400">ESPAÑOL</button>
          <button @click="changeLang('EN')" class="block w-full px-4 py-3 text-[10px] font-black hover:bg-red-600 hover:text-white transition-colors text-left text-gray-400">ENGLISH</button>
        </div>
      </div>
      
      <a href="https://github.com/martincarmna" target="_blank" class="hover:text-white transition-transform hover:scale-110">
        <svg class="w-5 h-5 fill-current" viewBox="0 0 24 24"><path d="M12 0C5.374 0 0 5.373 0 12c0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23A11.509 11.509 0 0 1 12 5.803c1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576C20.566 21.797 24 17.3 24 12c0-6.627-5.373-12-12-12z"/></svg>
      </a>
    </div>

    <button @click="toggleSidebar" class="md:hidden text-gray-400 hover:text-white p-2">
      <span class="material-symbols-outlined text-3xl">menu</span>
    </button>
  </header>

  <transition name="slide">
    <div v-if="isSidebarOpen" class="fixed inset-0 z-[60] flex">
      <div @click="isSidebarOpen = false" class="absolute inset-0 bg-black/90 backdrop-blur-md"></div>
      <aside class="relative w-80 bg-gray-950 h-full border-r border-gray-900 shadow-2xl flex flex-col">
        <div class="flex justify-between items-center px-8 py-6 border-b border-gray-900">
          <h2 class="text-white font-black uppercase italic text-sm tracking-tighter">Marty Carps<span class="text-red-600">.</span></h2>
          <span @click="isSidebarOpen = false" class="material-symbols-outlined text-gray-500 cursor-pointer hover:text-white">close</span>
        </div>
        <nav class="flex flex-col px-4 py-10 gap-2">
          <a v-for="item in texts[currentLang].nav" :key="item.href" :href="item.href" @click="isSidebarOpen = false"
            class="text-gray-400 font-bold uppercase tracking-[0.2em] text-[11px] py-4 px-6 rounded-sm hover:bg-red-600/10 hover:text-white transition-all">
            {{ item.label }}
          </a>
        </nav>
      </aside>
    </div>
  </transition>

  <main>
    <section id="inicio" class="bg-[url('/fondo.gif')] bg-cover bg-center bg-no-repeat h-[90vh] w-full relative flex flex-col items-center justify-center gap-10 px-6">
      <div class="absolute inset-0 bg-gradient-to-b from-black/60 via-black/40 to-gray-950"></div>
      <h1 class="relative text-white text-7xl md:text-9xl font-black uppercase tracking-tighter text-center italic drop-shadow-[0_10px_10px_rgba(0,0,0,0.5)]">
        Marty Carps
      </h1>
      <div class="relative group">
        <div class="absolute -inset-1 bg-gradient-to-r from-red-600 to-blue-600 rounded-full blur opacity-25 group-hover:opacity-50 transition duration-1000"></div>
        <div class="relative inline-flex flex-col sm:flex-row items-center bg-gray-950/80 backdrop-blur-xl border border-white/10 rounded-2xl sm:rounded-full p-2 max-w-sm w-full transition-transform duration-500 hover:scale-105">
          <div class="flex items-center gap-3 px-8 text-gray-300 py-3 sm:py-0">
            <span class="material-symbols-outlined text-red-500">terminal</span>
            <span class="text-xs font-black uppercase tracking-widest">{{ texts[currentLang].hero.title }}</span>
          </div>
          <a href="#proyectos" class="w-full sm:w-auto">
            <button class="w-full flex items-center justify-center gap-3 bg-white text-black font-black py-4 px-12 rounded-xl sm:rounded-full hover:bg-red-600 hover:text-white transition-all duration-300 active:scale-95 shadow-xl">
              <span class="text-[10px] uppercase tracking-[0.2em]">{{ texts[currentLang].hero.button }}</span>
              <span class="material-symbols-outlined text-lg">arrow_right_alt</span>
            </button>
          </a>
        </div>
      </div>
    </section>

    <Git :currentLang="currentLang" />
    <Proyectos id="proyectos" :currentLang="currentLang" />
    <Myself id="about" :currentLang="currentLang" />
    <Magikar id="cv" :currentLang="currentLang" />
  </main>

  <footer class="bg-black text-white py-20 px-8 md:px-24 border-t border-gray-900">
    <div class="max-w-7xl mx-auto grid grid-cols-1 md:grid-cols-2 gap-20">
      <div class="space-y-6">
        <h1 class="text-white text-2xl font-black uppercase italic tracking-tighter">Marty Carps<span class="text-red-600">.</span></h1>
        <p class="text-gray-500 text-sm leading-relaxed max-w-sm font-medium">{{ texts[currentLang].footer.desc }}</p>
      </div>
      <div class="space-y-8">
        <div class="flex items-center gap-4">
          <div class="w-10 h-[1px] bg-red-600"></div>
          <h3 class="text-[10px] font-black uppercase tracking-[0.3em] text-gray-400">Social Hub</h3>
        </div>
        <div class="flex flex-wrap gap-4">
          <a href="https://www.youtube.com/@JossMar_Carmona" target="_blank" class="flex items-center gap-3 bg-gray-900 hover:bg-red-600 border border-gray-800 text-white font-black px-8 py-4 rounded-sm transition-all text-[10px] tracking-widest">
            YOUTUBE
          </a>
          <a href="https://github.com/martincarmna" target="_blank" class="flex items-center gap-3 bg-gray-900 hover:bg-white hover:text-black border border-gray-800 text-white font-black px-8 py-4 rounded-sm transition-all text-[10px] tracking-widest">
            GITHUB
          </a>
        </div>
      </div>
    </div>
    <div class="max-w-7xl mx-auto mt-20 pt-10 border-t border-gray-900 flex flex-col md:flex-row justify-between items-center text-gray-600 text-[9px] font-mono uppercase tracking-[0.3em] gap-6">
      <p>© 2026 — {{ texts[currentLang].footer.madeIn }}</p>
      <p class="hover:text-red-600 cursor-default transition-colors text-gray-800">Design System v2.0</p>
    </div>
  </footer>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;700;900&family=JetBrains+Mono:wght@500&display=swap');

html { scroll-behavior: smooth; font-family: 'Inter', sans-serif; }
section[id] { scroll-margin-top: 100px; }

/* Pokéball Pro Styling */
.pokeball-container { position: relative; width: 60px; height: 60px; }
.pokeball-spinner {
  width: 60px; height: 60px;
  background: #fff; border: 4px solid #000;
  border-radius: 50%; position: relative;
  overflow: hidden; box-shadow: inset -4px -4px 0px rgba(0,0,0,0.1);
  z-index: 2;
}
.pokeball-spinner::before {
  content: ""; position: absolute;
  top: 0; left: 0; width: 100%; height: 50%;
  background: #ef5350; border-bottom: 4px solid #000;
}
.pokeball-spinner::after {
  content: ""; position: absolute;
  top: 50%; left: 50%;
  width: 14px; height: 14px;
  background: #fff; border: 4px solid #000;
  border-radius: 50%; transform: translate(-50%, -50%);
  z-index: 10; animation: buttonPulse 1s infinite;
}
.pokeball-spinner-reflect {
  position: absolute; top: 6px; left: 10px;
  width: 15px; height: 8px;
  background: rgba(255, 255, 255, 0.3);
  border-radius: 50%; z-index: 5; transform: rotate(-15deg);
}
.pokeball-glow {
  position: absolute; top: 50%; left: 50%;
  width: 100px; height: 100px;
  background: radial-gradient(circle, rgba(239, 83, 80, 0.2) 0%, transparent 70%);
  transform: translate(-50%, -50%); border-radius: 50%;
}
.pokeball-catching { animation: shake 1.25s cubic-bezier(.36,.07,.19,.97) infinite; }

/* Animations */
@keyframes shake {
  0%, 100% { transform: rotate(0deg); }
  20% { transform: rotate(-15deg); }
  40% { transform: rotate(15deg); }
  60% { transform: rotate(-10deg); }
  80% { transform: rotate(10deg); }
}
@keyframes buttonPulse {
  0%, 100% { background: #fff; box-shadow: 0 0 0px rgba(0,0,0,0); }
  50% { background: #ff7675; box-shadow: 0 0 10px #ff7675; }
}

.fade-enter-active, .fade-leave-active { transition: opacity 0.8s ease; }
.fade-enter-from, .fade-leave-to { opacity: 0; }
.slide-enter-active, .slide-leave-active { transition: transform 0.5s cubic-bezier(0.4, 0, 0.2, 1); }
.slide-enter-from, .slide-leave-to { transform: translateX(-100%); }
.fade-search-enter-active { animation: search-in 0.3s ease-out; }
@keyframes search-in { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }
</style>