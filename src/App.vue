<template>
  <section class="splide" aria-label="Basic Structure Example">
    <div class="splide__track">
      <ul class="splide__list">
        <li class="splide__slide" style="height: 150px; width: 150px;background: green;">Slide 01</li>
        <li class="splide__slide" style="height: 150px; width: 150px;background: blue;">Slide 02</li>
        <li class="splide__slide" style="height: 150px; width: 150px;background: black;">Slide 03</li>
      </ul>
    </div>
  </section>
</template>

<script setup lang="ts">
import '@splidejs/splide/css/default';
import { Splide } from '@splidejs/splide';
import { onMounted } from 'vue';

onMounted(() => {
  let splide = new Splide('.splide', {
    type: 'loop',
    height: '50px',
    perPage: 3,
    focus: 3,
  })

  // Code à reprendre pour le carousel
  splide.on('pagination:updated', (data) => {
    data.items.forEach((element) => {
      element.button.style.background = element.button.classList.contains('is-active')
        ? 'red'
        : ''
    })
  })

  splide.mount()
})
</script>

<style scoped></style>
