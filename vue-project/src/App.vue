<script setup>
import { ref } from "vue";
import SinglePostComponent from "./components/SinglePostComponent.vue";

const postTitle = ref('My journey with vue');

const postDetails ={
  title: ' My Post details ',
  id: 43
}
</script>

<template>
  <div>
    <h1>This is app component</h1>
    <single-post-component title="Santosh Web dev" :postTitle="postTitle" :id="43"/>
    <single-post-component :title="postDetails.title" :id="postDetails.id"/>
  </div>
</template>

<style scoped></style>
