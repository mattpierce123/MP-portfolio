<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue';
import { Menu, X } from 'lucide-vue-next';

defineProps<{
  activeSection: string;
}>();

const isScrolled = ref(false);
const isMobileMenuOpen = ref(false);

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50;
};

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
});

const navItems = [
  { name: 'Home', id: 'home' },
  { name: 'Experience', id: 'experience' },
  { name: 'Projects', id: 'projects' },
  { name: 'Skills', id: 'skills' },
  { name: 'Contact', id: 'contact' },
];

const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value;
};

const closeMobileMenu = () => {
  isMobileMenuOpen.value = false;
};
</script>

<template>
  <nav 
    class="fixed top-0 left-0 w-full z-50 transition-all duration-300 px-6 md:px-12 lg:px-24 py-6"
    :class="[
      isScrolled ? 'bg-white/80 backdrop-blur-md shadow-sm py-4' : 'bg-transparent'
    ]"
  >
    <div class="max-w-7xl mx-auto flex justify-between items-center">
      <a href="#home" class="text-xl font-bold tracking-tighter uppercase">
        Matthew Pierce
      </a>

      <!-- Desktop Navigation -->
      <div class="hidden md:flex items-center space-x-8">
        <a 
          v-for="item in navItems" 
          :key="item.id"
          :href="'#' + item.id"
          class="text-sm font-medium tracking-wide uppercase transition-colors hover:text-gray-500"
          :class="[activeSection === item.id ? 'text-black font-bold' : 'text-gray-400']"
        >
          {{ item.name }}
        </a>
      </div>

      <!-- Mobile Menu Toggle -->
      <button 
        class="md:hidden p-2 text-black"
        @click="toggleMobileMenu"
        aria-label="Toggle menu"
      >
        <Menu v-if="!isMobileMenuOpen" :size="24" />
        <X v-else :size="24" />
      </button>
    </div>

    <!-- Mobile Navigation -->
    <div 
      v-if="isMobileMenuOpen"
      class="fixed inset-0 bg-white z-40 flex flex-col items-center justify-center space-y-8 md:hidden"
    >
      <button 
        class="absolute top-6 right-6 p-2 text-black"
        @click="closeMobileMenu"
      >
        <X :size="32" />
      </button>
      
      <a 
        v-for="item in navItems" 
        :key="item.id"
        :href="'#' + item.id"
        class="text-2xl font-bold tracking-tighter uppercase transition-colors hover:text-gray-500"
        @click="closeMobileMenu"
      >
        {{ item.name }}
      </a>
    </div>
  </nav>
</template>
