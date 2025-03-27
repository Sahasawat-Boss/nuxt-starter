<template>
    <div>
        <h1>Home Page</h1>
        <div class="card-grid">
            <div class="card" v-for="data in items" :key="data.id">
                <img :src="data.coverimage" :alt="data.name" style="width:100%">
                <div class="container">
                    {{ data.id }} {{ data.name }}
                    <br />
                    <div class="button">
                        <NuxtLink :to="'/attractions/' + data.id">
                            Read More ->
                        </NuxtLink>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>


<script setup>//ผูกตัวแปรกับ Template

import { ref } from 'vue';

const items = ref([]);

fetch('https://www.melivecode.com/api/attractions')
    .then(res => res.json())
    .then((data) => {
        items.value = data
        console.log("Fetch API attractions:", data)
    })

</script>

<style scoped>
.card-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 0.8rem;
    padding: 0rem;
    width: 100%;
    max-width: 1200px;
    margin: 0 auto;
}

.card {
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
    transition: 0.3s;
    width: 100%;
}

.card:hover {
    box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
}

.container {
    padding: 2px 16px;
}

.button {
    background: #e4f0ff;
    border: 2px solid #19b99f;
    padding: 0.2rem 0.8rem;
    display: inline-block;
    margin-top: 0.5rem;
}
</style>