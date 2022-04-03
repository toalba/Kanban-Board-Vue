<template>
  <div class="p-2 alert alert-secondary">
    <h3>{{ elem }}</h3>
    <vuedraggable class="list-group kanban-colum" :list="aufg" group="Kanbanliste" @start="drag=true" @end="drag=false" @drop="dropfunction" item-key="name">
      <template  #item="{element}">
        <KMessage :name="element.name" v-if="element.krow===elem"></KMessage>
      </template>
    </vuedraggable>
  </div>
</template>

<script>
import vuedraggable from "vuedraggable"
import KMessage from "@/components/KMessage";

export default {
  components:{
    vuedraggable,
    KMessage

  },
  name: "KList",
  props: {
    elem:String,
    aufg:Object
  },
  data() {
    return {
      drag: false,
    }
  },
  methods:{
    dropfunction(){

    }
  }
}
</script>

<style scoped>
  .kanban-colum{
    min-height: 50vh;
  }
</style>