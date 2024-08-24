<template lang="">
    <div>
       <h3>Conditional Rendering</h3> 
       <h3 v-if="isAwesome">Vue is awesome!</h3>
       <h3 v-else>oh no. It is not awesome!</h3>
       <div>
        <button @click="isAwesome =!isAwesome">Toggle</button>
       </div>
       <div v-if="type ===1">1</div>
       <div v-else-if="type ===2">2</div>
       <div v-else-if="type ===3">3</div>
       <div v-else>Not a number</div>

       <template v-if="showArticle">
       <h4>paragraph Heading</h4>
       <p>This is a paragraph</p>
       </template>
       
       <div v-show="isAwesome">V-show Property</div>
    </div>
</template>
<script setup>
import { ref } from 'vue';
   const isAwesome = ref(true);

   const type = ref(1);
   setInterval(()=>{
    type.value++;
   }, 3000)

   const showArticle = ref(false)
</script>
<style>
    
</style>