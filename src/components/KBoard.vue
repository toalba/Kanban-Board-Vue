<template>
  <table class="">
    <tr>
      <th v-for="erows in krows" :key="erows">{{erows}}</th>
    </tr>
  </table>
</template>

<script>
export default {
  name: "KBoard",
  data() {
    return {
      message: "Hi",
      krows: ["Backlog","Offen","In Bearbeitung","Done"],
      tasks: [
        {name:"Vue verstehen",krow:"In Bearbeitung"},
        {name:"Kanban bauen",krow:"Offen"}
      ]
    }
  }
}
</script>

<style scoped>

</style>