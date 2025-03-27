<template>
    <div>
        <h1>Home Page</h1>

    </div>
</template>

<script setup> //ผูกตัวแปรกับ Template

import { ref } from 'vue';

const items = ref([]);

fetch('https://www.melivecode.com/api/attractions')
.then(res => res.json())
.then((data) => {
    items.value = data
    console.log("Fetch API attractions:", data)
})


</script>