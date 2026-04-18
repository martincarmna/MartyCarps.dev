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
    role: 'Desarrolador de Software Multiplataforma Full-stack',
    description: `Desarrollador Full-Stack con experiencia construyendo aplicaciones 
completas, desde la interfaz hasta la lógica de negocio y base de datos. 
Me apasiona crear soluciones funcionales, escalables y bien estructuradas, 
combinando lógica, creatividad y atención al detalle.`,
    statsTitle: 'Habilidades Base',
    toolsTitle: 'Herramientas de Combate'
  },
  EN: {
    pokedexEntry: 'Pokédex Entry: No. 001 - Marty',
    title: 'DEVELOPER INFO',
    role: 'Full-Stack Multiplatform Software Developer',
    description: `Full-Stack Developer with experience building complete 
    applications, from the interface to the business logic and database. I am passionate about creating functional, 
    scalable, and well-structured solutions, combining logic, creativity, and attention to detail.`,
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
  <div class="bg-gray-950 min-h-screen p-4 md:p-8 font-mono border-t border-gray-800">

    <!-- Barra Pokédex sin glow agresivo -->
    <div class="bg-gray-900 border border-gray-700 p-3 mb-8 rounded-lg max-w-6xl mx-auto flex justify-between items-center">
      <h2 class="text-blue-400 text-sm tracking-widest uppercase">
        {{ texts[currentLang].pokedexEntry }}
      </h2>
      <div class="flex gap-2">
        <div class="w-3 h-3 bg-red-500 rounded-full"></div>
        <div class="w-3 h-3 bg-yellow-400 rounded-full"></div>
        <div class="w-3 h-3 bg-green-500 rounded-full"></div>
      </div>
    </div>

    <!-- Título sin drop-shadow neon -->
    <h1 class="text-3xl md:text-4xl font-extrabold mb-10 text-center text-white tracking-tighter uppercase">
      {{ texts[currentLang].title }}
    </h1>

    <main class="flex flex-wrap lg:flex-nowrap gap-6 max-w-6xl mx-auto">

      <!-- Card info -->
      <div class="bg-gray-900 border border-gray-700 rounded-xl p-6 md:p-8 flex-1 hover:border-gray-500 transition-colors">
        
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

      <!-- Card herramientas -->
      <div class="bg-gray-900 border border-gray-700 p-6 rounded-xl w-full lg:w-1/3 hover:border-gray-500 transition-colors">
        <h2 class="text-lg font-bold mb-6 text-white text-center border-b border-gray-700 pb-3 uppercase tracking-wider">
          {{ texts[currentLang].toolsTitle }}
        </h2>

        <div class="space-y-3">
          <div class="flex items-center gap-4 bg-gray-800 p-4 rounded-lg border border-gray-700 hover:border-gray-500 transition-colors group">
            <img :src="logos.vue" alt="Vue" class="w-8 h-8 group-hover:scale-110 transition-transform">
            <p class="font-bold text-white">Vue.js</p>
          </div>

<div class="flex items-center gap-4 bg-gray-900/50 p-4 rounded-lg border border-gray-800 hover:border-blue-500/50 transition-all group backdrop-blur-sm">
  <img :src="logos.django" 
       alt="Django" 
       class="w-8 h-8 opacity-80 group-hover:opacity-100 group-hover:scale-110 transition-all brightness-0 invert">
  <p class="font-bold text-white group-hover:text-blue-400 transition-colors">Django & DRF</p>
</div>

          <div class="bg-gray-800 p-4 rounded-lg border border-gray-700">
            <p class="font-bold text-white mb-3">Databases</p>
            <div class="flex gap-4 justify-around bg-gray-900 p-3 rounded border border-gray-700">
              <img :src="logos.mysql" title="MySQL" class="w-8 h-8 opacity-70 hover:opacity-100 hover:scale-110 transition-all">
              <img :src="logos.postgresql" title="PostgreSQL" class="w-8 h-8 opacity-70 hover:opacity-100 hover:scale-110 transition-all">
              <img :src="logos.mongodb" title="MongoDB" class="w-8 h-8 opacity-70 hover:opacity-100 hover:scale-110 transition-all">
            </div>
          </div>
        </div>
      </div>

    </main>
  </div>
</template>

<style scoped>
/* Importamos una fuente monoespaciada para el look Pokedex si no está global */
@import url('https://fonts.googleapis.com/css2?family=Roboto+Mono:wght@400;700&display=swap');

.font-mono {
  font-family: 'Roboto Mono', monospace;
}
</style>