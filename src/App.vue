<!-- <script setup>
import { ref } from "vue";
const count = ref(0);
</script> -->
<script>
export default {
  // Properties returned from data() become reactive state
  // and will be exposed on `this`.
  data() {
    return {
      count: 0,
    };
  },

  // Methods are functions that mutate state and trigger updates.
  // They can be bound as event handlers in templates.
  methods: {
    increment() {
      this.count++;
    },
  },

  // Lifecycle hooks are called at different stages
  // of a component's lifecycle.
  // This function will be called when the component is mounted.
  mounted() {
    console.log(`The initial count is ${this.count}.`);
  },
};
</script>

<template>
  <section class="head-1">
    <div class="section-one">
      <h1>Part 1</h1>
      <button @click="count++">Count is: {{ count }}</button>
    </div>
  </section>
</template>

<style scoped>
button {
  font-weight: bold;
  display: flex;
  width: 100px;
  margin-top: 20px;
}

.section-one {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  /* top: 50%; */
  border: solid 1px;
  margin-bottom: 590px;
  width: 1000px;
  align-items: center;
}

.head-1 {
  display: flex;
  align-items: center;
}
</style>
