<script setup>
  import { useNumbersStore } from '../stores/numbers';

  const { numbers, filterNum } = useNumbersStore();
</script>

<template>
    <div>
        <h1>GreatGrandChild Component {{filterNum(16)}}</h1>
    </div>
</template>