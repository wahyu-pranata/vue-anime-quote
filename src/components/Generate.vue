<template>
  <button @click="$emit('generate')">{{ text }}</button>
</template>

<script setup>
defineProps({
  text: String
})
</script>

<style scoped>
  button {
    padding: 4px 12px;
    margin-top: 12px;
    background-color: #0369a1;
    border: none;
    font-size: 1.02em;
    color: #fff;
    cursor: pointer;
  } 
  button:hover {
    opacity: 0.9;
  }
  button:active {
    opacity: 0.7;
  }
</style>