
<script setup lang="ts">
import { ref, onMounted } from 'vue'

// reactive state
const count = ref(0)
const text = ref('')
// functions that mutate state and trigger updates
function increment() {
   count.value = count.value+1
}

function decrease() {
   count.value = count.value-1
}

// lifecycle hooks
onMounted(() => {
  console.log(`The initial count is ${count.value}.`)
})
</script>

<template>
  <div class="about">
    <div>
      <input v-model="text" placeholder="Type here">
      <p>{{ text }}</p>
      <p>Count is: {{ count }}</p>
      <button @click="increment">+</button>
      <button @click="decrease">-</button>
    </div>
  </div>
</template>

<style scoped>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}

p {
  font-size: 64px;
}
</style>