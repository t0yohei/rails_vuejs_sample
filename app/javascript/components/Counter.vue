<template>
  <div id="app">
    <p>{{ countingNum }}</p>
    <button v-on:click="startRecursionCalc()">start</button>
  </div>
</template>

<style scoped>
p {
  font-size: 2em;
  text-align: center;
}
</style>

<script>
export default {
  data: function() {
    return {
      start: 1,
      stop: 100,
      countingNum: 0,
      intervalId: ""
    };
  },

  // SPAになった場合はこの処理が必要になる
  // beforeDestroy() {
  //   clearInterval(this.intervalId);
  // },

  methods: {
    startRecursionCalc: function() {
      this.countingNum = this.start;
      this.intervalId = window.setInterval(this.recursionCalc, 10);
    },
    recursionCalc: function() {
      if (this.stop <= this.countingNum) {
        clearInterval(this.intervalId);
        return console.log("stop");
      }
      this.countingNum = this.countingNum + 1;
    }
  }
};
</script>
