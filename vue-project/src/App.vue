<script setup>
import { ref } from 'vue';
import MyComponent from './components/MyComponent.vue';
const count = ref(0);
function increaseCount(n) {
  count.value += n
}
</script>

<template>
  <div>
    <h1>This is app component</h1>
    {{ count }}
    <my-component @increase-by="increaseCount"/>
  </div>
</template>

<style scoped></style>
