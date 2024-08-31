<template>
  <div>
    <h3>Single Post component</h3>
    <p>{{ id }}-{{ title }}</p>
  </div>
</template>

<script setup>
 const props = defineProps({
    title: String,
    id: Number
 })
 console.log(props.title)
</script>

<style>

</style>