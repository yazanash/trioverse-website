<script setup>
import { Icon } from '@iconify/vue';
import { ref } from 'vue';
const contactItems = ref([
  {
    id:1,
    icon:'fa-solid:map-marker-alt',
    title:"Our location",
    content:`<p>123 Saraya Cinema, City Center <br> As-Suwayda 016,  Syria</p>`
  },
    {
    id:2,
    icon:'fa-solid:phone-alt',
    title:"Phone Number",
    content:`
    <p>
        Call: <a href="tel:+963994916917" class="hover:text-sky-600">+963994916917</a>
        <br>
        Technical support: <a href="tel:+963949395273" class="hover:text-sky-600">+963949395273</a>
    </p>`
  },
    {
    id:3,
    icon:'fa-solid:envelope',
    title:"Email",
    content:`
    <p>
        <a href="mailto:yazan.ash.doonaas@gmail.com" class="hover:text-sky-600">yazan.ash.doonaas@gmail.com</a>
        <br>
        <a href="mailto:yazan.k.aboshash@gmail.com" class="hover:text-sky-600">yazan.k.aboshash@gmail.com</a>
    </p>`
  },
   {
    id:4,
    icon:'fa-solid:clock',
    title:"Working Hours",
    content:`
    <p>
        Sunday - Thursday: 09:00 AM - 08:00 PM <br>
        Technical support: 24/7
    </p>`
  },
])

const items = ref([
    {id:1,label:'Web design',value:'web'},
    {id:2,label:'business solution',value:'business'},
    {id:3,label:'E-commerce applications',value:'e-commerce'},
    {id:4,label:'information systems',value:'information'},
    {id:5,label:'Cross platform applications',value:'apps'},
])

</script>

<template>
    <section class="py-20 overflow-hidden bg-gradient-to-r from-sky-100 to-teal-100" id="contact"> 
        <div class="container mx-auto px-4">
            <header class="text-center relative mb-16" data-aos="fade-up" data-aos-delay="400">
                <span class="absolute -top-10 left-1/2 transform -translate-x-1/2 w-20 h-20 
                bg-sky-100 rounded-full opacity-20"></span>

                <h2 class="text-3xl md:text-4xl font-bold text-gray-800 mb-4 relative z-10">
                    Contact us <span class="text-sky-600">Now...!</span>
                </h2>
                <p class="text-lg text-gray-600 max-w-2xl mx-auto relative z-10">
                    Lorem ipsum dolor, sit amet consectetur adipisicing elit. 
                    Deserunt dolorum tenetur vero soluta suscipit est sequi optio ipsa,
                     iusto nam ducimus error, itaque, placeat sed?
                      At obcaecati non illo reiciendis?
                </p>
                <span class="absolute -top-6 right-1/4  w-16 h-16 
                bg-sky-100 rounded-full opacity-20"></span>
            </header>   
            <!-- main content -->
             <main class="flex flex-col lg:flex-row gap-12">
                <!-- contact info -->
                 <aside class="lg:w-2/5">
                    <div class="bg-white rounded-2xl shadow-xl p-8 h-full">
                        <h2 class="text-2xl font-bold text-gray-800 mb-6">
                            Stay in touch
                        </h2>
                        <address class="space-y-6">
                            <article v-for="item in contactItems" :key="item.id" class="flex items-start">
                                <figure class="bg-sky-100 p-3 rounded-full mr-4 flex-shrink-0">
                                    <Icon :icon="item.icon" class="text-sky-600 text-xl"></Icon>
                                </figure>
                                <div>
                                    <h3 class="font-semibold text-gray-800 mb-1">
                                        {{ item.title }}
                                    </h3>
                                    <div v-html="item.content" class="text-gray-600"> </div>
                                </div>
                            </article>
                        </address>
                        <figure class="m-8 rounded-xl overflow-hidden shadow-md">
                            <img src="@assets/hero-img.jpg" alt=""
                            class="w-full h-48 object-cover hover:scale-105 transition-transform duration-500"
                            width="400" height="200" loading="lazy">
                        </figure>
                    </div>
                 </aside>
                 <!-- contact form -->
                  <section class="lg:w-3/5">
                        <div class="bg-white rounded-2xl shadow-xl p-8 h-full">
                            <h2 class="text-2xl font-bold text-gray-800 mb-6">
                                Send us a message
                            </h2>
                            <form action="" class="space-y-6">
                                <fieldset class="grid grid-cols-1 md:grid-cols-2 gap-6">
                                    <div>
                                        <label 
                                        class="block text-gray-700 font-medium mb-2" for="name">Name</label>
                                        <input type="text" id="name" name="name"
                                        class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-sky-600
                                        focus:border-transparent " placeholder="Your name" required>
                                    </div>
                                     <div>
                                        <label 
                                        class="block text-gray-700 font-medium mb-2" for="phone">Phone number</label>
                                        <input type="tel" id="phone" name="phone"
                                        class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-sky-600
                                        focus:border-transparent " placeholder="+123456789" required>
                                    </div>
                                </fieldset>
                                    <div>
                                        <label 
                                        class="block text-gray-700 font-medium mb-2" for="email">Email</label>
                                        <input type="email" id="email" name="email"
                                        class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-sky-600
                                        focus:border-transparent " placeholder="name@example.com" required>
                                    </div>
                                    <div>
                                        <label 
                                        class="block text-gray-700 font-medium mb-2" for="email">Service intreset in:</label>
                                        <select  id="service" name="service"
                                            class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-sky-600
                                            focus:border-transparent " required>
                                            <option value="" selected> Select A service</option>
                                            <option v-for="item in items" :key="item.id" :value="item.value">{{ item.label }}</option>
                                        </select>
                                    </div>
                                      <div>
                                        <label 
                                        class="block text-gray-700 font-medium mb-2" for="message">Message</label>
                                        <textarea  id="message" name="message" rows="5"
                                        placeholder="Tell us Your message"
                                            class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-sky-600
                                            focus:border-transparent " required>
                                      </textarea>
                                    </div>
                                    <button type="submit"
                                    class="bg-sky-600 hover:bg-sky-700 text-white px-8 py-3 rounded-full transition 
                                    shadow-lg w-full md:w-auto">Send</button>
                            </form>
                        </div>
                  </section>
            </main>
        </div>
    </section>
</template>

