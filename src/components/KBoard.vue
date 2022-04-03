<template>
  <div class="container">
    <div class="mb-3">
      <input class="form-control" v-model="newtask" placeholder="Enter Taks" @keydown.enter="add" >
    </div>
  </div>
  <div class="row mt-5">
    <div v-for="elem in krows" :key="elem" class="col-3">
      <KList :aufg="tasks" :elem="elem"></KList>
    </div>
  </div>
</template>

<script>
//import KList from "@/components/KList";
import KList from "@/components/KList";
export default {
  components: {
    KList
  },
  name: "KBoard",
  data() {
    return {
      drag: false,
      newtask: "",
      krows: ["Backlog","Offen","In Bearbeitung","Done"],
      tasks: [
        {name:"Vue verstehen",krow:"In Bearbeitung"},
        {name:"Duras",krow:"In Bearbeitung"},
        {name:"Kanban bauen",krow:"Offen"}
      ]
    }
  },
  methods:{
    add(){
      if(this.newtask)
      {
        this.tasks.push({name:this.newtask,krow:"Offen"})
        this.newtask="";

      }
    }
  }

}
</script>

<style scoped>
.kanban-colum{
  min-height: 300px;
}

</style>