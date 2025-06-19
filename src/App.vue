<script setup>
import { onMounted } from 'vue';
import Aos from 'aos';
import 'aos/dist/aos.css'
import Header from '@components/Header.vue';
import Hero from '@components/Hero.vue';
import Services from '@components/Services.vue';
import About from '@components/About.vue'
onMounted(()=>{
  Aos.init();
})
</script>

<template>
<Header></Header>
<Hero></Hero>
<Services></Services>
<About></About>
</template>

<style scoped>

</style>
