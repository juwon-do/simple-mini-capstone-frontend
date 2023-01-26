/* eslint-disable */
<script>
import axios from 'axios'


export default {
  data: function() {
    return {
      message: "Welcome to Vue.js!",
      products: []
    };
  },
  created: function() {
    this.getData();
  },
  methods: {
    getData: function() {
      console.log("Get Data")
      axios.get("http://localhost:3000/products.json").then(response => {
        this.products = response.data        
        console.log(response.data)
      })
    }
  }
};
</script>

<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <div v-for="product in products" v-bind:key="product.id">
      <p>{{ product.name}}</p>
      <p>{{ product.price}}</p>
      <p>{{ product.description}}</p>
      <img v-bind:src = "product.image" />
      <hr />
    </div>
</div>
</template>

<style></style>