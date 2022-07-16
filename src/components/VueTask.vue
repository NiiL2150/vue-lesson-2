<template>
  <h3
    :style="[task.isMarked ? { backgroundColor: 'yellow' } : { backgroundColor: 'transparent' }, task.isSelected ? { color: 'green' } : { color: 'black' }]"
    @click="task.isMarked = !task.isMarked">
    {{ task.value }}
  </h3>
  <button class="btn btn-primary" @click="task.isSelected = !task.isSelected">
    Select task
  </button>
</template>

<script>

export default{
  name: "VueTask",
  props: {
    parentTask: {
      required: true
    }
  },
  data() {
    return {
      task: this.parentTask
    }
  }
}
</script>