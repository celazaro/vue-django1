<template>
  <div class="container px-0">
    <NavbarComponents />
  </div>

      <!-- Hero Start -->
  <div class="container-fluid py-1 mb-1 ">
      <div class="container py-1 text-center">
          
          <div class="row g-5 align-items-center">
              <h5 class="mb-1 display-3 text-primary">Verdulería y Frutería Carlitos</h5>
              <img class='img-fluid' src='../src/assets/img/hero-img.jpg'>
              <h3 class="mb-1 text-secondary">100% Productos de Calidad </h3>

          </div>
      </div>
      <hr>
      <hr>
  </div>
  <!-- Hero End -->

  <router-view/>

  <FooterComponents />

</template>

<script setup >

import NavbarComponents from './components/NavbarComponents.vue';
import FooterComponents from './components/FooterComponents.vue';

</script>


<style>



</style>
 