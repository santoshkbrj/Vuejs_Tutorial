<template lang="">
    <div>
        <h3>Watcher or Side effect component</h3>
        <p>Ask a Yes/No question: 
            <input type="text" v-model="question" :disabled="loading"/>
        </p>
        <p>{{answer}}</p>
        <img :src="imageData" style="width:200px"/>

        <div>
            X: <input type="text" v-model="x"/>
        </div>
        <div>
            y: <input type="text" v-model="y"/>
        </div>
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

const x = ref('');
const y = ref('');

watch(x, (newX)=>{
    console.log(`value of newx is ${newX}` )
});
watch(y, (newY)=>{
    console.log(`value of newx is ${newY}` )
});

watch([x,y], ([newx, newy])=>{
    console.log(`values of x and y is ${newx} and ${newy}`)
})

watch([x,()=>y.value], ([newx, newy])=>{
    console.log(`values of x and y is ${newx} and ${newy}`)
})
</script>
<style>
    
</style>