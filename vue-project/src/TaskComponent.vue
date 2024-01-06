<template>
    <!-- Display individual task information -->
    <div class="task">
      <h3>{{ task.name }}</h3> <!-- Display task name -->
      <p>{{ task.description }}</p> <!-- Display task description -->
      <p>Duration: {{ task.duration }} minutes</p> <!-- Display task duration -->
      <button @click="deleteTask(task.id)">Delete</button> <!-- Button to delete the task -->
    </div>
  </template>
  
  <script>
  export default {
    props: ['task'], // Define a prop called 'task' to receive task data from the parent component
    methods: {
      // Method to emit a custom event to notify the parent component to delete this task
      deleteTask(taskId) {
        this.$emit('deleteTask', taskId); // Emit the 'deleteTask' event with the task ID as data
      }
    }
  };
  </script>
  