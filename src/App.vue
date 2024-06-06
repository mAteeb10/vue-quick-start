<script setup>
import { ref } from "vue";
const count = ref(0);
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
