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
<script>
import {ref} from 'vue';
export default {
    setup(){
        const counter = ref(0)
        function increment(){
            counter.value++;
        }
        function decrement(){
            counter.value--;
        }
        return{
            counter,
            increment,
            decrement
        }
    },

  
    
}
</script>
<style scoped>
.text-center{
    text-align: center;
}
    
</style>