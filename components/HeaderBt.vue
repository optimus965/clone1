<template>
    <div class="flex justify-between">
        <div class="md:hidden">
            <router-link to="/"><img class="w-[230px] h-[61px]" src="/images/logo.png" /></router-link>
        </div>
        <div @click="collapse" class=" md:hidden absolute right-6 z-20">
            <img :src="!open ? '/images/svg/align-center.svg' : '/images/svg/close.svg'" class="h-12 w-12" />
        </div>
        <div class="flex bg-white-500 shadow-md md:shadow-none w-full   flex-col md:flex-row items-center md:h-auto absolute space-x-4 duration-700"
            :class="[open ? 'left-0 h-screen bg-white z-10' : 'left-[100%] h-screen']">
            <div>
                <router-link to="/"><img class="w-[230px] h-[61px]" src="/images/logo.png" /></router-link>
            </div>
            <div>
                <div @click="toggleCollapse(1)" class="relative" ref="dropdown"> IT Services <svg class="inline"
                        xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
                        <path d="M7 10l5 5 5-5z" />
                    </svg>

                    <div v-show="isOpen(1)"
                        class="absolute top-8 w-48 shadow-md bg-white z-30 hover:w-64 hover:space-y-4 hover:item-center rounded-md transition-all duration-300 ease-in-out">
                        <div class="border-b-[1px] border-gray-500"><router-link to="/appdev">Application
                                Modernization</router-link></div>
                        <div class="border-b-[1px] border-gray-500"><router-link to="/productdev">Custom Product
                                Development</router-link></div>
                        <div class="border-b-[1px] border-gray-500"><router-link to="/appweb">App And Website
                                Development</router-link></div>
                        <div class="border-b-[1px] border-gray-500"><router-link to="/uxui">UX/UI Design</router-link>
                        </div>
                    </div>
                </div>
            </div>
            <div>AWS Consulting And Services</div>
            <div>Technologies</div>
            <div>Projects</div>
            <div>
                <div @click="toggleCollapse(2)" class="relative " ref="dropdown1">
                    About us <svg class="inline" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
                        <path d="M7 10l5 5 5-5z" />
                    </svg>

                    <div v-show="isOpen(2)"
                        class="absolute top-8 w-32 z-30 shadow-md bg-white hover:w-48 hover:space-y-4 hover:item-center rounded-md transition-all duration-300 ease-in-out">
                        <div class="border-b-[1px] border-gray-500"><router-link to="/about">Our Team</router-link>
                        </div>
                        <div class="border-b-[1px] border-gray-500">.NET Migration</div>
                        <div class="border-b-[1px] border-gray-500">CMMI Level 3</div>
                    </div>
                </div>
            </div>
        </div>
    </div>

</template>

<script setup>
import { ref, onMounted, onBeforeUnmount, computed } from 'vue';
const tracker = ref(null);
const dropdown = ref(null);
const dropdown1 = ref(null);
const open = ref(false)
const visited = ref(false)
function collapse() {
    open.value = !(open.value)
    console.log(open.value)
}
const handleResize = () => {
    //   windowWidth.value = window.innerWidth;
    if (window.innerWidth >= 768) {
        open.value = true
        visited.value = true
    }
    else {
        if (visited.value) {
            open.value = false
            visited.value = false
        }
    }

};

onMounted(() => {
    // Set up the resize event listener when the component is mounted
    window.addEventListener('resize', handleResize);
    if (window.innerWidth >= 768) {
        open.value = true
    }
});

onBeforeUnmount(() => {
    // Remove the resize event listener when the component is destroyed
    window.removeEventListener('resize', handleResize);
});

function toggleCollapse(item) {
    tracker.value = (tracker.value === item) ? null : item;
}
function isOpen(item) {
    return (item === tracker.value);
}
const closeOnOutSideClick = (event) => {
    if (dropdown.value && !dropdown.value.contains(event.target) && dropdown1.value && !dropdown1.value.contains(event.target)) {
        tracker.value = null
    }
}
onMounted(() => {
    document.addEventListener('click', closeOnOutSideClick);
});
// onBeforeUnmount(() => {
//       document.removeEventListener('click', closeOnOutSideClick);
//     });

</script>
<!--   
  <style scoped>
  /* Scoped styling for the component */
  </style> -->