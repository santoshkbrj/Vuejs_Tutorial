<template>
    <div>
        <div>Counter component</div>
        <div class="text-center">
            <button @click.prevent="increment()">+</button>
            <span>{{ counter }}</span>
            <button @click.prevent="decrement()">-</button>
        </div>
    </div>
</template>
<script setup>
import {ref} from 'vue';
        const counter = ref(0);
        function increment(){
            counter.value++;
        }
        function decrement(){
            counter.value--;
        }
</script>
<style scoped>
.text-center{
    text-align: center;
}
    
</style>