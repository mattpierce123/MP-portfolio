<script setup lang="ts">
import { Linkedin, Mail, Phone, MapPin, ArrowUpRight } from 'lucide-vue-next';

const contactInfo = [
  { icon: Mail, label: 'Email', value: 'matthewmpierce@gmail.com', href: 'mailto:matthewmpierce@gmail.com' },
  { icon: Phone, label: 'Phone', value: '(925) 357-5098', href: 'tel:9253575098' },
  { icon: Linkedin, label: 'LinkedIn', value: 'linkedin.com/in/matthewmpierce', href: 'https://linkedin.com/in/matthewmpierce' },
  { icon: MapPin, label: 'Location', value: 'Pleasant Hill, CA 94523', href: '#' }
];
</script>

<template>
  <div class="max-w-7xl mx-auto space-y-24">
    <!-- Section Header -->
    <div class="space-y-4">
      <h2 class="text-sm font-bold tracking-widest uppercase text-gray-400">
        Get In Touch
      </h2>
      <h3 class="text-4xl md:text-6xl font-bold tracking-tighter uppercase leading-none font-serif">
        Let's <br /> Connect
      </h3>
    </div>

    <div class="grid grid-cols-1 lg:grid-cols-2 gap-24 items-end">
      <!-- Contact List -->
      <div class="space-y-12">
        <div 
          v-for="(contact, index) in contactInfo" 
          :key="index"
          class="group flex items-center space-x-6 border-b border-gray-800 pb-8 transition-all hover:border-gray-600"
        >
          <div class="p-4 bg-gray-800 rounded-full group-hover:bg-white group-hover:text-black transition-all">
            <component :is="contact.icon" :size="24" />
          </div>
          <div class="space-y-1">
            <p class="text-xs font-bold tracking-widest uppercase text-gray-500">{{ contact.label }}</p>
            <a 
              :href="contact.href" 
              class="text-xl md:text-2xl font-bold tracking-tight hover:text-gray-400 transition-colors flex items-center space-x-2"
            >
              <span>{{ contact.value }}</span>
              <ArrowUpRight :size="18" class="opacity-0 group-hover:opacity-100 transition-opacity" />
            </a>
          </div>
        </div>
      </div>

      <!-- Call to Action -->
      <div class="space-y-12">
        <div class="space-y-4">
          <p class="text-lg text-gray-400 leading-relaxed max-w-md">
            I'm currently looking for opportunities in business analytics and information management. 
            If you're interested in my work or just want to say hi, feel free to reach out.
          </p>
        </div>

        <div class="relative group inline-block">
          <a 
            href="mailto:matthewmpierce@gmail.com" 
            class="relative z-10 block px-12 py-6 bg-white text-black text-xl font-bold tracking-widest uppercase transition-transform group-hover:-translate-x-2 group-hover:-translate-y-2"
          >
            Send Message
          </a>
          <div class="absolute inset-0 border-2 border-white translate-x-2 translate-y-2 -z-0"></div>
        </div>
      </div>
    </div>
  </div>
</template>
