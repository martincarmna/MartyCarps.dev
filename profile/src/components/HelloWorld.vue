<script setup lang="ts">
import Magikar from './Magikar.vue';
import Myself from './Myself.vue';
import Banner from './Banner.vue';
import Proyectos from './Proyectos.vue';
import Git from './Git.vue';

</script>

<template>
  <header class="bg-black flex items-center justify-between px-8 py-2 w-full">

    <img src="/Pokemon-Logo.png" alt="logo pok" class="w-[150px] h-auto object-contain">

    <nav class="flex gap-8 text-blue-500 font-semibold uppercase tracking-wide">
      <a href="#" class="hover:text-blue-300 transition-colors">Home</a>
      <a href="#" class="hover:text-blue-300 transition-colors">Projects</a>
      <a href="#" class="hover:text-blue-300 transition-colors">About</a>
    </nav>

    <div class="flex items-center gap-5 text-white">
      <span class="material-symbols-outlined cursor-pointer hover:text-blue-400">
        search
      </span>
      <span class="material-symbols-outlined cursor-pointer hover:text-blue-400">
        language
      </span>
      <span class="material-symbols-outlined cursor-pointer hover:text-blue-400">
        account_circle
      </span>
    </div>

  </header>
  <main>
    <section class="bg-[url('/fondo.gif')] bg-cover bg-center bg-no-repeat h-screen w-full relative">
      <div class="absolute inset-0 bg-black/20"></div>

      <div class="relative flex flex-col min-h-screen items-center justify-center gap-12">

        <h1 class="text-white text-6xl md:text-8xl font-black drop-shadow-2xl uppercase tracking-tighter">
          Marty Carps
        </h1>

        <div
          class="inline-flex items-center bg-white border border-gray-100 rounded-full shadow-2xl p-2 max-w-sm transform hover:scale-105 transition-transform">

          <div class="flex items-center gap-3 px-6 text-gray-700">
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
              stroke="currentColor" class="size-6 text-gray-400">
              <path stroke-linecap="round" stroke-linejoin="round"
                d="M20.25 14.15v4.25c0 1.035-.84 1.875-1.875 1.875H5.625A1.875 1.875 0 0 1 3.75 18.4V14.15m16.5 0c.516-.14.938-.562 1.078-1.078l1-3.75c.188-.705-.285-1.422-1.078-1.422H3.75c-.793 0-1.266.717-1.078 1.422l1 3.75c.14.516.562.938 1.078 1.078m16.5 0a5.25 5.25 0 0 1-16.5 0M15 6.75A1.5 1.5 0 1 1 13.5 8.25V6.75a1.5 1.5 0 0 1 1.5-1.5Zm-6 1.5V6.75a1.5 1.5 0 0 1-1.5-1.5H9a1.5 1.5 0 1 1-1.5 1.5Z" />
            </svg>
            <span class="text-xl font-semibold tracking-tight">
              Ver proyectos
            </span>
          </div>

          <button
            class="flex items-center gap-2.5 bg-yellow-500 text-gray-900 font-bold py-4 px-10 rounded-full hover:bg-yellow-400 transition-all active:scale-95 shadow-md">
            <span class="text-xl">Ir</span>
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="3"
              stroke="currentColor" class="size-6">
              <path stroke-linecap="round" stroke-linejoin="round" d="M13.5 4.5 21 12m0 0-7.5 7.5M21 12H3" />
            </svg>
          </button>

        </div>
      </div>
    </section>
<Banner/>
  <Myself/>
  <Git/>
<Magikar/>

<Proyectos/>



  </main>
<footer class="bg-black text-white py-12 px-8 md:px-20 border-t border-gray-800">
  <div class="max-w-7xl mx-auto flex flex-col md:flex-row justify-between gap-12">
    
    <div class="flex-1 space-y-6">
      <img src="/Pokemon-Logo.png" alt="logo pok" class="w-32 h-auto object-contain brightness-110">
      <p class="text-gray-400 text-sm leading-relaxed max-w-md">
        Portafolio personal diseñado para demostrar habilidades frontend y backend. 
        Como creativo apasionado por el dibujo y la música, busco que cada proyecto 
        capte la atención mediante un estilo visual único y funcional.
      </p>
    </div>

    <div class="flex-1 space-y-4">
      <h3 class="text-xl font-bold text-blue-500">Suscríbete al canal</h3>
      <p class="text-gray-400 text-sm">Recibe actualizaciones de mis tutoriales de guitarra y dibujo.</p>
      
      <form class="flex flex-col sm:flex-row gap-2">
        <input 
          type="email" 
          placeholder="Email@.com" 
          class="bg-white border border-gray-700 text-gray-700 px-4 py-2 rounded-lg focus:outline-none focus:border-blue-500 flex-1 transition-all"
        >
        <button class="bg-blue-600 hover:bg-blue-700 text-white font-bold px-6 py-2 rounded-lg transition-colors">
          Unirse
        </button>
      </form>
    </div>

  </div>

  <div class="max-w-7xl mx-auto mt-12 pt-8 border-t border-gray-900 flex flex-col md:flex-row justify-between items-center gap-4 text-gray-500 text-xs">
    <p>© 2026 Marty Carps. Todos los derechos reservados.</p>
    <div class="flex gap-6">
      <a href="#" class="hover:text-blue-500 transition">YouTube</a>
      <a href="#" class="hover:text-blue-500 transition">GitHub</a>
      <a href="#" class="hover:text-blue-500 transition">LinkedIn</a>
    </div>
  </div>
</footer>

</template>