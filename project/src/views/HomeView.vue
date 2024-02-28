<template>
  <video autoplay muted loop :id="backgroundvideoClass">
  <source src="https://cdn.coverr.co/videos/coverr-rear-view-of-a-porsche-gt3-3421/1080p.mp4" type="video/mp4">
</video>

  <nav :class="navClass">
    <h1 :id="porschetitleClass">Porsche</h1>
  </nav>
  <div :class="bigcontainerClass">
  <div :class="containerClass" >
    <div v-for="car in cars" :key="cars.id" :class="cardClass">
      <h1 :class="titleClass">{{ car.id }}</h1>
      <h4>{{ car.caption }}</h4>
      <img :src="car.img" alt="" />
      <h3 :class="priceClass">{{ car.price }}</h3>
      <button @click="purchaseCar(car)">Add to Cart</button>
    </div>
  </div>
  <!-- <div :class="cartcontainerClass"></div> -->
  <div :class="cartClass">
    <h2>Total Cost: ${{ total }}</h2>
    <h4>Number Of Cars Selected:</h4>
    <ul v-for="car in cars">
      <h3> {{ car.id }}: {{ car.owned }}</h3>
    </ul>
  </div>
  </div>
</template>

<script setup>
import { ref, computed } from "vue";

const containerClass = "container"
const navClass = "nav"
const porschetitleClass = "porschetitle"
const titleClass = "title"
const cardClass = "card"
const priceClass = "price"
const cartClass = "cart"
const bigcontainerClass = "bigcontainer"
const backgroundvideoClass = "backgroundvideo"

const cars = ref([
  { id: "718", img: "https://shorturl.at/wFR14", caption: "The mid-engine sports car for two", price: "From $69,950", owned: ref(0), actualprice: 69950 },
  { id: "911", img: "https://shorturl.at/hyBC6", caption: "The quintessential, rear engine sports car", price: "From $116,050", owned: ref(0), actualprice: 116050 },
  { id: "Taycan", img: "https://shorturl.at/hvTU4", caption: "The pure expression of an electric sports car", price: "From $92,550", owned: ref(0), actualprice: 92550 },
  { id: "Macan", img: "https://configurator.porsche.com/model-start/pictures/XABFD1/extcam102.webp", caption: "The sports car of compact SUVs", price: "From $62,550", owned: ref(0), actualprice: 62550 },
  { id: "Cayenne", img: "https://shorturl.at/ftAC7", caption: "Impressive sports car with up to 5 seats", price: "From $80,850", owned: ref(0), actualprice: 80850 },
])


const cart = ref([]);
const total = computed(() => {
  return cart.value.reduce((total, price) => total + price, 0);
});

function purchaseCar(car) {
  cart.value.push(car.actualprice);
  car.owned++;
}

</script>

<style scoped>
.container {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-evenly;
  width: 70%;
}

.nav {
  justify-content: space-around;
  align-items: baseline;
  display: flex;
  flex-direction: row;
  padding-left: 2rem;
  padding-right: 2rem;
  /* padding-top: 1.5rem; */
  align-items: center;
  font-family: "Porsche Next','Arial Narrow',Arial,'Heiti SC',SimHei,sans-serif";
  font-size: 2rem;
}

#porschetitle {
  padding-bottom: 5%;
  padding-top: 1.5%;
  text-align: center;
  text-justify: center;
  color:#ffffff;
}

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

h1,h2,h3,h4 {
  color: #000000
}

.cart {
  display:flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  background: #ffffff;
  border-radius: 0.8rem;
  width: 15%;
  height: 16rem;
  /* margin-left: 7%; */
}
.bigcontainer {
  display:flex;
  flex-direction: row;
  align-items:baseline;
  justify-content: space-around;
}

#backgroundvideo {
  position: fixed;
  top: 0;
  left: 0;
  min-width: 100%;
  min-height: 100%;
  z-index: -1;
}

</style>