<template>
  <div>
    <mainphoto 
    :key="cars.id" 
    
    />
    <DestCard 
    
    />
  </div>
</template>

<script setup>

import DestCard from "@/components/DestCard.vue";
import { ref } from "vue";

let id = 0

const cars = ref([
  { id: id++, img: "https://shorturl.at/ajKS5" },
  { id: id++, img: "https://shorturl.at/ehlt9" },
])

</script>

<style scoped></style>