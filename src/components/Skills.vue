<template>
  <section id="skills" class="section dark">
    <div class="container">
      <h2 class="section-title-center">Technical Skills</h2>
      
      <div class="skills-layout">
        <!-- Scrolling Programming Languages Column -->
        <div class="programming-scroll-column">
          <h3 class="scroll-column-title">Programming Languages</h3>
          <div class="scroll-track">
            <div class="scroll-content">
              <div class="lang-item" v-for="(lang, index) in languages" :key="`lang-${index}`">
                <div class="lang-icon">
                  <img v-if="lang.icon" :src="lang.icon" :alt="lang.name" />
                  <svg v-else viewBox="0 0 24 24" fill="currentColor">
                    <path d="M12 2L2 7v10c0 5.55 3.84 10.74 9 12 5.16-1.26 9-6.45 9-12V7l-10-5zm0 2.18l8 3.82v8.53c0 4.29-3.12 8.35-8 9.47-4.88-1.12-8-5.18-8-9.47V7.82l8-3.64z"/>
                    <path d="M7 12l2 2 5-5 1.5 1.5L9 17 5.5 13.5z"/>
                  </svg>
                </div>
                <span class="lang-name">{{ lang.name }}</span>
              </div>
            </div>
          </div>
        </div>

        <!-- Static Skills Grid -->
        <div class="masonry-grid">
          <div class="skill-card" v-for="(category, index) in skillCategories" :key="`skill-${index}`">
            <div class="skill-card-icon">{{ category.icon }}</div>
            <h3 class="skill-card-title">{{ category.title }}</h3>
            <div class="skill-card-tags">
              <span class="skill-chip" v-for="(skill, idx) in category.skills" :key="`skill-item-${idx}`">
                {{ skill }}
              </span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Skills',
  data() {
    return {
      languages: [
        { name: 'Python', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg' },
        { name: 'R', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/r/r-original.svg' },
        { name: 'JavaScript', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg' },
        { name: 'Bash', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/bash/bash-original.svg' },
        { name: 'C++', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/cplusplus/cplusplus-original.svg' },
        { name: 'Nextflow', icon: null },
        // Duplicate for seamless loop
        { name: 'Python', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg' },
        { name: 'R', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/r/r-original.svg' },
        { name: 'JavaScript', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg' },
        { name: 'Bash', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/bash/bash-original.svg' },
        { name: 'C++', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/cplusplus/cplusplus-original.svg' },
        { name: 'Nextflow', icon: null }
      ],
      skillCategories: [
        {
          icon: '🌐',
          title: 'Web Development',
          skills: ['Vue 3', 'Vite', 'Flask', 'REST API', 'Vuetify']
        },
        {
          icon: '🧬',
          title: 'Genomics & Bioinformatics',
          skills: ['VCF/BCF', 'Bedtools', 'pysam', 'GWAS', 'REGENIE', 'KING', 'PLINK 2', 'PCA/Ancestry']
        },
        {
          icon: '📊',
          title: 'Data Visualization',
          skills: ['D3.js', 'Chart.js', 'Interactive QC', 'Manhattan Plots']
        },
        {
          icon: '⚡',
          title: 'HPC & DevOps',
          skills: ['SLURM', 'Docker', 'Apptainer', 'Linux/Unix', 'SSH']
        },
        {
          icon: '🤖',
          title: 'Machine Learning',
          skills: ['scikit-learn', 'TensorFlow', 'Keras', 'ROC/AUC', 'Cross-validation']
        },
        {
          icon: '🛠️',
          title: 'Tools & Productivity',
          skills: ['Git/GitHub', 'VS Code', 'Cursor', 'Adobe Illustrator', 'Photoshop', 'ChatGPT', 'Claude']
        },
        {
          icon: '🗄️',
          title: 'Data Processing',
          skills: ['Pandas', 'NumPy', 'Data Wrangling', 'Feature Engineering']
        }
      ]
    }
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
  max-width: 1400px;
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

  .section {
    padding: 4rem 1.5rem;
  }
}
</style>
