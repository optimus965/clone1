<template>
    <div class=" bg-blue-200 mx-12 p-8 space-y-8">
    <div class="grid   grid-cols-1 md:grid-cols-2   space-y-8 md:gap-8   md:justify-between md:items-center">
        <div>
            <img src="/images/BodyIm/success-1.png" />
        </div>
        <div>
            <div>We'r all about creating your success</div>
            <div>Most companies have core values- the beliefs or guiding <br />principles that define how they expect to conduct <br /> business.Our particulare core values are unique to use.</div>
            <div>From Web's earlies days. our business has been built  on <br /> the principles of fairness, integrity and respect for <br /> people. Or we put it as, "The essence of life <br /> is Relationships." As a company, we belive that everyone <br /> has an inherent worth,</div>
        </div>
    </div>
    <div class="flex gap-4">
        <div @click="changeIt(1)">OUR VALUES</div>
        <div @click="changeIt(2)">OUR MISSION</div>
    </div>
    <div class="grid grid-cols-1 md:grid-cols-2 items-center justify-between">
        <div>
            <div>{{data1.title}}</div>
            <div>{{data1.heading}}</div>
            <div>{{data1.description}}</div>
        </div>
        <div>
            <img :src="data1.image" />
        </div>
    </div>
    </div>
</template>
<script setup>
import { computed, ref } from 'vue';

const check = ref(1);
const data = ref([
    {
        title:"OUR VALUES",
        heading:"Our particular core values are unique to us",
        image:"/images/BodyIm/successVa.jpg",
        description:"Most companies have core values- the beliefs or guiding principles that define how they expect to conduct business. Our particular core values are unique to us."
    
    },
    {
        title:"OUR MISSION",
        heading:"We're a Team of Creative Problem Solvers",
        image:"/images/BodyIm/successMi.jpg",
        description:"True Production is a small,but resourceful group of passionate individuals.",
        description1:"Most companies have core values- the beliefs or guiding principles that define how they expect to conduct business. Our particular core values are unique to us."
    
    }, 
])
function changeIt(to) {
    check.value = to
    console.log(check.value)
}
var data1 = computed(()=> data.value[check.value - 1])
// data1 = data1.value
console.log(data1)
</script>