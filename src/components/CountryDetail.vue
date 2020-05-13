<template lang="html">
  <div v-if='country'>
      <h3>Name: {{country.name}}</h3>
      <h3>Capital: {{country.capital}}</h3>
      <h3>Population: {{country.population}}</h3>
      <h3>Native Name: {{country.nativeName}}</h3>
</div>
  
</template>

<script>
import { eventBus } from '../main.js';

export default {
    name: 'country-detail',
    props: ['country']
}

</script>

<style>


</style>