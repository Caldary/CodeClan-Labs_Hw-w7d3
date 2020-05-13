<template>
<div class="main-container">
<h1>Countries:</h1>

<div class="sub-container">
    <countries-list :countries='countries'></countries-list>
    <country-detail :country='selectedCountry'></country-detail>
</div>
</div>
  
</template>

<script>
import CountryDetail from './components/CountryDetail.vue';
import {eventBus} from './main.js';
import CountriesList from './components/CountriesList.vue';


export default {
  name: 'app',
  data(){
    return {
      countries: [],
      selectedCountry: null
    };

  },

mounted(){
  fetch('https://restcountries.eu/rest/v2/all')
  .then(res => res.json())
  .then(countries => this.countries = countries)

  eventBus.$on('country-selected', (country) => {
    this.selectedCountry = country
  })
  },
  components: {
    "countries-list": CountriesList,
    "country-detail": CountryDetail
  }
};

</script>

<style>

h1 {
  border: white;height: 4700px;
  color: red;
  text-align: center;
  align-items: center;
  justify-content: center;
}
.main-container {
  display: flex;
  background-color: blue;
  align-items: center;
  text-align: start;
  justify-content: center;
  
}

.sub-container {
  display: flex;
  background-color: black;
  color: white;
  padding: 20px;
  border:darkgoldenrod;
  justify-content: start;
  margin: 75px;
}

</style>
