<template>
    <div>
<img :src = "Cars.img" alt=""/>
    </div>
</template>

<script setup>
import {ref} from "vue"

const cars = ref([
    {id: white, img: "https://shorturl.at/betT7"},
    {id: black, img: "https://shorturl.at/agzNQ"},
    {id: red, img: "https://shorturl.at/xAEKV"},
    {id: yellow, img: "https://shorturl.at/uIMWX"},
])

</script>

<style lang="scss" scoped>

</style>