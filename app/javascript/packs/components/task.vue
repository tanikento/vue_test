<template>
  <div>
    <draggable :options="{group:'tasks',animation:300,delay:50}">
      <div class="tasks" v-for="task in lane.tasks.edges">
        <b-alert class="task" show variant="dark">
          <draggable>{{ task.node.title }}</draggable>
        </b-alert>
      </div>
    </draggable>
  </div>
</template>

<script>
import draggable from 'vuedraggable';

export default {
  components: {
    draggable,
  },
  props: [ "lane" ],
  data(){
    return {
      title: "",
      lane: [],
    }
  },
}

</script>

<style>
.body {
}

.tasks {
}

.task {
  box-shadow: 0 0px 20px rgba(0,0,0,0.2);
}

.form-control {
  width: 100%;
  margin: 10px 0px;
}
</style>
