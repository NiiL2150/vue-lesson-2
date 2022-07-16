<template>
<div class="container">
  <img alt="Vue logo" src="./assets/logo.png">
  <h1>{{ name }}</h1>
  <!--
    <HelloWorld msg="Welcome to Your Vue.js App" :name="name" />
  -->
  <!--
  <MyCounter :startCount="5" :startStep="3" />
  -->
  <TaskList></TaskList>
</div>
</template>

<script>
import TaskList from './components/TaskList.vue'

export default {
  name: 'App',
  data () {
    return {
      name: 'NiiL'
    }
  },
  components: {
    TaskList
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /*
  margin-top: 60px;
  */
}
</style>
