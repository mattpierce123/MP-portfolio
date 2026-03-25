<script setup lang="ts">
import { ArrowDownRight, Linkedin, Mail, Phone } from 'lucide-vue-next';
</script>

<template>
  <div class="relative min-h-screen flex flex-col justify-center px-6 md:px-12 lg:px-24 pt-20">
    <div class="max-w-7xl mx-auto grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
      <!-- Left Content -->
      <div class="space-y-8">
        <div class="space-y-4">
          <h2 class="text-sm font-bold tracking-widest uppercase text-gray-400">
            Business Analytics & Information Management
          </h2>
          <h1 class="text-5xl md:text-7xl lg:text-8xl font-bold tracking-tighter leading-[0.9] uppercase font-serif">
            Matthew <br /> Pierce
          </h1>
          <p class="text-lg md:text-xl text-gray-600 max-w-lg font-medium leading-relaxed">
            Purdue University student at the Daniels School of Business. 
            Passionate about transforming data into actionable business insights and strategic growth.
          </p>
        </div>

        <div class="flex flex-wrap gap-6 items-center">
          <a 
            href="#experience" 
            class="group flex items-center space-x-2 text-sm font-bold tracking-widest uppercase border-b-2 border-black pb-1 transition-all hover:pr-4"
          >
            <span>View Experience</span>
            <ArrowDownRight :size="18" class="transition-transform group-hover:translate-x-1 group-hover:translate-y-1" />
          </a>

          <div class="flex items-center space-x-4">
            <a href="https://linkedin.com/in/matthewmpierce" target="_blank" class="p-2 rounded-full hover:bg-gray-100 transition-colors">
              <Linkedin :size="20" />
            </a>
            <a href="mailto:matthewmpierce@gmail.com" class="p-2 rounded-full hover:bg-gray-100 transition-colors">
              <Mail :size="20" />
            </a>
          </div>
        </div>
      </div>

      <!-- Right Content (Image) -->
      <div class="relative group">
        <div class="aspect-[3/4] overflow-hidden rounded-2xl bg-gray-100 shadow-2xl transition-transform duration-500 group-hover:scale-[1.02]">
          <img 
            src="/BP5_4080.jpg" 
            alt="Matthew Pierce" 
            class="w-full h-full object-cover grayscale hover:grayscale-0 transition-all duration-700"
            referrerPolicy="no-referrer"
          />
        </div>
        <!-- Decorative elements -->
        <div class="absolute -bottom-6 -right-6 w-32 h-32 bg-[#F27D26] -z-10 rounded-full blur-3xl opacity-20"></div>
        <div class="absolute -top-6 -left-6 w-32 h-32 bg-blue-400 -z-10 rounded-full blur-3xl opacity-10"></div>
      </div>
    </div>

    <!-- Scroll Indicator -->
    <div class="absolute bottom-12 left-1/2 -translate-x-1/2 hidden md:block animate-bounce">
      <div class="w-[1px] h-12 bg-gray-300"></div>
    </div>
  </div>
</template>
