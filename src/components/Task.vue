<template>
  <div
    @dblclick="$emit('toggle-reminder', task.id)"
    :class="[task.reminder ? 'reminder' : '', 'task']"
  >
    <!-- We can use Both ways , 
  Either to pass a function and then using emit 
  or directly emit a function... 
  Emit is use to access a function in level up app thats a parent app 
  that means we use it to pass a function from child to parent. -->

    <h3>
      {{ task.text }}
      <i @click="onDelete(task.id)" class="fas fa-solid fa-xmark"></i>
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
  methods: {
    onDelete(id) {
      this.$emit("delete-task", id);
    },
  },
};
</script>

<style scope>
.fas {
  color: red;
}
.task {
  background: #f4f4f4;
  margin: 5px;
  padding: 10px 20px;
  cursor: pointer;
}
.task.reminder {
  border-left: 5px solid green;
}
.task h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
