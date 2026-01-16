<template>
  <div id="app">
    <!-- Navigation -->
    <nav class="navbar">
      <div class="nav-content">
        <h2 class="nav-logo">
          <span class="logo-short">HX</span>
        </h2>
        <div class="nav-links">
          <a href="#about">About</a>
          <a href="#education">Education</a>
          <a href="#research">Research</a>
          <a href="#skills">Skills</a>
        </div>
      </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero">
      <div class="hero-content">
        <h1 class="hero-title fade-in">Hongyu Xiao</h1>
        <p class="hero-subtitle fade-in-delay">M.Sc. in Human Genetics | Computational Genomics</p>
        <p class="hero-subtext fade-in-delay">McGill University | McMaster University</p>
        <div class="hero-links fade-in-delay-2">
          <a href="https://www.linkedin.com/in/hongyuxiao12138/" target="_blank" class="hero-link">
            <span>LinkedIn</span>
          </a>
          <a href="https://github.com/xiaoh11" target="_blank" class="hero-link">
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

    <!-- About Section -->
    <section id="about" class="section light">
      <div class="container">
        <div class="section-content">
          <h2 class="section-title">About Me</h2>
          <p class="section-text">
            I am a Master's student in Human Genetics at McGill University, specializing in Computational Genomics 
            and Bioinformatics. My research focuses on developing web-based tools and applications for genomic data 
            analysis, with expertise in full-stack development, data visualization, and large-scale genomic data processing. 
            I am passionate about creating accessible and interactive platforms that bridge the gap between complex 
            genomic datasets and researchers.
          </p>
        </div>
      </div>
    </section>

    <!-- Education Section -->
    <section id="education" class="section dark">
      <div class="container">
        <h2 class="section-title-center">Education</h2>
        
        <div class="experience-grid">
          <!-- McGill -->
          <div class="experience-card">
            <div class="card-image" style="background-image: url('/Figure/flower.jpg')"></div>
            <div class="card-content">
              <h3>McGill University</h3>
              <p class="card-location">Quebec, Canada</p>
              <p class="card-role">M.Sc. in Human Genetics</p>
              <p class="card-text">
                <strong>cGPA: 4.0/4.4</strong><br/>
                Sep 2024 – Present<br/>
                Focus: Computational Genomics, Bioinformatics, Web-based Genomic Tools
              </p>
            </div>
          </div>

          <!-- McMaster -->
          <div class="experience-card">
            <div class="card-image" style="background-image: url('/Figure/IMG_2787.JPG')"></div>
            <div class="card-content">
              <h3>McMaster University</h3>
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

    <!-- Research Experience -->
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
              <h3>CARTaGENE Variant Browser</h3>
              <p class="card-role">Master Thesis Project | Bravo-Based Platform</p>
              <p class="card-text">
                <strong>McGill CERC Program in Genomic Medicine</strong><br/>
                Lead Developer & Maintainer | Sep 2024 – Present<br/><br/>
                <strong>Key Achievements:</strong><br/>
                • Lead developer for Version 1.3.0 (75M+ variants, 2,173 genomes)<br/>
                • Developed new ClinVar annotation API module (Python/Flask)<br/>
                • Implemented genome-level missingness summary statistics<br/>

                • Enabled real-time ClinVar cohort comparisons
              </p>
              <div class="project-links">
                <a href="https://cartagene-bravo.cerc-genomic-medicine.ca/" target="_blank" class="project-btn">
                  🔗 Launch CARTaGENE Browser
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
                Lead Developer & Maintainer | Sep 2024 – Present<br/><br/>
                <strong>Key Achievements:</strong><br/>
                • Full-stack development for stratified GWAS result visualization tool<br/>
                • Demonstrated how and why stratified GWAS result and its sharing is critical<br/>

              </p>
              <div class="project-links">
                <a href="https://clsa-pheweb.cerc-genomic-medicine.ca/" target="_blank" class="project-btn">
                  🔗 Launch CLSA PheWeb
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

    <!-- Technical Skills Section -->
    <section id="skills" class="section dark">
      <div class="container">
        <h2 class="section-title-center">Technical Skills</h2>
        
        <div class="skills-layout">
          <!-- Scrolling Programming Languages Column -->
          <div class="programming-scroll-column">
            <h3 class="scroll-column-title">Programming Languages</h3>
            <div class="scroll-track">
              <div class="scroll-content">
                <div class="lang-item">
                  <div class="lang-icon">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" alt="Python" />
                  </div>
                  <span class="lang-name">Python</span>
                </div>
                <div class="lang-item">
                  <div class="lang-icon">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/r/r-original.svg" alt="R" />
                  </div>
                  <span class="lang-name">R</span>
                </div>
                <div class="lang-item">
                  <div class="lang-icon">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" alt="JavaScript" />
                  </div>
                  <span class="lang-name">JavaScript</span>
                </div>
                <div class="lang-item">
                  <div class="lang-icon">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/bash/bash-original.svg" alt="Bash" />
                  </div>
                  <span class="lang-name">Bash</span>
                </div>
                <div class="lang-item">
                  <div class="lang-icon">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/cplusplus/cplusplus-original.svg" alt="C++" />
                  </div>
                  <span class="lang-name">C++</span>
                </div>
                <div class="lang-item">
                  <div class="lang-icon">
                    <svg viewBox="0 0 24 24" fill="currentColor">
                      <path d="M12 2L2 7v10c0 5.55 3.84 10.74 9 12 5.16-1.26 9-6.45 9-12V7l-10-5zm0 2.18l8 3.82v8.53c0 4.29-3.12 8.35-8 9.47-4.88-1.12-8-5.18-8-9.47V7.82l8-3.64z"/>
                      <path d="M7 12l2 2 5-5 1.5 1.5L9 17 5.5 13.5z"/>
                    </svg>
                  </div>
                  <span class="lang-name">Nextflow</span>
                </div>
                <!-- Duplicate for seamless loop -->
                <div class="lang-item">
                  <div class="lang-icon">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" alt="Python" />
                  </div>
                  <span class="lang-name">Python</span>
                </div>
                <div class="lang-item">
                  <div class="lang-icon">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/r/r-original.svg" alt="R" />
                  </div>
                  <span class="lang-name">R</span>
                </div>
                <div class="lang-item">
                  <div class="lang-icon">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" alt="JavaScript" />
                  </div>
                  <span class="lang-name">JavaScript</span>
                </div>
                <div class="lang-item">
                  <div class="lang-icon">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/bash/bash-original.svg" alt="Bash" />
                  </div>
                  <span class="lang-name">Bash</span>
                </div>
                <div class="lang-item">
                  <div class="lang-icon">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/cplusplus/cplusplus-original.svg" alt="C++" />
                  </div>
                  <span class="lang-name">C++</span>
                </div>
                <div class="lang-item">
                  <div class="lang-icon">
                    <svg viewBox="0 0 24 24" fill="currentColor">
                      <path d="M12 2L2 7v10c0 5.55 3.84 10.74 9 12 5.16-1.26 9-6.45 9-12V7l-10-5zm0 2.18l8 3.82v8.53c0 4.29-3.12 8.35-8 9.47-4.88-1.12-8-5.18-8-9.47V7.82l8-3.64z"/>
                      <path d="M7 12l2 2 5-5 1.5 1.5L9 17 5.5 13.5z"/>
                    </svg>
                  </div>
                  <span class="lang-name">Nextflow</span>
                </div>
              </div>
            </div>
          </div>

          <!-- Static Skills Grid -->
          <div class="masonry-grid">

          <!-- Web Development Card -->
          <div class="skill-card">
            <div class="skill-card-icon">🌐</div>
            <h3 class="skill-card-title">Web Development</h3>
            <div class="skill-card-tags">
              <span class="skill-chip">Vue 3</span>
              <span class="skill-chip">Vite</span>
              <span class="skill-chip">Flask</span>
              <span class="skill-chip">REST API</span>
              <span class="skill-chip">Vuetify</span>
            </div>
          </div>

          <!-- Genomics Card -->
          <div class="skill-card skill-card-large">
            <div class="skill-card-icon">🧬</div>
            <h3 class="skill-card-title">Genomics & Bioinformatics</h3>
            <div class="skill-card-tags">
              <span class="skill-chip">VCF/BCF</span>
              <span class="skill-chip">Bedtools</span>
              <span class="skill-chip">pysam</span>
              <span class="skill-chip">GWAS</span>
              <span class="skill-chip">REGENIE</span>
              <span class="skill-chip">KING</span>
              <span class="skill-chip">PLINK 2</span>
              <span class="skill-chip">PCA/Ancestry</span>
            </div>
          </div>

          <!-- Data Viz Card -->
          <div class="skill-card">
            <div class="skill-card-icon">📊</div>
            <h3 class="skill-card-title">Data Visualization</h3>
            <div class="skill-card-tags">
              <span class="skill-chip">D3.js</span>
              <span class="skill-chip">Chart.js</span>
              <span class="skill-chip">Interactive QC</span>
              <span class="skill-chip">Manhattan Plots</span>
            </div>
          </div>

          <!-- HPC Card -->
          <div class="skill-card">
            <div class="skill-card-icon">⚡</div>
            <h3 class="skill-card-title">HPC & DevOps</h3>
            <div class="skill-card-tags">
              <span class="skill-chip">SLURM</span>
              <span class="skill-chip">Docker</span>
              <span class="skill-chip">Apptainer</span>
              <span class="skill-chip">Linux/Unix</span>
              <span class="skill-chip">SSH</span>
            </div>
          </div>

          <!-- ML Card -->
          <div class="skill-card">
            <div class="skill-card-icon">🤖</div>
            <h3 class="skill-card-title">Machine Learning</h3>
            <div class="skill-card-tags">
              <span class="skill-chip">scikit-learn</span>
              <span class="skill-chip">TensorFlow</span>
              <span class="skill-chip">Keras</span>
              <span class="skill-chip">ROC/AUC</span>
              <span class="skill-chip">Cross-validation</span>
            </div>
          </div>

          <!-- Tools Card -->
          <div class="skill-card skill-card-large">
            <div class="skill-card-icon">🛠️</div>
            <h3 class="skill-card-title">Tools & Productivity</h3>
            <div class="skill-card-tags">
              <span class="skill-chip">Git/GitHub</span>
              <span class="skill-chip">VS Code</span>
              <span class="skill-chip">Cursor</span>
              <span class="skill-chip">Adobe Illustrator</span>
              <span class="skill-chip">Photoshop</span>
              <span class="skill-chip">ChatGPT</span>
              <span class="skill-chip">Claude</span>
            </div>
          </div>

          <!-- Databases Card -->
          <div class="skill-card">
            <div class="skill-card-icon">🗄️</div>
            <h3 class="skill-card-title">Data Processing</h3>
            <div class="skill-card-tags">
              <span class="skill-chip">Pandas</span>
              <span class="skill-chip">NumPy</span>
              <span class="skill-chip">Data Wrangling</span>
              <span class="skill-chip">Feature Engineering</span>
            </div>
          </div>
        </div>
        </div>
      </div>
    </section>

    <!-- Beyond Research Section -->
    <section class="section light">
      <div class="container">
        <div class="section-content">
          <img src="/Figure/voice.png" alt="Music" class="feature-icon music-icon" width="100" height="100"/>
          <h2 class="section-title">Beyond Research</h2>
          <p class="section-text">
            Research isn't the only thing in my life. I can't imagine my life without music.
          </p>
          <div class="skills">
            <span class="skill-tag">Guitar</span>
            <span class="skill-tag">Logic Pro</span>
            <span class="skill-tag">MIDI Keyboard</span>
          </div>
        </div>
      </div>
    </section>

    <!-- Gallery Section -->
    <section class="gallery">
      <div class="gallery-grid">
        <div class="gallery-item" style="background-image: url('/Figure/IMG_1667 2.JPG')"></div>
        <div class="gallery-item" style="background-image: url('/Figure/IMG_1668.JPG')"></div>
        <div class="gallery-item" style="background-image: url('/Figure/IMG_9058.jpg')"></div>
      </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
      <p>Photography by Hongyu Xiao</p>
      <p>© 2026 Hongyu Xiao | All rights reserved</p>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'App',
  mounted() {
    // Smooth scroll for navigation links
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
      anchor.addEventListener('click', function (e) {
        e.preventDefault();
        const target = document.querySelector(this.getAttribute('href'));
        if (target) {
          target.scrollIntoView({
            behavior: 'smooth',
            block: 'start'
          });
        }
      });
    });

    // Intersection Observer for scroll animations
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

    document.querySelectorAll('.section, .experience-card').forEach(el => {
      observer.observe(el);
    });
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

:root {
  --bg-primary: #000000;
  --bg-secondary: #ffffff;
  --text-primary: #ffffff;
  --text-secondary: #000000;
  --text-gray: #86868b;
  --accent: #0071e3;
  --accent-hover: #0077ed;
  --border-radius: 18px;
  --transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
}

body {
  font-family: -apple-system, BlinkMacSystemFont, "SF Pro Display", "SF Pro Text", "Helvetica Neue", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background: var(--bg-primary);
  color: var(--text-primary);
  overflow-x: hidden;
}

#app {
  width: 100%;
}

/* Navigation */
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
  display: none;
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

/* Inner background to hide center */
.nav-logo::after {
  content: '';
  position: absolute;
  inset: 2px;
  background: rgba(0, 0, 0, 0.9);
  border-radius: 10px;
  z-index: -1;
}

@keyframes rotateBorder {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}

/* Enhanced glow on hover */
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

/* Logo text styling */
.logo-full,
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
  transition: var(--transition);
  opacity: 0.8;
}

.nav-links a:hover {
  opacity: 1;
}

/* Hero Section */
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
}

.hero-title {
  font-size: clamp(3rem, 8vw, 6rem);
  font-weight: 600;
  letter-spacing: -0.02em;
  margin-bottom: 1rem;
  background: linear-gradient(135deg, #ffffff 0%, #a0a0a0 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.hero-subtitle {
  font-size: clamp(1.2rem, 3vw, 1.8rem);
  color: var(--text-gray);
  font-weight: 300;
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

/* Scroll Indicator */
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

/* Fade In Animations */
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

/* Sections */
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

.section.dark {
  background: var(--bg-primary);
  color: var(--text-primary);
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

.section-title-center {
  font-size: clamp(2rem, 5vw, 3.5rem);
  font-weight: 600;
  margin-bottom: 4rem;
  text-align: center;
  letter-spacing: -0.02em;
}

.section-text {
  font-size: 1.125rem;
  line-height: 1.7;
  color: inherit;
  opacity: 0.9;
  margin-bottom: 2rem;
}

.section.light .section-text {
  color: var(--text-secondary);
}

/* Skills */
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

/* Skills Layout Container */
.skills-layout {
  display: grid;
  grid-template-columns: 300px 1fr;
  gap: 3rem;
  max-width: 1400px;
  margin: 0 auto;
}

/* Programming Scroll Column */
.programming-scroll-column {
  background: rgba(255, 255, 255, 0.03);
  border-radius: 20px;
  padding: 2rem;
  border: 1px solid rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(10px);
  position: sticky;
  top: 100px;
  height: fit-content;
  max-height: 600px;
}

.scroll-column-title {
  font-size: 1.3rem;
  font-weight: 600;
  color: var(--text-primary);
  text-align: center;
  margin-bottom: 1.5rem;
  opacity: 0.9;
}

.scroll-track {
  height: 400px;
  overflow: hidden;
  position: relative;
  mask-image: linear-gradient(
    to bottom,
    transparent 0%,
    black 15%,
    black 85%,
    transparent 100%
  );
  -webkit-mask-image: linear-gradient(
    to bottom,
    transparent 0%,
    black 15%,
    black 85%,
    transparent 100%
  );
}

.scroll-content {
  animation: infiniteScroll 20s linear infinite;
}

.scroll-content:hover {
  animation-play-state: paused;
}

@keyframes infiniteScroll {
  0% {
    transform: translateY(0);
  }
  100% {
    transform: translateY(-50%);
  }
}

.lang-item {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 1.2rem 1.5rem;
  margin-bottom: 0.8rem;
  background: rgba(255, 255, 255, 0.05);
  border-radius: 12px;
  border: 1px solid rgba(255, 255, 255, 0.08);
  transition: var(--transition);
}

.lang-item:hover {
  background: rgba(0, 113, 227, 0.15);
  border-color: rgba(0, 113, 227, 0.3);
  transform: translateX(5px);
}

.lang-icon {
  width: 48px;
  height: 48px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: rgba(255, 255, 255, 0.05);
  border-radius: 10px;
  flex-shrink: 0;
}

.lang-icon img,
.lang-icon svg {
  width: 32px;
  height: 32px;
  object-fit: contain;
  transition: var(--transition);
}

.lang-icon svg {
  fill: var(--text-primary);
  opacity: 0.9;
}

.lang-item:hover .lang-icon img,
.lang-item:hover .lang-icon svg {
  transform: scale(1.1);
}

.lang-name {
  font-size: 1.1rem;
  font-weight: 500;
  color: var(--text-primary);
}

/* Masonry Grid Layout */
.masonry-grid {
  column-count: 2;
  column-gap: 2rem;
}

@media (max-width: 1200px) {
  .skills-layout {
    grid-template-columns: 280px 1fr;
    gap: 2rem;
  }
  
  .masonry-grid {
    column-count: 2;
  }
}

@media (max-width: 900px) {
  .skills-layout {
    grid-template-columns: 1fr;
    gap: 3rem;
  }
  
  .programming-scroll-column {
    position: relative;
    top: 0;
    max-width: 400px;
    margin: 0 auto;
  }
  
  .masonry-grid {
    column-count: 2;
  }
}

@media (max-width: 640px) {
  .masonry-grid {
    column-count: 1;
  }
}

/* Skill Cards */
.skill-card {
  break-inside: avoid;
  page-break-inside: avoid;
  background: rgba(255, 255, 255, 0.05);
  border-radius: 16px;
  padding: 2rem;
  margin-bottom: 2rem;
  transition: var(--transition);
  border: 1px solid rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(10px);
}

.skill-card:hover {
  transform: translateY(-5px);
  background: rgba(255, 255, 255, 0.08);
  border-color: rgba(0, 113, 227, 0.3);
  box-shadow: 0 10px 30px rgba(0, 113, 227, 0.2);
}

.skill-card-large {
  /* Larger cards for more important categories */
}

.skill-card-icon {
  font-size: 2.5rem;
  margin-bottom: 1rem;
  text-align: center;
  filter: grayscale(30%);
  transition: var(--transition);
}

.skill-card:hover .skill-card-icon {
  filter: grayscale(0%);
  transform: scale(1.1);
}

.skill-card-title {
  font-size: 1.3rem;
  font-weight: 600;
  margin-bottom: 1.5rem;
  color: var(--text-primary);
  text-align: center;
}

.skill-card-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  justify-content: center;
}

.skill-chip {
  padding: 0.5rem 1rem;
  background: rgba(0, 113, 227, 0.15);
  color: var(--accent);
  border-radius: 20px;
  font-size: 0.85rem;
  font-weight: 500;
  transition: var(--transition);
  border: 1px solid rgba(0, 113, 227, 0.2);
}

.skill-chip:hover {
  background: rgba(0, 113, 227, 0.25);
  transform: scale(1.05);
  border-color: var(--accent);
}

.card-location {
  color: var(--text-gray);
  font-size: 0.9rem;
  margin-bottom: 0.5rem;
}

.hero-subtext {
  font-size: clamp(1rem, 2vw, 1.2rem);
  color: var(--text-gray);
  font-weight: 300;
  margin-bottom: 2rem;
  opacity: 0.8;
}

/* Experience Grid */
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

.card-text a {
  color: var(--accent);
  text-decoration: none;
  border-bottom: 1px solid transparent;
  transition: var(--transition);
}

.card-text a:hover {
  border-bottom-color: var(--accent);
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

/* Gallery */
.gallery {
  background: var(--bg-primary);
  padding: 0;
}

.gallery-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 0;
}

.gallery-item {
  height: 400px;
  background-size: cover;
  background-position: center;
  transition: var(--transition);
  cursor: pointer;
}

.gallery-item:hover {
  transform: scale(1.05);
  z-index: 10;
}

/* Footer */
.footer {
  background: var(--bg-primary);
  padding: 3rem 2rem;
  text-align: center;
  color: var(--text-gray);
  font-size: 0.9rem;
  line-height: 1.8;
}

/* Responsive */
@media (max-width: 768px) {
  .nav-links {
    gap: 1rem;
  }

  .nav-links a {
    font-size: 0.8rem;
  }

  /* Show HX on mobile */
  .logo-full {
    display: none;
  }

  .logo-short {
    display: inline;
    font-weight: 700;
    letter-spacing: 0.05em;
  }

  .experience-grid {
    grid-template-columns: 1fr;
    gap: 2rem;
  }

  .hero-links {
    flex-direction: column;
  }

  .section {
    padding: 4rem 1.5rem;
  }

  .nav-content {
    padding: 0.8rem 1.5rem;
  }
}

/* Smooth Scrolling */
html {
  scroll-behavior: smooth;
}
</style>
