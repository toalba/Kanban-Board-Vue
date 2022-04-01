<template>
  <div class="container">
    <div class="mb-3">
      <input class="form-control" v-model="newtask" placeholder="Enter Taks" @keydown.enter="add" >
    </div>
  </div>
  <div class="row mt-5">
    <div v-for="elem in krows" :key="elem" class="col-3">
      <div class="p-2 alert alert-secondary">
        <h3>{{ elem }}</h3>
        <vuedraggable class="list-group kanban-colum" :model-value="tasks"  group="aufgaben" @start="drag=true" @end="drag=false" item-key="id">
          <template  #item="{element}">
            <KMessage :name="element.name" v-if="element.krow===elem"></KMessage>
          </template>
          <template #footer>
            <button @click="addPeople">Add</button>
          </template>
        </vuedraggable>
      </div>
    </div>
  </div>
  <KMessage :name="'Test'"></KMessage>
</template>

<script>
//import KList from "@/components/KList";
import vuedraggable from "vuedraggable";
import KMessage from "@/components/KMessage";
export default {
  components: {
    KMessage,
    vuedraggable,
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