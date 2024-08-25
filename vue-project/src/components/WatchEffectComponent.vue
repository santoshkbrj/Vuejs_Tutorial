<template>
  <div>
    <h3>Watch Effect Component</h3>
    <div class="">
      <input type="text" v-model="todoId">
      <p>{{ data }}</p>
    </div>
  </div>
</template>

<script setup>
import {onBeforeMount, onBeforeUnmount, onBeforeUpdate, onMounted, onUpdated, ref, watchEffect} from 'vue';
// import {watch} from 'vue'

  const todoId = ref(1);
  const data = ref(null);

  // watch(todoId, async()=>{
  //   let response = await fetch( `https://jsonplaceholder.typicode.com/todos/${todoId.value}`);
  //   data.value = response.json();
  // },{
  //   immediate:true
  // })

  watchEffect(async()=>{
    let response = await fetch( `https://jsonplaceholder.typicode.com/todos/${todoId.value}`);
    data.value = (await response.json()).title;
  })

  const unwatch = watchEffect(() => {})
  unwatch();

// Different Life cycle hooks
  onBeforeMount(()=>{
    console.log('before mounted')
  });
  onMounted(()=>{
    console.log('mounted')
  });
  onBeforeUnmount(()=>{
    console.log('On Before Unmount')
  });
  onMounted(()=>{
    console.log('on unMounted')
  })
  onBeforeUpdate(()=>{
    console.log('On Before update')
  });

  onUpdated(()=>{
    console.log('Updated')
  })
</script>

<style>

</style>