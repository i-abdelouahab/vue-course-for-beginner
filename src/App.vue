<template>
  <RouterView />
</template>

<script>
import { RouterView } from 'vue-router';
export default {
  name: 'App',
  components: {
    RouterView
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

nav>a{
  padding-right: 16px;
}
</style>
