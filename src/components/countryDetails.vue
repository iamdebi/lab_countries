<template lang="html">
  <div>
    <p>{{ country.name }}</p>
    <p>{{ country.capital }}</p>
    <p>{{ country.population }}</p>
    <p v-for="language in country.languages">
      Language Spoken: {{ language.name }}
    </p>
    <img :src="country.flag" />
  </div>
</template>

<script>
export default {
  name: "country-details",
  props: ["country"]
};
</script>

<style lang="css" scoped></style>
