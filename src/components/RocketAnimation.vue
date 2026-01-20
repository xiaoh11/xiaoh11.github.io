<template>
  <transition name="fade">
    <div v-if="isAnimating" class="rocket-overlay" @click="stopAnimation">
      <div class="rocket-container">
        <div class="rocket">
          <div class="light-trail light-trail-1"></div>
          <div class="light-trail light-trail-2"></div>
          <span class="rocket-text">HX</span>
          <div class="flame flame-1"></div>
          <div class="flame flame-2"></div>
          <div class="flame flame-3"></div>
        </div>
        <div class="particles">
          <div class="particle" v-for="i in 20" :key="i"></div>
        </div>
      </div>
    </div>
  </transition>
</template>

<script>
export default {
  name: 'RocketAnimation',
  data() {
    return {
      isAnimating: false
    }
  },
  methods: {
    launch() {
      this.isAnimating = true;
      setTimeout(() => {
        this.isAnimating = false;
      }, 3000);
    },
    stopAnimation() {
      this.isAnimating = false;
    }
  }
}
</script>

<style scoped>
.rocket-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background: rgba(0, 0, 0, 0.95);
  z-index: 9999;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
}

.rocket-container {
  position: relative;
  width: 200px;
  height: 200px;
}

.rocket {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  animation: rocketLaunch 3s ease-in forwards;
  transform-origin: center center;
}

.rocket-text {
  font-size: 4rem;
  font-weight: 900;
  color: white;
  text-shadow: 
    0 0 20px rgba(255, 255, 255, 0.8),
    0 0 40px rgba(0, 170, 255, 0.6),
    0 0 60px rgba(0, 113, 227, 0.4);
  display: block;
  animation: textGlow 0.5s ease-in-out infinite alternate;
}

@keyframes rocketLaunch {
  0% {
    transform: translate(-50%, -50%) scale(0.3);
    opacity: 0;
  }
  10% {
    transform: translate(-50%, -50%) scale(1);
    opacity: 1;
  }
  25% {
    transform: translate(-50%, -50%) scale(1.1);
  }
  35% {
    transform: translate(-50%, -50%) scale(1) scaleY(1);
  }
  45% {
    transform: translate(-50%, -55%) scale(1) scaleY(1.2);
  }
  55% {
    transform: translate(-50%, -80%) scale(0.95) scaleY(2);
  }
  65% {
    transform: translate(-50%, -150%) scale(0.85) scaleY(4);
  }
  75% {
    transform: translate(-50%, -300%) scale(0.7) scaleY(8);
  }
  85% {
    transform: translate(-50%, -600%) scale(0.5) scaleY(15);
  }
  100% {
    transform: translate(-50%, -1500%) scale(0.2) scaleY(30);
    opacity: 0;
  }
}

@keyframes textGlow {
  from {
    text-shadow: 
      0 0 20px rgba(255, 255, 255, 0.8),
      0 0 40px rgba(0, 170, 255, 0.6),
      0 0 60px rgba(0, 113, 227, 0.4);
  }
  to {
    text-shadow: 
      0 0 30px rgba(255, 255, 255, 1),
      0 0 60px rgba(0, 170, 255, 0.8),
      0 0 90px rgba(0, 113, 227, 0.6);
  }
}

.light-trail {
  position: absolute;
  top: -50%;
  left: 50%;
  transform: translateX(-50%);
  width: 2px;
  height: 200%;
  background: linear-gradient(to bottom,
    transparent 0%,
    rgba(0, 170, 255, 0.8) 45%,
    rgba(255, 255, 255, 0.9) 50%,
    rgba(0, 170, 255, 0.8) 55%,
    transparent 100%
  );
  opacity: 0;
  animation: lightTrailAppear 3s ease-in forwards;
  filter: blur(1px);
}

.light-trail-1 {
  animation-delay: 0.4s;
  margin-left: -15px;
}

.light-trail-2 {
  animation-delay: 0.4s;
  margin-left: 15px;
}

@keyframes lightTrailAppear {
  0%, 40% {
    opacity: 0;
    height: 0%;
  }
  45% {
    opacity: 0.6;
    height: 100%;
  }
  55% {
    opacity: 0.8;
    height: 200%;
  }
  70% {
    opacity: 0.7;
    height: 400%;
  }
  85% {
    opacity: 0.4;
    height: 800%;
  }
  100% {
    opacity: 0;
    height: 1500%;
  }
}

.flame {
  position: absolute;
  top: 100%;
  left: 50%;
  transform: translateX(-50%);
  width: 50px;
  height: 80px;
  background: linear-gradient(to top, 
    rgba(255, 80, 0, 1) 0%,
    rgba(255, 150, 0, 0.9) 30%,
    rgba(255, 200, 0, 0.7) 60%,
    rgba(255, 255, 100, 0.3) 85%,
    transparent 100%
  );
  border-radius: 50% 50% 50% 50% / 60% 60% 40% 40%;
  animation: flameFlicker 0.08s ease-in-out infinite alternate,
             flameGrow 3s ease-in forwards;
  filter: blur(4px);
}

.flame-1 {
  animation-delay: 0s, 0.35s;
  z-index: 3;
}

.flame-2 {
  animation-delay: 0.04s, 0.35s;
  transform: translateX(-50%) scale(0.85);
  opacity: 0.8;
  z-index: 2;
}

.flame-3 {
  animation-delay: 0.08s, 0.35s;
  transform: translateX(-50%) scale(0.7);
  opacity: 0.6;
  z-index: 1;
}

@keyframes flameFlicker {
  from {
    transform: translateX(-50%) scaleX(1) scaleY(1);
  }
  to {
    transform: translateX(-50%) scaleX(1.15) scaleY(1.05);
  }
}

@keyframes flameGrow {
  0%, 35% {
    height: 0px;
    opacity: 0;
  }
  40% {
    height: 80px;
    opacity: 1;
  }
  50% {
    height: 120px;
    opacity: 1;
  }
  65% {
    height: 200px;
    width: 40px;
    opacity: 1;
  }
  75% {
    height: 350px;
    width: 30px;
    opacity: 0.9;
  }
  85% {
    height: 600px;
    width: 20px;
    opacity: 0.6;
  }
  100% {
    height: 1000px;
    width: 10px;
    opacity: 0;
  }
}

.particles {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 100%;
  height: 100%;
  pointer-events: none;
}

.particle {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 4px;
  height: 4px;
  background: white;
  border-radius: 50%;
  opacity: 0;
  animation: particleExplode 1.5s ease-out forwards;
}

.particle:nth-child(1) { animation-delay: 0.3s; --angle: 0deg; }
.particle:nth-child(2) { animation-delay: 0.3s; --angle: 20deg; }
.particle:nth-child(3) { animation-delay: 0.3s; --angle: 40deg; }
.particle:nth-child(4) { animation-delay: 0.3s; --angle: 60deg; }
.particle:nth-child(5) { animation-delay: 0.3s; --angle: 80deg; }
.particle:nth-child(6) { animation-delay: 0.3s; --angle: 100deg; }
.particle:nth-child(7) { animation-delay: 0.3s; --angle: 120deg; }
.particle:nth-child(8) { animation-delay: 0.3s; --angle: 140deg; }
.particle:nth-child(9) { animation-delay: 0.3s; --angle: 160deg; }
.particle:nth-child(10) { animation-delay: 0.3s; --angle: 180deg; }
.particle:nth-child(11) { animation-delay: 0.35s; --angle: 200deg; }
.particle:nth-child(12) { animation-delay: 0.35s; --angle: 220deg; }
.particle:nth-child(13) { animation-delay: 0.35s; --angle: 240deg; }
.particle:nth-child(14) { animation-delay: 0.35s; --angle: 260deg; }
.particle:nth-child(15) { animation-delay: 0.35s; --angle: 280deg; }
.particle:nth-child(16) { animation-delay: 0.35s; --angle: 300deg; }
.particle:nth-child(17) { animation-delay: 0.35s; --angle: 320deg; }
.particle:nth-child(18) { animation-delay: 0.35s; --angle: 340deg; }
.particle:nth-child(19) { animation-delay: 0.4s; --angle: 10deg; }
.particle:nth-child(20) { animation-delay: 0.4s; --angle: 190deg; }

@keyframes particleExplode {
  0% {
    transform: translate(0, 0) scale(1);
    opacity: 0;
  }
  10% {
    opacity: 1;
  }
  100% {
    transform: translate(
      calc(cos(var(--angle)) * 150px),
      calc(sin(var(--angle)) * 150px)
    ) scale(0);
    opacity: 0;
  }
}

.fade-enter-active, .fade-leave-active {
  transition: opacity 0.3s ease;
}

.fade-enter-from, .fade-leave-to {
  opacity: 0;
}
</style>
