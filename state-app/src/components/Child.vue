<script setup>
 import GrandChild from "./GrandChild.vue";
 import useNumbers from "../composables/useNumbers";

 const {numbers, addNumber} = useNumbers();
</script>

<template>
    <div>
        <h1>Child Component {{numbers}}</h1>
        <button @click="addNumber(4)">Add</button>
        <div class="line"></div>
        <GrandChild />
    </div>
</template>