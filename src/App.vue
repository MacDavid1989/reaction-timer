<template>
  <h1>Reaction Timer</h1>
  <button @click="start">Play</button>
  <Block />
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
    };
  },
  methods: {
    start() {
      this.isPlaying = !this.isPlaying;
      this.delay = 2000 + Math.random() * 5;
    },
  },
};
</script>
