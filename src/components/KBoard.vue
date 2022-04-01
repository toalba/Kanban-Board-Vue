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
        <vuedraggable class="list-group kanban-colum" :model-value="tasks" group="aufgaben" @start="drag=true" @end="drag=false" item-key="id">
          <template  #item="{element}">
            <div class="list-group-item" v-if="element.krow===elem">{{element.name}}</div>
          </template>
        </vuedraggable>
      </div>
    </div>
  </div>
</template>

<script>
//import KList from "@/components/KList";
import vuedraggable from "vuedraggable";
export default {
  components: {
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