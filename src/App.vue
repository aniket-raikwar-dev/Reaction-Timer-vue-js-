<template>
  <div>
    <h1>Reaction Timer</h1>
    <button class="btn" @click="start" :disabled="isPlaying">play</button>
    <div v-if="isPlaying">
       <BlockComp :delay="delay" @end="endGame" />
    </div>
    <ResultComp v-if="showResult" :score="score" />
  </div>
</template>

<script>
import BlockComp from './components/Block.vue';
import ResultComp from './components/Result.vue'

export default {
  name: 'App',
  components: {
    BlockComp,
    ResultComp
  },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResult: false
    }

  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true;
      this.showResult = false;
    },
    endGame(reactionTime) {
      this.score = reactionTime;
      this.isPlaying = false;
      this.showResult = true;
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.btn {
  width: 100px;
  padding: 10px;
  background-color: rgb(201, 193, 196);
  cursor: pointer;
  font-size: 16px;
  
  
}
</style>
