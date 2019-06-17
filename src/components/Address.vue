<template>
  <div class="container">
    <h1>Address Demo</h1>
    <div>
      <label for="address">Address:</label>
      <input type="text" id="address" name="address" v-model="address">
    </div>
    <div>
      <label for="postcode">Postcode:</label>
      <input type="text" id="postcode" name="postcode" v-model="postCode">
    </div>    
    <div>
      <label for="countries">Country:</label>
      <countries
        id="countries"
        name="countries"
        @countryChangeEvent="countryChangeEventHandler"
        propCountry='TR'
      ></countries>
    </div>

    <div>
      selected country: {{country}}
    </div>
    <div>
      <button v-on:click="submitClickHandler">Submit</button>
    </div>
  </div>
</template>

<script>
import Countries from "./Countries";

export default {
  components: {
    countries: Countries
  },
  data: function() {
    return {
      address: "",
      postCode: "",
      country: ""
    };
  },
  methods: {
    countryChangeEventHandler: function(option) {
      this.country = option;
    },
    submitClickHandler:function(){
        alert("submit values address:"+this.address+' postCode:'+this.postCode+' country:'+this.country)
    }

  }
};
</script>

