<!-- ParentComponent.vue -->
<template>
  <div  class="mt-12">
    <div class="text-center"> WORK PROCESS</div>
    <div class="text-center text-[32px] font-bold">Our Working Process</div>
    <div class="  gap-4 p-8 transition-all duration-700 ease-in-out" :class="size1 ? 'md:flex   md:justify-around scale-[0.9]':'sm:grid flex flex-col items-center  sm:grid-cols-2 scale-100'">
      <!-- Loop through cardsData and pass data to each Card -->
      <WorkProcess
        v-for="(item, index) in cardsData"
        :key="index"
        :title="item.title"
        :description="item.description"
        :image="item.image"
        :category="item.category"
      />
    </div>
  </div>
  </template>
  
  <script setup>
  
  import { onMounted,onBeforeUnmount, ref } from 'vue';
  import WorkProcess from './WorkProcess.vue';
 
  // Define the cards data using ref (reactive data)
  const cardsData = ref([
    {
      title: 'Discovery',
      description: 'We use Design Thinking to empathize with and understand your target audience, we take a deep dive into the needs and challenges of your business, customers, and desired technology. ',
      image: '/images/work/discovery.png',
      category: 'Category A',
    },
    {
      title: 'Planning',
      description: 'Our Scrum-based Agile Development methodology drives a dynamic, iterative development process of measuring, testing, and scaling your product for results aligned with your business objectives.',
      image: '/images/work/planning.png',
      category: 'Category B',
    },
    {
      title: 'Develop',
      description: 'We give life to designs and make them a reality. The latest technologies are leveraged to develop robust applications that are seamless, secure, maintainable, scalable and efficient.',
      image: '/images/work/develop.png',
      category: 'Category C',
    },
    {
      title: 'Delivery',
      description: 'Our DevOps-defined culture delivers value to development through launch and beyond, including rapid, continuous delivery, ongoing innovation, and rich opportunities for ROI and business growth.',
      image: '/images/work/delivery.png',
      category: 'Category C',
    },
  ]);
  const size1 = ref(false);
  function handleResize() {
    if(window.innerWidth >=1200) {
      size1.value = true
    }
    else {
      size1.value = false
    }
  }
  onMounted(()=> {
    window.addEventListener('resize', handleResize);
    if (window.innerWidth >= 1200) {
        size1.value = true
    }
  })
  onBeforeUnmount(() => {
    // Remove the resize event listener when the component is destroyed
    window.removeEventListener('resize', handleResize);
});
  </script>
  
  <style scoped>
  /* Optional: Tailwind classes for the layout */
  
  </style>
  