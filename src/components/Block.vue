<template>
  <div class="block" v-if="showBlock" @click="stopTimer">
    click me
  </div>
</template>

<script>

export default {
  name: "BlockComp",
  props: ['delay'],
  data() {
    return {
      showBlock: false,
      timer: null,
      reactionTime: 0,
    }
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = true;
      this.startTimer()
    }, this.delay);
  }, 
  methods: {
    startTimer() {
       this.timer = setInterval(() => {
        this.reactionTime += 10;
       }, 10)
    },

    stopTimer() {
      clearInterval(this.timer)
      this.$emit('end', this.reactionTime);
    }
  }

}
</script>

<style>
  .block {
    width: 400px;
    border-radius: 20px;
    background: rgb(44, 44, 247);
    color: white;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
    cursor: pointer;
    font-size: 18px;
    font-style: italic;
    font-family: monospace;
  }
</style>