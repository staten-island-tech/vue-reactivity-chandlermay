<template>
  <header>
<h1>Porsche</h1>
  </header>
    <div :class="containerClass">
    <Mainphoto v-for="car in cars" :key=cars.id :car="car" />
  </div>
</template>

<script setup>

import DestCard from "@/components/DestCard.vue";
import Mainphoto from "@/components/mainphoto.vue";
import { ref } from "vue";
const containerClass = "container"
const cars = ref([
  { id: "718", img: "https://shorturl.at/wFR14", caption:"The mid-engine sports car for two", price:"From $69,950" },
  { id: "911", img: "https://shorturl.at/hyBC6", caption:"The quintessential, rear engine sports car", price: "From $116,050"},
  { id: "Taycan", img: "https://shorturl.at/hvTU4",caption:"The pure expression of an electric sports car" , price: "From $92,550"},
  { id: "Macan", img: "https://configurator.porsche.com/model-start/pictures/XABFD1/extcam102.webp", caption:"The sports car of compact SUVs" , price: "From $62,550"},
  { id: "Cayenne", img: "https://shorturl.at/ftAC7",caption:"Impressive sports car with up to 5 seats" , price: "From $80,850"},
])

</script>

<style scoped>
.container{
    display:flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content:space-between;
}
</style>