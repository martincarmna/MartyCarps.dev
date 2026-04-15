<template>
  <div class="bg-gray-100 min-h-screen p-8">
    <h1 class="text-5xl font-bold mb-10 text-center">Sobre mí</h1>

    <main class="flex flex-wrap lg:flex-nowrap gap-8 max-w-6xl mx-auto">
      
      <div class="bg-white shadow-lg rounded-xl p-8 flex-1">
        <div class="flex items-center gap-6 mb-6 bg-gray-50 p-4 rounded-lg">
          <img src="/perfil.jpg" class="w-24 h-24 rounded-full object-cover border-4 border-gray-400" alt="Avatar">
          <div>
            <h3 class="text-xl font-bold">Jose Martin Carmona Palestina</h3>
            <h4 class="text-gray-600">Desarrollador Software Multiplataforma | Frontend</h4>
          </div>
        </div>
        
        <div class="text-gray-700 leading-relaxed">
          <p>
            Soy una persona que disfruta dejando su sello 
            personal en todo lo que hace. Me apasiona el arte 
            y la música; de hecho, toco la guitarra, dibujo y 
            comparto tutoriales en mis redes sociales. Esa 
            chispa creativa es la que me impulsa hacia el Frontend,
             donde lo visual cobra vida, aunque también tengo un dominio
              sólido del Backend. Como puedes observar aquí al lado, estas
               son las habilidades 
            que manejo en el mundo del Desarrollo de Software.
          </p>
        </div>
      </div>

      <div class="bg-amber-200 p-8 rounded-xl w-full lg:w-1/3">
        <h2 class="text-2xl font-bold mb-6">Tools</h2>
        
        <div class="space-y-4">
          <section class="flex items-center gap-3 bg-white/50 p-2 rounded">
            <img src="" alt="Vue" class="w-8 h-8">
            <p class="font-medium">Vue</p>
          </section>
          
          <section class="flex items-center gap-3 bg-white/50 p-2 rounded">
            <img src="" alt="Django" class="w-8 h-8">
            <p class="font-medium">Django & DRF</p>
          </section>

          <section class="flex items-center gap-3 bg-white/50 p-2 rounded">
            <img src="" alt="BD" class="w-8 h-8">
            <p class="font-medium">MySQL, PSQL, MongoDB</p>
          </section>
        </div>
      </div>
          <div class="flex justify-center mt-12">
        <img src="/team.png" alt="equipo" class="w-64 h-auto opacity-80 hover:opacity-100 transition ">
    </div>
    </main>


  </div>
</template>