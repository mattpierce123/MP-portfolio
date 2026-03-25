<script setup lang="ts">
const technicalSkills = [
  { name: 'Power BI', level: 'Advanced', category: 'Visualization' },
  { name: 'Python', level: 'Intermediate', category: 'Analytics' },
  { name: 'R', level: 'Intermediate', category: 'Analytics' },
  { name: 'Salesforce', level: 'Intermediate', category: 'CRM' },
  { name: 'Excel', level: 'Expert', category: 'Data Mgmt' },
  { name: 'SQL', level: 'Intermediate', category: 'Database' },
  { name: 'Minitab', level: 'Intermediate', category: 'Statistics' },
  { name: 'PowerPoint', level: 'Expert', category: 'Communication' }
];

const interests = [
  { name: 'Guitar', description: 'Musical expression and creativity.' },
  { name: 'Audio Engineering', description: 'Technical precision in sound production.' },
  { name: 'Power Lifting', description: 'Discipline and physical strength.' }
];
</script>

<template>
  <div class="max-w-7xl mx-auto space-y-24">
    <!-- Section Header -->
    <div class="space-y-4">
      <h2 class="text-sm font-bold tracking-widest uppercase text-gray-400">
        Technical Expertise
      </h2>
      <h3 class="text-4xl md:text-6xl font-bold tracking-tighter uppercase leading-none font-serif">
        Skills & <br /> Interests
      </h3>
    </div>

    <div class="grid grid-cols-1 lg:grid-cols-2 gap-24">
      <!-- Skills Grid -->
      <div class="grid grid-cols-2 md:grid-cols-4 gap-4">
        <div 
          v-for="(skill, index) in technicalSkills" 
          :key="index"
          class="p-6 bg-white border border-gray-100 rounded-2xl shadow-sm hover:shadow-md transition-all group"
        >
          <p class="text-[10px] font-bold tracking-widest uppercase text-gray-400 mb-2">{{ skill.category }}</p>
          <h4 class="text-lg font-bold tracking-tight mb-1">{{ skill.name }}</h4>
          <p class="text-[10px] font-bold uppercase text-gray-300 group-hover:text-black transition-colors">{{ skill.level }}</p>
        </div>
      </div>

      <!-- Interests & Education -->
      <div class="space-y-12">
        <div class="space-y-6">
          <h4 class="text-2xl font-bold tracking-tight uppercase">Education</h4>
          <div class="p-8 bg-[#F8F7F5] rounded-2xl space-y-2">
            <h5 class="text-xl font-bold tracking-tight">Purdue University</h5>
            <p class="text-sm font-bold text-gray-500 uppercase">Daniels School of Business</p>
            <p class="text-lg font-medium text-gray-600 italic">BS in Business Analytics & Information Management</p>
            <p class="text-sm text-gray-400">Expected May 2026</p>
            <div class="pt-4 flex flex-wrap gap-2">
              <span class="text-[10px] font-bold tracking-widest uppercase px-3 py-1 bg-white rounded-full">Data Mining</span>
              <span class="text-[10px] font-bold tracking-widest uppercase px-3 py-1 bg-white rounded-full">SQL</span>
              <span class="text-[10px] font-bold tracking-widest uppercase px-3 py-1 bg-white rounded-full">Python</span>
            </div>
          </div>
        </div>

        <div class="space-y-6">
          <h4 class="text-2xl font-bold tracking-tight uppercase">Beyond the Data</h4>
          <div class="grid grid-cols-1 gap-4">
            <div 
              v-for="(interest, index) in interests" 
              :key="index"
              class="flex items-center space-x-4 p-4 border-l-2 border-black"
            >
              <h5 class="text-lg font-bold tracking-tight min-w-[120px]">{{ interest.name }}</h5>
              <p class="text-sm text-gray-500">{{ interest.description }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
