<!-- <script setup>
  // let count = 0;

  import { ref } from "vue";
  const count = ref(0);

  console.log(count);

  const addToCount = () => {
    console.log("from add to count: ", count);
    count.value = count.value + 1;
  }

  const subtractFromCount = () => {
    console.log("from subtract from count: ", count);
    count.value = count.value - 1;
  }
</script> -->

<script>
  export default {
    data() {
      return {
        count: 0
      }
    },
    methods: {
      addToCount() {
        this.count = this.count + 1
      },
      subtractFromCount() {
        this.count = this.count - 1 
      }
    }
  }
</script>

<template>
  <main>
    <div>
      <h4>The current count is...</h4>
      <h1>
        {{ count }}
      </h1>
      <button @click="subtractFromCount()">-</button>
      <button @click="addToCount() ">+</button>
    </div>
  </main>
</template>

<style scoped>
  main {
    background-color: aliceblue;
    width: 100vw;
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    color: black;
  }

  div {
    text-align: center;
  }

</style>