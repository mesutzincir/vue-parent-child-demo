<template>
  <select @change="changeHandler" v-model="selectedCountry">
    <option
      v-for="country in countryArray"
      :key="country.iso"
      :value="country.iso"
    >{{country.iso}}-{{country.currency}}</option>
    <!--
      <option value="TR">TR</option>
      <option value="GB">GB</option>
      <option value="FR">FR</option>
      <option value="US">US</option>
    -->
  </select>
</template>
<script>
import listCountryJSON from "@/assets/list_country.json";
export default {
  props: {    
    propCountry: String
  },
  data: function() {
    return {
      countryArray: listCountryJSON.country_array,
      selectedCountry: this.propCountry
    };
  },

  methods: {
    changeHandler: function() {
      this.$emit("countryChangeEvent", this.selectedCountry);
    }
  }
};
</script>
