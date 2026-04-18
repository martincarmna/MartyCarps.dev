<script setup lang="ts">
// Definimos la prop para recibir el idioma del padre
defineProps<{
  currentLang: 'ES' | 'EN'
}>();

// Diccionario local para este componente
const texts = {
  ES: { download: 'Descargar CV' },
  EN: { download: 'Download CV' }
};

// Función para descargar el PDF
const downloadCV = () => {
  const link = document.createElement('a');
  link.href = '/JoseMartin_DesarrolladorFullStack.pdf'; 
  link.download = 'JoseMartin_DesarrolladorFullStack.pdf';
  link.click();
};
</script>

<template>
  <main>
    <section class="h-[420px] md:h-[500px] w-full relative overflow-hidden flex items-center p-6 md:p-16 bg-slate-950">
      
      <div class="absolute inset-0 bg-[radial-gradient(circle_at_30%_50%,rgba(30,58,138,0.2),transparent)] z-0"></div>
      
      <div class="absolute inset-0 bg-black/40 z-0"></div>

      <img
        src="/red.png"
        alt="red"
        class="z-10 w-48 md:w-80 absolute bottom-0 right-4 md:left-[20%] md:right-auto opacity-90 drop-shadow-[0_0_15px_rgba(59,130,246,0.3)] transition-all duration-500 hover:scale-105"
      >

      <div class="relative z-20 flex flex-col items-start gap-4 max-w-[60%] md:max-w-none md:ml-auto md:items-end md:text-right">
        
        <p class="text-blue-400 text-xs uppercase tracking-[0.3em] font-bold">
          {{ currentLang === 'ES' ? 'Currículum Vitae' : 'Resume' }}
        </p>

        <h2 class="text-white text-4xl md:text-7xl font-black uppercase italic tracking-tighter leading-none">
          Jose Martin<br>
          <span class="text-slate-400">Carmona Palestina</span>
        </h2>

        <button
          @click="downloadCV"
          class="flex items-center gap-2 bg-white text-black font-black uppercase tracking-widest text-[10px] md:text-xs px-6 md:px-10 py-3 md:py-4 hover:bg-blue-500 hover:text-white active:scale-95 transition-all shadow-[6px_6px_0px_0px_rgba(30,58,138,1)]"
        >
          <span class="material-symbols-outlined text-lg">download</span>
          {{ texts[currentLang].download }}
        </button>

      </div>
      
      <div class="absolute bottom-0 left-0 w-full h-1 bg-gradient-to-r from-blue-900 via-blue-500 to-blue-900 opacity-30"></div>
    </section>
  </main>
</template>

<style scoped>
/* Un pequeño efecto de parpadeo suave para el texto de CV */
p {
  animation: pulse 3s infinite;
}

@keyframes pulse {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.7; }
}
</style>