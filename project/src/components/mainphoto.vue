<template>
    <button @click="AddOwn" :class="cardClass">
        <h1 :class="titleClass">{{ car.id }}</h1>
        <h3>{{ car.caption }}</h3>
        <img :src="car.img" alt="" />
        <h3 :class="priceClass">{{ car.price }}</h3>
        <h4>Owned: {{ car.owned }}</h4>
</button>
</template>

<script setup>
import { ref } from "vue"
const props = defineProps({
    car: Object,
    balance: Number,
    actualprice: Number,
});
const titleClass = "title"
const cardClass = "card"
const priceClass = "price"

function AddOwn(){
    if (props.balance >= props.car.actualprice){
        props.car.owned++;
        console.log(props.balance - props.car.actualprice);
    } else {
       prompt("YOU'RE TOO POOR. SELECT OK AND WORK HARDER."); 
    }
}
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

