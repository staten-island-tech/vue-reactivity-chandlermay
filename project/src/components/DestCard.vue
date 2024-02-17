<template>
  <div>
    <ul  :id="list" v-for="color in colors" :key="colors.id" >
    <button @click="display" :class="button" id="colors.id">{{ color.name }}</button>
    </ul>
  </div>
</template>

<script setup>
import { ref } from "vue";

const chosen = ref(false);

function display(){
  chosen.value = !chosen.value;
  console.log(chosen.value);
}

let id = 0;
const colors = ref([
  {id: id++, name: "White"},
  {id: id++, name: "Black"},
  {id: id++, name: "Guards Red"},
  {id: id++, name: "Racing Yellow"},
  {id: id++, name: "GT Silver Metallic"},
  {id: id++, name: "Arctic Grey"},
  {id: id++, name: "Shark Blue"},
  {id: id++, name: "Ice Grey Metallic"},
])
</script>

<style scoped>
img {
  width: 300px;
  height: 350px;
  object-fit: cover;
}
button {
  width: 7rem;
  height: 3rem;
}
#list {
  display:flex;
  flex-direction: row;
}
</style>
