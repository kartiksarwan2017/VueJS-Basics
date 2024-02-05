<script setup>
import { ref } from 'vue';
import BreakingBadCards from './components/BreakingBadCards.vue';
import RickMortyCards from "./components/RickMortyCards.vue";

const showRickMortyCards = ref(true);

</script>

<template>
 <main>
  <h1>HERO</h1> 
  <Suspense>
    <template #default>
        <BreakingBadCards />
    </template>
    <template #fallback>
        <div> 
            <p>Loading...</p>
        </div>
    </template>
  </Suspense>
  <RickMortyCards v-if="showRickMortyCards"/>
  <button @click="showRickMortyCards = !showRickMortyCards">Toggle</button>
 </main>
</template>

