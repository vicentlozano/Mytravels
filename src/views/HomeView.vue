<template>
  <div class="basic-container">
    <section class="paralax"><div class="paralax" aria-hidden="true"></div></section>
    <section class="last-travels">
      <TravelCard/>
    </section>
    <sectionm class="next-travels"> </sectionm>
  </div>
</template>

<script setup>
import TravelCard from '@/components/TravelCard.vue';

</script>

<style lang="scss" scoped>
$primary-color: black;
$secondary-color: white;
$font-size-large: 3em;
$font-size-medium: 2em;
$font-weight-bold: 900;
$gap-spacing: 2rem;
$margin-spacing: 3rem;
$height-paralax-large: 70vh;
$height-paralax-small: 30vh;
.basic-container {
  display: grid;
  grid-template-rows: auto auto;
  height: 100%;
  width: 100%;
}
.paralax {
  display: flex;
  width: 100%;
  height: $height-paralax-large;
  background-image: url('../assets/boat.jpg');
  background-attachment: fixed;
  background-position: center;
  background-color: $primary-color;
  background-repeat: no-repeat;
  background-size: cover;
  background-position-x: center;
}

@media (max-width: 768px) {
}
@media (min-width: 769px) and (max-width: 1300px) {
}
@media (min-width: 1301px) {
}
@media (min-width: 1701px) {
}
</style>
