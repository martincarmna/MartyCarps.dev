<template>
  <main class="bg-gray-900 py-10 overflow-hidden">
    <div class="relative flex overflow-hidden group border-y border-gray-600 bg-gray-800 py-4">
      
      <div class="animate-infinite-scroll flex gap-8 px-4">
        
        <img src="/banner.webp" alt="banner" class="w-[500px] h-64 object-cover rounded-xl shadow-2xl">
        <img src="/choose.jpeg" alt="banner" class="w-[500px] h-64 object-cover rounded-xl shadow-2xl">
        <img src="/perfil.jpg" alt="perfil" class="w-[500px] h-64 object-cover rounded-xl shadow-2xl">

        <img src="/banner.webp" alt="banner" class="w-[500px] h-64 object-cover rounded-xl shadow-2xl">
        <img src="/choose.jpeg" alt="banner" class="w-[500px] h-64 object-cover rounded-xl shadow-2xl">
        <img src="/perfil.jpg" alt="perfil" class="w-[500px] h-64 object-cover rounded-xl shadow-2xl">
        
      </div>

      <div class="pointer-events-none absolute inset-y-0 left-0 w-32 bg-gradient-to-r from-gray-900 to-transparent"></div>
      <div class="pointer-events-none absolute inset-y-0 right-0 w-32 bg-gradient-to-l from-gray-900 to-transparent"></div>
    </div>
  </main>
</template>