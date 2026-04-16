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
  link.href = '/MartyCarps_Cv.pdf'; // Asegúrate de que el archivo esté en la carpeta /public
  link.download = 'MartyCarps_CV.pdf';
  link.click();
};
</script>

<template>
  <main>
    <section
      class="bg-[url('/Bs1G.gif')] bg-cover bg-center bg-no-repeat h-screen w-full relative overflow-hidden flex flex-col items-center md:items-start p-6 md:p-16"
    >
      <div class="absolute inset-0 bg-black/20 hover:bg-black/10 transition-colors duration-500 z-0"></div>

      <img 
        src="/Pokemon-Logo.png" 
        alt="logo pok" 
        class="z-30 w-64 md:w-[450px] h-auto object-contain relative md:translate-x-0"
      >

      <img 
        src="/red.png" 
        alt="red" 
        class="z-20 w-48 md:w-auto absolute bottom-0 md:bottom-auto md:top-1/2 left-1/2 md:left-1/3 transform -translate-x-1/2 md:-translate-y-1/2 md:translate-x-0 transition-all duration-500"
      >

      <div class="absolute bottom-10 md:bottom-auto md:top-1/2 md:right-10 lg:right-20 z-40 transform md:-translate-y-1/2 w-full px-6 md:px-0 md:w-auto">
        <button 
          @click="downloadCV"
          class="bg-[#FF0000] w-full md:w-72 lg:w-96 h-24 md:h-32 flex flex-col md:flex-row items-center justify-center gap-2 border-4 border-white shadow-[8px_8px_0px_0px_rgba(0,0,0,0.5)] active:translate-y-1 active:shadow-none transition-all group"
        >
          <span class="material-symbols-outlined text-white text-4xl group-hover:animate-bounce">
            download
          </span>
          <h3 class="text-white text-2xl md:text-xl lg:text-3xl font-black uppercase tracking-tighter">
            {{ texts[currentLang].download }}
          </h3>
        </button>
      </div>

    </section>
  </main>
</template>