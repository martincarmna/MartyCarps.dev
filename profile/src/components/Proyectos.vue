<script setup lang="ts">
import { ref } from 'vue';

// Recibimos el idioma del padre
defineProps<{
  currentLang: 'ES' | 'EN'
}>();

const scrollContainer = ref<HTMLElement | null>(null);

// Diccionario de textos
const texts = {
  ES: {
    title: 'Proyectos',
    subtitle: 'más relevantes',
    desc: 'Explora mi trabajo reciente como desarrollador Fullstack.',
    view: 'VER PROYECTO',
    comingSoon: 'PRÓXIMAMENTE',
    rickDesc: 'Explorador de personajes consumiendo la API oficial.',
    smytDesc: 'Participación en equipo. Sistema 100% funcional para depósitos.',
    ferreDesc: 'Sistema de inventario y ventas para negocio local.',
  },
  EN: {
    title: 'Projects',
    subtitle: 'most relevant',
    desc: 'Explore my recent work as a Fullstack developer.',
    view: 'VIEW PROJECT',
    comingSoon: 'COMING SOON',
    rickDesc: 'Character explorer consuming the official API.',
    smytDesc: 'Team project. 100% functional system for vehicle impounds.',
    ferreDesc: 'Inventory and sales system for local business.',
  }
};

const scroll = (direction: 'left' | 'right') => {
  const container = scrollContainer.value;
  if (!container) return;
  const scrollAmount = 400;
  container.scrollBy({ left: direction === 'left' ? -scrollAmount : scrollAmount, behavior: 'smooth' });
};
</script>

<template>
  <div class="bg-gray-200 min-h-screen p-4 md:p-16 font-sans border-t-8 border-yellow-500">
    
    <header class="flex flex-col md:flex-row md:items-center justify-between mb-12 gap-4 max-w-7xl mx-auto">
      <div>
        <h1 class="text-4xl md:text-6xl font-black text-gray-900 tracking-tighter uppercase italic">
          {{ texts[currentLang].title }} <span class="text-yellow-600">{{ texts[currentLang].subtitle }}</span>
        </h1>
        <p class="text-gray-600 mt-2 font-mono font-bold">{{ texts[currentLang].desc }}</p>
      </div>
      
      <div class="hidden md:flex items-center gap-4">
        <button @click="scroll('left')" class="w-14 h-14 rounded-full border-4 border-gray-400 flex items-center justify-center text-gray-700 hover:bg-yellow-500 hover:border-yellow-600 transition-all shadow-[4px_4px_0px_0px_rgba(0,0,0,0.2)] active:translate-y-1 active:shadow-none">
          <span class="material-symbols-outlined font-bold">arrow_back</span>
        </button>
        <button @click="scroll('right')" class="w-14 h-14 rounded-full bg-yellow-500 border-4 border-yellow-600 flex items-center justify-center text-white hover:bg-yellow-400 transition shadow-[4px_4px_0px_0px_rgba(0,0,0,0.2)] active:translate-y-1 active:shadow-none">
          <span class="material-symbols-outlined font-bold">arrow_forward</span>
        </button>
      </div>
    </header>

    <main 
      ref="scrollContainer"
      class="flex gap-12 overflow-x-auto snap-x snap-mandatory pb-12 no-scrollbar px-4"
    >
      <div class="min-w-[300px] md:min-w-[340px] snap-start mb-4">
        <div class="bg-[#f0d000] rounded-t-lg rounded-b-3xl p-4 shadow-[10px_10px_0px_0px_rgba(0,0,0,0.15)] border-t-2 border-l-2 border-white/30 relative overflow-hidden group">
          <div class="absolute top-0 left-1/2 -translate-x-1/2 w-32 h-6 bg-[#d4b800] rounded-b-xl border-x-2 border-b-2 border-black/10"></div>
          
          <div class="mt-8 bg-gray-300 p-1 border-4 border-black/20 rounded shadow-inner">
            <div class="relative overflow-hidden aspect-square border-2 border-black/10">
              <img src="/image.png" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-700">
              <div class="absolute top-0 left-0 w-full h-full bg-gradient-to-b from-transparent to-black/60"></div>
              <img src="/Pokemon-Logo.png" class="absolute top-2 left-1/2 -translate-x-1/2 w-20 opacity-80" alt="logo">
            </div>
          </div>

          <div class="mt-4 px-2">
            <h3 class="text-xl font-black text-blue-900 uppercase italic leading-none">Rick & Morty</h3>
            <p class="text-[10px] font-bold text-gray-800 mt-2 h-8 line-clamp-2 uppercase leading-tight">{{ texts[currentLang].rickDesc }}</p>
            
            <a href="https://martincarmna.github.io/Rick-and-Morty/" target="_blank" 
               class="mt-4 block w-full text-center py-2 bg-gray-800 text-yellow-400 font-black text-xs rounded hover:bg-black transition-colors border-b-4 border-black/50">
              {{ texts[currentLang].view }}
            </a>
          </div>
          <p class="absolute right-0 top-1/2 -rotate-90 text-[8px] font-bold text-black/30 translate-x-3 italic">THIS SIDE OUT</p>
        </div>
      </div>

      <div class="min-w-[300px] md:min-w-[340px] snap-start">
        <div class="bg-[#f0d000] rounded-t-lg rounded-b-3xl p-4 shadow-[10px_10px_0px_0px_rgba(0,0,0,0.15)] border-t-2 border-l-2 border-white/30 relative overflow-hidden group">
          <div class="absolute top-0 left-1/2 -translate-x-1/2 w-32 h-6 bg-[#d4b800] rounded-b-xl border-x-2 border-b-2 border-black/10"></div>
          
          <div class="mt-8 bg-gray-300 p-1 border-4 border-black/20 rounded shadow-inner">
            <div class="relative overflow-hidden aspect-square border-2 border-black/10">
              <img src="/myst.png" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-700">
              <div class="absolute top-0 left-0 w-full h-full bg-gradient-to-b from-transparent to-red-900/60"></div>
              <div class="absolute top-2 right-2 bg-red-600 text-white text-[8px] px-2 py-1 font-bold rounded italic">TEAM</div>
            </div>
          </div>

          <div class="mt-4 px-2">
            <h3 class="text-xl font-black text-red-800 uppercase italic leading-none">SMyT Depósitos</h3>
            <p class="text-[10px] font-bold text-gray-800 mt-2 h-8 line-clamp-2 uppercase leading-tight">{{ texts[currentLang].smytDesc }}</p>
            
            <a href="https://smytdepositos.netlify.app/" target="_blank" 
               class="mt-4 block w-full text-center py-2 bg-red-700 text-white font-black text-xs rounded hover:bg-red-800 transition-colors border-b-4 border-black/50">
              {{ texts[currentLang].view }}
            </a>
          </div>
          <p class="absolute right-0 top-1/2 -rotate-90 text-[8px] font-bold text-black/30 translate-x-3 italic tracking-widest">DMG-APSE-USA</p>
        </div>
      </div>

      <div class="min-w-[300px] md:min-w-[340px] snap-start opacity-90">
        <div class="bg-[#f0d000] rounded-t-lg rounded-b-3xl p-4 shadow-[10px_10px_0px_0px_rgba(0,0,0,0.15)] border-t-2 border-l-2 border-white/30 relative overflow-hidden group grayscale-[0.5] hover:grayscale-0 transition-all">
          <div class="absolute top-0 left-1/2 -translate-x-1/2 w-32 h-6 bg-[#d4b800] rounded-b-xl border-x-2 border-b-2 border-black/10"></div>
          
          <div class="mt-8 bg-gray-300 p-1 border-4 border-black/20 rounded shadow-inner">
            <div class="relative overflow-hidden aspect-square border-2 border-black/10">
              <img src="/ferret.jpeg" class="w-full h-full object-cover">
              <div class="absolute inset-0 bg-black/40 flex items-center justify-center">
                 <span class="text-white font-black text-xl italic drop-shadow-lg -rotate-12">{{ texts[currentLang].comingSoon }}</span>
              </div>
            </div>
          </div>

          <div class="mt-4 px-2">
            <h3 class="text-xl font-black text-gray-700 uppercase italic leading-none italic">Ferretería J.</h3>
            <p class="text-[10px] font-bold text-gray-800 mt-2 h-8 line-clamp-2 uppercase leading-tight">{{ texts[currentLang].ferreDesc }}</p>
            
            <button disabled class="mt-4 block w-full text-center py-2 bg-gray-400 text-white font-black text-xs rounded border-b-4 border-gray-600 cursor-not-allowed">
              LOCKED
            </button>
          </div>
        </div>
      </div>

    </main>

    <div class="flex justify-center md:hidden gap-2 mt-4">
       <div class="w-8 h-2 bg-yellow-500 rounded-full animate-pulse"></div>
       <div class="w-2 h-2 bg-gray-400 rounded-full"></div>
       <div class="w-2 h-2 bg-gray-400 rounded-full"></div>
    </div>
  </div>
</template>

<style scoped>
.no-scrollbar::-webkit-scrollbar {
  display: none;
}
.no-scrollbar {
  -ms-overflow-style: none;
  scrollbar-width: none;
}

/* Efecto de inclinación para que parezca cartucho real */
.group:hover {
  transform: perspective(1000px) rotateX(2deg);
}
</style>