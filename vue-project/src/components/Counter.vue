<template>
    <div>
        <div>Counter component</div>
        <div class="text-center">
            <button @click.prevent="increment()">+</button>
            <span>{{ counter }}</span>
            <button @click.prevent="decrement()">-</button>
            <div>The counter value is {{ oddorEven }}</div>
        </div>
    </div>
</template>
<script setup>
import {ref, computed} from 'vue';
        const counter = ref(0);
        function increment(){
            counter.value++;
        }
        function decrement(){
            counter.value--;
        }
    const oddorEven = computed(()=>{
        return counter.value%2 == 0 ? 'even' : 'odd'
    })
</script>
<style scoped>
.text-center{
    text-align: center;
}
    
</style>