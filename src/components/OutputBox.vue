<template>
  <div class="output-box"><span class="label">{{ label }}:</span><input
    :value="value"
    @input="$emit('change', $event.target.value)"
    disabled
  /></div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name:"output-box",
  props: {
    label: String,
    value: String 
  },
  model: {
    prop: "value",
    event: "change"
  }
})
</script>

<style lang="scss" scoped>
  .output-box {
    display: flex;
    margin: 2px;
  }
  .output-box .label {
    margin-right: 1ex;
  }
  .output-box input {
    flex: 1;
  }
</style>
