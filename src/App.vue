<template>
  <div class="heading">
    <h1>Random Anime Quote Generator</h1>
    <!-- <img src="../src/assets/sakura.png"> -->
  </div>
  <p>Made with <a href="https://animechan.vercel.app/">Animechan API</a></p>
  <Generate @generated="fetchAPI" :text="Object.keys(quoteInfo).length === 0 ? 'Generate quote' : 'Refresh quote'"/>
  <Result v-if="Object.keys(quoteInfo).length !== 0" :quote="quoteInfo.quote" :character="quoteInfo.character" :anime="quoteInfo.anime"/>
</template>

<script>
import Generate from './components/Generate.vue'
import Result from './components/Result.vue'
export default {
  name: 'App',
  components: {Generate, Result},
  data() {
    return {
      quoteInfo: {}
    }
  },
  methods: {
    fetchAPI() {
      fetch('https://animechan.vercel.app/api/random')
      .then(response => response.json())
      .then(quote => this.quoteInfo = quote)
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Neucha&display=swap');
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: Arial, sans-serif
}
#app {
  height: 100vh;
  background-image: linear-gradient(to bottom right, #c3829e, #e9b1cd);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.heading {
  position: relative;
}
.heading h1 {
  font-family: "Neucha";
  color:#562135;
  text-align: center;
  display: flex;
  position: relative;
}
.heading h1::before {
  content: url("../src/assets/sakura.png");
  z-index: 2;
  position: absolute;
  top: -30px;
  left: -35px;
  opacity: 0.8;
}
.heading h1::after {
  content: url("../src/assets/sakura.png");
  z-index: 2;
  position: absolute;
  bottom: -45px;
  right: -35px;
  opacity: 0.8;
}
.heading img {
  position: absolute;
  top:-25px;
  left:-30px;
  width: 50px;
  opacity: 0.8;
}
@media (max-width: 476px) {
  .heading {
    width: 80%;
  }
  .heading img {
    top: -10;
    left: -10;
  }
}
</style>
