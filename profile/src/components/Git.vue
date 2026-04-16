<template>
  <section class="bg-black text-blue-600 flex flex-col md:flex-row items-center justify-between p-8 md:p-20 gap-10 min-h-[400px]">
    
    <div class="flex flex-col items-center group">
      <img 
        src="/git.png" 
        alt="Github" 
        class="w-32 md:w-48 lg:w-64 object-contain transition-transform group-hover:scale-110"
      >
      <button class="mt-6 px-10 py-3 bg-blue-600 text-white font-bold uppercase rounded-lg hover:bg-blue-400 hover:text-black transition-all shadow-[0_0_15px_rgba(37,99,235,0.4)]">
        
        <a href="https://github.com/martincarmna">Ir a Github</a>
      </button>
    </div>

    <div class="flex flex-col items-center">
      <img 
        src="/podex.png" 
        alt="pokedex" 
        class="w-48 md:w-64 lg:w-80 object-contain drop-shadow-[0_0_20px_rgba(255,0,0,0.3)]"
      >
      <p class="text-pokedex-red mt-4 font-mono text-sm tracking-widest animate-pulse">
        SISTEMA POKÉDEX ONLINE
      </p>
    </div>

  </section>
</template>