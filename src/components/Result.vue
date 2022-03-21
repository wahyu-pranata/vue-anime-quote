<template>
  <div class="quote">
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><!--! Font Awesome Pro 6.0.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2022 Fonticons, Inc. --><path fill="#74204A" d="M96 224C84.72 224 74.05 226.3 64 229.9V224c0-35.3 28.7-64 64-64c17.67 0 32-14.33 32-32S145.7 96 128 96C57.42 96 0 153.4 0 224v96c0 53.02 42.98 96 96 96s96-42.98 96-96S149 224 96 224zM352 224c-11.28 0-21.95 2.305-32 5.879V224c0-35.3 28.7-64 64-64c17.67 0 32-14.33 32-32s-14.33-32-32-32c-70.58 0-128 57.42-128 128v96c0 53.02 42.98 96 96 96s96-42.98 96-96S405 224 352 224z"/></svg>
    <p>{{ quote }}</p>
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><!--! Font Awesome Pro 6.0.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2022 Fonticons, Inc. --><path fill="#74204A" d="M96 96C42.98 96 0 138.1 0 192s42.98 96 96 96c11.28 0 21.95-2.305 32-5.879V288c0 35.3-28.7 64-64 64c-17.67 0-32 14.33-32 32s14.33 32 32 32c70.58 0 128-57.42 128-128V192C192 138.1 149 96 96 96zM448 192c0-53.02-42.98-96-96-96s-96 42.98-96 96s42.98 96 96 96c11.28 0 21.95-2.305 32-5.879V288c0 35.3-28.7 64-64 64c-17.67 0-32 14.33-32 32s14.33 32 32 32c70.58 0 128-57.42 128-128V192z"/></svg>
  </div>
  <p class="desc">By<span>「{{ character }}」</span>in<span>「{{ anime }}」</span></p>
</template>

<script>
export default {
  props: {
    quote: String,
    character: String,
    anime: String
  }
}
</script>
<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Merienda:wght@400;700&family=Neucha&display=swap');
  .quote {
    width: min(100vw - 2rem, 800px);
    margin-top: 0.8rem;
    padding: 2rem 3rem;
    border: 2px solid #74204A;
    background-color: #ffe7de;
    border-radius: 0.6rem;
    display: flex;
    flex-direction: column;
    align-items:center;
  }
  .quote p {
    text-align: center;
    font-family: "Merienda";
  }
  .quote svg {
    width: 20px;
  }
  .desc, .desc span {
    text-align: center;
    color: #240A17;
    font-family: "Merienda";
  }
  .desc span {
    font-weight: bold;
  }
</style>