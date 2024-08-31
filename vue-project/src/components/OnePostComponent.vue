<template>
  <div>
    <div>Id: {{ post.id }}</div>
    <div>Title: {{ post.title }}</div>
        <buton @click.prevent="updatePost">Edit Post</buton>
        <hr/>
  </div>

</template>

<script setup>
  const props = defineProps({
     post: {
        type: Object,
        required: true
     }
   })
   const emit = defineEmits({
    editPost(postId){
        if(postId && typeof postId === 'number' ) {
            return true
        }
        else{
            return false
        }
    }
   });

   const updatePost = ()=>{
    emit('editPost', props.post.id);
   }

</script>

<style>

</style>