<template>
  <div class="app">
    <h1>Hello World!</h1>
    <p>Welcome to my Vite + Vue starter template</p>

    <div class="counter-section">
      <h2>Counter</h2>
      <div class="counter-display">{{ count }}</div>
      <div class="counter-buttons">
        <button @click="decrement" :disabled="count === 0">-</button>
        <button @click="reset">Reset</button>
        <button @click="increment">+</button>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { reactive, toRefs } from 'vue'

const state = reactive({count: 0})
const {count} = toRefs(state)

const increment = () => {
  count.value++
}

const decrement = () => {
  count.value--
}

const reset = () => {
  count.value = 0
}
</script>

<style scoped>
.app {
  text-align: center;
  padding: 2rem;
}

h1 {
  color: #42b983;
  font-size: 3rem;
  margin-bottom: 1rem;
}

p {
  color: #666;
  font-size: 1.2rem;
}

.counter-section {
  margin-top: 2rem;
  padding: 2rem;
  background: #f5f5f5;
  border-radius: 8px;
  max-width: 400px;
  margin-left: auto;
  margin-right: auto;
}

.counter-section h2 {
  color: #42b983;
  margin-bottom: 1rem;
}

.counter-display {
  font-size: 4rem;
  font-weight: bold;
  color: #333;
  margin: 1.5rem 0;
}

.counter-buttons {
  display: flex;
  gap: 1rem;
  justify-content: center;
}

.counter-buttons button {
  padding: 0.75rem 1.5rem;
  font-size: 1.2rem;
  border: none;
  border-radius: 4px;
  background: #42b983;
  color: white;
  cursor: pointer;
  transition: background 0.3s;
}

.counter-buttons button:hover {
  background: #35a372;
}

.counter-buttons button:active {
  transform: scale(0.95);
}

.counter-buttons button:disabled {
  background: #ccc;
  cursor: not-allowed;
  opacity: 0.6;
}

.counter-buttons button:disabled:hover {
  background: #ccc;
}
</style>
