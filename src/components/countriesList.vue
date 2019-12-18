<template lang="html">
  <div>
    <h1>Countries</h1>
    <select>
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

export default {
  name: "countries-list",
  props: ["listOfCounties"],
  components: {
    country: Country
  }
};
</script>

<style lang="css" scoped></style>
