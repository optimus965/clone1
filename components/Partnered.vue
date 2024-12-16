<template>
    <div>
        <div class="text-[42px] text-center font-bold"> We are partnered with</div>
    <div class="grid sm:grid-cols-2 md:grid-cols-4 grid-cols-1 justify-between gap-4 p-8">
        <div v-for="item in data" class="flex shadow-md rounded-md justify-center border h-48 hover:border-red-500 items-center  hover:border-2 transition 300">
            <img class="h-[60px] w-48" :src="item.image" />
        </div>
    </div>
    </div>
</template>
<script setup>
import { ref } from 'vue';

const data = ref([
    {
        name:"aws",
        image:"/images/partnered/aws.png"
    },
    {
        name:"Azure",
        image:"/images/partnered/azure.png"
    },
    {
        name:"Microsoft",
        image:"/images/partnered/Microsoft.png"
    },
    {
        name:"MongoDB",
        image:"/images/partnered/MongoDB.png"
    }
])
</script>