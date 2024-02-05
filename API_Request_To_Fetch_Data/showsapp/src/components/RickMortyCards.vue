<script setup>
import axios from "axios";
import { ref, watch, onMounted, onUpdated, onUnmounted, onBeforeMount } from "vue";
import Card from "./Card.vue";

const page = ref(0);

onBeforeMount(() => {
    console.log("COMPONENT IS ABOUT TO MOUNT!");
});

onMounted(() => {
    console.log("COMPONENT IS MOUNTED!");
});

onUpdated(() => {
    console.log("COMPONENT WAS UPDATED");
});

onUnmounted(() => {
    console.log("COMPONENT UNMOUNTED");
});

</script>

<template>
    <div class="container">
        <div class="cards">
            <p style="color: white;">{{ page }}</p>
            <!-- <Card 
                v-for="character in characters" 
                :key="character.id" 
                :name="character.name"
                :image="`${character.thumbnail.path}.jpg`" 
                :seriesItems="character.series.items" 
            /> -->
        </div>
        <div class="button-container">
            <button @click="page--">&lt;</button>
            <button @click="page++">&gt;</button>
        </div>
    </div>
</template>

<style scoped>
.container {
    background-color: rgb(27, 26, 26);
    padding: 30px;
    margin-top: 100px;
}

.cards {
    max-width: 1000px;
    margin: 0 auto;
    display: flex;
    flex-wrap: wrap;
    height: 700px
}

.cards h3 {
    font-weight: bold;
}

.cards p {
    font-size: 10px;
}

.jobs {
    display: flex;
    flex-wrap: wrap;
}

.button-container {
    display: flex;
    justify-content: center;
    padding-top: 150px;
}

.button-container button {
    border: none;
    width: 50px;
    height: 50px;
    border-radius: 100%;
    margin: 0 5px;
    cursor: pointer;
}

.spinner {
    display: flex;
    align-items: center;
    justify-content: center;
}</style>