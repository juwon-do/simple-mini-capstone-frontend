/* eslint-disable */
<script>
import axios from 'axios'


export default {
  data: function() {
    return {
      message: "Welcome to Vue.js!",
      products: [],
      product: {
        "name": "",
        "price": "",
        "description": "",
        "quantity": "",
        "supplier_id": ""
      }
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
    },
    newProduct: function() {
      console.log("Create new");
      axios.post("http://localhost:3000/products.json", this.product).then(response => {
        console.log(response.data);
        this.products.push(response.data);
        this.product = {};
      })
    }
  }
};
</script>

<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <h2>{{ product }}</h2>
    <p>Name: <input type="text" v-model="product.name" /></p>
    <p>Price: <input type="text" v-model="product.price" /></p>
    <p>Description: <input type="text" v-model="product.description" /></p>
    <p>Quant: <input type="text" v-model="product.quantity" /></p>
    <p>Supplier_id: <input type="text" v-model="product.supplier_id" /></p>
    <button v-on:click="newProduct">New Product</button>


    <div v-for="product in products" v-bind:key="product.id">
      <h3>ID: {{ product.id}}</h3>
      <p>{{ product.name}}</p>
      <p>{{ product.price}}</p>
      <p>{{ product.description}}</p>
      <img v-bind:src = "product.image" />
      <hr />
    </div>
</div>
</template>

<style></style>