<template>
  <div class="container">
    <div class="row">
      <div class="col text-center">
        <h2>Counter: {{counter}}</h2>
      </div>
    </div>
    <div class="row">
      <div class="col col-6">
        <button class="btn btn-primary w-100" @click="increment">+</button>
      </div>
      <div class="col col-6">
        <button class="btn btn-danger w-100" @click="decrement">-</button>
      </div>
    </div>
  </div>
</template>

<script>
export default{
  name:"MyCounter",
  props: {
    startCount: {
      type: Number,
      default: 0
    },
    startStep: {
      type: Number,
      default: 1
    }
  },
  data() {
    return {
      counter: this.startCount,
      step: this.startStep
    };
  },
  methods: {
    increment() {
      this.counter += this.step;
    },
    decrement() {
      this.counter -= this.step;
    }
  },
}
</script>