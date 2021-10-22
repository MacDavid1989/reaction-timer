<template>
  <div class="block" v-if="showBlock">Click Me!</div>
</template>

<script>
export default {
  name: "Block",
  props: ["delay"],
  data() {
    return {
      showBlock: false,
    };
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = !this.showBlock;
    }, this.delay);
  },
};
</script>

<style scoped>
.block {
  width: 400px;
  border-radius: 20px;
  background: #0faf87;
  color: white;
  text-align: center;
  padding: 100px 0;
  margin: 40px auto;
  cursor: pointer;
}
</style>
