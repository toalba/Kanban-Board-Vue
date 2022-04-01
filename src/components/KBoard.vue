<template>
  <div>

  </div>


  <!--<div class="container">
    <table class="table-bordered">
      <thead>
        <tr>
          <th scope="col" v-for="erows in krows" :key="erows">{{erows}} </th>
        </tr>
      </thead>
      <tbody class="table-striped">
        <tr v-for="etask in tasks" :key="etask.krow">
          <th v-if="etask.krow=='Backlog'">{{etask.name}}</th>
          <th v-else> </th>
          <th v-if="etask.krow=='Offen'">{{etask.name}}</th>
          <th v-else> </th>
          <th v-if="etask.krow=='In Bearbeitung'">{{etask.name}}</th>
          <th v-else> </th>
          <th v-if="etask.krow=='Done'">{{etask.name}}</th>
          <th v-else> </th>
        </tr>
      </tbody>
    </table>
  </div> --->
</template>

<script>
export default {
  name: "KBoard",
  data() {
    return {
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