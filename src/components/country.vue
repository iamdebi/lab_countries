<template lang="html">
  <option :value="country">{{ country.name }}</option>
</template>

<script>
import { eventBus } from "../main.js";

export default {
  name: "country-item",
  props: ["country"]
};
</script>

<style lang="css" scoped></style>
