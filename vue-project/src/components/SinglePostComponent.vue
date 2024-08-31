<template>
  <div>
    <h3>Single Post component</h3>
     <p>{{ id }} and {{ title }}</p>
  </div>
</template>

<script setup>
defineProps({
  title: String,
  id: Number,
  commentId: Array
})
</script>

<style>

</style>