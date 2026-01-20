<template>
  <section id="about" class="section light">
    <div class="container">
      <div class="section-content">
        <h2 class="section-title">About Me</h2>
        <p class="section-text">
            For the past few years, my work focuses on developing secure web-based tools and applications for genomic data 
            analysis, with experience in full-stack development, data visualization, and large-scale genomic data processing. 
        </p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'About'
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

@media (max-width: 768px) {
  .section {
    padding: 4rem 1.5rem;
  }
}
</style>
