<style>
/* Spinner de Pokébola */
.pokeball-spinner {
  width: 60px;
  height: 60px;
  background: #fff;
  border: 4px solid #000; /* Borde más grueso para estilo cómic/Pokémon */
  border-radius: 50%;
  position: relative;
  overflow: hidden;
  box-shadow: inset -4px -4px 0px rgba(0,0,0,0.1), 0 0 15px rgba(59, 130, 246, 0.5);
}

/* Animación de captura (shake) */
.pokeball-catching {
  animation: shake 1.25s cubic-bezier(.36,.07,.19,.97) infinite;
}

/* Mitad roja */
.pokeball-spinner::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 50%;
  background: #ef5350; /* Rojo Pokémon */
  border-bottom: 4px solid #000;
}

/* Botón central con luz */
.pokeball-spinner::after {
  content: "";
  position: absolute;
  top: 50%;
  left: 50%;
  width: 16px;
  height: 16px;
  background: #fff;
  border: 4px solid #000;
  border-radius: 50%;
  transform: translate(-50%, -50%);
  z-index: 10;
  /* Efecto de luz parpadeante en el botón */
  animation: buttonPulse 1s infinite;
}

/* Reflejo de luz superior (Efecto cristal) */
.pokeball-spinner-reflect {
  content: "";
  position: absolute;
  top: 5px;
  left: 10px;
  width: 15px;
  height: 8px;
  background: rgba(255, 255, 255, 0.4);
  border-radius: 50%;
  z-index: 5;
  transform: rotate(-10deg);
}

/* --- ANIMACIONES --- */

@keyframes shake {
  0% { transform: translate(0, 0) rotate(0deg); }
  20% { transform: translate(-5px, 0) rotate(-15deg); }
  30% { transform: translate(5px, 0) rotate(15deg); }
  50% { transform: translate(-5px, 0) rotate(-10deg); }
  60% { transform: translate(5px, 0) rotate(10deg); }
  100% { transform: translate(0, 0) rotate(0deg); }
}

@keyframes buttonPulse {
  0%, 100% { background: #fff; box-shadow: 0 0 2px rgba(0,0,0,0.2); }
  50% { background: #ff7675; box-shadow: 0 0 8px #ff7675; } /* Luz roja al parpadear */
}

@keyframes spin {
  from { transform: rotate(0deg); }
  to { transform: rotate(360deg); }
}</style>
