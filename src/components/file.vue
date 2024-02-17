<template>
<div class="w-full h-full">
  <swiper-container
    :slides-per-view="1"
    navigation 
    pagination>
    <swiper-slide lazy="true" v-for=index in imagesLength>
    <img loading="lazy" :src="../assets/${index}.jpeg">
   </swiper-slide>
  </swiper-container>
</template>

<script setup>
  import { register } from 'swiper/element/bundle';
  register();

 const imagesLength = ref(20)
</script>