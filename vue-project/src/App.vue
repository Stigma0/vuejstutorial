<template>
  <div id="app" class="container">
    <!-- Title of the To-Do List -->
    <h1>My To-Do List</h1>
    <div class="split">
      <div class="left">
        <!-- Input fields for adding a new task -->
        <input v-model="newTaskName" placeholder="Task Name" />
        <textarea v-model="newTaskDescription" placeholder="Task Description"></textarea>
        <input v-model="newTaskDuration" placeholder="Duration (in minutes)" type="number" />
        <!-- Button to add a new task -->
        <button @click="addTask">Add Task</button>
      </div>
      <div class="right">
        <ul>
          <!-- Render the TaskComponent for each task in the 'tasks' array -->
          <TaskComponent 
            v-for="task in tasks" 
            :key="task.id" 
            :task="task" 
            @deleteTask="deleteTask"
          />
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import TaskComponent from './TaskComponent.vue';

export default {
  name: 'App',
  components: {
    TaskComponent
  },
  data() {
    return {
      // Data properties to store new task information and existing tasks
      newTaskName: '',
      newTaskDescription: '',
      newTaskDuration: '',
      tasks: [], // Array to store tasks
      nextTaskId: 1 // ID for the next task to be added
    };
  },
  methods: {
    // Method to add a new task to the 'tasks' array
    addTask() {
      if (this.newTaskName.trim() === '') return; // Check if the task name is empty
      this.tasks.push({ 
        id: this.nextTaskId++, // Generate a unique task ID
        name: this.newTaskName, 
        description: this.newTaskDescription, 
        duration: this.newTaskDuration 
      });
      // Clear input fields after adding a task
      this.newTaskName = '';
      this.newTaskDescription = '';
      this.newTaskDuration = '';
    },
    // Method to delete a task based on its ID
    deleteTask(taskId) {
      this.tasks = this.tasks.filter(task => task.id !== taskId); // Remove the task with the specified ID
    }
  }
};
</script>
