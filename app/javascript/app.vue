<template>
  <div id="app">
    <p>{{ message }}</p>
    <counter />
  </div>
</template>

<script>
import Counter from "./components/Counter.vue";

export default {
  components: {
    Counter
  },
  data: function() {
    return {
      message: "Hello Vue!"
    };
  }
};
</script>

<style scoped>
p {
  font-size: 2em;
  text-align: center;
}
</style>
