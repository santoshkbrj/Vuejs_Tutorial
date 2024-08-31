<template>
 <div>
    <h3>Template Ref</h3>
    <input type="text" ref="inputRef">

    <ul>
    <li v-for="(item, index) in list" ref="itemRefs" v-bind:key="index">
      {{ item }}
    </li>
  </ul>

  <ChildComponent ref="childRef"/>
 </div>
</template>

<script setup>
import { onMounted, ref, watchEffect } from 'vue';
import ChildComponent from './ChildComponent.vue';

  const inputRef = ref(null)

  onMounted(()=>{
   inputRef.value.style.color = 'red';
  })

  watchEffect(() => {
  if (inputRef.value) {
    inputRef.value.focus()
  } else {
    // not mounted yet, or the element was unmounted (e.g. by v-if)
  }
})

const itemRefs = ref([])
const list = ref([
1, 2 ,3, 4, 5, 6
]);
onMounted(() => console.log(itemRefs.value));

const childRef = ref(null);
onMounted(()=>{
   console.log(childRef.value)
})
defineExpose({
   childRef,
})

</script>

<style scoped>

</style>