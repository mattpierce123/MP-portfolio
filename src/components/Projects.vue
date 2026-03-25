<script setup lang="ts">
import { ExternalLink, ArrowRight } from 'lucide-vue-next';

const projects = [
  {
    title: 'Ripple Effect Case Competition',
    category: 'Sustainability Strategy',
    description: 'Presented a sustainability-driven “Trade-In, Trade-Up” program to Pentair’s executive board at the 2025 Intern Summit in Minneapolis, incentivizing users to replace outdated or competitor pool pumps with energy-efficient Pentair models.',
    impact: 'Estimated up to 35% reduction in energy usage per upgraded pump and 100+ lbs. of material waste diverted per unit, supporting Pentair’s environmental goals.',
    tags: ['Strategy', 'Sustainability', 'Business Analytics'],
    image: 'https://picsum.photos/seed/sustainability/1200/800'
  }
];
</script>

<template>
  <div class="max-w-7xl mx-auto space-y-24">
    <!-- Section Header -->
    <div class="space-y-4">
      <h2 class="text-sm font-bold tracking-widest uppercase text-gray-400">
        Featured Projects
      </h2>
      <h3 class="text-4xl md:text-6xl font-bold tracking-tighter uppercase leading-none font-serif">
        Work <br /> Highlights
      </h3>
    </div>

    <!-- Project List -->
    <div class="grid grid-cols-1 gap-24">
      <div 
        v-for="(project, index) in projects" 
        :key="index"
        class="group grid grid-cols-1 lg:grid-cols-2 gap-12 items-center"
      >
        <!-- Project Image -->
        <div class="relative aspect-video overflow-hidden rounded-2xl bg-gray-200 shadow-xl transition-transform duration-500 group-hover:scale-[1.02]">
          <img 
            :src="project.image" 
            :alt="project.title" 
            class="w-full h-full object-cover grayscale hover:grayscale-0 transition-all duration-700"
            referrerPolicy="no-referrer"
          />
        </div>

        <!-- Project Content -->
        <div class="space-y-8">
          <div class="space-y-4">
            <p class="text-sm font-bold tracking-widest uppercase text-gray-400">{{ project.category }}</p>
            <h4 class="text-3xl md:text-5xl font-bold tracking-tight uppercase leading-none">{{ project.title }}</h4>
            <p class="text-lg text-gray-600 leading-relaxed">{{ project.description }}</p>
            <div class="p-6 bg-white rounded-xl border border-gray-100 shadow-sm">
              <p class="text-sm font-bold uppercase text-gray-400 mb-2">Impact</p>
              <p class="text-gray-700 italic">{{ project.impact }}</p>
            </div>
          </div>

          <div class="flex flex-wrap gap-2">
            <span 
              v-for="tag in project.tags" 
              :key="tag"
              class="px-4 py-1 bg-gray-100 text-xs font-bold tracking-widest uppercase rounded-full"
            >
              {{ tag }}
            </span>
          </div>

          <div class="flex items-center space-x-6">
            <a 
              href="#" 
              class="group flex items-center space-x-2 text-sm font-bold tracking-widest uppercase border-b-2 border-black pb-1 transition-all hover:pr-4"
            >
              <span>View Case Study</span>
              <ArrowRight :size="18" class="transition-transform group-hover:translate-x-1" />
            </a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
