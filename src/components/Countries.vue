<template>
    <select @change="changeHandler" v-model="selectedCountry">
      <option value="TR">TR</option>
      <option value="GB">GB</option>
      <option value="FR">FR</option>
      <option value="US">US</option>
    </select>
</template>
<script>
export default {
  props: {
    propCountry: String
  },
  data: function() {
    return {
      selectedCountry: ""
    };
  },
  mounted() {
    this.selectedCountry = this.propCountry;
  },
  methods: {
    changeHandler: function() {     
      this.$emit("countryChangeEvent", this.selectedCountry);
    }
  }
};
</script>
