<template>
  <div
    @dblclick="$emit('toggle-reminder', task.id)"
    :class="[task.reminder ? 'reminder' : '', 'task']"
  >
    <h3>
      {{ task.text }}
      <Icon
        @click="$emit('delete-task', task.id)"
        icon="material-symbols:delete-outline"
        class="del"
      />
    </h3>
    <p>
      {{ task.day }}
      <!-- <Icon icon="material-symbols:edit-square-outline" class="edit" /> -->
    </p>
  </div>
</template>

<script>
import { Icon } from "@iconify/vue";
export default {
  name: "Task",
  props: {
    task: Object,
  },
  components: {
    Icon,
  },
};
</script>

<style scoped>
.del {
  color: red;
}
.edit {
  color: #ffa309;
}

.task {
  background: #fefefe;
  border-radius: 5px;
  margin: 9px;
  padding: 13px 12px;
  cursor: pointer;
}

.task.reminder {
  border-left: 4px solid #ffa309;
}

.task h3,
.task p {
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-weight: 400;
  font-size: 18px;
  margin-bottom: 10px;
  line-height: 22px;
}
</style>