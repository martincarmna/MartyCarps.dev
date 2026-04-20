<script setup lang="ts">
defineProps<{
  currentLang: 'ES' | 'EN'
}>();

const texts = {
  ES: {
    pokedexEntry: 'Entrada Pokédex: No. 001 - Marty',
    title: 'INFO DESARROLLADOR',
    role: 'Desarrollador de Software Multiplataforma Full-stack',
    description: `Desarrollador Full-Stack con experiencia construyendo aplicaciones completas, desde la interfaz hasta la lógica de negocio y base de datos. Me apasiona crear soluciones funcionales, escalables y bien estructuradas, combinando lógica, creatividad y atención al detalle.`,
    statsTitle: 'BASE STATS',
    toolsTitle: 'HERRAMIENTAS DE COMBATE',
    skills: ['Frontend', 'Backend', 'Database', 'DevOps']
  },
  EN: {
    pokedexEntry: 'Pokédex Entry: No. 001 - Marty',
    title: 'DEVELOPER INFO',
    role: 'Full-Stack Multiplatform Software Developer',
    description: `Full-Stack Developer with experience building complete applications, from the interface to the business logic and database. I am passionate about creating functional, scalable, and well-structured solutions, combining logic, creativity, and attention to detail.`,
    statsTitle: 'BASE STATS',
    toolsTitle: 'COMBAT TOOLS',
    skills: ['Frontend', 'Backend', 'Database', 'DevOps']
  }
};

const logos = {
  vue:        'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vuejs/vuejs-original.svg',
  django:     'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/django/django-plain.svg',
  python:     'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg',
  js:         'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg',
  tailwind:   'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/tailwindcss/tailwindcss-original.svg',
  html:       'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg',
  css:        'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg',
  mysql:      'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg',
  postgresql: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/postgresql/postgresql-original.svg',
  mongodb:    'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mongodb/mongodb-original.svg'
};
</script>

<template>
  <div class="section-root">

    <!-- Header bar -->
    <div class="header-bar">
      <span class="header-text">{{ texts[currentLang].pokedexEntry }}</span>
      <div class="dots">
        <span class="dot dot-red"></span>
        <span class="dot dot-yellow"></span>
        <span class="dot dot-green"></span>
      </div>
    </div>

    <main class="main-layout">

      <!-- ── Info card ── -->
      <div class="info-card">

        <div class="avatar-row">
          <img
            src="/perfil.jpg"
            class="avatar-img"
            alt="Avatar"
            @error="(e) => (e.target as HTMLImageElement).style.display = 'none'"
          >
          <div>
            <p class="dev-name">Jose Martin Carmona Palestina</p>
            <p class="dev-role">{{ texts[currentLang].role }}</p>
          </div>
        </div>

        <p class="dev-desc">{{ texts[currentLang].description }}</p>

        <p class="stats-label">{{ texts[currentLang].statsTitle }}</p>
        <div class="skills-row">
          <span
            v-for="(skill, i) in texts[currentLang].skills"
            :key="skill"
            class="skill-tag"
            :style="`animation-delay: ${i * 0.08}s`"
          >{{ skill }}</span>
        </div>
      </div>

      <!-- ── 3D World ── -->
      <div class="world-wrap">
        <div class="floating-world">

          <div class="layer layer-back"></div>
          <div class="layer layer-mid"></div>

          <div class="layer layer-front">
            <p class="tools-label">{{ texts[currentLang].toolsTitle }}</p>
            <div class="db-strip">
              <div
                v-for="(db, i) in [
                  { src: logos.mysql,      name: 'MySQL' },
                  { src: logos.postgresql, name: 'Postgres' },
                  { src: logos.mongodb,    name: 'MongoDB' }
                ]"
                :key="db.name"
                class="db-item"
                :style="`animation-delay: ${i * 0.4}s`"
              >
                <img :src="db.src" :alt="db.name">
                <span>{{ db.name }}</span>
              </div>
            </div>
          </div>

          <div class="tech vue-pos"      style="animation-delay: 0s">
            <span class="tip">Vue.js</span>
            <img :src="logos.vue" alt="Vue">
          </div>

          <div class="tech tailwind-pos" style="animation-delay: 0.3s">
            <span class="tip">Tailwind</span>
            <img :src="logos.tailwind" alt="Tailwind">
          </div>

          <div class="tech django-pos"   style="animation-delay: 0.6s">
            <span class="tip">Django</span>
            <img :src="logos.django" alt="Django" class="invert-icon">
          </div>

          <div class="tech python-pos"   style="animation-delay: 0.9s">
            <span class="tip">Python</span>
            <img :src="logos.python" alt="Python">
          </div>

          <div class="tech js-pos"       style="animation-delay: 1.1s">
            <span class="tip">JavaScript</span>
            <img :src="logos.js" alt="JavaScript" class="js-icon">
          </div>

          <div class="tech htmlcss-pos"  style="animation-delay: 1.4s">
            <span class="tip">HTML5 &amp; CSS3</span>
            <img :src="logos.html" alt="HTML5">
            <img :src="logos.css"  alt="CSS3" style="margin-top: 4px">
          </div>

        </div>
      </div>

    </main>
  </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Roboto+Mono:wght@400;700&display=swap');

/* ── Root ── */
.section-root {
  background: #020817;
  min-height: 100vh;
  padding: 2.5rem 3rem;
  font-family: 'Roboto Mono', monospace;
  border-top: 1px solid #0f1f35;
}

/* ── Header ── */
.header-bar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: #0d1424;
  border: 1px solid #1e2d45;
  border-radius: 10px;
  padding: 12px 22px;
  max-width: 1300px;
  margin: 0 auto 3.5rem;
}
.header-text { color: #4fc3f7; font-size: 13px; letter-spacing: .15em; }
.dots        { display: flex; gap: 6px; }
.dot         { width: 11px; height: 11px; border-radius: 50%; display: block; }
.dot-red     { background: #ef4444; }
.dot-yellow  { background: #facc15; }
.dot-green   { background: #22c55e; }

/* ── Layout ── */
.main-layout {
  display: flex;
  flex-wrap: wrap;
  gap: 3rem;
  max-width: 1300px;
  margin: 0 auto;
  align-items: center;
}

/* ── Info card ── */
.info-card {
  flex: 1;
  min-width: 340px;
  background: #0d1424;
  border: 1px solid #1e2d45;
  border-radius: 16px;
  padding: 28px 32px;
  animation: fade-up .5s ease both;
}

.avatar-row {
  display: flex;
  align-items: center;
  gap: 18px;
  background: #111d30;
  border: 1px solid #1e2d45;
  border-radius: 12px;
  padding: 18px 20px;
  margin-bottom: 20px;
}
.avatar-img {
  width: 64px;
  height: 64px;
  border-radius: 50%;
  object-fit: cover;
  border: 2px solid #4fc3f7;
  flex-shrink: 0;
}
.dev-name { color: #e2e8f0; font-size: 15px; font-weight: 700; margin: 0; }
.dev-role { color: #4fc3f7; font-size: 11px; margin: 5px 0 0; line-height: 1.5; }

.dev-desc {
  color: #94a3b8;
  font-size: 12px;
  line-height: 1.85;
  background: #080f1e;
  border: 1px solid #1e2d45;
  border-radius: 10px;
  padding: 16px 18px;
  margin-bottom: 22px;
}

.stats-label {
  color: #374151;
  font-size: 9px;
  letter-spacing: .2em;
  margin-bottom: 12px;
}

.skills-row { display: flex; flex-wrap: wrap; gap: 8px; }
.skill-tag {
  font-size: 11px;
  padding: 5px 14px;
  border-radius: 7px;
  border: 1px solid #1e2d45;
  color: #64748b;
  background: #080f1e;
  opacity: 0;
  animation: fade-up .35s ease forwards;
}

/* ── 3D World ── */
.world-wrap {
  flex: 1.2;
  min-width: 420px;
  height: 560px;
  display: flex;
  align-items: center;
  justify-content: center;
  perspective: 1200px;
  position: relative;
}

.floating-world {
  position: relative;
  width: 520px;
  height: 300px;
  transform-style: preserve-3d;
  transform: rotateX(20deg) rotateY(-15deg);
  animation: float-world 8s ease-in-out infinite;
}

.layer {
  position: absolute;
  inset: 0;
  border-radius: 40px;
  transform-style: preserve-3d;
}
.layer-back {
  background: #020817;
  border: 1px solid #0f1f35;
  transform: translateZ(-24px) scale(.95);
  box-shadow: 0 60px 120px rgba(0,0,0,1);
}
.layer-mid {
  background: #080f1e;
  border: 1px solid #111d30;
  transform: translateZ(-11px) scale(.977);
}
.layer-front {
  background: #0d1a2d;
  border: 1px solid #1e2d45;
  transform: translateZ(0);
  overflow: hidden;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  padding: 18px 28px;
}

.tools-label {
  text-align: center;
  font-size: 9px;
  letter-spacing: .45em;
  color: #1e3a5f;
  margin: 0 0 12px;
}

.db-strip {
  display: flex;
  justify-content: space-around;
  align-items: center;
  background: rgba(0,0,0,.4);
  border-radius: 50px;
  padding: 12px 28px;
  border: 1px solid #0f1f35;
}
.db-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 5px;
  animation: db-pulse 3.5s ease-in-out infinite;
}
.db-item img  { width: 36px; height: 36px; transition: transform .2s; }
.db-item span { font-size: 9px; color: #374151; }
.db-item:hover img { transform: scale(1.2); }

/* ── Tech icons ── */
.tech {
  position: absolute;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 3px;
  cursor: pointer;
  animation: bob 4.5s ease-in-out infinite;
}
.tech img {
  width: 58px;
  height: 58px;
  transition: transform .25s, filter .25s;
  filter: drop-shadow(0 4px 10px rgba(0,0,0,.7));
}
.tech:hover img {
  transform: scale(1.2);
  filter: drop-shadow(0 0 16px rgba(79,195,247,.55));
}
.invert-icon {
  filter: brightness(0) invert(1) opacity(.75) drop-shadow(0 4px 10px rgba(0,0,0,.7)) !important;
}
.tech:hover .invert-icon {
  filter: brightness(0) invert(1) drop-shadow(0 0 16px rgba(255,255,255,.3)) !important;
}
.js-icon { border-radius: 5px; }

.tip {
  position: absolute;
  bottom: 110%;
  left: 50%;
  transform: translateX(-50%);
  background: #0d1424;
  border: 1px solid #1e2d45;
  color: #4fc3f7;
  font-size: 10px;
  padding: 4px 10px;
  border-radius: 5px;
  white-space: nowrap;
  opacity: 0;
  pointer-events: none;
  transition: opacity .2s;
  z-index: 10;
}
.tech:hover .tip { opacity: 1; }

/* ── Posiciones ── */
.vue-pos      { top: -72px;   left: 14px; }
.tailwind-pos { top: -60px;   left: 50%; transform: translateX(-50%); }
.django-pos   { top: -86px;   right: 18px; }
.python-pos   { bottom: 100px; left: -32px; }
.js-pos       { bottom: 76px;  left: 26%; }
.htmlcss-pos  { top: 28px;    right: -36px; }

/* ── Keyframes ── */
@keyframes float-world {
  0%, 100% { transform: translateY(0)     rotateX(20deg) rotateY(-15deg); }
  50%       { transform: translateY(-20px) rotateX(17deg) rotateY(-10deg); }
}

@keyframes bob {
  0%, 100% { transform: translateY(0); }
  50%       { transform: translateY(-16px); }
}

@keyframes db-pulse {
  0%, 100% { opacity: .8;  transform: scale(1); }
  50%       { opacity: 1;  transform: scale(1.13); }
}

@keyframes fade-up {
  from { opacity: 0; transform: translateY(8px); }
  to   { opacity: 1; transform: translateY(0); }
}
</style>