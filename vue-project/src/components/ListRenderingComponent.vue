<template>
    <div>
       <h3>List Rendering</h3> 
        <li v-for="(item, index) in items" v-bind:key="index">
            {{ item.message }}
        </li>
        <ul>
            <li v-for="(book,index) in books" v-bind:key="index">
                {{ book.title }}
            </li>
        </ul>

        <ul>
  <li v-for="value of myObject">
    {{ value }}
  </li>
</ul>

  <span v-for="n in 13">{{ n }}</span>

  <ul style="margin-top: 20px;">
  <template v-for="item in items">
    <li>{{ item.message }}</li>
    <li class="divider" role="presentation"></li>
  </template>
</ul>

<template v-for="(todo, index) in todos">
  <li v-if="!todo.isComplete" v-bind:key="index">
    {{ todo.name }}
  </li>
</template>

    </div>
</template>
<script setup>
import { reactive } from 'vue';
import { ref } from 'vue';

   const items = ref([{message:'Foo'}, {message:'Bar'}]);

   const books = reactive([
    {title:'Book 1'},
    {title:'Book 2'},
    {title:'Book 3'},
    {title:'Book 4'},
    {title:'Book 5'},
   ]);

   const myObject = reactive({
  title: 'How to do lists in Vue',
  author: 'Jane Doe',
  publishedAt: '2016-04-10'
})

const todos = reactive([{
    name: 'buy a coffee',
    isComplete: true
},
{
    name: 'wash your hand',
    isComplete: false
},
])
</script>
<style>
    
</style>