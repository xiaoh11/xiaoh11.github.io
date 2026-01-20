<template>
  <section id="contact" class="section light">
    <div class="container">
      <div class="section-content">
        <h2 class="section-title">Get In Touch</h2>
        <p class="section-text">
          Feel free to reach out for collaborations, questions, or just to say hi!
        </p>
        
        <GlobeD3 />
        
        <div class="contact-methods">
          <a href="mailto:hongyu.xiao@mail.mcgill.ca" class="contact-card">
            <div class="contact-icon">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"/>
              </svg>
            </div>
            <div class="contact-info">
              <h3>Email</h3>
              <p>hongyu.xiao@mail.mcgill.ca</p>
            </div>
          </a>

          <a href="https://www.linkedin.com/in/hongyuxiao12138/" target="_blank" class="contact-card">
            <div class="contact-icon">
              <svg viewBox="0 0 24 24" fill="currentColor">
                <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
              </svg>
            </div>
            <div class="contact-info">
              <h3>LinkedIn</h3>
              <p>Connect with me</p>
            </div>
          </a>

          <a href="https://github.com/xiaoh11" target="_blank" class="contact-card">
            <div class="contact-icon">
              <svg viewBox="0 0 24 24" fill="currentColor">
                <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
              </svg>
            </div>
            <div class="contact-info">
              <h3>GitHub</h3>
              <p>View my projects</p>
            </div>
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import GlobeD3 from './GlobeD3.vue'

export default {
  name: 'Contact',
  components: {
    GlobeD3
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

.section-content {
  max-width: 900px;
  margin: 0 auto;
  text-align: center;
}

.section-title {
  font-size: clamp(2rem, 5vw, 3.5rem);
  font-weight: 600;
  margin-bottom: 1.5rem;
  letter-spacing: -0.02em;
}

.section-text {
  font-size: 1.125rem;
  line-height: 1.7;
  color: var(--text-gray);
  margin-bottom: 4rem;
}

.contact-methods {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
  margin-top: 3rem;
}

.contact-card {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1.5rem;
  padding: 2.5rem 2rem;
  background: rgba(255, 255, 255, 0.6);
  backdrop-filter: blur(10px);
  border-radius: 20px;
  border: 1px solid rgba(0, 0, 0, 0.05);
  text-decoration: none;
  color: inherit;
  transition: var(--transition);
  cursor: pointer;
}

.contact-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 20px 60px rgba(0, 0, 0, 0.1);
  background: rgba(255, 255, 255, 0.8);
  border-color: rgba(0, 113, 227, 0.2);
}

.contact-icon {
  width: 60px;
  height: 60px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: linear-gradient(135deg, rgba(0, 113, 227, 0.1), rgba(0, 170, 255, 0.1));
  border-radius: 16px;
  transition: var(--transition);
}

.contact-card:hover .contact-icon {
  transform: scale(1.1) rotate(-5deg);
  background: linear-gradient(135deg, rgba(0, 113, 227, 0.2), rgba(0, 170, 255, 0.2));
}

.contact-icon svg {
  width: 32px;
  height: 32px;
  color: var(--accent);
}

.contact-info {
  text-align: center;
}

.contact-info h3 {
  font-size: 1.3rem;
  font-weight: 600;
  margin-bottom: 0.5rem;
  color: var(--text-secondary);
}

.contact-info p {
  font-size: 0.95rem;
  color: var(--text-gray);
  word-break: break-word;
}

@media (max-width: 768px) {
  .contact-methods {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }

  .section {
    padding: 4rem 1.5rem;
  }
}
</style>
