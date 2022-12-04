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
    border: 2px solid #562135;
    background-color: #74204A;
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