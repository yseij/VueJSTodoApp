<template>
  <v-list flat class="pt-0">
    <draggable :list="$store.getters.tasksFiltered" handle=".handle">
      <task
        v-for="task in $store.getters.tasksFiltered"
        :key="task.id"
        :task="task"
      />
    </draggable>
    <v-divider></v-divider>
  </v-list>
</template>

<script>
import draggable from "vuedraggable";
export default {
  components: {
    task: require("@/components/Todo/Task.vue").default,
    draggable,
  },
};
</script>
