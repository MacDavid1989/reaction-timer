<template>
  <h1>Reaction Timer</h1>
  <button @click="start" :disabled="isPlaying">Play</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame" />
  <p>Reaction time: {{ score }} ms</p>
</template>

<script>
import { Block } from "./components";

export default {
  name: "App",
  components: { Block },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
    };
  },
  methods: {
    start() {
      this.isPlaying = !this.isPlaying;
      this.delay = 2000 + Math.random() * 5000;
    },
    endGame(time) {
      this.score = time;
      this.isPlaying = !this.isPlaying;
    },
  },
};
</script>
