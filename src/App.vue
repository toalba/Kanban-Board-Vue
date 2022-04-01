<template>
  <Button class="btn-danger">Click me</Button>
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
