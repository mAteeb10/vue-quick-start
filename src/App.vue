<script setup>
import { reactive, ref, computed, onMounted } from "vue";
const counter = reactive({ count: 0 });
const message = ref("Hello World!");
const text = ref("");
const count = ref(0);
const awesome = ref(true);

function increament() {
  count.value++;
}

function toggle() {
  awesome.value = !awesome.value;
}

let id = 0;
const newTodo = ref("");
const hideCompleted = ref(false);
const todos = ref([]);

const filteredTodos = computed(() => {
  return hideCompleted.value ? todos.value.filter((t) => !t.done) : todos.value;
});
function addTodo() {
  todos.value.push({ id: id++, text: newTodo.value, done: false });
  newTodo.value = "";
}

function removeTodo(todo) {
  todos.value = todos.value.filter((t) => t !== todo);
}

const pElementRef = ref(null);

onMounted(() => {
  pElementRef.value.textContent = "mounted!";
});
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
    <div class="toggle-button">
      <button @click="toggle">Toggle</button>
      <h1 v-if="awesome">Vue is awesome</h1>
      <h1 v-else>oh no 😥</h1>
    </div>
    <div class="todo-list">
      <form @submit.prevent="addTodo">
        <input v-model="newTodo" required placeholder="new todos" />
        <button>Add Todo</button>
      </form>
      <ul>
        <li v-for="todo in filteredTodos" :key="todo.id">
          <input type="checkbox" v-model="todo.done" />
          <span :class="{ done: todo.done }">{{ todo.text }}</span>
          <button @click="removeTodo(todo)">X</button>
        </li>
      </ul>
      <button @click="hideCompleted = !hideCompleted">
        {{ hideCompleted ? "show all" : "Hide Completed" }}
      </button>
    </div>
    <div>
      <p ref="pElementRef">Hello</p>
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

.head .toggle-button {
  display: flex;
  flex-direction: column;
  margin-top: 20px;
}

.head .todo-list {
  display: flex;
  flex-direction: column;
  margin-top: 20px;
  gap: 20px;
}

.head .todo-list .done {
  text-decoration: line-through;
}
</style>
