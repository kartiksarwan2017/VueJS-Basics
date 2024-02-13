<script setup>
import Parent from "./components/Parent.vue";
import { ref, provide } from "vue";

const numbers = ref([1, 2, 3, 4, 5, 6, 7, 8, 9]);

provide("numbers", numbers);

const addNumber = (num) => {
  numbers.value.push(num);
}

</script>

<template>
  <main>
    <Parent />
  </main>
</template>

<style scoped>
  main {
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  div {
    display: flex;
    flex-direction: column;
  }
</style>
