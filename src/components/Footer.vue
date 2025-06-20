<script setup>
import { Icon } from '@iconify/vue';
import { ref,computed } from 'vue';

const currentYear=computed(()=>new Date().getFullYear())

const links = ref([
    { id: 1, icon: 'fa-brands:facebook-f', label: "Facebook" },
    { id: 2, icon: 'fa-brands:twitter', label: "Twitter" },
    { id: 3, icon: 'fa-brands:instagram', label: "Instagram" },
    { id: 4, icon: 'fa-brands:linkedin-in', label: "Linkedin" },
])

const quickLinks = ref([
    {id:1,name:"Home",link:"#home"},
    {id:2,name:"Services",link:"#services"},
    {id:3,name:"About Us",link:"#about"},
    {id:4,name:"Our Specialists",link:"#specialists"},
    {id:5,name:"Contact Us",link:"#contact"},
])

const contactInfo=ref([
    {
        icon:"material-symbols:location-on",
        content:{
            type:"a",
            props:{
                href:"",
                target:'_blank',
                rel:'noopener norefferrer'
            },
            text:"123 Trioverse street"
        }
        
    },
      {
        icon:"fa-solid:phone-alt",
        content:{
            type:"a",
            props:{
                href:"tel:+963994916917",
            },
            text:"+9639949161917"
        }
        
    },{
        icon:"material-symbols:mail",
        content:{
            type:"a",
            props:{
                href:"mailto:yazan.ash.doonaas@gmail.com",
            },
            text:"123 Trioverse street"
        }
        
    },
    {
        icon:"fa-solid:clock",
        content:{
            type:"span",
            props:{},
            text:"Sun - Thu : 9 AM - 8 PM "
        }
        
    },
])
const legalLinks=ref([
    {id:1,name:"Privacy Policy",link:"#privacy"},
    {id:1,name:"Terms of Service",link:"#privacy"},
    {id:1,name:"Privacy Policy",link:"#privacy"},
    {id:1,name:"Sitemap",link:"#privacy"}
])
</script>


<template>
    <footer class="bg-secondary text-white pt-16 pb-8 ">
        <div class="container mx-auto px-4">
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-12 mb-12">
                <section class="lg:col-span-2">
                    <header class="flex items-center mb-6">
                        <Icon icon="fa-solid:clinic-medical" class="text-3xl text-primary mr-3"></Icon>
                        <h2 class="text-2xl font-bold">Trioverse</h2>
                    </header>
                    <p class="text-gray-400 mb-6">
                        Lorem ipsum dolor sit amet consectetur adipisicing elit.
                        Quam facere recusandae vel numquam laboriosam, consectetur, beatae fuga,
                        et iure provident molestiae alias fugiat cum corporis sit placeat mollitia
                        aliquid quidem!
                    </p>
                    <nav>
                        <ul class="flex space-x-4">
                            <li v-for="link in links" :key="link.id">
                                <a href="" class="bg-gray-800
                                 hover:bg-primary w-10 h-10 rounded-full 
                                 flex items-center justify-center transition">
                                    <Icon :icon="link.icon" class="text-lg"></Icon>
                                </a>
                            </li>
                        </ul>
                    </nav>
                </section>
                <!-- Quick links -->
                 <section>
                    <h3 class="text-xl font-bold mb-6 relative pb-2 after:content- after:absolute after:left-0 after:bottom-0 after:w-12 after:h-1 after:bg-primary">
                        Quick Links
                    </h3>
                    <nav>
                        <ul class="space-y-3">
                            <li v-for="link in quickLinks" :key="link.id">
                                <a :href="link.link" class="text-gray-400
                                 hover:text-primary transition">
                                   {{ link.name }}
                                </a>
                            </li>
                        </ul>
                    </nav>
                 </section>
                 <!-- contact info  -->
                  <address> 
                      <h3 class="text-xl font-bold mb-6 relative pb-2 after:content- after:absolute after:left-0 after:bottom-0 after:w-12 after:h-1 after:bg-primary">
                        contact us
                    </h3>
                    <nav>
                        <ul class="space-y-4">
                            <li v-for="item in contactInfo" :key="item.id"
                            class="flex items-start">
                               <Icon :icon="item.icon"
                               class="text-primary text-xl mt-1 mr-4 flex-shrink-0">
                               </Icon>
                               <component :is="item.content.type" v-bind="item.content.props"
                               class="text-gray-400 hover:text-primary transition">{{ item.content.text }}</component>
                            </li>
                        </ul>
                    </nav>
                  </address>
            </div>
            <!-- news letter -->
             <section class="bg-gray-800 rounded-xl p-8 mb-12">
                <div class="flex flex-col lg:flex-row items-center justify-between">
                    <div class="mb-6 lg:mb-0 lg:mr-8">
                        <h3 class="text-xl font-bold mb-2">
                            Join our Newsletters
                        </h3>
                        <p class="text-gray-400">Lorem ipsum dolor sit amet consectetur adipisicing elit. 
                            Voluptas ducimus ut doloremque culpa ea vero atque expedita natus facere nobis 
                            fugiat quaerat suscipit, eos, quibusdam maiores repellat nesciunt cumque? Magni?
                        </p>
                    </div>
                    <form action="" class="flex flex-col sm:flex-row w-full lg:w-auto">
                        <label for="news-email" class="sr-only">
                            Email Address
                        </label>
                        <input type="email" placeholder="Enter your email" name="news-email" id="news-email" class="px-6 py-3 rounded-full bg-gray-700 text-white focus:outline-none focus:ring-2
                         focus:ring-primary mb-3 sm:mb-0 sm:mr-4 w-full" required>
                         <button type="submit"
                                    class="bg-sky-600 hover:bg-sky-700 text-white px-8 py-3 rounded-full transition 
                                    shadow-lg whitespace-nowrap">Subscribe</button>
                    </form>
                </div>
             </section>
             <footer class="pt-8 border-t border-gray-800 flex flex-col md:flex-row justify-between items-center">
                <p class="text-gray-500 text-sm mb-4 md:mb-0" >
                    &copy;{{ currentYear }} Trioverse.All rights reserved
                </p>
                <nav>
                    <ul class="flex space-x-6">
                        <li v-for="elink in legalLinks" :key="elink.id">
                            <a :href="elink.link"
                            class="text-gray-500 hover:text-primary text-sm transition">{{ elink.name }}</a>
                        </li>
                    </ul>
                </nav>
             </footer>
        </div>
    </footer>
</template>


<style></style>