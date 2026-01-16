<template>
  <div id="app">
    <!-- Navigation -->
    <nav class="navbar">
      <div class="nav-content">
        <h2 class="nav-logo">Hongyu Xiao</h2>
        <div class="nav-links">
          <a href="#about">About</a>
          <a href="#research">Research</a>
          <a href="#experience">Experience</a>
          <a href="#music">Music</a>
        </div>
      </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero">
      <div class="hero-content">
        <h1 class="hero-title fade-in">Hongyu Xiao</h1>
        <p class="hero-subtitle fade-in-delay">Computational Neuroscience Researcher</p>
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
          <img src="/Figure/brain.png" alt="Brain" class="feature-icon" />
          <h2 class="section-title">Research Interests</h2>
          <p class="section-text">
            My research interests lie in Computational Neuroscience. 
            I am eager to utilize computational methodologies, models, and analysis to examine the nervous system 
            from both systemic and cognitive perspectives. For instance, I have a strong interest in building 
            computational observer models and juxtaposing their outcomes with human performance. 
            Additionally, I am enthusiastic about creating mechanistic models in neuroscience, integrating aspects 
            of biophysics, biochemistry, probabilistic theories, and information theory.
          </p>
        </div>
      </div>
    </section>

    <!-- Research Experience -->
    <section id="research" class="section dark">
      <div class="container">
        <h2 class="section-title-center">Research Experience</h2>
        
        <div class="experience-grid">
          <!-- McGill -->
          <div class="experience-card">
            <div class="card-image" style="background-image: url('/Figure/flower.jpg')"></div>
            <div class="card-content">
              <h3>McGill University</h3>
              <p class="card-role">Full-Stack Developer</p>
              <p class="card-text">
                <strong>The McGill CERC Program in Genomic Medicine</strong><br/>
                Under supervision of Dr. Daniel Taliun<br/>
                Built: <a href="https://cartagene-bravo.cerc-genomic-medicine.ca/" target="_blank">CARTaGENE Variant Browser</a>
              </p>
            </div>
          </div>

          <!-- McMaster -->
          <div class="experience-card">
            <div class="card-image" style="background-image: url('/Figure/IMG_2787.JPG')"></div>
            <div class="card-content">
              <h3>McMaster University</h3>
              <p class="card-role">Research Assistant</p>
              <p class="card-text">
                <strong>TRIMBA Lab</strong> - Dr. Jonathan Cannon<br/>
                <strong>Goldreich's Lab</strong> - Dr. Daniel Goldreich<br/>
                Focus: Computational & Cognitive NeuroSci, Bayesian Inference, Rhythmic & Tactile Perception
              </p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Music Section -->
    <section id="music" class="section light">
      <div class="container">
        <div class="section-content">
          <img src="/Figure/voice.png" alt="Music" class="feature-icon music-icon" />
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
      <p>© 2026 - Designed with Vue 3</p>
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
  width: 100px;
  height: 100px;
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
}

/* Smooth Scrolling */
html {
  scroll-behavior: smooth;
}
</style>
