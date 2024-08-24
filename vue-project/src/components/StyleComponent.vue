<template lang="">
    <div>
        <h3>Style component</h3>
        <div :style="{ color: activeColor, fontSize: fontSize + 'px' }">Text of the color</div>
        <div :style="{ 'font-size': 'font-size' + 'px' }">Text of the color</div>
        <div :style="styleObject">Text of the color</div>
        <div :style="{ display: ['-webkit-box', '-ms-flexbox', 'flex'] }">Text of the color</div>
    </div>
</template>
<script setup>
import { ref, reactive } from 'vue';
const activeColor = ref('red')
const fontSize = ref(20)
const styleObject = reactive({
  color: 'red',
  fontSize: '30px'
})
</script>
<style lang="">
    
</style>