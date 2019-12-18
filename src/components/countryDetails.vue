<template lang="html"> 
<div>
<p>{{country.name}}</p>
<p>{{country.capital}}</p>
<p>{{country.population}}</p>
</div>
</template>

<script>
export default {
    name: "country-details",
    props: ["country"]
};
</script>

<style lang="css" scoped></style>