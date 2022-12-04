<template>
  <div class="heading">
    <h1>Random Anime Quote Generator</h1>
    <p>Made with <a href="https://animechan.vercel.app/">Animechan API</a></p>
  </div>
  <Generate @generate="fetchAPI" :text="Object.keys(quoteInfo).length === 0 ? 'Generate quote' : 'Refresh quote'"/>
  <Result 
    v-if="showResult"
    :quote="quoteInfo ? quoteInfo : null"
  />
</template>

<script setup>
import { ref } from "vue"
import Generate from './components/Generate.vue'
import Result from './components/Result.vue'

let quoteInfo = ref({})
let showLoader = ref()
let showResult = ref(false)
function fetchAPI() {
  showResult.value = true
  showLoader.value = true
  quoteInfo.value = {}
  fetch('https://animechan.vercel.app/api/random')
  .then(response => response.json())
  .then(quote => quoteInfo.value = quote)
  showLoader.value = false
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Josefin+Sans:wght@400;700&display=swap');
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Josefin Sans" ,Arial, sans-serif;
}
#app {
  height: 100vh;
  background-image: linear-gradient(to bottom right, #0f172a, #1e293b);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.heading {
  position: relative;
  text-align: center;
}
.heading h1 {
  color: #f8fafc;
}
.heading p {
  color: #f8fafcaa;
}
.heading a {
  color: #f8fafcaa;
}
@media (max-width: 476px) {
  .heading {
    width: 80%;
  }
}
</style>
