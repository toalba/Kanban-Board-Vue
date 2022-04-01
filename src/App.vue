<template>
  <KBoard></KBoard>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import KBoard from "@/components/KBoard";

export default {
  name: 'App',
  components: {
    KBoard
  }
}
</script>
<link rel="stylesheet" href="node_modules/bootstrap/dist/css/bootstrap.css">
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
