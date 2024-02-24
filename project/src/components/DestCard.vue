<template>
  <div :class="buttoncontainerClass">
    <button :id="moneybuttonClass">Make Money</button>
  </div>

</template>

<script setup>
import { ref } from "vue";
const buttoncontainerClass = "buttoncontainer"
const moneybuttonClass = "moneybutton"
</script>


<style scoped>

button{
  width:20rem;
  height:15rem;
}
.buttoncontainer{
  margin-left:5rem;
  margin-right:5rem;
}
#moneybutton{
  margin-left:10rem;
  margin-top:5rem;
  background-image: url:;
}
</style>
