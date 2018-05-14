<template>
  <div id="app">
    <tri-calc />
    <angle-from-angle />
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import TriCalc from './components/TriCalc.vue';
import AngleFromAngle from './components/AngleFromAngle.vue';

export default Vue.extend({
  name: 'app',
  components: {
    TriCalc,
    AngleFromAngle
  }
});
</script>

<style lang="scss">
body, html {
  margin: 0;
  padding: 0;
  width: 100vw;
  height: 100vh;
  color: #d0d2d5;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background-color: #101215;
  margin: 0;
  padding: 10px;
  height: 100%;
  box-sizing: border-box;
  display: flex;
  align-items: flex-start;
}

#app input {
  background-color: #15171a;
  color: #d0d2d5;
  border: none;
  border-radius: 3px;
  padding: 3px;
}

</style>
