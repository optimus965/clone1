<template>
    <div class="grid sm:grid-cols-2 md:grid-cols-4 grid-cols-1 justify-between gap-4 p-8">
        <div v-for="item in data" class="shadow-md rounded-md p-2 border hover:border-red-500 hover:border-2 transition 300">
            <img :src="item.image" />
        </div>
    </div>
</template>
<script setup>
import { ref } from 'vue';

const data = ref([
    {
        name:"terex",
        image:"/images/clients/Terex_Corporation.jpg"
    },
    {
        name:"Baker",
        image:"/images/clients/Baker_Real_Estate.png"
    },
    {
        name:"Nangia",
        image:"/images/clients/Nangia_Andersen_LLP.png"
    },
    {
        name:"Tranway",
        image:"/images/clients/Tranway.png"
    }
])
</script>