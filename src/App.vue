<template>
  <div id="app">
    <MayTinh ten ="This is my computer"/>

  </div>
</template>

<script>

import MayTinh from "@/components/MayTinh.vue";

export default {
  name: 'App',
  components: {
    MayTinh,

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
