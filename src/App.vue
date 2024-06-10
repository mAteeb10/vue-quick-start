<script setup>
import { reactive, ref } from "vue";
const counter = reactive({ count: 0 });
const message = ref("Hello World!");
const text = ref("");
const count = ref(0);

function increament () {
  count.value++
}
</script>
<!-- <script>
export default {
import { ref }
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
</script> -->

<template>
  <section class="head">
    <div class="section-one">
      <h1>Part 1</h1>
      <h1>{{ message }}</h1>
    </div>
    <div class="section-two">
      <p>count is: {{ counter.count }}</p>
      <button @click="increament">Count is {{ count }}</button>
    </div>
    <div class="section-three">
      <input v-model="text" placeholder="Type here" />
      <p>{{ text }}</p>
    </div>
  </section>
</template>

<style scoped>
.head {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-bottom: 500px;
}

.head .section-one {
  display: flex;
  flex-direction: column;
  /* justify-content: flex-start; */
  /* top: 50%; */
  border: solid 1px;
  /* margin-bottom: 590px; */
  width: 1000px;
  align-items: center;
}

.head .section-one button {
  font-weight: bold;
  display: flex;
  width: 100px;
  margin-top: 20px;
}
.head .section-two {
  display: flex;
  flex-direction: column;
  margin-top: 20px;
  /* top: 50%; */
  border: solid 1px grey;
  width: 1000px;
  align-items: center;
  color: red;
}

.head .section-three {
  display: flex;
  flex-direction: column;
  margin-top: 20px;
}
</style>
