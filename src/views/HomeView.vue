<template>
  <div class="basic-container">
    <section class="paralax"><div class="paralax" aria-hidden="true"></div></section>
    <h2>MIS ÚLTIMOS VIAJES</h2>
    <section v-if="travels.length > 0" class="last-travels">
      <TravelCard
        v-for="travel in travels"
        :key="travel.id"
        :name="travel.name"
        :days="travel.days"
        :places="travel.places"
        :price="travel.price"
        :background-image="travel.backgroundImage"
        :year="travel.year"
      />
    </section>
    <section v-if="travels.length == 0" class="no-travels">
      <h3 class="message-empty">Sin viajes actualmente!</h3>
    </section>
    <section class="next-travels"></section>
  </div>
</template>

<script setup>
import TravelCard from '@/components/TravelCard.vue'
import { onMounted, ref } from 'vue'
import { getAllTravels } from '@/api/travelsService'
const travels = ref([])
onMounted(async () => {
  travels.value = await getAllTravels()
  const totalTravels = travels.value.length
  travels.value = travels.value.slice(totalTravels - 4, totalTravels)
})
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
.last-travels {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
  grid-gap: 3rem;
  justify-items: center;
  align-items: center;
  padding: 2rem;
  background-color: rgb(198, 228, 235);
}
h2 {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  font-size: 2em;
  font-weight: 700;
  height: 200px;
  background-color: azure;
  color: rgb(49, 47, 47);
}
.no-travels {
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 2em;
  background-color: rgb(198, 228, 235);
  height: 80vh;
  color: black;
}
.no-travels h3 {
  font-weight: 500;
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
