/* eslint-disable */
<script>
export default {
  data: function() {
    return {
      message: "Welcome to Vue.js!",
      year: "2023",
      showInfo: true,
      image: "https://media.gettyimages.com/id/1399037422/photo/justin-thomas-of-the-usa-celebrates-with-the-wanamaker-trophy-after-the-final-round-of-the.jpg?s=612x612&w=gi&k=20&c=PEg1Y_edTrX3OlvPSi7CQWYB0_J6VNCnwgSOra1UH5U=",
      golfs: ["titleist","callaway","taylormade"]
    };
  },
  created: function() {},
  methods: {
    printSomething: function() {
      console.log("Print out from printSomething method")
      this.showInfo = !this.showInfo
    }
  }
};
</script>

<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <h2>{{ year }}</h2>
    <div v-for=" golf in golfs" :key="golf.id">
      <p>{{ golf }}</p>
    </div>
    <img v-bind:src = "image"/>
    <p>Year: <input type="text" v-model="year"/></p>
   
    <button v-on:click="printSomething">Print</button>
    <div v-if="showInfo">
      <p>Toggle</p>
    </div>
  </div>
</template>

<style></style>