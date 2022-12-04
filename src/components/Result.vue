<template>
  <div class="quote">
    <div v-if="(quote.quote != null)" class="quote-container">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><path fill="#1c1917" d="M96 224C84.72 224 74.05 226.3 64 229.9V224c0-35.3 28.7-64 64-64c17.67 0 32-14.33 32-32S145.7 96 128 96C57.42 96 0 153.4 0 224v96c0 53.02 42.98 96 96 96s96-42.98 96-96S149 224 96 224zM352 224c-11.28 0-21.95 2.305-32 5.879V224c0-35.3 28.7-64 64-64c17.67 0 32-14.33 32-32s-14.33-32-32-32c-70.58 0-128 57.42-128 128v96c0 53.02 42.98 96 96 96s96-42.98 96-96S405 224 352 224z"/></svg>
      <p>{{ quote.quote }}</p>
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><path fill="#1c1917" d="M96 96C42.98 96 0 138.1 0 192s42.98 96 96 96c11.28 0 21.95-2.305 32-5.879V288c0 35.3-28.7 64-64 64c-17.67 0-32 14.33-32 32s14.33 32 32 32c70.58 0 128-57.42 128-128V192C192 138.1 149 96 96 96zM448 192c0-53.02-42.98-96-96-96s-96 42.98-96 96s42.98 96 96 96c11.28 0 21.95-2.305 32-5.879V288c0 35.3-28.7 64-64 64c-17.67 0-32 14.33-32 32s14.33 32 32 32c70.58 0 128-57.42 128-128V192z"/></svg>
    </div>
    <div v-else class="loading">
      <p>Albedo is thinking...</p>
      <img src="../assets/albedo_question_mark.png" alt="Loading Image">
    </div>
  </div>
  <p class="desc" v-if="(quote.quote != null)">By<span>「{{ quote.character }}」</span>in<span>「{{ quote.anime }}」</span></p>
</template>

<script setup>
defineProps({
  quote: Object
})
</script>
<style scoped>
.quote-container {
  text-align: center;
}
.quote {
  width: min(100vw - 2rem, 800px);
  margin-top: 0.8rem;
  padding: 2rem 3rem;
  background-color: #F2F2F2;
  border-radius: 4px;
  text-align: center;
}
.quote p {
  text-align: center;
  color: #1c1917;
  font-size: 1.2rem;
}
.quote svg {
  width: 20px;
  display: inline-block;
  margin: 0 auto;
}
.desc, .desc span {
  color: #f1f5f9aa;
  text-align: center;
}
.desc span {
  font-weight: bold;
}
.loading img {
  width: 100px;
}
.loading {
  animation: 2s bounce infinite;
}
@keyframes bounce {
  25% {
    transform: translateY(-6px)
  }
  50% {
    transform: translateY(6px)
  }
  75% {
    transform: translateY(-6px)
  }
  100% {
    transform: translateY(0px)
  }
}
</style>