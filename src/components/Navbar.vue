<template>
  <nav class="navbar">
    <div class="nav-content">
      <h2 class="nav-logo" @click="handleLogoClick">
        <span class="logo-short">HX</span>
      </h2>
      <div class="nav-links">
        <a href="#about">About</a>
        <a href="#education">Education</a>
        <a href="#research">Research</a>
        <a href="#skills">Skills</a>
        <a href="#contact">Contact</a>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'Navbar',
  methods: {
    handleLogoClick() {
      this.$emit('launch-rocket');
    }
  }
}
</script>

<style scoped>
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
  backdrop-filter: blur(20px);
  background: rgba(0, 0, 0, 0.8);
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
}

.nav-content {
  max-width: 1200px;
  margin: 0 auto;
  padding: 1rem 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.nav-logo {
  font-size: 1.5rem;
  font-weight: 600;
  color: var(--text-primary);
  position: relative;
  cursor: pointer;
  padding: 0.6rem 1.2rem;
  border-radius: 12px;
  background: rgba(255, 255, 255, 0.02);
  overflow: hidden;
  isolation: isolate;
}

.logo-short {
  display: inline;
  font-weight: 700;
  letter-spacing: 0.05em;
}

/* Rotating Border Light Effect */
.nav-logo::before {
  content: '';
  position: absolute;
  inset: -2px;
  background: conic-gradient(
    from 0deg,
    transparent 0deg,
    transparent 60deg,
    rgba(0, 113, 227, 0.8) 120deg,
    rgba(0, 170, 255, 0.9) 160deg,
    rgba(255, 255, 255, 0.6) 180deg,
    rgba(0, 170, 255, 0.9) 200deg,
    rgba(0, 113, 227, 0.8) 240deg,
    transparent 300deg,
    transparent 360deg
  );
  border-radius: 14px;
  animation: rotateBorder 4s linear infinite;
  z-index: -1;
}

.nav-logo::after {
  content: '';
  position: absolute;
  inset: 2px;
  background: rgba(0, 0, 0, 0.9);
  border-radius: 10px;
  z-index: -1;
}

@keyframes rotateBorder {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}

.nav-logo:hover::before {
  background: conic-gradient(
    from 0deg,
    transparent 0deg,
    transparent 40deg,
    rgba(0, 113, 227, 1) 100deg,
    rgba(0, 170, 255, 1) 140deg,
    rgba(255, 255, 255, 0.9) 180deg,
    rgba(0, 170, 255, 1) 220deg,
    rgba(0, 113, 227, 1) 260deg,
    transparent 320deg,
    transparent 360deg
  );
  animation: rotateBorder 2s linear infinite;
}

.logo-short {
  position: relative;
  z-index: 1;
  display: inline-block;
}

.nav-links {
  display: flex;
  gap: 2rem;
}

.nav-links a {
  color: var(--text-primary);
  text-decoration: none;
  font-size: 0.9rem;
  font-weight: 400;
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
  opacity: 0.8;
}

.nav-links a:hover {
  opacity: 1;
}

@media (max-width: 768px) {
  .nav-links {
    gap: 1rem;
  }

  .nav-links a {
    font-size: 0.8rem;
  }

  .nav-content {
    padding: 0.8rem 1.5rem;
  }
}
</style>
