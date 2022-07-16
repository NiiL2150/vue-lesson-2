<template>
  <div class="row">
    <div class="col text-center">
      <h2 :style="[taskCount >= 10 ? { color: 'red' } : { color: 'blue' }]">
        Task count: {{ taskCount }}
      </h2>
    </div>
  </div>
  <div class="row justify-content-center align-items-center">
    <div class="col col-3 text-center">
      <input type="text" v-model="taskInput" />
    </div>
    <div class="col col-2">
      <button class="btn btn-primary w-100" @click="addTask">
        Add task
      </button>
    </div>
  </div>
  <ul class="row text-center">
    <li style="display: inline-block" class="mt-4" v-for="task in tasks" :key="task">
      <VueTask :parentTask="task" />
        <button class="btn btn-danger" @click="removeTask(task.id)">
          Remove task
        </button>
    </li>
  </ul>
</template>

<script>
import VueTask from './VueTask.vue'

export class MyTask {
  constructor(value) {
    this.value = value;
    this.isMarked = false;
    this.isSelected = false;
    this.id = this.generateId();
  }

  generateId() {
    return Math.random().toString(36).substring(2, 15);
  }
}

export default{
  name: "TaskList",
  data() {
    return{
      tasks: [],
      taskInput: "",
    }
  },
  computed: {
    taskCount() {
      return this.tasks.length;
    }
  },
  methods: {
    addTask() {
      this.tasks.push(new MyTask(this.taskInput));
      this.taskInput = "";
    },
    removeTask(id) {
      this.tasks = this.tasks.filter(task => task.id !== id);
    }
  },
  components: {
    VueTask
  }
}
</script>