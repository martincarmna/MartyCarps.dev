<template>
  <div class="safari-wrapper" @click="handleClick">
    <span class="whatsapp-label">WhatsApp</span>
    
    <div class="safari-ball">
      <div class="top-half">
        <div class="camo-patch p1"></div>
        <div class="camo-patch p2"></div>
      </div>
      
      <div class="button-outer">
        <div class="button-inner" :class="{ 'catching-light': isCapturing }">
          <svg viewBox="0 0 448 512" class="wa-svg">
            <path d="M380.9 97.1C339 55.1 283.2 32 223.9 32c-122.4 0-222 99.6-222 222 0 39.1 10.2 77.3 29.6 111L0 480l117.7-30.9c32.4 17.7 68.9 27 106.1 27h.1c122.3 0 224.1-99.6 224.1-222 0-59.3-25.2-115-67.1-157zm-157 341.6c-33.1 0-65.6-8.9-94-25.7l-6.7-4-69.8 18.3L72 359.2l-4.4-7c-18.5-29.4-28.2-63.3-28.2-98.2 0-101.7 82.8-184.5 184.6-184.5 49.3 0 95.6 19.2 130.4 54.1 34.8 34.9 56.2 81.2 56.1 130.5 0 101.8-84.9 184.6-186.6 184.6zm101.2-138.2c-5.5-2.8-32.8-16.2-37.9-18-5.1-1.9-8.8-2.8-12.5 2.8-3.7 5.6-14.3 18-17.6 21.8-3.2 3.7-6.5 4.2-12 1.4-32.6-16.3-54-29.1-75.5-66-5.7-9.8 5.7-9.1 16.3-30.3 1.8-3.7.9-6.9-.5-9.7-1.4-2.8-12.5-30.1-17.1-41.2-4.5-10.8-9.1-9.3-12.5-9.5-3.2-.2-6.9-.2-10.6-.2-3.7 0-9.7 1.4-14.8 6.9-5.1 5.6-19.4 19-19.4 46.3 0 27.3 19.9 53.7 22.6 57.4 2.8 3.7 39.1 59.7 94.8 83.8 35.2 15.2 49 16.5 66.6 13.9 10.7-1.6 32.8-13.4 37.4-26.4 4.6-13 4.6-24.1 3.2-26.4-1.3-2.5-5-3.9-10.5-6.6z"/>
          </svg>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const isCapturing = ref(false);
const catchSound = new Audio('https://www.myinstants.com/media/sounds/pokebola-capturando.mp3');

const handleClick = () => {
  isCapturing.value = true;
  catchSound.currentTime = 0;
  catchSound.play().catch(() => console.log("Interacción necesaria para audio"));

  setTimeout(() => {
    isCapturing.value = false;
    const phone = '522411612654';
    const message = encodeURIComponent('¡Hola! Me gustaría recibir más información.');
    window.open(`https://wa.me/${phone}?text=${message}`, '_blank');
  }, 800);
};
</script>

<style scoped>
.safari-wrapper {
  position: fixed;
  bottom: 25px;
  right: 25px;
  display: flex;
  align-items: center;
  cursor: pointer;
  z-index: 9999;
  /* IMPORTANTE: El origen a la derecha evita que al crecer se salga de la pantalla */
  transform-origin: right;
  transition: transform 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
}

.safari-wrapper:hover {
  transform: scale(1.1);
}

.whatsapp-label {
  background: #2d4c2a;
  color: white;
  padding: 8px 15px;
  border-radius: 20px 5px 5px 20px;
  margin-right: -15px;
  font-family: 'Segoe UI', Roboto, sans-serif;
  font-weight: bold;
  font-size: 14px;
  box-shadow: 0 4px 10px rgba(0,0,0,0.2);
  border: 2px solid #333;
  border-right: none;
  /* Evita que el texto fuerce scroll si el contenedor es muy pequeño */
  white-space: nowrap;
}

.safari-ball {
  position: relative;
  width: 60px;
  height: 60px;
  background: white;
  border-radius: 50%;
  border: 3px solid #333;
  overflow: hidden;
  box-shadow: 0 5px 15px rgba(0,0,0,0.3);
  /* Mantiene la bola contenida durante la rotación */
  backface-visibility: hidden;
}

.top-half {
  position: absolute;
  top: 0;
  width: 100%;
  height: 50%;
  background: #4a7c44;
}

.camo-patch {
  position: absolute;
  background: #2d4c2a;
  border-radius: 50%;
}
.p1 { width: 25px; height: 12px; top: 5px; left: -5px; transform: rotate(-20deg); }
.p2 { width: 20px; height: 10px; top: 8px; right: 5px; background: #8ba342; }

.button-outer {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 20px;
  height: 20px;
  background: #333;
  border-radius: 50%;
  transform: translate(-50%, -50%);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 2;
}

.button-inner {
  width: 14px;
  height: 14px;
  background: white;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: background 0.2s ease;
}

.wa-svg {
  width: 10px;
  fill: #25D366;
}

.catching-light {
  background: #ff0000 !important;
  box-shadow: 0 0 12px #ff0000;
  animation: pulse 0.2s infinite;
}

@keyframes pulse {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.6; }
}

.safari-wrapper:hover .safari-ball {
  animation: shake 0.5s infinite;
}

@keyframes shake {
  0% { transform: rotate(0); }
  25% { transform: rotate(-10deg); }
  75% { transform: rotate(10deg); }
  100% { transform: rotate(0); }
}
</style>