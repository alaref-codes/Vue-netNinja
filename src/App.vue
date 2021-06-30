<template>
  <Greet msg="Rection Timer Game"/>
  <button v-on:click="activate" :disabled="isPlaying" class="play" ref="play" >play</button>
  <Big v-if="isPlaying" :delay="delay" v-on:end="endGame" />
  <Result v-if="showResult" :result="result"/>
</template>

<script>

import Greet from './components/Greet.vue'
import Result from './components/Result.vue'
import Big from './components/BigButton.vue'


export default {
  name: 'App',
  components: {
    Greet,
    Result,
    Big
  },
  data() {
    return {
      isPlaying: false,
      delay : null,
      showResult: false,
      showBig: false,
      startTime : 0,
      endTime: 0,
      elapse: 0,
      result: null,
    }
  },
  methods: {
    activate() {
      this.delay = 2000 + Math.random() * 5000; 
      this.isPlaying = true;
      this.showResult = false;
    },
    endGame(reactionTime) {
      this.result = reactionTime;
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
.play {
  padding: 10px;
  background-color: #bedefd;
  width: 65px;
  border-radius: 5px;
  font-style: italic;
  font-size: 1rem;
}
</style>
