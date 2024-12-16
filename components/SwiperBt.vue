<template>
    <div class="bg-orange-100  h-auto">
        <swiper :modules="modules" :slides-per-view="1" :space-between="50" :autoplay='true' :navigation='true'
            :loop="true">
            <swiper-slide>
                <img :src="reach?'/images/slides/Banner-with-text.png':'/images/slides/Banner-with-text-small.png'" class="rounded-md bg-cover w-full md:h-[440px]" alt="Slide 1" />
            </swiper-slide>
            <swiper-slide>
                <div
                    class="flex flex-col-reverse md:flex-row h-[1000px] md:h-auto justify-center items-center md:items-start  p-4 md:items-center rounded-md">
                    <div>
                        <div class="flex flex-col ">
                            <p class="text-[48px]  sm:text-[24px]  font-bold ">Bhavitha Tech becomes an <br /> AWS Select Services
                            <br /> Partner.</p>
                        </div>
                        <div class="pt-3">
                            <button class="p-3 bg-orange-500 rounded-md  text-xl text-white ">Know More</button>
                        </div>
                    </div>
                    <img src="/images/slides/business-banner-3.png" class="   -translate-y-6 sm:object-contain md:-translate-y-0 duration 700" alt="Slide 2" />
                    </div>
            </swiper-slide>
            <swiper-slide><img :src="reach?'/images/slides/cmmmi.png':'/images/slides/cmmi3mobile.jpg'" class="w-full md:h-[440px]  rounded-md bg-cover bg-contain" alt="Slide 3" />
            </swiper-slide>
        </swiper>
    </div>
</template>
<script setup>
import { Swiper, SwiperSlide } from 'swiper/vue';
import 'swiper/css'
import { Navigation, Pagination, Scrollbar, Autoplay } from 'swiper/modules';
import 'swiper/css/navigation';
import 'swiper/css/pagination';
import 'swiper/css/scrollbar';
import 'swiper/css/autoplay';
import { onMounted, ref } from 'vue';
var modules = [Navigation, Pagination, Scrollbar, Autoplay]
const reach = ref(false)
function handleResize() {
    if(window.innerWidth >= 768) {
        reach.value = true;
    }
    else {
        reach.value = false;
    }
}
onMounted(() => {
    // Set up the resize event listener when the component is mounted
    window.addEventListener('resize', handleResize);
    if (window.innerWidth >= 768) {
        reach.value = true
    }
});
</script>