<script setup lang="ts">
import { ref } from 'vue';

const props = defineProps<{
  currentLang: 'ES' | 'EN'
}>();

const scrollContainer = ref<HTMLElement | null>(null);

const texts = {
  ES: {
    title: 'Proyectos',
    subtitle: 'más relevantes',
    desc: 'Explora mi trabajo reciente como desarrollador Fullstack.',
    view: 'VER PROYECTO',
    comingSoon: 'PRÓXIMAMENTE',
    rickDesc: 'Explorador de personajes dinámico que consume la API oficial de Rick & Morty.',
    smytDesc: 'Desarrollo colaborativo de un sistema integral para depósitos vehiculares, optimizando la gestión y previniendo el robo de autopartes.',
    ferreDesc: 'Sistema de gestión de inventarios y punto de venta (POS) diseñado para optimizar el control financiero y flujo de stock.',
    ssacDesc: 'Sistema de Solicitud y Atención Ciudadana desarrollado localmente como propuesta para un ayuntamiento. Se mantiene como un prototipo funcional no implementado.'
  },
  EN: {
    title: 'Projects',
    subtitle: 'most relevant',
    desc: 'Explore my recent work as a Fullstack Developer.',
    view: 'VIEW PROJECT',
    comingSoon: 'COMING SOON',
    rickDesc: 'Dynamic character explorer leveraging the official Rick & Morty API.',
    smytDesc: 'Team-based development of a full-scale vehicle impound system, designed to streamline management and prevent auto-part theft.',
    ferreDesc: 'Inventory and Sales (POS) system for local businesses, focused on optimizing financial tracking and stock management.',
    ssacDesc: 'Citizen Request and Attention System developed locally as a town hall proposal. It remains a functional, non-implemented prototype.'
  }
};

const scroll = (direction: 'left' | 'right') => {
  const container = scrollContainer.value;
  if (!container) return;
  const cardWidth = container.querySelector('div')?.clientWidth || 400;
  const gap = 32; 
  const scrollAmount = cardWidth + gap;
  
  container.scrollBy({ 
    left: direction === 'left' ? -scrollAmount : scrollAmount, 
    behavior: 'smooth' 
  });
};
</script>

<template>
  <div class="bg-slate-950 min-h-screen p-4 md:p-16 font-sans border-t-2 border-gray-800">
    
    <header class="flex flex-col md:flex-row md:items-center justify-between mb-12 gap-4 max-w-7xl mx-auto">
      <div>
        <h1 class="text-4xl md:text-6xl font-black text-white tracking-tighter uppercase italic">
          {{ texts[currentLang].title }} <span class="text-yellow-600">{{ texts[currentLang].subtitle }}</span>
        </h1>
        <p class="text-gray-500 mt-2 font-mono text-sm">{{ texts[currentLang].desc }}</p>
      </div>
      
      <div class="hidden md:flex items-center gap-3">
        <button 
          @click="scroll('left')" 
          aria-label="Scroll left"
          class="w-12 h-12 rounded-full border-2 border-gray-300 flex items-center justify-center text-gray-600 hover:bg-gray-200 active:scale-90 transition-all"
        >
          <span class="material-symbols-outlined">arrow_back</span>
        </button>
        <button 
          @click="scroll('right')" 
          aria-label="Scroll right"
          class="w-12 h-12 rounded-full bg-gray-800 flex items-center justify-center text-white hover:bg-gray-700 active:scale-90 transition-all"
        >
          <span class="material-symbols-outlined">arrow_forward</span>
        </button>
      </div>
    </header>

    <main 
      ref="scrollContainer" 
      class="flex gap-8 overflow-x-auto snap-x snap-mandatory pb-12 no-scrollbar px-2 items-stretch"
    >
      
      <div class="min-w-[280px] md:min-w-[320px] snap-start flex">
        <div class="bg-[#e8e0c8] rounded-2xl p-4 shadow-md border border-gray-300 relative overflow-hidden group flex flex-col w-full hover:shadow-xl transition-all duration-300">
          <div class="absolute top-0 left-1/2 -translate-x-1/2 w-24 h-4 bg-[#d4ccb0] rounded-b-lg"></div>
          <div class="mt-6 bg-gray-400/30 p-1 border-2 border-gray-400/40 rounded">
            <div class="relative overflow-hidden aspect-square rounded-sm">
              <img src="/image.png" alt="Rick and Morty Project" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-700">
              <div class="absolute inset-0 bg-gradient-to-b from-transparent to-black/40"></div>
            </div>
          </div>
          <div class="mt-4 px-1 flex flex-col flex-grow">
            <h3 class="text-lg font-black text-gray-800 uppercase italic">Rick & Morty</h3>
            <p class="text-[10px] font-bold text-gray-600 mt-2 h-14 line-clamp-4 uppercase leading-tight tracking-wide">
              {{ texts[currentLang].rickDesc }}
            </p>
            <a href="https://martincarmna.github.io/Rick-and-Morty/" target="_blank" rel="noopener noreferrer" class="mt-auto block w-full text-center py-2 bg-gray-800 text-white font-black text-xs rounded hover:bg-black transition-colors">
              {{ texts[currentLang].view }}
            </a>
          </div>
        </div>
      </div>

      <div class="min-w-[280px] md:min-w-[320px] snap-start flex">
        <div class="bg-[#e8e0c8] rounded-2xl p-4 shadow-md border border-gray-300 relative overflow-hidden group flex flex-col w-full hover:shadow-xl transition-all duration-300">
          <div class="absolute top-0 left-1/2 -translate-x-1/2 w-24 h-4 bg-[#d4ccb0] rounded-b-lg"></div>
          <div class="mt-6 bg-gray-400/30 p-1 border-2 border-gray-400/40 rounded">
            <div class="relative overflow-hidden aspect-square rounded-sm">
              <img src="/myst.png" alt="SMyT Project" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-700">
              <div class="absolute top-2 right-2 bg-red-600 text-white text-[7px] px-2 py-0.5 font-bold rounded-sm uppercase">Gobierno</div>
            </div>
          </div>
          <div class="mt-4 px-1 flex flex-col flex-grow">
            <h3 class="text-lg font-black text-gray-800 uppercase italic">SMyT Depósitos</h3>
            <p class="text-[10px] font-bold text-gray-600 mt-2 h-14 line-clamp-4 uppercase leading-tight tracking-wide">
              {{ texts[currentLang].smytDesc }}
            </p>
            <a href="https://smytdepositos.netlify.app/" target="_blank" rel="noopener noreferrer" class="mt-auto block w-full text-center py-2 bg-red-700 text-white font-black text-xs rounded hover:bg-red-800 transition-colors">
              {{ texts[currentLang].view }}
            </a>
          </div>
        </div>
      </div>

      <div class="min-w-[280px] md:min-w-[320px] snap-start flex">
        <div class="bg-[#e8e0c8] rounded-2xl p-4 shadow-md border border-gray-300 relative overflow-hidden group flex flex-col w-full opacity-80 hover:opacity-100 transition-all">
          <div class="absolute top-0 left-1/2 -translate-x-1/2 w-24 h-4 bg-[#d4ccb0] rounded-b-lg"></div>
          <div class="mt-6 bg-gray-400/30 p-1 border-2 border-gray-400/40 rounded">
            <div class="relative overflow-hidden aspect-square rounded-sm">
              <img src="/ferret.jpeg" alt="Ferretería Project" class="w-full h-full object-cover grayscale opacity-50">
              <div class="absolute inset-0 bg-black/60 flex items-center justify-center">
                <span class="text-white font-black text-lg italic -rotate-12 border-2 border-white px-2 py-1 tracking-tighter">{{ texts[currentLang].comingSoon }}</span>
              </div>
            </div>
          </div>
          <div class="mt-4 px-1 flex flex-col flex-grow">
            <h3 class="text-lg font-black text-gray-500 uppercase italic">Ferretería J.</h3>
            <p class="text-[10px] font-bold text-gray-500 mt-2 h-14 line-clamp-4 uppercase leading-tight tracking-wide">
              {{ texts[currentLang].ferreDesc }}
            </p>
            <button disabled class="mt-auto block w-full text-center py-2 bg-gray-300 text-gray-500 font-black text-xs rounded cursor-not-allowed uppercase tracking-widest">
              {{ currentLang === 'ES' ? 'BLOQUEADO' : 'LOCKED' }}
            </button>
          </div>
        </div>
      </div>

      <div class="min-w-[280px] md:min-w-[320px] snap-start flex">
        <div class="bg-[#e8e0c8] rounded-2xl p-4 shadow-md border border-gray-300 relative group flex flex-col w-full opacity-80 hover:opacity-100 transition-all">
          <div class="absolute top-0 left-1/2 -translate-x-1/2 w-24 h-4 bg-[#d4ccb0] rounded-b-lg"></div>
          <div class="mt-6 bg-gray-400/30 p-1 border-2 border-gray-400/40 rounded">
            <div class="relative overflow-hidden aspect-square rounded-sm">
              <img src="/ssac.png" alt="SSAC Project" class="w-full h-full object-cover grayscale opacity-50 bg-white">
              <div class="absolute inset-0 bg-black/40 flex items-center justify-center text-center px-4">
                 <span class="text-white font-black text-[10px] uppercase border border-white px-2 py-1">{{ currentLang === 'ES' ? 'PROYECTO LOCAL' : 'LOCAL PROJECT' }}</span>
              </div>
            </div>
          </div>
          <div class="mt-4 px-1 flex flex-col flex-grow">
            <h3 class="text-lg font-black text-gray-500 uppercase italic">SSAC</h3>
            <p class="text-[10px] font-bold text-gray-500 mt-2 h-14 line-clamp-4 uppercase leading-tight tracking-wide italic">
              {{ texts[currentLang].ssacDesc }}
            </p>
            <button disabled class="mt-auto block w-full text-center py-2 bg-gray-300 text-gray-500 font-black text-xs rounded cursor-not-allowed uppercase tracking-widest">
              {{ currentLang === 'ES' ? 'ESTADO: PROPUESTA' : 'STATUS: PROPOSAL' }}
            </button>
          </div>
        </div>
      </div>

    </main>
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

.group {
  transition: transform 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
}
.group:hover {
  transform: perspective(1000px) rotateX(4deg) translateY(-5px);
}
</style>