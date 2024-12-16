<!-- <template>
    <div>
        <div><img src="/images/slides/Banner-with-text.png" /></div>
        <div><img src="/images/slides/business-banner-3.png" /></div>
        <div><img src="/images/slides/cmmmi.png" /></div>
    </div>
</template>
<script setup>
</script> -->

<template>
    <div class="relative w-full  mx-auto p-24">
      <div class="overflow-hidden  relative">
        <div 
          class="flex transition-transform duration-300 shadow-lg rounded-lg bg-gray-500"
          :style="{ transform: `translateX(-${currentSlide * 100}%)` }"
        >
          <div class="w-full flex-shrink-0">
            
            <img src="/images/slides/Banner-with-text.png" class="w-full h-96  rounded-md bg-cover" alt="Slide 1" />
          
          </div>
          <div class="w-full flex-shrink-0 bg-gray-500">
            <div class="flex flex-row justify-between items-center rounded-md">
                <div class="pl-8">
                <p class="sm:text-[48px] text-xl font-bold ">Bhavitha Tech becomes an AWS Select Service Partner.</p>
                <button class="p-3 bg-orange-500 rounded-md mt-48 text-xl text-white">Know More</button>
                </div>
            
                <img src="/images/slides/business-banner-3.png" class=" w-96 h-96  pr-12 bg-cover bg-center" alt="Slide 2" />
            </div>
          </div>
          <div class="w-full flex-shrink-0 bg-gray-500 trasitionn ease-in-out">
            <img src="/images/slides/cmmmi.png" class="w-full h-96  rounded-md bg-cover bg-contain" alt="Slide 3" />
          
          </div>
        </div>
      </div>
      <button
        @click="prevSlide"
        class="absolute top-1/2 left-0 transform -translate-y-1/2 bg-gray-600 text-white p-2 rounded-full"
      >
        &#10094;
      </button>
      <button
        @click="nextSlide"
        class="absolute top-1/2 right-0 transform -translate-y-1/2 bg-gray-600 text-white p-2 rounded-full"
      >
        &#10095;
      </button>
    </div>
    


  </template>
  
  <script setup>
// import { onMounted } from 'vue';
// import { initFlowbite } from 'flowbite'
// // import Carousel from 'flowbite';
// onMounted(() => { 
//     initFlowbite();
// })
import { ref, onMounted, onBeforeUnmount } from 'vue';

const currentSlide = ref(0); // The current slide index
const totalSlides = 3; // Total number of slides
let autoplayInterval = null; // Autoplay interval handle
const autoplayDelay = 3000; // Delay between slides in milliseconds (3 seconds)

// Start the autoplay
const startAutoplay = () => {
  autoplayInterval = setInterval(() => {
    nextSlide();
  }, autoplayDelay);
};

// Stop the autoplay
const stopAutoplay = () => {
  if (autoplayInterval) {
    clearInterval(autoplayInterval);
    autoplayInterval = null;
  }
};

// Go to the next slide
const nextSlide = () => {
  if (currentSlide.value === totalSlides - 1) {
    setTimeout(() => {
      currentSlide.value = 0;
    }, 300); // Delay added to avoid transition stuttering
  } else {
    currentSlide.value = (currentSlide.value + 1) % totalSlides;
  }
}

// Go to the previous slide
const prevSlide = () => {
  currentSlide.value = (currentSlide.value - 1 + totalSlides) % totalSlides;
};

// Start autoplay when component is mounted
onMounted(() => {
  startAutoplay();
});

// Clean up the autoplay interval when the component is destroyed
onBeforeUnmount(() => {
  stopAutoplay();
});
  </script>
<!--   
  <style scoped>  
  /* Optional: Add custom styles */
  </style>
   -->