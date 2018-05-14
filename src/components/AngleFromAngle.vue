<template>
  <div class="angle-from-angle">
    <div class="title">Right Triangle Other Angle Calculator</div>
    <div class="subtitle">Version 0.1.1 (NOW WITH DARK THEME!)</div><hr />
    <div class="input-group">
      <input-box v-model.number="model.input" label="Known Angle" />
    </div><hr />
    <div class="input-group">
      <output-box :value="output" label="Unknown Angle" />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import InputBox from './InputBox.vue';
import OutputBox from './OutputBox.vue';

export default Vue.extend({
  name: "angle-from-angle",
  components: {
    InputBox,
    OutputBox
  },
  data: function() {
    return {
      model: {
        input: 30
      }
    }
  },
  computed: {
    output: function(): number | string {
      if (typeof this.model.input !== "string") {
        return 180 - 90 - this.model.input;
      } else {
        return "INVALID INPUT"
      }
    }
  }
})
</script>

<style lang="scss" scoped>
  .angle-from-angle {
    display: inline-flex;
    flex-direction: column;
    padding: 5px;
    margin: 5px;
    border-width: 1px;
    border-color: #1a1c1f;
    border-style: solid;
    border-radius: 3px;
  }

  .angle-from-angle .title {
    font-size: 20px;
    font-weight: bold;
  }

  .angle-from-angle .subtitle {
    color: #35373a;
  }

  .angle-from-angle hr {
    width: 100%;
    box-sizing: border-box;
    border: none;
    height: 1px;
    background-color: #1a1c1f;
  }
</style>

