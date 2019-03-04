<template>
  <div class="human-age">
    <h1>{{ message }}</h1>
    <h3>What is your hooman's age?</h3>
    <input type="number" v-model="realAge">

    <div v-if="realAge">
    	<h4>Your cat in human years is: {{ calculateCatAge }}</h4>
    </div>

  </div>
</template>

<style>
</style>

<script>
export default {
  data: function() {
    return {
      message: "Hooman Age Calculator",
      realAge: "",
      catAge: ""
    };
  },
  created: function() {},
  methods: {},
  computed: {
  	calculateCatAge: function() {
  		if (this.realAge <= 15) {
  			this.catAge = 1;
  		} else if (this.realAge > 15 && this.realAge <= 24) {
  			this.catAge = 2;
  		} else {
  			this.catAge = ((this.realAge - 24) / 4) + 2;
  		}
  		return this.catAge;
  	}
  }
};
</script>