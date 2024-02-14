<template>
  <div>
    <li v-for ></li>
  </div>
</template>

<script setup>
import { ref } from "vue";

//clicker logic
const clicked = ref(0);
function increment() {
  clicked.value++;
}

const colors = ref([
  {id: id++, name: White}
])
</script>

<style scoped>
img {
  width: 300px;
  height: 350px;
  object-fit: cover;
}
</style>