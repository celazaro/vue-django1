<template>

  <NavbarComponents  v-if = "$route.path !== '/'" />


  <HeroComponents  v-if = "$route.path !== '/'"  />

  <router-view/>

  <FooterComponents />

</template>

<script setup >

import NavbarComponents from './components/NavbarComponents.vue';
import HeroComponents from './components/HeroComponents.vue';
import FooterComponents from './components/FooterComponents.vue';

</script>


<style>



</style>
 