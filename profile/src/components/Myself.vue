<script setup lang="ts">
// Recibimos el idioma actual desde el componente principal
defineProps<{
  currentLang: 'ES' | 'EN'
}>();

// Diccionario de textos para la sección "Sobre mí"
const texts = {
  ES: {
    pokedexEntry: 'Entrada Pokédex: No. 001 - Marty',
    title: 'INFO DESARROLLADOR',
    role: 'Desarrolador de Software Multiplataforma Front-end / Full-stack',
    description: `¡Qué tal! Soy alguien que cree firmemente en dejar un sello personal en cada proyecto que toco. Para mí, programar no es solo escribir líneas de código; es una extensión de mi proceso creativo.

Soy un apasionado total del arte y la música. Cuando no estoy frente al monitor, probablemente me encuentres con una guitarra en las manos, dibujando algo nuevo o editando tutoriales para compartir lo que sé con los demás. Siento que esa chispa artística es, precisamente, lo que alimenta mi visión como desarrollador.

En el mundo tecnológico, mi enfoque principal es el Frontend. Me fascina ese momento mágico donde lo visual cobra vida y la interfaz se vuelve una experiencia real para el usuario. Sin embargo, no me quedo solo en la superficie: mantengo un dominio sólido del Backend, lo que me permite construir estructuras robustas que soporten toda esa creatividad visual.

Básicamente, soy un desarrollador que disfruta fusionar la técnica con la estética para crear algo único.`,
    statsTitle: 'Habilidades Base',
    toolsTitle: 'Herramientas de Combate'
  },
  EN: {
    pokedexEntry: 'Pokédex Entry: No. 001 - Marty',
    title: 'DEVELOPER INFO',
    role: 'Class: Front-end / Full-stack',
    description: `I truly enjoy leaving my personal stamp on everything I do. For me, coding is more than just logic—it’s an extension of my creative process.

I am deeply passionate about art and music; whether I’m playing the guitar, sketching, or sharing tutorials, I’m always looking for ways to express myself. This creative spark is exactly what drives my focus toward Frontend development, where I love seeing the visual aspects of a project come to life.

However, I don't just stay on the surface—I maintain a solid mastery of the Backend, ensuring that every beautiful interface is supported by a robust and efficient structure. I bridge the gap between aesthetics and functionality to create digital experiences that truly resonate.`,
    statsTitle: 'Base Stats',
    toolsTitle: 'Combat Tools'
  }
};

// URLs de los logos (CDN)
const logos = {
  vue: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vuejs/vuejs-original.svg',
  django: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/django/django-plain.svg',
  mysql: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg',
  postgresql: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/postgresql/postgresql-original.svg',
  mongodb: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mongodb/mongodb-original.svg'
};
</script>

<template>
  <div class="bg-[url('/pokedex_kalos_bg.png')] bg-cover bg-center min-h-screen p-4 md:p-8 font-mono border-t-4 border-blue-900">
    
    <div class="bg-black/70 border-2 border-blue-400 p-3 mb-8 rounded-t-lg max-w-6xl mx-auto flex justify-between items-center shadow-[0_0_15px_rgba(0,163,255,0.5)]">
      <h2 class="text-blue-300 text-sm md:text-base tracking-widest uppercase animate-pulse">
        {{ texts[currentLang].pokedexEntry }}
      </h2>
      <div class="flex gap-2">
        <div class="w-3 h-3 bg-red-600 rounded-full border border-red-900 shadow-[0_0_5px_rgba(255,0,0,0.8)]"></div>
        <div class="w-3 h-3 bg-yellow-500 rounded-full border border-yellow-800 shadow-[0_0_5px_rgba(255,255,0,0.8)]"></div>
        <div class="w-3 h-3 bg-green-600 rounded-full border border-green-900 shadow-[0_0_5px_rgba(0,255,0,0.8)]"></div>
      </div>
    </div>

    <h1 class="text-4xl md:text-5xl font-extrabold mb-10 text-center text-white tracking-tighter drop-shadow-[0_2px_2px_rgba(0,163,255,0.8)] uppercase">
      {{ texts[currentLang].title }}
    </h1>

    <main class="flex flex-wrap lg:flex-nowrap gap-8 max-w-6xl mx-auto">
      
      <div class="bg-black/60 border-2 border-blue-500 shadow-[0_0_20px_rgba(0,163,255,0.3)] rounded-xl p-6 md:p-8 flex-1 transform transition-all hover:border-blue-300 hover:shadow-[0_0_30px_rgba(0,163,255,0.6)]">
        <div class="flex flex-col sm:flex-row items-center gap-6 mb-6 bg-blue-950/40 p-5 rounded-lg border border-blue-700">
          <img src="/perfil.jpg" class="w-28 h-28 rounded-full object-cover border-4 border-blue-400 shadow-[0_0_10px_rgba(0,163,255,0.7)]" alt="Avatar">
          <div class="text-center sm:text-left">
            <h3 class="text-2xl font-bold text-white tracking-tight">Jose Martin Carmona Palestina</h3>
            <h4 class="text-blue-300 font-medium text-lg mt-1">{{ texts[currentLang].role }}</h4>
          </div>
        </div>
        
        <div class="text-gray-200 leading-relaxed text-base bg-black/40 p-5 rounded-lg border border-gray-700 space-y-3">
          <p>{{ texts[currentLang].description }}</p>
        </div>
      </div>

      <div class="bg-black/70 border-2 border-blue-500 p-8 rounded-xl w-full lg:w-1/3 shadow-[0_0_20px_rgba(0,163,255,0.3)] transform transition-all hover:border-blue-300 hover:shadow-[0_0_30px_rgba(0,163,255,0.6)]">
        <h2 class="text-2xl font-bold mb-6 text-white text-center border-b-2 border-blue-500 pb-3 uppercase tracking-wider">
          {{ texts[currentLang].toolsTitle }}
        </h2>
        
        <div class="space-y-5">
          <section class="flex items-center gap-4 bg-blue-950/50 p-4 rounded-lg border border-blue-700 hover:bg-blue-900/60 transition-colors shadow-inner group">
            <img :src="logos.vue" alt="Vue" class="w-10 h-10 transition-transform group-hover:scale-110">
            <p class="font-bold text-xl text-white">Vue.js</p>
          </section>
          
          <section class="flex items-center gap-4 bg-blue-950/50 p-4 rounded-lg border border-blue-700 hover:bg-blue-900/60 transition-colors shadow-inner group">
            <img :src="logos.django" alt="Django" class="w-10 h-10 transition-transform group-hover:scale-110">
            <p class="font-bold text-xl text-white">Django & DRF</p>
          </section>

          <section class="bg-blue-950/50 p-4 rounded-lg border border-blue-700 hover:bg-blue-900/60 transition-colors shadow-inner">
            <div class="flex items-center gap-4 mb-4">
               <p class="font-bold text-xl text-white">Databases</p>
            </div>
            <div class="flex gap-5 justify-around bg-black/40 p-3 rounded border border-gray-700">
              <img :src="logos.mysql" title="MySQL" class="w-9 h-9 opacity-90 hover:opacity-100 hover:scale-110 transition-transform">
              <img :src="logos.postgresql" title="PostgreSQL" class="w-9 h-9 opacity-90 hover:opacity-100 hover:scale-110 transition-transform">
              <img :src="logos.mongodb" title="MongoDB" class="w-9 h-9 opacity-90 hover:opacity-100 hover:scale-110 transition-transform">
            </div>
          </section>
        </div>
      </div>
    </main>

    <div class="flex justify-center mt-12 relative">
      <div class="absolute inset-0 bg-blue-500/20 blur-xl rounded-full transform scale-150"></div>
      <img src="/team.png" alt="equipo" class="w-72 h-auto opacity-90 hover:opacity-100 transition transform hover:scale-110 relative z-10 drop-shadow-[0_0_10px_rgba(0,163,255,0.8)]">
    </div>
  </div>
</template>

<style scoped>
/* Importamos una fuente monoespaciada para el look Pokedex si no está global */
@import url('https://fonts.googleapis.com/css2?family=Roboto+Mono:wght@400;700&display=swap');

.font-mono {
  font-family: 'Roboto Mono', monospace;
}
</style>