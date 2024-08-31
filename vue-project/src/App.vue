<script setup>
import { ref } from 'vue';
import SinglePostComponent from './components/SinglePostComponent.vue';

const post = {
  id: 1,
  title: "My Jorney with vue",
}

const postComment = ref({
  commentsId:[234, 345, 453, 231],
})

</script>

<template>
  <div>
    <h1>This is app component</h1>
    <single-post-component v-bind="post" :commentId="postComment.commentsId"/>
  </div>
</template>

<style scoped></style>
