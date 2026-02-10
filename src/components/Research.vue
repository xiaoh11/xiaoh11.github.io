<template>
  <section id="research" class="section light">
    <div class="container">
      <h2 class="section-title-center">Research Experience</h2>
      
      <div class="experience-grid">
        <!-- Master Thesis - Bravo -->
        <div class="experience-card">
          <div class="card-image project-preview" style="background-image: url('/Figure/bravo-screenshot.png')">
            <div class="preview-overlay">
              <span class="preview-text">CARTaGENE Variant Browser</span>
            </div>
          </div>
          <div class="card-content">
            <h3>CARTaGENE Variant Frequency Browser</h3>
            <p class="card-role">TOPMed-BRAVO Based Platform</p>
            <p class="card-text">
              <strong>CARTaGENE Cohort</strong><br/>
              Supervised by <u>Dr. Daniel Taliun</u> <br/>
              Sole Developer & Maintainer | Sep 2024 – Present<br/><br/>
              <strong>Key Achievements:</strong><br/>
              • Lead developer for Version 1.3.0 (75M+ variants, 2,173 genomes)<br/>
              • Developed new ClinVar annotation API module (Python/Flask)<br/>
              • Implemented genome-level missingness summary statistics<br/>
              • Enabled real-time ClinVar cohort comparisons <br/>
              
            </p>
            <div class="project-links">
              <a href="https://cartagene-bravo.cerc-genomic-medicine.ca/" target="_blank" class="project-btn">
                🔗 Launch CARTaGENE Variant Frequency Browser
              </a>
              <a href="https://www.nature.com/articles/s41467-026-68820-7" target="_blank" class="project-btn nature-btn">
                <svg class="nature-logo" viewBox="0 0 100 100" fill="currentColor">
                  <text x="10" y="70" font-family="serif" font-weight="bold" font-size="60" font-style="italic">N</text>
                </svg>
                <span>Nature Communications Publication</span>
              </a>
            </div>
          </div>
        </div>

        <!-- CLSA PheWeb -->
        <div class="experience-card">
          <div class="card-image project-preview" style="background-image: url('/Figure/pheweb-screenshot.png')">
            <div class="preview-overlay">
              <span class="preview-text">CLSA on PheWeb 2 Platform</span>
            </div>
          </div>
          <div class="card-content">
            <h3>PheWeb 2</h3>
            <p class="card-role">Stratified GWAS Visualization Platform</p>
            <p class="card-text">
              <strong>Canadian Longitudinal Study on Aging (CLSA)</strong><br/>
              Supervised by <u>Dr. Daniel Taliun</u> & <u>Dr. Sarah Gagliano Taliun</u><br/>
              Lead Developer & Maintainer | Sep 2024 – Present<br/><br/>
              <strong>Key Achievements:</strong><br/>
              • Full-stack development for stratified GWAS result visualization tool<br/>
              • Implemented by many different world-wide research groups<br/>
              • Bellavance, J.*, <strong>Xiao, H.*</strong> et al. Exploring and visualizing stratified GWAS results with PheWeb2. Nat Genet (2026).
            </p>
            <div class="project-links">
              <a href="https://clsa-pheweb.cerc-genomic-medicine.ca/" target="_blank" class="project-btn">
                🔗 Launch CLSA PheWeb 2
              </a>
              <a href="https://imaging-pheweb.cerc-genomic-medicine.ca/" target="_blank" class="project-btn">
                🔗 Launch UKB Imaging PheWeb 2
              </a>
              <a href="https://doi.org/10.1038/s41588-025-02469-8" target="_blank" class="project-btn nature-btn">
                <svg class="nature-logo" viewBox="0 0 100 100" fill="currentColor">
                  <text x="10" y="70" font-family="serif" font-weight="bold" font-size="60" font-style="italic">N</text>
                </svg>
                <span>Nature Genetics Publication</span>
              </a>
            </div>
          </div>
        </div>

        <!-- McMaster Research -->
        <div class="experience-card">
          <div class="card-image" style="background-image: url('/Figure/undergrad-thesis.png')"></div>
          <div class="card-content">
            <h3>Neuroscience Research</h3>
            <p class="card-role">Undergraduate Researcher</p>
            <p class="card-text">
              <strong>McMaster University</strong><br/>
              2019 – 2024<br/><br/>
              <strong>METRE Lab</strong> (Dr. Jonathan Cannon)<br/>
              • Computational modeling of human internal rhythmic-motor control<br/>
              • Haptic robotic application in psychophysical experiments<br/><br/>
              <strong>Goldreich's Lab</strong> (Dr. Daniel Goldreich)<br/>
              • Tactile perception studies<br/>
              • Bayesian inference in human tactile perception
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Research',
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

.section.light {
  background: var(--bg-secondary);
  color: var(--text-secondary);
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

.project-preview {
  background-size: contain;
  background-repeat: no-repeat;
  background-color: #f5f5f7;
  cursor: pointer;
  position: relative;
  overflow: hidden;
}

.preview-overlay {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  background: linear-gradient(to top, rgba(0, 0, 0, 0.8), transparent);
  padding: 1rem;
  opacity: 0;
  transition: var(--transition);
}

.project-preview:hover .preview-overlay {
  opacity: 1;
}

.preview-text {
  color: white;
  font-weight: 600;
  font-size: 0.95rem;
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
}

.card-content {
  padding: 2rem;
}

.card-content h3 {
  font-size: 1.8rem;
  margin-bottom: 0.5rem;
  font-weight: 600;
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

.project-links {
  margin-top: 1.5rem;
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
}

.project-btn {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.75rem 1.5rem;
  background: var(--accent);
  color: white;
  text-decoration: none;
  border-radius: 8px;
  font-weight: 500;
  font-size: 0.95rem;
  transition: var(--transition);
  box-shadow: 0 2px 8px rgba(0, 113, 227, 0.2);
}

.project-btn:hover {
  background: var(--accent-hover);
  transform: translateY(-2px);
  box-shadow: 0 4px 16px rgba(0, 113, 227, 0.3);
}

/* Nature Genetics Button */
.nature-btn {
  background: linear-gradient(135deg, #c41e3a 0%, #8b1a2e 100%);
  border: 1px solid rgba(255, 255, 255, 0.2);
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.nature-btn:hover {
  background: linear-gradient(135deg, #d42842 0%, #9c1f35 100%);
  box-shadow: 0 4px 16px rgba(196, 30, 58, 0.4);
}

.nature-logo {
  width: 24px;
  height: 24px;
  fill: white;
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
