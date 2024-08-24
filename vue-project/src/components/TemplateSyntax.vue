<template lang="">
    <div>
        <h3 :[titleAttr]="titleValue">Text Interpolation</h3>
        <div v-html="message"></div>
        <div :id="dynamicId">Template Code</div>
        <div v-bind="objectofAttrs">Object attribute binding</div>
        <div>Count is 2+2 {{2 + 2}}</div>
        <div>{{message ? 'Yes': 'No'}}</div>
        <div>{{Math.floor(Math.random()*8)}}</div>
        <div v-on:[eventName]="changeTitle">Hello, Good morning</div>
    </div>
</template>
<script setup>
    const message = '<p>This is simple message</p>';
    const dynamicId = 'my-id';
    const objectofAttrs = {
        id: "my-id",
        class: 'container',
        style: 'backgorund-color: red'
    };

    const titleAttr = 'title';
    const titleValue = 'title-item';
    const changeTitle = ()=>{
      alert('Hello, Good evening');
    }
    const eventName = 'click';

</script>
<style lang="">
    
</style>