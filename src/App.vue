<script setup lang="ts">
import { ref, onMounted } from 'vue';
import Navbar from './components/Navbar.vue';
import Hero from './components/Hero.vue';
import Experience from './components/Experience.vue';
import Projects from './components/Projects.vue';
import Skills from './components/Skills.vue';
import Contact from './components/Contact.vue';

const activeSection = ref('home');

onMounted(() => {
  const observerOptions = {
    root: null,
    rootMargin: '0px',
    threshold: 0.5,
  };

  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry) => {
      if (entry.isIntersecting) {
        activeSection.value = entry.target.id;
      }
    });
  }, observerOptions);

  document.querySelectorAll('section[id]').forEach((section) => {
    observer.observe(section);
  });
});
</script>

<template>
  <div class="min-h-screen bg-[#FDFCFB] text-[#1A1A1A] font-sans selection:bg-[#E5E7EB]">
    <Navbar :active-section="activeSection" />
    
    <main>
      <section id="home">
        <Hero />
      </section>
      
      <section id="experience" class="py-24 px-6 md:px-12 lg:px-24">
        <Experience />
      </section>
      
      <section id="projects" class="py-24 px-6 md:px-12 lg:px-24 bg-[#F8F7F5]">
        <Projects />
      </section>
      
      <section id="skills" class="py-24 px-6 md:px-12 lg:px-24">
        <Skills />
      </section>
      
      <section id="contact" class="py-24 px-6 md:px-12 lg:px-24 bg-[#1A1A1A] text-white">
        <Contact />
      </section>
    </main>

    <footer class="py-12 px-6 md:px-12 lg:px-24 border-t border-gray-100 text-center text-sm text-gray-500">
      <p>© {{ new Date().getFullYear() }} Matthew Pierce. Built with Vue & Tailwind.</p>
    </footer>
  </div>
</template>

<style>
html {
  scroll-behavior: smooth;
}

body {
  margin: 0;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

/* Custom scrollbar */
::-webkit-scrollbar {
  width: 8px;
}

::-webkit-scrollbar-track {
  background: #FDFCFB;
}

::-webkit-scrollbar-thumb {
  background: #E5E7EB;
  border-radius: 4px;
}

::-webkit-scrollbar-thumb:hover {
  background: #D1D5DB;
}
</style>
