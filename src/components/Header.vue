<script setup>
import { Icon } from '@iconify/vue'
import { ref } from 'vue'
const navLinks=ref([
    {id:1,name:"Home",link:"#home"},
    {id:2,name:"Services",link:"#services"},
    {id:3,name:"About Us",link:"#about"},
    {id:4,name:"Our Specialists",link:"#specialists"},
    {id:5,name:"Contact Us",link:"#contact"},
])

const isMenuOpen=ref(false)

const toggleMenu=()=>{
    isMenuOpen.value = !isMenuOpen.value
}
</script>

<template>
    <header class="bg-gradient-to-r from-sky-100 to-teal-100 sticky top-0 z-50 ">
        <div class="max-w-screen-xl mx-auto px-4 py-4 flex justify-between items-center">
            <a href="" class="flex items-center focus:outline-none focus:ring-2 focus:ring-sky-600 rounded ">
                <h1 class="text-2xl font-bold text-sky-600">TrioVerse</h1> 
            </a>

            <nav class="hidden md:flex space-x-6" aria-label="Primary navigation">
                <a v-for="item in navLinks" :key="item.id"
                 :href="item.link"
                 class="text-gray-700 hover:text-sky-600 transition-colors duration-200
                 focus:outline-none focus:ring-2 focus:ring-sky-600 rounded">
                    {{ item.name }}
                </a>
            </nav>
            <!-- Appointment button (Desktop) -->
             <div class="hidden md:block">
                <a href="#appointment"
                class="bg-sky-600 hover:bg-sky-700 text-white px-5 py-2 rounded-full transition-colors
                duration-200 shadow-md focus:outline-none focus:ring-2 focus:ring-sky-800 ring-offset-2">
                    Book Now
                </a>
             </div>
             <!-- Mobile Menu Button -->
              <button class="md:hidden p-2 
              focus:outline-none focus:ring-2
               focus:ring-sky-600 rounded-full"
                @click="toggleMenu" aria-label="Toggle menu" :aria-expanded="isMenuOpen.toString()" aria-controls="mobile menu">
                <Icon class="w-6 h-6" :icon=" isMenuOpen? 'mdi:close' : 'mdi:menu' " />
              </button>
        </div>
        <aside v-if="isMenuOpen" id="mobile-menu"
         class="md:hidden bg-white shadow-lg py-4 px-4 absolute top-full
         left-0 right-0 z-40" aria-label="Mobile menu">
         <nav aria-label="Mobile navigation">
            <ul class="flex flex-col space-y-4">
                <li v-for="item in navLinks" :key="item.id">
                    <a :href="item.link"
                    class="block text-gray-700 hover:text-sky-600
                    transition-colors duration-200 py-2 px-2
                    focus:outline-none focus:ring-2
                    focus:ring-sky-600 rounded-full"
                    @click="toggleMenu">{{ item.name }}</a>
                </li>
                <li>
                    <a href="#appointment" @click="toggleMenu"
                class="block text-center bg-sky-600 hover:bg-sky-700 text-white px-4 py-2 rounded-full transition-colors
                duration-200 shadow-md focus:outline-none focus:ring-2 focus:ring-sky-800 ring-offset-2">
                    Book Now
                </a>
            </li>
            </ul>
         </nav>

        </aside>
    </header>
</template>

<style>

</style>