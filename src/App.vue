<template>
  <div id="app">
    <Navbar @launch-rocket="launchRocket" />
    <Hero />
    <About />
    <Education />
    <Research />
    <Skills />
    <Beyond />
    <Gallery />
    <Contact />
    <Footer />
    <RocketAnimation ref="rocketAnimation" />
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue'
import Hero from './components/Hero.vue'
import About from './components/About.vue'
import Education from './components/Education.vue'
import Research from './components/Research.vue'
import Skills from './components/Skills.vue'
import Beyond from './components/Beyond.vue'
import Contact from './components/Contact.vue'
import Gallery from './components/Gallery.vue'
import Footer from './components/Footer.vue'
import RocketAnimation from './components/RocketAnimation.vue'

export default {
  name: 'App',
  components: {
    Navbar,
    Hero,
    About,
    Education,
    Research,
    Skills,
    Beyond,
    Contact,
    Gallery,
    Footer,
    RocketAnimation
  },
  methods: {
    launchRocket() {
      this.$refs.rocketAnimation.launch();
    }
  },
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

    document.querySelectorAll('.section').forEach(el => {
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

html {
  scroll-behavior: smooth;
}
</style>
