<template lang="">
    <div>
       <h3>Form Input Binding</h3> 
       <!-- <input type="text" :value="text" @input="(e)=>(text=e.target.value)"> -->
       <p>{{text}}</P>

        <!-- input field two data binding -->
        <input type="text" v-model="text"/>

        <!-- textarea -->
        <textarea v-model="message" cols="20" rows="10" placeholder="add multiple line"></textarea>
        <p style="white-space: pre-line;">{{message}}</p>


        <!-- checkbox -->
        <input type="checkbox" v-model="toggle" true-value="Yes" false-value="No"/>
        <label for="jack">{{toggle}}</label>

        <input type="checkbox" id="jack" value="Jack" v-model="checkNames"/>
        <label for="jack">Jack</label>
        <input type="checkbox" id="john" value="John" v-model="checkNames"/>
        <label for="john">John</label>
        <input type="checkbox" id="mike" value="Mike" v-model="checkNames"/>
        <label for="mike">Mike</label>
        <p>{{checkNames}}</p>

        <!-- Radio button -->
        <input type="radio" value="one" v-model="picked"/>
        <label for="one">One</label>
        <input type="radio" value="two" v-model="picked"/>
        <label for="two">Two</label>
        <p>you picked: {{picked}}</p>

        <!-- select option -->
         <select v-model="selected">
            <option>A</option>
            <option>B</option>
            <option>C</option>
         </select>
         <p>You selected: {{selected}}</p>

         <select v-model="choose" multiple>
            <option>A</option>
            <option>B</option>
            <option>C</option>
         </select>
         <p>You selected: {{choose}}</p>

         <!-- Dynamiclly rendering -->
         <select v-model="selecting">
        <option v-for="(option,index) in options" :value="option.value" v-bind:key="index">
            {{ option.text }}
        </option>
        </select>

        <div>Selected: {{ selecting }}</div>

    </div>
</template>
<script setup>
import { ref } from 'vue';

  const text = ref('santosh')
  const message = ref('');
  const checkNames = ref([]);
  const picked = ref('two');
  const selected = ref('A');
  const choose = ref([]);

  const toggle= ref('Yes');

  const selecting= ref('A')
  const options = ref([
    {text:'A', value:'One'},
    {text:'B', value:'Two'},
    {text:'C', value:'Three'},
  ])
</script>
<style lang="">
    
</style>