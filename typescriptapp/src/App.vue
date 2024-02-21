<script setup lang="ts">
  import { ref } from "vue";

  const number = ref("");
</script>

<template>
  <main>
    <h1>Guess My Favourite Number</h1>
    <input type="text" v-model="number" />
    <h1 v-if="number === '27'">YOU GUESS IT</h1>
    <!-- {{ typeof(number) }}
    {{ typeof(27) }} -->
  </main>
</template>

<style scoped>
</style>
