<template>
  <div class="card">
    <img class="card-img-top" src="@/assets/logo.png" alt="Card image cap" style="max-width: 2.3vw">
    <div class="card-body">
      <h5 class="card-title">{{name}}</h5>
      <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
      <a  href="#" class="btn btn-primary">Go somewhere</a>
    </div>
  </div>
</template>

<script>
export default {
  name: "KMessage",
  props:['name']
}
</script>

<style scoped>

</style>