<script setup lang="ts">
defineProps<{
  currentLang: 'ES' | 'EN'
}>();

const repos = [
  { 
    name: 'smyt-depositos-control', 
    tech: 'Django / DRF / Vue.js', 
    color: 'bg-emerald-500', // Color oficial Django
    url: 'https://github.com/martincarmna' 
  },
  { 
    name: 'ferreteria-juquilita-pos', 
    tech: 'Vue.js / PSQL', 
    color: 'bg-sky-500', // Color Vue/React
    url: 'https://github.com/martincarmna' 
  },
  { 
    name: 'rick-and-morty-wiki', 
    tech: 'JavaScript / HTML', 
    color: 'bg-blue-600', // Color TypeScript
    url: 'https://github.com/martincarmna' 
  }
];
</script>

<template>
  <section class="bg-gray-950 border-t border-gray-900 py-24 px-8 md:px-20 w-full">
    <div class="flex flex-col md:flex-row items-center justify-between gap-16 max-w-7xl mx-auto">

      <div class="flex-1 flex flex-col gap-8">
        <div>
          <p class="text-red-600 text-[10px] uppercase tracking-[0.5em] font-black mb-4">
            {{ currentLang === 'ES' ? 'Código Fuente' : 'Source Code' }}
          </p>
          <h2 class="text-white text-5xl md:text-7xl font-black uppercase italic tracking-tighter leading-[0.9]">
            {{ currentLang === 'ES' ? 'Explora mi' : 'Explore my' }}<br>
            <span class="text-gray-800 outline-text">{{ currentLang === 'ES' ? 'ecosistema' : 'ecosystem' }}</span>
          </h2>
        </div>

        <p class="text-gray-500 text-sm leading-relaxed max-w-sm font-medium">
          {{ currentLang === 'ES'
            ? 'Desde sistemas de gestión gubernamental hasta arquitecturas escalables en la nube. Todo mi progreso vive aquí.'
            : 'From government management systems to scalable cloud architectures. All my progress lives here.' }}
        </p>

        <div class="self-start group">
          <a 
            href="https://github.com/martincarmna"
            target="_blank"
            rel="noopener noreferrer"
            class="inline-flex items-center gap-4 bg-white text-black font-black uppercase tracking-[0.2em] text-[10px] px-10 py-5 hover:bg-red-600 hover:text-white active:scale-95 transition-all duration-300 shadow-xl shadow-white/5"
          >
            <svg class="w-5 h-5 fill-current flex-shrink-0" viewBox="0 0 24 24">
              <path d="M12 0C5.374 0 0 5.373 0 12c0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23A11.509 11.509 0 0 1 12 5.803c1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576C20.566 21.797 24 17.3 24 12c0-6.627-5.373-12-12-12z" />
            </svg>
            {{ currentLang === 'ES' ? 'VER GITHUB' : 'VIEW GITHUB' }}
          </a>
        </div>
      </div>

      <div class="hidden lg:block w-px h-64 bg-gradient-to-b from-transparent via-gray-800 to-transparent"></div>

      <div class="flex-1 w-full flex flex-col gap-8">
        
        <div class="bg-gray-900/40 backdrop-blur-sm border border-gray-900 p-6 flex items-center gap-6 hover:border-red-900/30 transition-all group rounded-sm">
          <div class="w-14 h-14 bg-gray-800 border border-gray-700 rounded-full flex items-center justify-center flex-shrink-0 group-hover:scale-110 group-hover:bg-gray-700 transition-all duration-500">
            <svg class="w-7 h-7 fill-white" viewBox="0 0 24 24">
              <path d="M12 0C5.374 0 0 5.373 0 12c0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23A11.509 11.509 0 0 1 12 5.803c1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576C20.566 21.797 24 17.3 24 12c0-6.627-5.373-12-12-12z" />
            </svg>
          </div>
          <div>
            <p class="text-white font-black text-xs tracking-widest">martincarmna</p>
            <p class="text-gray-600 text-[10px] mt-1 font-mono italic">github.com/martincarmna</p>
            <div class="flex items-center gap-2 mt-3">
              <span class="relative flex h-2 w-2">
                <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-emerald-400 opacity-75"></span>
                <span class="relative inline-flex rounded-full h-2 w-2 bg-emerald-500"></span>
              </span>
              <span class="text-emerald-500 text-[9px] font-black uppercase tracking-tighter">
                {{ currentLang === 'ES' ? 'Sincronizado' : 'Synced' }}
              </span>
            </div>
          </div>
        </div>

        <div class="flex flex-col border-y border-gray-900">
          <a v-for="repo in repos" :key="repo.name" :href="repo.url" target="_blank" 
            class="flex items-center justify-between py-5 border-b border-gray-900 last:border-0 group/item hover:px-2 transition-all duration-300">
            <div class="flex items-center gap-4">
              <div :class="['w-1 h-4 rounded-full transition-all group-hover/item:h-6', repo.color]"></div>
              <span class="text-gray-300 text-[11px] font-mono group-hover/item:text-white transition-colors">{{ repo.name }}</span>
            </div>
            <span class="text-gray-700 text-[9px] font-black uppercase tracking-widest group-hover/item:text-red-600 transition-colors">
              {{ repo.tech }}
            </span>
          </a>
        </div>

        <div class="grid grid-cols-3 gap-8 pt-4">
          <div class="space-y-1">
            <span class="text-white text-3xl font-black italic tracking-tighter italic block">10+</span>
            <span class="text-gray-700 text-[9px] uppercase font-black tracking-widest leading-none block">
              {{ currentLang === 'ES' ? 'Repositorios' : 'Repositories' }}
            </span>
          </div>
          <div class="space-y-1">
            <span class="text-white text-3xl font-black italic tracking-tighter italic block">2026</span>
            <span class="text-gray-700 text-[9px] uppercase font-black tracking-widest leading-none block">
              {{ currentLang === 'ES' ? 'Activo' : 'Active Year' }}
            </span>
          </div>
          <div class="space-y-1">
            <span class="text-white text-3xl font-black italic tracking-tighter italic block">ONLINE</span>
            <span class="text-gray-700 text-[9px] uppercase font-black tracking-widest leading-none block">
              {{ currentLang === 'ES' ? 'Jugador' : 'Player' }}
            </span>
          </div>
        </div>

      </div>
    </div>
  </section>
</template>

<style scoped>
.outline-text {
  -webkit-text-stroke: 1px #1f2937;
  color: transparent;
}
</style>