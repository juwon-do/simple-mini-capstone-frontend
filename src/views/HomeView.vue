/* eslint-disable */
<script>
export default {
  data: function() {
    return {
      message: "Welcome to Vue.js!",
      year: "2023"
    };
  },
  created: function() {},
  methods: {
    printSomething: function() {
      console.log("Print out from printSomething method")
    }
  }
};
</script>

<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <h2>{{ year }}</h2>
    <button v-on:click="printSomething">Print</button>
  </div>
</template>

<style></style>