<script setup>
import { ref } from 'vue';

const stats = ref([
    {id:1,value:"2500+",name:'Happy Clients'},
    {id:2,value:"15+",name:'Specialists'},
    {id:3,value:"50+",name:'Treatments'},
    {id:4,value:"20+",name:'Years'},
])
</script>

<template>
  <header class="relative overflow-hidden bg-gradient-to-r from-pink-100 to-purple-100" id="home">
    <article class="max-w-screen-xl mx-auto px-4 sm:px-8 py-16 md:py-28 flex flex-col-reverse lg:flex-row 
    items-center gap-10 lg:gap-20">
        <!-- Hero content -->
         <section class="w-full lg:w-1/2 text-center lg:text-left">
            <hgroup data-aos="fade-up" data-aos-delay="500">
                <h1 class="text-3xl sm:text-4xl md:text-5xl lg:text-6xl font-bold text-gray-800 mb-4">
                    Get your business up
                    <mark class="text-sky-600 bg-transparent">With us</mark>
                </h1>
                <p class="text-base sm:text-lg text-gray-600 mb-8 max-w-xl mx-auto lg:mx-0">
                  Lorem ipsum dolor sit amet consectetur adipisicing elit.
                   Consequuntur amet voluptates veritatis,
                    dignissimos unde culpa atque similique animi
                     assumenda praesentium, autem nesciunt adipisci
                      mollitia sapiente cumque earum qui magni odit.
                </p>
            </hgroup>
            <nav data-aos="fade-up" data-aos-delay="400"
            class="flex flex-col sm:flex-row justify-center lg:justify-start gap-4 mb-12"> 
                <a  href="#appointment"
                    class="bg-sky-600 hover:bg-sky-700 text-white text-center px-8 py-3 rounded-full transition
                    shadow-lg ">
                    Book Now
                </a>
                <a href="#services"
                class="border border-sky-600 text-sky-600 hover:bg-sky-50 text-center px-8 py-3 rounded-full transition"
                aria-label="Explore our services">
                Checkout Our services
                </a>
            </nav>
            <!-- Stats section -->
             <aside data-aos="fade-up" data-aos-delay="600" class="py-4">
                <ul class="flex flex-wrap justify-center lg:justify-start gap-x-6 gap-y-4 text-center">
                    <li v-for="item in stats" :key="item.id"
                    class="w-1/2 sm:w-auto">
                        <strong class="text-2xl font-bold text-sky-600">{{ item.value }}</strong>
                        <small class="block text-sm text-gray-600">{{ item.name }}</small>
                    </li>
                </ul>
             </aside>
         </section>
         <!-- Hero Image -->
          <figure data-aos="fade-up" data-aos-delay="700"
          class="w-full lg:w-1/2 flex justify-center relative"
          >
            <div class="relative w-full max-w-xs sm:max-w-sm md:max-w-md">
                <span class="bg-sky-500 rounded-full w-64 h-64 sm:w-80 sm:h-80 absolute -top-10 -left-10 opacity-20"
               ></span>
                 <span class="bg-teal-400 rounded-full w-64 h-64 sm:w-64 sm:h-64 absolute -bottom-10 -right-10 opacity-20"
                aria-hidden="true"></span>
                <img src="@assets/hero-img.jpg" alt="Software coding"
                class="relative z-10 rounded-full shadow-2xl w-full object-cover" width="400" height="400" loading="eager">
            </div>
          </figure>
    </article>
  </header>
</template>



<style>

</style>