<template>
  <section class="hero">
    <div class="hero-content">
      <div class="title-wrapper">
        <h1 class="hero-title fade-in">Hongyu Xiao</h1>
      </div>
      <p class="hero-subtitle fade-in-delay">Human Genetics | Computational Genomics | Bioinformatics</p>
      <div class="hero-links fade-in-delay-2">
        <a href="https://www.linkedin.com/in/hongyuxiao12138/" target="_blank" class="hero-link social-link">
          <svg class="social-icon" viewBox="0 0 24 24" fill="currentColor">
            <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
          </svg>
          <span>LinkedIn</span>
        </a>
        <a href="https://github.com/xiaoh11" target="_blank" class="hero-link social-link">
          <svg class="social-icon" viewBox="0 0 24 24" fill="currentColor">
            <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
          </svg>
          <span>GitHub</span>
        </a>
      </div>
    </div>
    <div class="scroll-indicator">
      <div class="mouse">
        <div class="wheel"></div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Hero'
}
</script>

<style scoped>
.hero {
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  position: relative;
  background: linear-gradient(135deg, #000000 0%, #1a1a1a 100%);
}

.hero-content {
  z-index: 2;
  display: flex;
  flex-direction: column;
  align-items: center;
}

/* Title Wrapper */
.title-wrapper {
  position: relative;
  display: inline-block;
  padding: 0.5rem 0;
}

.hero-title {
  font-size: clamp(3rem, 8vw, 6rem);
  font-weight: 600;
  letter-spacing: -0.02em;
  margin-bottom: 0;
  background: linear-gradient(135deg, #ffffff 0%, #e0e0e0 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  position: relative;
  z-index: 1;
}

/* Enhanced silver shimmer effect */
.hero-title::before {
  content: 'Hongyu Xiao';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(
    110deg,
    transparent 0%,
    transparent 25%,
    rgba(255, 255, 255, 1) 40%,
    rgba(240, 240, 255, 1) 50%,
    rgba(255, 255, 255, 1) 60%,
    transparent 75%,
    transparent 100%
  );
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  background-size: 200% 100%;
  animation: silverShimmer 8s ease-in-out infinite;
  z-index: 2;
}

/* Enhanced glow effect */
.hero-title::after {
  content: '';
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 150%;
  height: 150%;
  background: radial-gradient(
    ellipse at center,
    rgba(255, 255, 255, 0.3) 0%,
    rgba(255, 255, 255, 0.15) 30%,
    transparent 70%
  );
  filter: blur(40px);
  opacity: 0;
  animation: softGlow 3s ease-in-out infinite;
  z-index: 0;
}

@keyframes silverShimmer {
  0% {
    background-position: -200% 0;
  }
  20% {
    background-position: -200% 0;
  }
  70% {
    background-position: 200% 0;
  }
  100% {
    background-position: 200% 0;
  }
}

@keyframes softGlow {
  0%, 20%, 100% {
    opacity: 0;
  }
  50% {
    opacity: 1;
  }
}

.hero-subtitle {
  font-size: clamp(1.2rem, 3vw, 1.8rem);
  color: var(--text-gray);
  font-weight: 300;
  margin-top: 2rem;
  margin-bottom: 2rem;
}

.hero-links {
  display: flex;
  gap: 1.5rem;
  justify-content: center;
}

.hero-link {
  padding: 0.8rem 2rem;
  background: var(--accent);
  color: white;
  text-decoration: none;
  border-radius: 980px;
  font-weight: 500;
  transition: var(--transition);
  font-size: 1rem;
}

.hero-link:hover {
  background: var(--accent-hover);
  transform: translateY(-2px);
  box-shadow: 0 10px 30px rgba(0, 113, 227, 0.3);
}

.social-link {
  display: flex;
  align-items: center;
  gap: 0.6rem;
  padding: 0.9rem 1.8rem;
  background: rgba(255, 255, 255, 0.08);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.2);
}

.social-link:hover {
  background: rgba(255, 255, 255, 0.15);
  border-color: rgba(255, 255, 255, 0.4);
  box-shadow: 0 8px 32px rgba(255, 255, 255, 0.1);
}

.social-icon {
  width: 20px;
  height: 20px;
  transition: var(--transition);
}

.social-link:hover .social-icon {
  transform: scale(1.1) rotate(-5deg);
}

.scroll-indicator {
  position: absolute;
  bottom: 3rem;
  animation: float 2s ease-in-out infinite;
}

.mouse {
  width: 24px;
  height: 36px;
  border: 2px solid var(--text-gray);
  border-radius: 12px;
  position: relative;
}

.wheel {
  width: 3px;
  height: 8px;
  background: var(--text-gray);
  border-radius: 2px;
  position: absolute;
  top: 8px;
  left: 50%;
  transform: translateX(-50%);
  animation: scroll 1.5s ease-in-out infinite;
}

@keyframes float {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(10px); }
}

@keyframes scroll {
  0% { opacity: 1; transform: translateX(-50%) translateY(0); }
  100% { opacity: 0; transform: translateX(-50%) translateY(12px); }
}

.fade-in {
  animation: fadeIn 1s ease-out;
}

.fade-in-delay {
  animation: fadeIn 1s ease-out 0.3s both;
}

.fade-in-delay-2 {
  animation: fadeIn 1s ease-out 0.6s both;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@media (max-width: 768px) {
  .hero-links {
    flex-direction: column;
  }
}
</style>
