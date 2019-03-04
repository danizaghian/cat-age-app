<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <h3>What is your cat's calendar year age?</h3>
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
      message: "Cat Age Calculator",
      realAge: "",
      catAge: ""
    };
  },
  created: function() {},
  methods: {},
  computed: {
  	calculateCatAge: function() {
  		if (this.realAge == 1) {
  			this.catAge = 15;
  		} else if (this.realAge == 2) {
  			this.catAge = 24;
  		} else {
  			this.catAge = ((this.realAge - 2) * 4) + 24;
  		}
  		return this.catAge;
  	}
  }
};
</script>