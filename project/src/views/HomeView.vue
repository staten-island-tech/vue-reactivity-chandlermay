<template>
  <nav :class="navClass">
    <button :id="moneybuttonClass" @click="increase" >Make Money</button>
    <h1 :id="porschetitleClass">Porsche</h1>
    <h2 :id="balancetitleClass">Bank Balance: {{ balance }}</h2>
  </nav>
  <div :class="containerClass">
    <Mainphoto  v-for="car in cars" :key=cars.id :car="car" :balance = "balance" :actualprice = cars.actualprice />
  </div>
</template>

<script setup>
import Mainphoto from "@/components/mainphoto.vue";
import { ref } from "vue";

const containerClass = "container"
const navClass = "nav"
const porschetitleClass = "porschetitle"
const moneybuttonClass = "moneybutton"
const balancetitleClass = "balancetitle"


const cars = ref([
  { id: "718", img: "https://shorturl.at/wFR14", caption: "The mid-engine sports car for two", price: "From $69,950" , owned: ref(0), actualprice:69950 },
  { id: "911", img: "https://shorturl.at/hyBC6", caption: "The quintessential, rear engine sports car", price: "From $116,050" , owned: ref(0), actualprice:116050 },
  { id: "Taycan", img: "https://shorturl.at/hvTU4", caption: "The pure expression of an electric sports car", price: "From $92,550", owned: ref(0), actualprice:92550 },
  { id: "Macan", img: "https://configurator.porsche.com/model-start/pictures/XABFD1/extcam102.webp", caption: "The sports car of compact SUVs", price: "From $62,550" , owned: ref(0), actualprice: 62550},
  { id: "Cayenne", img: "https://shorturl.at/ftAC7", caption: "Impressive sports car with up to 5 seats", price: "From $80,850" , owned: ref(0), actualprice: 80850},
])

const balance = ref(0);
function increase(){
  balance.value += 11000;
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
  padding-right:2rem;
  padding-top:1.5rem;
  align-items: center;
  font-family: "Porsche Next','Arial Narrow',Arial,'Heiti SC',SimHei,sans-serif";
  font-size:2rem;
}

#porschetitle {
  padding-bottom: 5%;
  padding-top: 1.5%;
  text-align: center;
  text-justify: center;
}

#moneybutton{
  background-image: url("https://cdn-icons-png.flaticon.com/128/2936/2936744.png");
  background-size:contain;
  font-size:2rem;
  border-radius: 1.6rem;
  font-family: "Porsche Next','Arial Narrow',Arial,'Heiti SC',SimHei,sans-serif";
}
.makeMoney {
  width: 6rem;
  height: 2rem;
}

#balancetitle {
  font-size: 2rem;
}
</style>