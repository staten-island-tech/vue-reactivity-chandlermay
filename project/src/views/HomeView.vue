<template>
  <nav :class="navClass">
    <h1 :id="porschetitleClass">Porsche</h1>
  </nav>
  <div :class="containerClass">
    <ul v-for="car in cars" :key="cars.id">
      <div :class="cardClass">
        <h1 :class="titleClass">{{ car.id }}</h1>
        <h3>{{ car.caption }}</h3>
        <img :src="car.img" alt="" />
        <h3 :class="priceClass">{{ car.price }}</h3>
        <button @click="purchaseCar(car)">Add to Cart</button>
      </div>
    </ul>
  </div>
  <p>Total Cost: ${{ total }}</p>
</template>

<script setup>
import { ref,computed} from "vue";

const containerClass = "container"
const navClass = "nav"
const porschetitleClass = "porschetitle"
const titleClass = "title"
const cardClass = "card"
const priceClass = "price"

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
}

</script>

<style scoped>
.container {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-evenly;
}

.nav {
  justify-content: space-around;
  align-items: baseline;
  display: flex;
  flex-direction: row;
  padding-left: 2rem;
  padding-right: 2rem;
  padding-top: 1.5rem;
  align-items: center;
  font-family: "Porsche Next','Arial Narrow',Arial,'Heiti SC',SimHei,sans-serif";
  font-size: 2rem;
}

#porschetitle {
  padding-bottom: 5%;
  padding-top: 1.5%;
  text-align: center;
  text-justify: center;
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

h1,
h2 {
  color: #000000
}

h3 {
  color: #000000
}
</style>