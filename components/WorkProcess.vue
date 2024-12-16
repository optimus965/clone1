<!-- Card.vue -->
<template>
    <div class="max-w-sm rounded overflow-hidden shadow-lg p-4 duration-700 hover:scale-[1.04] scale-100">
        <h2 class="font-bold text-xl mb-2 text-center">{{ title }}</h2>
      <img :src="image" alt="Card image" class="w-full  object-cover" />
      <div class="px-6 py-4">
       
        <p class="text-gray-700  text-xl text-center">{{ description }}</p>
      </div>
      <!-- <div class="px-6 pt-4 pb-2">
        <span class="text-sm font-semibold text-gray-600">Category: {{ category }}</span>
      </div> -->
    </div>
  </template>
  
  <script setup>
  import { defineProps } from 'vue'
  // Define props using Composition API
  const props = defineProps({
    title: String,
    description: String,
    image: String,
  });
//   console.log(image);
  </script>
  
  <!-- <style scoped>
  /* Optional: Tailwind classes for styling */
  </style> -->
  