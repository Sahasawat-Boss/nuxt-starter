<template>
    <div>
        <h1> Page of id: {{ route.params.id }}</h1>
        <h3>{{ data.name }}</h3>
        <img :src="data.coverimage" alt="imag">
        <p>{{ data.detail }}</p>
    </div>
    
</template>

<script setup>
import { ref } from 'vue'
const route = useRoute()
const data = ref({})

console.log(route.params.id)
fetch('https://www.melivecode.com/api/attractions/' + route.params.id)
    .then(res => res.json())
    .then((result) => {
        data.value = result.attraction
    })
</script>

