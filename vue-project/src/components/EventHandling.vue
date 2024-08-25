<template>
    <div>
        <h3>Event Handling</h3>
        <button @click="count++">+</button>
        <h4>{{count}}</h4>
        <button v-on:click="greet">greet</button>

        <!-- inline argument pass to function -->
        <button @click="say('hello')">Say Hello</button>
        <button @click="say('bye')">Say Bye</button>

        <!-- preventDefault -->
        <a href="http://www.google.com" @click="linkClick">Click link</a>
    
        <!-- stop propogation -->
        <div @click="parentClick">
            <a href="http://www.google.com" @click.stop.prevent="childrenLink">google</a>
        </div>

        <!-- first parent and then children got fired -->
        <div @click.capture="parentClick">
            <a href="http://www.google.com" @click.stop.prevent="childrenLink">google</a>
        </div>

            <!-- first children got fired -->
         <div @click.self="parentClick">
            <a href="http://www.google.com" @click.stop.prevent="childrenLink">google</a>
        </div>

    </div>
</template>
<script setup>
import { ref } from 'vue';

   const count = ref(0);

   const name= ref('Santosh');

   function greet(){
    alert(`Hello ${name.value}`);
    if(event){
    alert(event.target.tagName);
   }
   }

   function say(greet){
    alert(greet);
   }

   function linkClick(event){
      event.preventDefault();
      console.log('link is click')
   }

   function childrenLink(){
    console.log('children link got fired')
   }
   function parentClick(){
    console.log('parentLink got fired');
   }
</script>
<style>
    
</style>