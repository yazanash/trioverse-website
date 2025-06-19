<script setup>
    import { Icon } from '@iconify/vue';
import { ref } from 'vue';
    const items=ref([
        {
            id:1,
            icon:'fa-solid:heart',
            text:'fa-solid:Some text about approach',
        },
        {
            id:2,
            icon:'fa-solid:user-md',
            text:'fa-solid:Some text about approach',
        },
        {
            id:3,
            icon:'fa-solid:clinic-medical',
            text:'fa-solid:Some text about approach',
        }
    ]);
    const stats=ref([
        {
            id:1,
            value:'10+',
            label:'Years exp',
            icon:'fa-solid:award'
        },
        {
            id:2,
            value:'10+',
            label:'Years exp',
            icon:'fa-solid:award'
        },
        {
            id:3,
            value:'10+',
            label:'Years exp',
            icon:'fa-solid:award'
        },
        {
            id:4,
            value:'10+',
            label:'Years exp',
            icon:'fa-solid:award'
        }
    ])
</script>
<template>
    <section class="py-14 overflow-hidden bg-gradient-to-br from-sky-100 to-teal-100" id="about">
        <div class="container mx-auto px-4">

        
        <article data-aos="fade-up" data-aos-delay="400"
        class="flex flex-col lg:flex-row items-center gap-12">
            <figure class="lg:w-5/12 relative">
                <div class="relative z-10 rounded-2xl overflow-hidden shadow-2xl w-full max-w-md mx-auto">
                    <img src="@assets/Digital.png" alt="" loading="lazy"
                    class="w-full h-auto object-cover aspect-[4/5 ]"> 
                    <div class="absolute inset-0 bg-gradient-to-t from-black/40 to-transparent" aria-hidden="true">

                    </div>
                </div>
                <span class="hidden lg:block absolute -bottom-8
                 -left-8 w-32 h-32 rounded-full bg-sky-500 opacity-20 z-0" aria-hidden="true"></span>

                  <span class="hidden lg:block absolute -top-8
                 -right-8 w-40 h-40 rounded-full bg-sky-600 opacity-20 z-0" aria-hidden="true"></span>
            </figure>
            <!-- content column -->
             <div data-aos="fade-up" data-aos-delay="600"
             class="lg:w--7/12">
                <header>
                    <h2 id="About heading" class="text-3xl
                    md:text-4xl font-bold text-gray-800 mb-6">
                        About <span class="text-sky-600">Trioverse</span>
                    </h2>
                    <p class="text-lg text-gray-600 mb-6">
                        Lorem ipsum dolor sit amet consectetur 
                        adipisicing elit. Aut, rem ipsum 
                        accusamus repudiandae, et ea deleniti
                         vitae nemo placeat dolorum atque quas
                          mollitia amet sapiente corporis illo
                           reiciendis architecto labore.
                    </p>
                </header>

                <section class="mb-8"> 
                    <h3 class="text-xl font-semibold text-gray-800 mb-4">Our approach</h3>
                    <ul class="space-y-3">
                        <li v-for="item in items" :key="item.id" class="flex items-start"> 
                            <figure class="bg-pink-100 p-1 rounded-full mr-3">
                                <Icon :icon="item.icon" class="text-sky-600" aria-hidden="true"></Icon>
                            </figure>
                            <p class="text-gray-700">{{ item.text }}</p>
                        </li>
                    </ul>
                </section>
                <!-- stats section -->
                 <section class="grid grid-cols-2 gap-4 mb-8">
                    <article v-for="stat in stats" :key="stat.id"
                    class="bg-white p-4 rounded-lg shadow-sm 
                    flex items-center">
                        <figure class="mr-3">
                            <Icon :icon="stat.icon" 
                            class="text-sky-500" aria-hidden="true"></Icon>
                        </figure>
                        <div>
                            <strong class="text-xl font-bold text-gray-800">
                                {{ stat.value }}
                            </strong>
                            <p class="text-sm text-gray-600">
                                {{ stat.label }}
                            </p>
                        </div>
                    </article>
                 </section>
                 <nav>
                    <a  href="#appointment"
                    class="bg-sky-600 hover:bg-sky-700
                     text-white text-center px-8 py-3 rounded-full
                     inline-block transition
                    shadow-lg focus:outline-none focus:ring-2 focus:ring-sky-800
                    focus:ring-offset-2">
                  Meet our specialist
                </a>
                 </nav>
            </div>
        </article>
        <aside class="mt-20 bg-white rounded-2xl p-8 md:p-12 shadow-lg relative overflow-hidden">
            <span class="absolute -top-20 -right-20 w-64 h-64 rounded-full bg-sky-500 opacity-40" aria-hidden="true"></span>
            <div class="relative z-10">
                <h3 class="text-2xl font-bold text-gray-800 mb-6">Our mission</h3>
                <blockquote class="text-lg text-gray-700 mb-6">
                    Lorem ipsum dolor sit amet consectetur 
                    adipisicing elit. Eveniet explicabo quae 
                    natus. Nostrum nihil quibusdam id illo 
                    atque modi, quam fuga quis, amet, 
                    asperiores numquam reiciendis quae
                     nobis dicta aliquid.
                </blockquote>
                <figure class="flex items-center">
                    <div class="w-12 h-12 rounded-full
                     bg-pink-100 flex items-center justify-center mr-4">
                        <Icon icon="fa-solid:user-md" class="text-sky-600"/>
                    </div>
                    <figcaption>
                        <cite class="font-semibold text-gray-800 not-italic">
                            Eng.Yazan Aboshash
                        </cite>
                        <p class="text-sm text-gray-600">Co-Founder & software engineer</p>
                    </figcaption>
                </figure>
            </div>
        </aside>
        </div>
    </section>
</template>



<style>

</style>