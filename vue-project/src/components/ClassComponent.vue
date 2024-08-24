<template>
    <div>
        <h3>Class Component</h3>
        <div :class="{active:isActive}">Apply active class</div>
        <div class="static" :class="{ active: isActive, 'text-danger': hasError}">Apply active class</div>
        <div :class="classObject">Apply active class</div>
        <div :class="classObj">Apply active class</div>
        <div :class="[activeClass, errorClass]">Apply active class</div>
        <div :class="[isActive ? activeClass : '', errorClass]">Apply active class</div>
        <div :class="[{[activeClass]:isActive}, errorClass]">Apply active class</div>
    </div>
</template>
<script setup>
import { reactive,  ref, computed } from 'vue';

  const isActive = ref(false);
  const error = ref(null)
  const hasError = ref(true);
  const errorClass = ref('text-danger');
  const activeClass = ref('active');

  const classObject = reactive({
    active: true,
    'text-danger': false
  })

  const classObj = computed(()=>({
    active:isActive.value && !error.value, 
    'text-danger':error.value && error.value.type === 'fatal'
  }))

</script>
<style >
    
</style>