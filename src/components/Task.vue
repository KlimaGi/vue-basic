<template>
  <div @dblclick="$emit('toggle-reminder', task.id)" :class="[task.reminder ? 'reminder' : '', 'task']">
    <h3>
      {{ task.text }}
      <i @click="$emit('delete-task', task.id)" class="fas fa-times"></i>
    </h3>
    <p>{{ task.day }}</p>
  </div>
</template>

<script>
export default {
  name: "Task",
  props: {
    task: Object,
  },
};
</script>

<style scope>
.fas {
  color: #8a8f8a;
}

.task {
  background: #e9f0e9;
  margin: 5px;
  padding: 10px 20px;
  cursor: pointer;
}

.task.reminder {
  border-left: 5px solid #008000;
}

.task h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
