<template>
  <div>
    <div>Id: {{ post.id }}</div>
    <div>Title: {{ post.title }}</div>
        <buton @click.prevent="$emit('editPost', post.id)">Edit Post</buton>
  </div>
</template>

<script setup>
  const props = defineProps({
     post: {
        type: Object,
        required: true
     }
   })
//    const emit = defineEmits(['editPost']);
//    const updatePost = ()=>{
//     emit('editPost', 'post.id');
//    }

</script>

<style>

</style>