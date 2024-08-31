<template>
  <div>
    <h3>Post component</h3>
    <h3>Post Details</h3>
    <OnePostComponent v-for="post in posts" :post="post" :key="post.id" @edit-post="updatePost"/>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import OnePostComponent from './OnePostComponent.vue';
  const posts = ref([
    {id: 1, title: 'Post 1'},
    {id: 2, title: 'Post 2'},
    {id: 3, title: 'Post 3'},
    {id: 4, title: 'Post 4'},
  ])

  const updatePost = (postId)=>{
    posts.value = posts.value.map(post=>{
        if(post.id ===postId) return { ...post, title:'Post is updated'};
        return post;
    })
  }
</script>

<style>

</style>