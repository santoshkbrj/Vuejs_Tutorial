<template lang="">
    <div>
        <div>{{counterData.title}}</div>
        <div>{{counterData.count}}</div>
        <input type="text" placeholder="enter something" v-model="counterData.title">
    </div>
</template>
<script setup>
import { reactive } from 'vue';
 const counterData = reactive({
    title: 'Counter Title',
    count: 0
 })
</script>
<style lang="">
    
</style>