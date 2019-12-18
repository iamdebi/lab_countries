<template lang="html">
  <option v-on:click="handleClick">{{ country.name }}</option>
</template>

<script>
import { eventBus } from "../main.js";

export default {
  name: "country-item",
  props: ["country"],
  methods: {
    handleClick: function() {
      eventBus.$emit("clicked-country", this.country);
    }
  }
};
</script>

<style lang="css" scoped></style>
