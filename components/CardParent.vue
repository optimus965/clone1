<!-- ParentComponent.vue -->
<template>
    <div class="flex flex-wrap  justify-center md:justify-start  md:mx-24 gap-8 mt-24">
      <!-- Loop through cardsData and pass data to each Card -->
      <Card
        v-for="(item, index) in cardsData"
        :key="index"
        :title="item.title"
        :description="item.description"
        :image="item.image"
        :category="item.category"
      />
    </div>
  </template>
  <script setup>
  
  import { ref } from 'vue';
  import Card from './Card.vue';
  // Define the cards data using ref (reactive data)
  const cardsData = ref([
    {
      title: 'Application Modernization',
      description: 'Migrate Legacy to Micro Services, Micro Frontends and Cloud enabled applications ',
      image: '/images/cards/APMO.png',
      category: 'Category A',
    },
    {
      title: 'Custom Product Development',
      description: 'We Help Start-ups, Scale-ups & Enterprises Build Applications that Matter ',
      image: '/images/cards/CUPR.png',
      category: 'Category B',
    },
    {
      title: 'App and Website development',
      description: 'You can Leverage our decades of experience in mobile app and website development,',
      image: '/images/cards/APWE.png',
      category: 'Category C',
    },
    {
      title: 'Humanized UX/UI Design',
      description: 'We have empowered over 10 plus products from ECommerce to FinTech to Retail to EduTech.',
      image: '/images/cards/HUUX.png',
      category: 'Category C',
    },
    {
      title: 'Cloud Migration and Management Services',
      description: 'We provide Frictionless and Automated cloud management solutions 24X7 ',
      image: '/images/cards/CLMI.png',
      category: 'Category C',
    },

  ]);
  </script>
  
  <style scoped>
  /* Optional: Tailwind classes for the layout */
  </style>
  