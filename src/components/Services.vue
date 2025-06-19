<script setup>
import { ref } from 'vue';
const services = ref([
    {id:1,icon:"fa-solid:clinic-medical",
    title:"Software Development",
    link:"#development", 
    description: "Some description here"},

    {id:2,icon:"fa-solid:user-md",
    title:"System Design",
    link:"#design", 
    description: "Some description here"},

    {id:3,icon:"fa-regular:smile",
    title:"Websites and multi platform apps ",
    link:"#apps", 
    description: "Some description here"},

    {id:4,icon:"fa-solid:syringe",
    title:"Publishing and deployment",
    link:"#deploy", 
    description: "Some description here"}
])
</script>
<template>
    <section id="services" class="py-20 overflow-hidden bg-gradient-to-r 
    from-sky-100 to-teal-100" aria-labelledby="service-heading">
        <div class="container mx-auto px-4">
            <header data-aos="fade-up" data-aos-delay="500" class="text-center mb-16">
                <h2 id="services-heading" class="text-3xl md:text-4xl font-bold text-gray-800 mb-4">
                    Our <span class="text-sky-600">Services</span>
                </h2>
                <p class="text-lg text-gray-600 max-w-2xl mx-auto">
                    Discover Our creativity  
                </p>
            </header>
            <ul data-aos="fade-up" data-aos-delay="500"
            class="grid grid-cols-1 lg:grid-cols-4 gap-8">
                <li v-for="service in services" :key="service.id" >
                   <article class="bg-white rounded-xl p-8 hover-shadow-lg transition-all duration-300
                   hover:translate-y-[-5px] h-full flex flex-col">
                        <figure class="mb-6">
                            <Icon :icon="service.icon" class="text-4xl text-sky-600" aria-hidden="true"></Icon>
                        </figure>
                        <h3 class="text-xl font-bold text-gray-800 mb-3">
                            {{ service.title }}
                        </h3>
                        <p class="text-gray-600 mb-6 flex-grow">
                            {{ service.description }}
                        </p>
                        <a :href="service.link" :aria-label="`Learn more about ${service.title}`"
                         class="group inline-flex items-center
                          gap-2 text-sky-600 font-semibold
                           hover:text-sky-700 transition-colors mt-auto">
                           <span class="relative">
                            Learn More
                                <span class="absolute left-0 -bottom-0.5 w-full h-0.5 bg-sky-600 scale-x-0 group-hover:scale-x-100
                                                            transition-transform origin-left">

                                </span>
                                <Icon icon="weui:arrow-outlined"
                                class="w-5 h-5 transition-transform group-hover:translate-x-1"></Icon>
                           </span>
                           
                        </a>
                   </article>
                </li>
            </ul>
            <!-- CTA section -->
             <footer data-aos="fade-up" data-aos-delay="600" class="mt-20 text-center">
                <h3 class="text-2xl font-bold text-gray-800 mb-6">
                    Ready to transform your business
                </h3>
                 <a  href="#appointment"
                    class="bg-sky-600 hover:bg-sky-700
                     text-white text-center px-8 py-3 rounded-full
                     inline-block transition
                    shadow-lg focus:outline-none focus:ring-2 focus:ring-sky-800
                    focus:ring-offset-2">
                    Book Now
                </a>

             </footer>
        </div>
    </section>
</template>



<style>

</style>