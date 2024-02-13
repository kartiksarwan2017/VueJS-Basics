<script setup>
  import {inject} from "vue";

  const numbers = inject("numbers");
  const addNumber = (num) => {
  numbers.value.push(num);
}
</script>

<template>
    <div>
        <h1>GreatGrandChild Component {{numbers}}</h1>
    </div>
</template>