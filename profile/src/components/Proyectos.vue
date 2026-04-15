<template>
  <div class="bg-gray-100 min-h-screen p-8 md:p-16">
    
    <header class="flex items-center justify-between mb-12">
      <h1 class="text-4xl font-bold text-gray-900">Proyectos más relevantes</h1>
      
      <div class="flex items-center gap-4">
        <button class="w-12 h-12 rounded-full border border-gray-400 flex items-center justify-center text-gray-700 hover:border-gray-900 hover:text-gray-900 transition">
          <span class="material-symbols-outlined">arrow_back</span>
        </button>
        <button class="w-12 h-12 rounded-full bg-indigo-600 flex items-center justify-center text-white hover:bg-indigo-700 transition shadow-md">
          <span class="material-symbols-outlined">arrow_forward</span>
        </button>
      </div>
    </header>

    <main class="flex items-start gap-6 overflow-x-auto pb-6 -mb-6">
      
<div class="bg-white rounded-2xl shadow-lg w-[320px] flex-shrink-0">
  <img src="/image.png" alt="rick" class="w-full h-56 rounded-t-2xl object-cover">
  <div class="p-6">
    <h3 class="text-xl font-medium text-gray-900 leading-snug">Rick and Morty</h3>
    
    <a href="https://martincarmna.github.io/Rick-and-Morty/" 
       target="_blank" 
       class="text-blue-600 hover:text-blue-800 font-semibold mt-4 inline-block underline">
       Ver proyecto →
    </a>

    <footer class="flex items-center gap-3 mt-6">
      <p class="text-pink-500 font-medium text-sm">Proyecto Demo</p>
    </footer>
  </div>
</div>

<div class="bg-white rounded-2xl shadow-xl w-[350px] flex-shrink-0 -mt-8 overflow-hidden"> 
  <img src="/myst.png" alt="Myst Depositos" class="w-full h-64 object-cover"> 
  
  <div class="p-8"> 
    <h3 class="text-2xl font-semibold text-gray-950 leading-snug">
      SMyT Depositos Federales
    </h3>

    <a href="https://smytdepositos.netlify.app/" 
       target="_blank" 
       class="inline-block mt-4 text-indigo-600 font-bold hover:text-indigo-800 transition-colors">
       Visitar sitio oficial →
    </a>

    <footer class="flex items-center gap-3 mt-8">
       <span class="px-3 py-1 bg-gray-100 text-gray-600 text-xs rounded-full">Django</span>
       <span class="px-3 py-1 bg-gray-100 text-gray-600 text-xs rounded-full">Vue.js</span>

    </footer>
  </div>
</div>

<div class="bg-white rounded-2xl shadow-lg w-[320px] flex-shrink-0 overflow-hidden">
  <img src="/Carmonamusic.jpeg" alt="Canada" class="w-full h-56 object-cover">
  <div class="p-6">
    <h3 class="text-xl font-medium text-gray-900 leading-snug">
      Carmona music
    </h3>
    
    <a href="#" class="inline-block mt-4 text-sm font-bold text-indigo-600 hover:text-indigo-800">
      Ver más →
    </a>

    <footer class="flex items-center gap-3 mt-6">

      <p class="text-pink-500 font-medium text-sm">proyecto Demo</p>
    </footer>
  </div>
</div>

<div class="bg-white rounded-2xl shadow-lg w-[320px] flex-shrink-0 overflow-hidden">
  <img src="/ferret.jpeg" alt="Ferreteria Juquilita" class="w-full h-56 object-cover">
  
  <div class="p-6">
    <h3 class="text-xl font-medium text-gray-900 leading-snug line-clamp-2">
      Sistema de Gestión: Ferretería Juquilita
    </h3>
    
    <div class="flex gap-2 mt-3">
      <span class="bg-green-100 text-green-700 text-[10px] font-bold px-2 py-1 rounded-full uppercase">Vue.js</span>
      <span class="bg-green-800 text-white text-[10px] font-bold px-2 py-1 rounded-full uppercase">Django</span>
    </div>
    
    <a href="#" class="inline-block mt-4 text-sm font-bold text-indigo-600 hover:text-indigo-800">
      Próximamente →
    </a>
    
    <footer class="flex items-center justify-between mt-6 border-t pt-4">
      <p class="text-gray-500 text-xs font-semibold uppercase tracking-wider">Fullstack</p>
      <p class="text-pink-500 font-medium text-sm">Proyecto Demo</p>
    </footer>
  </div>
</div>
    </main>
  </div>
</template>