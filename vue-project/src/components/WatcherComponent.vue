<template lang="">
    <div>
        <h3>Watcher or Side effect component</h3>
        <p>Ask a Yes/No question: 
            <input type="text" v-model="question" :disabled="loading"/>
        </p>
        <p>{{answer}}</p>
        <img :src="imageData" style="width:200px"/>
    </div>
</template>
<script setup>
import { ref, watch } from 'vue';
  const question = ref('');
  const answer = ref("Question usually contain a question mark. 😉");
  const loading = ref(false);
  const imageData = ref('');

  watch(question, async(newQuestion, oldQuestion)=>{
  if(newQuestion.includes('?')){
     loading.value = true;
     answer.value = 'Thinking';
  }
  try{
    const res = await fetch('https://yesno.wtf/api');
    const resJson = await res.json();
    imageData.value = resJson.image;
    answer.value = resJson.answer;
  } catch(err){
    answer.value = 'Error could not reach to API' + err;
  } finally{
    loading.value = false;
  }
})
</script>
<style>
    
</style>