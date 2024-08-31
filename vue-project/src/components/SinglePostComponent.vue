<template>
  <div>
    <h3>Single Post component</h3>
    <p>{{ id }}-{{ title }}</p>
    <p>{{ name }}</p>
    <p>{{ quote }}</p>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue';

 const props = defineProps({
    title: String,
    id: Number
 })
 console.log(props.title)

 const name = computed(()=> props.title.trim().toLowerCase());

 const quote = ref(props.title);
 quote.value = " Life is beautiful ";
 console.log(name.value)
</script>

<style>

</style>