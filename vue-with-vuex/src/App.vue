<template>
  <div>
    <img alt="Vue logo" src="./assets/logo.png">
  <ComponentOne />
  </div>
</template>

<script>
import ComponentOne from "./components/Component.vue";
export default {
  name: 'App',
  components: {
    ComponentOne
  }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
