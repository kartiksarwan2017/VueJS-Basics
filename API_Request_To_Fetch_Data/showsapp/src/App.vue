<script setup>
import BreakingBadCards from './components/BreakingBadCards.vue';
import RickMortyCards from "./components/RickMortyCards.vue";
import PracticeSlot from "./components/PracticeSlot.vue";

</script>

<template>
 <main>
  <!-- <h1>HERO</h1> 
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
  <RickMortyCards /> -->
  <PracticeSlot>
    <div>
        <h1>Slot</h1>
    </div>
    <template #header>
        <div>
            <h2>This is a header</h2>
            <a href="">page 1</a>
            <a href="">page 2</a>
        </div>
    </template>
    <template #footer>
        <div>
            <ul>
                <li>Facebook</li>
                <li>Instagram</li>
                <li>Linkedin</li>
            </ul>
        </div>
    </template>
  </PracticeSlot>
 </main>
</template>

