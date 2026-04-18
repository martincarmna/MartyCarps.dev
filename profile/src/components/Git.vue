<script setup lang="ts">
defineProps<{
  currentLang: 'ES' | 'EN'
}>();
</script>

<template>
  <section class="bg-gray-950 border-t border-gray-800 py-24 px-8 md:px-20 w-full">
    <div class="flex flex-col md:flex-row items-center justify-between gap-12 w-full">

      <div class="flex-1 flex flex-col gap-8">
        <div>
          <p class="text-gray-600 text-xs uppercase tracking-[0.4em] font-mono mb-3">
            {{ currentLang === 'ES' ? 'Encuentra mi código' : 'Find my code' }}
          </p>
          <h2 class="text-white text-4xl md:text-6xl font-black uppercase italic tracking-tighter leading-none">
            {{ currentLang === 'ES' ? 'Ver mis' : 'See my' }}<br>
            <span class="text-gray-500">{{ currentLang === 'ES' ? 'repositorios' : 'repositories' }}</span>
          </h2>
        </div>

        <p class="text-gray-500 text-sm leading-relaxed max-w-sm">
          {{ currentLang === 'ES'
            ? 'Todos mis proyectos, experimentos y contribuciones están documentados y disponibles en GitHub.'
            : 'All my projects, experiments and contributions are documented and available on GitHub.' }}
        </p>

        <div class="self-start">
          <a 
            href="https://github.com/martincarmna"
            target="_blank"
            rel="noopener noreferrer"
            class="inline-flex items-center gap-3 bg-white text-black font-black uppercase tracking-widest text-xs px-8 py-4 hover:bg-gray-100 active:scale-95 transition-all"
          >
            <svg class="w-5 h-5 fill-current flex-shrink-0" viewBox="0 0 24 24">
              <path d="M12 0C5.374 0 0 5.373 0 12c0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23A11.509 11.509 0 0 1 12 5.803c1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576C20.566 21.797 24 17.3 24 12c0-6.627-5.373-12-12-12z" />
            </svg>
            {{ currentLang === 'ES' ? 'Ir a GitHub' : 'Go to GitHub' }}
          </a>
        </div>
      </div>

      <div class="hidden md:block w-px self-stretch bg-gray-800"></div>

      <div class="flex-1 flex flex-col gap-10">

        <div class="bg-gray-900 border border-gray-800 rounded-xl p-6 flex items-center gap-6 hover:border-gray-600 transition-colors group">
          <div class="w-16 h-16 bg-gray-800 rounded-full flex items-center justify-center flex-shrink-0 group-hover:bg-gray-700 transition-colors">
            <svg class="w-8 h-8 fill-white" viewBox="0 0 24 24">
              <path d="M12 0C5.374 0 0 5.373 0 12c0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23A11.509 11.509 0 0 1 12 5.803c1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576C20.566 21.797 24 17.3 24 12c0-6.627-5.373-12-12-12z" />
            </svg>
          </div>
          <div>
            <p class="text-white font-bold text-sm">martincarmna</p>
            <p class="text-gray-500 text-xs mt-0.5 font-mono">github.com/martincarmna</p>
            <div class="flex items-center gap-1.5 mt-2">
              <div class="w-2 h-2 bg-green-500 rounded-full"></div>
              <span class="text-green-500 text-[10px] font-mono uppercase tracking-wider">
                {{ currentLang === 'ES' ? 'Activo' : 'Active' }}
              </span>
            </div>
          </div>
        </div>

        <div class="flex flex-col">
          <div v-for="repo in [
            { name: 'rick-and-morty-explorer', tech: 'Vue.js', color: 'bg-yellow-500' },
            { name: 'smyt-depositos', tech: 'Django', color: 'bg-green-500' },
            { name: 'ferreteria-j-pos', tech: 'PostgreSQL', color: 'bg-blue-500' }
          ]" :key="repo.name" class="flex items-center justify-between py-3 border-b border-gray-800">
            <div class="flex items-center gap-3">
              <div :class="['w-1.5 h-1.5 rounded-full', repo.color]"></div>
              <span class="text-gray-300 text-sm font-mono">{{ repo.name }}</span>
            </div>
            <span class="text-gray-600 text-xs font-mono">{{ repo.tech }}</span>
          </div>
        </div>

        <div class="grid grid-cols-3 gap-6 border-t border-gray-800 pt-8">
          <div class="flex flex-col gap-1">
            <span class="text-white text-2xl font-black">3+</span>
            <span class="text-gray-600 text-[10px] uppercase tracking-widest font-mono">
              {{ currentLang === 'ES' ? 'Proyectos' : 'Projects' }}
            </span>
          </div>
          <div class="flex flex-col gap-1">
            <span class="text-white text-2xl font-black">2+</span>
            <span class="text-gray-600 text-[10px] uppercase tracking-widest font-mono">
              {{ currentLang === 'ES' ? 'Años exp.' : 'Years exp.' }}
            </span>
          </div>
          <div class="flex flex-col gap-1">
            <span class="text-white text-2xl font-black">5+</span>
            <span class="text-gray-600 text-[10px] uppercase tracking-widest font-mono">
              {{ currentLang === 'ES' ? 'Tecnologías' : 'Technologies' }}
            </span>
          </div>
        </div>

      </div>
    </div>
  </section>
</template>