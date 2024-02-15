<template>
    <div>
<img :src = "Cars.img" alt=""/>
    </div>
</template>

<script setup>
import {ref} from "vue"

const id = 0
const cars = ref([
    {id: id++, img: "https://shorturl.at/betT7"},
    {id: id++, img: "https://shorturl.at/agzNQ"},
    {id: id++, img: "https://shorturl.at/xAEKV"},
    {id: id++, img: "https://shorturl.at/uIMWX"},
])

</script>

<style lang="scss" scoped>

</style>