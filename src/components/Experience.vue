<script setup lang="ts">
const experiences = [
  {
    company: 'Pentair',
    role: 'Water Solutions Sales Intern',
    location: 'Moorpark, CA',
    period: 'May 2025 – August 2025',
    description: [
      'Shadowed territory sales managers across Tucson, Albuquerque, and Phoenix, gaining hands-on exposure to regional performance metrics, client relationship management, and data-driven strategies for improving market coverage.',
      'Developed a comprehensive growth strategy by analyzing Salesforce CRM data and visualizing key performance trends in Power BI dashboards, uncovering over $3.5M in potential revenue opportunities through optimized territory planning and trend forecasting.',
      'Performed Pareto analysis on 2500+ dealer accounts, identifying the top 20% of dealers generating 80% of total sales, amounting to $18M in revenue, providing actionable insights to improve resource allocation and territory alignment.'
    ]
  },
  {
    company: 'Tasi Bank',
    role: 'Operations Associate',
    location: 'San Francisco, CA',
    period: 'June 2024 – August 2024',
    description: [
      'Assisted commercial underwriters through projects targeted at streamlining the loan review process, boosting average approval time by 17% and underwriting accuracy by 20%.',
      'Aided the marketing department in enhancing branding strategies, by optimizing social media content, resulting in a 30% increase in brand awareness surveys and a 15% growth in social media engagement over three months.',
      'Attended and helped coordinate several conferences and luncheons hosting 100+ banking and credit union representatives in the San Francisco area.'
    ]
  }
];

const leadership = [
  {
    org: 'Larsen Leaders Academy',
    role: 'Active Member',
    period: 'August 2022 – Present',
    description: 'Research and explore the critical insights of effective business leadership, emphasizing essential attributes of successful team leaders, and encouraging innovation and adaptability to navigate market changes.'
  },
  {
    org: 'BAIM Association',
    role: 'Active Member',
    period: 'September 2024 – Present',
    description: 'Enhance technical expertise through hands-on workshops and training sessions focused on data visualization, reporting tools, and analytics software such as Power BI.'
  }
];
</script>

<template>
  <div class="max-w-7xl mx-auto space-y-24">
    <!-- Section Header -->
    <div class="space-y-4">
      <h2 class="text-sm font-bold tracking-widest uppercase text-gray-400">
        Professional Experience
      </h2>
      <h3 class="text-4xl md:text-6xl font-bold tracking-tighter uppercase leading-none font-serif">
        Career <br /> Journey
      </h3>
    </div>

    <!-- Experience List -->
    <div class="grid grid-cols-1 gap-16">
      <div 
        v-for="(exp, index) in experiences" 
        :key="index"
        class="group grid grid-cols-1 md:grid-cols-[1fr_2fr] gap-8 border-t border-gray-100 pt-12"
      >
        <div class="space-y-2">
          <p class="text-sm font-bold tracking-widest uppercase text-gray-400">{{ exp.period }}</p>
          <h4 class="text-2xl font-bold tracking-tight">{{ exp.company }}</h4>
          <p class="text-lg font-medium text-gray-600 italic">{{ exp.role }}</p>
          <p class="text-sm text-gray-400">{{ exp.location }}</p>
        </div>
        
        <div class="space-y-4">
          <ul class="space-y-4">
            <li 
              v-for="(item, i) in exp.description" 
              :key="i"
              class="text-lg text-gray-600 leading-relaxed relative pl-6 before:content-[''] before:absolute before:left-0 before:top-3 before:w-2 before:h-2 before:bg-black before:rounded-full"
            >
              {{ item }}
            </li>
          </ul>
        </div>
      </div>
    </div>

    <!-- Leadership Section -->
    <div class="space-y-12 pt-12">
      <h3 class="text-2xl font-bold tracking-tight uppercase">Leadership & Organizations</h3>
      <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
        <div 
          v-for="(lead, index) in leadership" 
          :key="index"
          class="p-8 bg-[#F8F7F5] rounded-2xl space-y-4 transition-transform hover:scale-[1.02]"
        >
          <div class="flex justify-between items-start">
            <h4 class="text-xl font-bold tracking-tight">{{ lead.org }}</h4>
            <span class="text-xs font-bold tracking-widest uppercase text-gray-400">{{ lead.period }}</span>
          </div>
          <p class="text-sm font-bold text-gray-500 uppercase">{{ lead.role }}</p>
          <p class="text-gray-600 leading-relaxed">{{ lead.description }}</p>
        </div>
      </div>
    </div>
  </div>
</template>
