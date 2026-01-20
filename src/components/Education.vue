<template>
  <section id="education" class="section dark">
    <div class="container">
      <h2 class="section-title-center">Education</h2>
      
      <div class="experience-grid">
        <!-- McGill -->
        <div class="experience-card">
          <div class="card-image" style="background-image: url('/Figure/flower.jpg')"></div>
          <div class="card-content">
            <h3>McGill</h3>
            <p class="card-location">Quebec, Canada</p>
            <p class="card-role">M.Sc. in Human Genetics</p>
            <p class="card-text">
              <strong>cGPA: 4.0/4.0</strong><br/>
              Sep 2024 – Present<br/>
              <em>McGill CERC Program in Genomic Medicine</em><br/>
              Focus: Computational Genomics, Bioinformatics, Web-based Genomic Tools
            </p>
          </div>
        </div>

        <!-- McMaster -->
        <div class="experience-card">
          <div class="card-image" style="background-image: url('/Figure/IMG_2787.JPG')"></div>
          <div class="card-content">
            <h3>McMaster</h3>
            <p class="card-location">Ontario, Canada</p>
            <p class="card-role">Honours B.Sc. in Neuroscience</p>
            <p class="card-text">
              <strong>Summa cum laude | cGPA: 3.95/4.0</strong><br/>
              Sep 2019 – Apr 2024<br/>
              Focus: Computational & Cognitive Neuroscience
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Education',
  mounted() {
    const observerOptions = {
      threshold: 0.1,
      rootMargin: '0px 0px -100px 0px'
    };

    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible');
        }
      });
    }, observerOptions);

    document.querySelectorAll('.experience-card').forEach(el => {
      observer.observe(el);
    });
  }
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

.section.dark {
  background: var(--bg-primary);
  color: var(--text-primary);
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  width: 100%;
}

.section-title-center {
  font-size: clamp(2rem, 5vw, 3.5rem);
  font-weight: 600;
  margin-bottom: 4rem;
  text-align: center;
  letter-spacing: -0.02em;
}

.experience-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
  gap: 3rem;
  margin-top: 2rem;
}

.experience-card {
  background: rgba(255, 255, 255, 0.05);
  border-radius: var(--border-radius);
  overflow: hidden;
  transition: var(--transition);
  opacity: 0;
  transform: translateY(30px);
}

.experience-card.visible {
  opacity: 1;
  transform: translateY(0);
}

.experience-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
}

.card-image {
  width: 100%;
  height: 250px;
  background-size: cover;
  background-position: center;
  position: relative;
}

.card-content {
  padding: 2rem;
}

.card-content h3 {
  font-size: 1.8rem;
  margin-bottom: 0.5rem;
  font-weight: 600;
}

.card-location {
  color: var(--text-gray);
  font-size: 0.9rem;
  margin-bottom: 0.5rem;
}

.card-role {
  color: var(--accent);
  font-weight: 500;
  margin-bottom: 1rem;
}

.card-text {
  line-height: 1.7;
  opacity: 0.9;
}

@media (max-width: 768px) {
  .experience-grid {
    grid-template-columns: 1fr;
    gap: 2rem;
  }

  .section {
    padding: 4rem 1.5rem;
  }
}
</style>
