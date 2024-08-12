<script setup>
import { ref } from 'vue'
const count = ref(0)
</script>

<template>
  <div>
    <button @click="count++">Increment</button>
    <button @click="count--">decrement</button>
    <h2>{{ count }}</h2>
  </div>
</template>

<style scoped></style>
