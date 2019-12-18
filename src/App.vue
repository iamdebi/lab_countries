<template lang="html">
  <div class="main-container">
    <countries-list :listOfCounties="countries"></countries-list>
    <country-details
      v-if="selectedCountry"
      :country="selectedCountry"
    ></country-details>
  </div>
</template>

<script>
import CountriesList from "./components/countriesList.vue";
import { eventBus } from "./main.js";
import countryDetails from "./components/countryDetails.vue";

export default {
  name: "app",

  data() {
    return {
      countries: [],
      selectedCountry: null
    };
  },

  mounted() {
    fetch("https://restcountries.eu/rest/v2/all")
      .then(res => res.json())
      .then(country => (this.countries = country));

    eventBus.$on("clicked-country", passedCountry => {
      this.selectedCountry = passedCountry;
    });
  },

  components: {
    "countries-list": CountriesList,
    "country-details": countryDetails
  }
};
</script>

<style lang="css" scoped>
.main-container {
  display: flex;
  justify-content: space-between;
}
</style>
