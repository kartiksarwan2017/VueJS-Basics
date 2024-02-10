<script setup>
   import { ref, reactive } from "vue";

  //  const red = ref(0);
  //  const blue = ref(0);
  //  const green = ref(0);

  // const color = ref({
  //   red: 0,
  //   green: 0,
  //   blue: 0
  // });
 
  // const selecRandomColor = () => {
  //   color.value.red = Math.floor(Math.random()*255),
  //   color.value.blue = Math.floor(Math.random()*255),
  //   color.value.green = Math.floor(Math.random()*255)
  // }

  /* Defining State using reactive */
  const color = reactive({
    red: 0,
    green: 0,
    blue: 0
  });

  const selecRandomColor = () => {
    color.red = Math.floor(Math.random()*255),
    color.blue = Math.floor(Math.random()*255),
    color.green = Math.floor(Math.random()*255)
  }
</script>

<template>
  <main :style="{backgroundColor: `rgb(${color.red}, ${color.green}, ${color.blue})`}">
    <div>
      <input type="number" v-model="color.red" placeholder="red"/>
      <input type="number" v-model="color.blue"  placeholder="blue"/>
      <input type="number" v-model="color.green"  placeholder="green"/>
      <button @click="selecRandomColor">Select Random Color</button>
    </div>
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
