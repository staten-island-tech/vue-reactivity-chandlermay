<template>
  <div>
    <li v-for="color in colors" :key="colors.id" >
      <input type ="checkbox">
    <span :class="colortitles">{{ color.name }}</span>
    </li>
  </div>
</template>

<script setup>
import { ref } from "vue";

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