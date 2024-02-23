<template>
    <button @click="changeScreen" :class="cardClass">
        <h1 :class="titleClass">{{ car.id }}</h1>
        <h3>{{ car.caption }}</h3>
        <img :src="car.img" alt="" />
        <h3 :class="priceClass">{{ car.price }}</h3>
</button>
</template>

<script setup>
import { ref } from "vue"
const props = defineProps({
    car: Object,
});
const titleClass = "title"
const cardClass = "card"
const priceClass = "price"

</script>

<style scoped>
img {
    width: 300px;
}

.title {
    font-size: 35px;
}

.card {
    display: flex;
    flex-direction: column;
    align-items: center;
    min-width: 22.5%;
    padding-bottom: 1rem;
    border-radius: 1.6rem;
    background: #ffffff;
    margin-top: 2rem;
    padding-top: 0.5rem;
}

h1,
h2 {
    color: #000000
}

h3 {
    color: #000000
}

</style>

