<script setup>
const id = 2
const number = 8
const ok = false
const message = 'Have a nice day'
</script>

<template>
  <div>
    <p>{{ number + 1 }}</p>
    <p>{{ ok ? 'YES' : 'NO' }}</p>

    <p>{{ message.split('').reverse().join('') }}</p>

    <div :id="`list-${id}`">This is a simple paragraph</div>
    <my-component/>
  </div>
</template>

<style scoped></style>
