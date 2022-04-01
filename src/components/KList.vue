<template>
  <div class="p-2 alert alert-secondary">
    <h3>{{ elem }}</h3>
    <vuedraggable class="list-group kanban-colum" :model-value="aufg" group="aufgaben" @start="drag=true" @end="drag=false" item-key="id">
      <template  #item="{element}">
        <div class="list-group-item" v-if="element.krow===elem">{{element.name}}</div>

      </template>
    </vuedraggable>
  </div>
</template>

<script>
import vuedraggable from "vuedraggable"

export default {
  components:{
    vuedraggable
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
  }
}
</script>

<style scoped>
  .kanban-colum{
    min-height: 300px;
  }
</style>