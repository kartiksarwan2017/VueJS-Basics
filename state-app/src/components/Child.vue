<script setup>
 import GrandChild from "./GrandChild.vue";
 import {inject} from "vue";

 const numbers = inject("numbers");
 const addNumber = (num) => {
  numbers.value.push(num);
}
</script>

<template>
    <div>
        <h1>Child Component {{numbers}}</h1>
        <button @click="addNumber(4)">Add</button>
        <div class="line"></div>
        <GrandChild />
    </div>
</template>