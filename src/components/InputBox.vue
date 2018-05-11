<template>
  <div class="input-box"><span class="label">{{ label }}:</span><input
    :value="value"
    :placeholder="label"
    @input="$emit('change', $event.target.value)"
  /></div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name:"input-box",
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
  .input-box {
    display: flex;
    margin: 2px;
  }
  .input-box .label {
    margin-right: 1ex;
  }
  .input-box input {
    flex: 1;
  }
</style>
