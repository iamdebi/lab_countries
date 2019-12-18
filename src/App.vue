<template lang="html"> </template>

<script>
export default {
  name: "app",

  data() {
    return {
      countries: []
    };
  },

  mounted() {
    fetch("https://restcountries.eu/rest/v2/all")
      .then(res => res.json())
      .then(country => (this.countries = country));
  }
};
</script>

<style lang="css" scoped></style>
