<script setup lang="ts">
// Recibimos el idioma actual desde el componente principal
defineProps<{
  currentLang: 'ES' | 'EN'
}>();

// Diccionario de textos
const texts = {
  ES: {
    pokedexEntry: 'Entrada Pokédex: No. 001 - Marty',
    title: 'INFO DESARROLLADOR',
    role: 'Desarrollador de Software Multiplataforma Full-stack',
    description: `Desarrollador Full-Stack con experiencia construyendo aplicaciones completas, desde la interfaz hasta la lógica de negocio y base de datos. Me apasiona crear soluciones funcionales, escalables y bien estructuradas, combinando lógica, creatividad y atención al detalle.`,
    statsTitle: 'Habilidades Base',
    toolsTitle: 'Herramientas de Combate'
  },
  EN: {
    pokedexEntry: 'Pokédex Entry: No. 001 - Marty',
    title: 'DEVELOPER INFO',
    role: 'Full-Stack Multiplatform Software Developer',
    description: `Full-Stack Developer with experience building complete applications, from the interface to the business logic and database. I am passionate about creating functional, scalable, and well-structured solutions, combining logic, creativity, and attention to detail.`,
    statsTitle: 'Base Stats',
    toolsTitle: 'Combat Tools'
  }
};

// URLs oficiales de los logos (SVGs de alta calidad vía DevIcon)
const logos = {
  vue: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vuejs/vuejs-original.svg',
  django: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/django/django-plain.svg',
  python: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg',
  js: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg',
  tailwind: 'https://www.vectorlogo.zone/logos/tailwindcss/tailwindcss-icon.svg',
  html: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg',
  css: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg',
  mysql: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg',
  postgresql: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/postgresql/postgresql-original.svg',
  mongodb: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mongodb/mongodb-original.svg'
};
</script>

<template>
  <div class="bg-gray-950 min-h-screen p-4 md:p-8 font-mono border-t border-gray-800">
    
    <div class="bg-gray-900 border border-gray-700 p-3 mb-8 rounded-lg max-w-6xl mx-auto flex justify-between items-center shadow-lg">
      <h2 class="text-blue-400 text-sm tracking-widest uppercase">
        {{ texts[currentLang].pokedexEntry }}
      </h2>
      <div class="flex gap-2">
        <div class="w-3 h-3 bg-red-500 rounded-full animate-pulse"></div>
        <div class="w-3 h-3 bg-yellow-400 rounded-full"></div>
        <div class="w-3 h-3 bg-green-500 rounded-full"></div>
      </div>
    </div>

    <h1 class="text-3xl md:text-4xl font-extrabold mb-10 text-center text-white tracking-tighter uppercase">
      {{ texts[currentLang].title }}
    </h1>

    <main class="flex flex-wrap lg:flex-nowrap gap-6 max-w-6xl mx-auto items-start">
      
      <div class="bg-gray-900 border border-gray-700 rounded-xl p-6 md:p-8 flex-1 hover:border-gray-500 transition-colors shadow-2xl">
        <div class="flex flex-col sm:flex-row items-center gap-6 mb-6 bg-gray-800 p-5 rounded-lg border border-gray-700">
          <img src="/perfil.jpg" class="w-24 h-24 rounded-full object-cover border-2 border-blue-400" alt="Avatar">
          <div class="text-center sm:text-left">
            <h3 class="text-xl font-bold text-white tracking-tight">Jose Martin Carmona Palestina</h3>
            <h4 class="text-blue-400 text-sm mt-1">{{ texts[currentLang].role }}</h4>
          </div>
        </div>
        <div class="text-gray-300 leading-relaxed text-sm bg-gray-800/50 p-5 rounded-lg border border-gray-700">
          <p>{{ texts[currentLang].description }}</p>
        </div>
      </div>

      <div class="world-container relative w-full lg:w-1/2 h-[500px] flex items-center justify-center">
        <div class="floating-world relative w-[400px] h-[250px]">
          
          <div class="island-layer bg-gray-900 shadow-2xl translate-z-[-20px] border-b-8 border-gray-950"></div>
          <div class="island-layer bg-gray-800/80 translate-z-[-10px] backdrop-blur-sm border border-gray-700/50"></div>
          
          <div class="island-layer bg-gray-800 border border-gray-700 p-4 flex flex-col justify-between overflow-hidden">
            <h2 class="text-[10px] font-black text-gray-400 text-center border-b border-gray-700 pb-2 uppercase tracking-[0.4em] translate-z-[10px]">
              {{ texts[currentLang].toolsTitle }}
            </h2>
            <div class="h-16 w-full bg-black/40 rounded-full border border-gray-900/50 translate-z-[5px]"></div>
          </div>

          <div class="tech-island absolute -top-12 left-5 group" style="animation: bob 4s ease-in-out infinite;">
            <span class="tooltip">Vue.js</span>
            <img :src="logos.vue" class="w-14 h-14 drop-shadow-[0_0_10px_rgba(65,184,131,0.5)]">
            <div class="w-10 h-3 bg-emerald-950/50 mx-auto rounded-t-lg mt-1"></div>
          </div>

          <div class="tech-island absolute -top-20 right-10 group" style="animation: bob 4.5s ease-in-out infinite 0.5s;">
            <span class="tooltip">Django</span>
            <img :src="logos.django" class="w-12 h-12 brightness-0 invert opacity-80 group-hover:opacity-100">
            <div class="w-8 h-6 bg-gray-900 mx-auto rounded-t-sm mt-1 border-t border-gray-700"></div>
          </div>

          <div class="tech-island absolute bottom-10 -left-8 group" style="animation: bob 5s ease-in-out infinite 1s;">
            <span class="tooltip">Python</span>
            <img :src="logos.python" class="w-10 h-10">
          </div>

          <div class="tech-island absolute bottom-2 left-1/4 group" style="animation: bob 3.5s ease-in-out infinite 1.5s;">
            <span class="tooltip">JavaScript</span>
            <img :src="logos.js" class="w-9 h-9 rounded-sm shadow-lg">
          </div>

          <div class="tech-island absolute top-10 left-1/2 -translate-x-1/2 group" style="animation: bob 6s ease-in-out infinite;">
            <span class="tooltip">Tailwind</span>
            <img :src="logos.tailwind" class="w-14 h-14">
          </div>

          <div class="tech-island absolute top-1/2 -right-6 -translate-y-1/2 flex flex-col gap-1 group" style="animation: bob 4s ease-in-out infinite 2s;">
            <span class="tooltip">HTML5 & CSS3</span>
            <img :src="logos.html" class="w-8 h-8 opacity-90">
            <img :src="logos.css" class="w-8 h-8 opacity-90">
          </div>

          <div class="absolute bottom-4 left-1/2 -translate-x-1/2 w-3/4 flex justify-around items-center translate-z-[15px]">
            <p class="absolute -top-6 text-[8px] font-black text-gray-600 uppercase tracking-widest">Databases</p>
            
            <div class="group cursor-help" style="animation: slowSpin 8s linear infinite;">
              <img :src="logos.mysql" class="w-8 h-8 group-hover:scale-125 transition-transform">
            </div>

            <div class="group cursor-help" style="animation: slowSpin 10s linear infinite reverse;">
              <img :src="logos.postgresql" class="w-8 h-8 group-hover:scale-125 transition-transform">
            </div>

            <div class="group cursor-help" style="animation: slowSpin 9s linear infinite 1s;">
              <img :src="logos.mongodb" class="w-8 h-8 group-hover:scale-125 transition-transform">
            </div>
          </div>

        </div>

        <div class="absolute inset-0 z-[-1] overflow-hidden pointer-events-none">
          <div class="absolute w-1 h-1 bg-blue-500 rounded-full top-1/4 left-1/4 opacity-30 animate-ping"></div>
          <div class="absolute w-1 h-1 bg-emerald-500 rounded-full bottom-1/4 right-1/4 opacity-20 animate-ping delay-700"></div>
        </div>
      </div>

    </main>
  </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Roboto+Mono:wght@400;700&display=swap');

.font-mono { font-family: 'Roboto Mono', monospace; }

/* 3D World Setup */
.world-container { perspective: 1200px; }

.floating-world {
  transform-style: preserve-3d;
  transform: rotateX(20deg) rotateY(-15deg);
  animation: float-island 8s ease-in-out infinite;
}

.island-layer {
  position: absolute;
  width: 100%;
  height: 100%;
  border-radius: 40px;
  transform-style: preserve-3d;
}

/* Animaciones */
@keyframes float-island {
  0%, 100% { transform: translateY(0px) rotateX(20deg) rotateY(-15deg); }
  50% { transform: translateY(-15px) rotateX(22deg) rotateY(-12deg); }
}

@keyframes bob {
  0%, 100% { transform: translateY(0px) scale(1); }
  50% { transform: translateY(-12px) scale(1.05); }
}

@keyframes slowSpin {
  from { transform: rotateY(0deg); }
  to { transform: rotateY(360deg); }
}

/* Tooltips */
.tech-island { position: absolute; transition: all 0.3s ease; }
.tech-island .tooltip {
  visibility: hidden;
  background: #111827;
  color: #60a5fa;
  border: 1px solid #1f2937;
  padding: 4px 8px;
  border-radius: 4px;
  position: absolute;
  bottom: 110%;
  left: 50%;
  transform: translateX(-50%);
  font-size: 9px;
  white-space: nowrap;
  opacity: 0;
  transition: opacity 0.3s ease;
  z-index: 50;
}
.tech-island:hover .tooltip {
  visibility: visible;
  opacity: 1;
}
</style>