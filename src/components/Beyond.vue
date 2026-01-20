<template>
  <section class="section light">
    <div class="container">
      <div class="section-content">
        <img src="/Figure/voice.png" alt="Music" class="feature-icon music-icon" width="100" height="100"/>
        <h2 class="section-title">Beyond Research</h2>
        <p class="section-text">
          I love playing guitar and making all kinds of synthetic music.    
        </p>
        <div class="skills">
          <span class="skill-tag">Guitar</span>
          <span class="skill-tag">Logic Pro</span>
          <span class="skill-tag">FL Studio</span>
          <span class="skill-tag">Serum</span>
          <span class="skill-tag">MIDI Keyboard</span>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Beyond'
}
</script>

<style scoped>
.section {
  min-height: 100vh;
  display: flex;
  align-items: center;
  padding: 6rem 2rem;
  opacity: 0;
  transform: translateY(50px);
  transition: opacity 1s ease, transform 1s ease;
}

.section.visible {
  opacity: 1;
  transform: translateY(0);
}

.section.light {
  background: var(--bg-secondary);
  color: var(--text-secondary);
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  width: 100%;
}

.section-content {
  max-width: 800px;
  margin: 0 auto;
  text-align: center;
}

.feature-icon {
  width: 100%;
  height: 100%;
  margin-bottom: 2rem;
  opacity: 0.9;
}

.music-icon {
  opacity: 0.6;
}

.section-title {
  font-size: clamp(2rem, 5vw, 3.5rem);
  font-weight: 600;
  margin-bottom: 2rem;
  letter-spacing: -0.02em;
}

.section-text {
  font-size: 1.125rem;
  line-height: 1.7;
  color: inherit;
  opacity: 0.9;
  margin-bottom: 2rem;
}

.skills {
  display: flex;
  gap: 1rem;
  justify-content: center;
  flex-wrap: wrap;
  margin-top: 2rem;
}

.skill-tag {
  padding: 0.6rem 1.5rem;
  background: rgba(0, 113, 227, 0.1);
  color: var(--accent);
  border-radius: 980px;
  font-size: 0.9rem;
  font-weight: 500;
  transition: var(--transition);
}

.skill-tag:hover {
  background: rgba(0, 113, 227, 0.2);
  transform: translateY(-2px);
}

@media (max-width: 768px) {
  .section {
    padding: 4rem 1.5rem;
  }
}
</style>
