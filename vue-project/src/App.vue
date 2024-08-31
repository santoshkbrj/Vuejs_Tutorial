<script setup>
import SinglePostComponent from './components/SinglePostComponent.vue';
const post = {
  id: 1,
  title: "My Jorney with vue",
}

</script>

<template>
  <div>
    <h1>This is app component</h1>
    <single-post-component v-bind="post"/>
  </div>
</template>

<style scoped></style>
