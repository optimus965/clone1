<template>

    <div class="flex flex-col justify-center items-center bg-blue-300 h-[480px]  sm:mx-8  space-y-4">
        
            <div class="text-xl">
                Contact
            </div>
            <div class="p-2 text-[24px] sm:text-[32px] md:text-[42px]  font-bold">
                Any Questions ? Leave us a little info
            </div>
    </div>

    <div class="flex  mx-12 flex-col md:flex-row   md:justify-center -translate-y-32">
        <div class="p-8 shadow-lg  bg-orange-100 space-y-4">
            <div class="space-y-2">
                <img src="/images/contact/map.png" />
                <div class="text-lg font-bold mt-4">Location</div>
                <div>#163, 9th Main road, 6th <br /> Sector HSR Layout,<br /> Bengaluru 560102. </div>
            </div>
            <div class="space-y-2">
                <div class="text-lg font-bold">Email</div>
                <div>
                    <a href="mailto:connect@bhavithatech.com" class="mt-2">
                        connect@bhavithatech.com
                    </a>
                </div>
            </div>
            <div class="space-y-2">
                <div class="text-lg font-bold">Phone</div>
                <div><a href="tel:+917204374626" class="">+91 7204374626</a></div>
            </div>
            <div class="space-y-2">
                <div class="text-lg font-bold">Social</div>
                <div></div>
            </div>
        </div>
        <div class="bg-white p-8 md:px-12 md:py-12   shadow-lg space-y-4">
            <div class="text-2xl font-bold">Send a Message</div>
            <div>Fill up the form and our team will get back to you with in 24 hours</div>
            <div class="flex flex-col md:flex-row gap-4">
                <div class="flex-1 mb-4  ">
                    <input
                        class="shadow bg-gray-50 appearance-none border shadow-sm border-none w-full   py-4 px-4 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
                        id="username" type="text" placeholder="Name">
                </div>
                <div class="flex-1 mb-4 ">
                    <input
                        class="shadow bg-gray-50 appearance-none border shadow-sm border-none w-full  py-4 px-4 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
                        id="username" type="text" placeholder="Phone">
                </div>
            </div>
            <div class="flex-1 overflow-hidden">
                <div class="mb-4">
                    <input
                        class="shadow bg-gray-50 appearance-none border shadow-sm border-none  w-full py-4 px-4 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
                        id="username" type="text" placeholder="Subject">
                </div>
            </div>
            <div>
                <textarea
                    class="w-full p-4 border bg-gray-50 border-gray-300  shadow-sm  focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500 resize-none"
                    rows="4" placeholder="Message"></textarea>
            </div>
            <br />
            <div class="bg-black text-white rounded-md p-4 inline">Submit Message</div>
        </div>
    </div>
</template>
<script setup>
import { ref } from 'vue';

const clientName = ref('');
const phone = ref('');
const subject = ref('');
const message = ref('');

</script>