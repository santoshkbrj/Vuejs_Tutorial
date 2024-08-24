<template>
    <div>
         <h3>{{ count + 10 }}</h3>
         <h3>My name is {{ name}}</h3>
         <h3>{{ colorSheme ? 'light' : 'dark' }}</h3>
    </div>
</template>
<script setup>
import {ref} from 'vue';
   const count = ref(20);
   const name = ref('Santosh');
   const colorSheme = ref('false');
</script>
<style>
    
</style>