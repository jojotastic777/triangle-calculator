<template>
  <div class="tri-calc">
    <div class="title">Right Triangle Angle Calculator</div>
    <div class="subtitle">Version 0.1.1 (NOW WITH DARK THEME!)</div><hr />
    <div class="input-group">
      <input-box v-model.number="model.l1" label="Leg 1" />
      <input-box v-model.number="model.l2" label="Leg 2" />
      <input-box v-model.number="model.h" label="Hypotenuse" />
    </div><hr />
    <div class="input-group">
      <output-box :value="a1" label="Angle 1" />
      <output-box :value="a2" label="Angle 2" />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import InputBox from './InputBox.vue';
import OutputBox from './OutputBox.vue';

function rad_to_deg(radians: number): number {
	return radians * 180 / Math.PI;
}

export default Vue.extend({
  name: "tri-calc",
  components: {
    InputBox,
    OutputBox
  },
  data: function() {
    return {
      model: {
        l1: 2,
        l2: 2,
        h:  ""
      }
    }
  },
  computed: {
    a1: function(): number | string {
      // Opposite = l1
      // Adjacent = l2
      if (typeof this.model.l1 !== "string") {
        if (typeof this.model.l2 !== "string") {
          return rad_to_deg(Math.atan(this.model.l1/this.model.l2));
        } else if (typeof this.model.h !== "string") {
          return rad_to_deg(Math.asin(this.model.l1/this.model.h));
        } else {
          return "INVALID INPUT";
        }
      } else if (typeof this.model.l2 !== "string") {
        if (typeof this.model.h !== "string") {
          return rad_to_deg(Math.acos(this.model.l2/this.model.h));
        } else {
          return "INVALID INPUT";
        }
      } else {
        return "INVALID INPUT";
      }
    },
    a2: function(): number | string {
      // Opposite = l2
      // Adjacent = l1
      if (typeof this.model.l2 !== "string") {
        if (typeof this.model.l1 !== "string") {
          return rad_to_deg(Math.atan(this.model.l2/this.model.l1));
        } else if (typeof this.model.h !== "string") {
          return rad_to_deg(Math.asin(this.model.l2/this.model.h));
        } else {
          return "INVALID INPUT";
        }
      } else if (typeof this.model.l1 !== "string") {
        if (typeof this.model.h !== "string") {
          return rad_to_deg(Math.acos(this.model.l1/this.model.h));
        } else {
          return "INVALID INPUT";
        }
      } else {
        return "INVALID INPUT";
      }
    }
  }
})
</script>

<style lang="scss" scoped>
  .tri-calc {
    display: inline-flex;
    flex-direction: column;
    padding: 5px;
    border-width: 1px;
    border-color: #1a1c1f;
    border-style: solid;
    border-radius: 3px;
    margin: 5px;
  }

  .tri-calc .title {
    font-size: 20px;
    font-weight: bold;
  }

  .tri-calc .subtitle {
    color: #35373a;
  }

  .tri-calc hr {
    width: 100%;
    box-sizing: border-box;
    border: none;
    height: 1px;
    background-color: #1a1c1f;
  }
</style>
