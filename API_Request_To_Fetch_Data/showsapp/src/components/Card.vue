<script setup>
import { defineProps } from 'vue';
const {name, image} = defineProps(['name', 'image']);

</script>

<template>
    <NCard>
        <template #cover>
          <img :src="image" />
        </template>
        <h3>{{ name }}</h3>
        <slot></slot>
    </NCard>
</template>

<style scoped>
.n-card {
    width: 200px;
    margin:10px 20px;

}
.n-card img {
    height: 250px;
}


</style>