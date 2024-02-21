<template>
    <div :class="cardClass">
        <h1 :class="titleClass">{{ car.id }}</h1>
        <h2>{{ car.caption }}</h2>
        <img :src="car.img" alt="" />
        <h3 :class= "priceClass">{{ car.price }}</h3>
    </div>
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
    display:flex;
    flex-direction: column;
    align-items: center;
    padding:2rem;
}

.price{

}
</style>

