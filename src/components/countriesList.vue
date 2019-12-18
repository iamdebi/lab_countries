<template lang="html">
  <div>
    <h1>Countries</h1>
    <select v-on:change="handleClick" v-model="selectedCountry">
      <country
        v-for="(country, index) in listOfCounties"
        :country="country"
        :key="index"
      ></country>
    </select>
  </div>
</template>

<script>
import Country from "./country.vue";
import { eventBus } from "./../main.js";

export default {
  name: "countries-list",
  data() {
    return {
      selectedCountry: {}
    };
  },
  props: ["listOfCounties"],
  components: {
    country: Country
  },
  methods: {
    handleClick: function() {
      eventBus.$emit("clicked-country", this.selectedCountry);
    }
  }
};
</script>

<style lang="css" scoped></style>
