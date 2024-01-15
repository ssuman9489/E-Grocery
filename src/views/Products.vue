<template>
  <v-app style="background-color: rgb(157, 201, 201);">
    <Navbar />
   
  <v-row justify="center" class="space px-16">
    <v-col
      cols="12" xs="12" sm="6" md="4"
     v-for="(product, i) in products"
      :key="i"
    > 
      <v-card class="mx-auto " max-width="300" color="" flat outlined>
        <div align="center" justify="center">
          <router-link :to="{ name: 'order' }">
          <v-img
            max-height="300"
            max-width="300"
            contain
            :src="product.img"
           
          >
        </v-img>
        </router-link>
        </div>

        <v-card-title class="">{{ product.title }}</v-card-title>
        <v-card-title class="grey--text text-grey-darken-1 caption mt-n6">{{
          product.subtitle
        }}</v-card-title>
        <v-card-title class="mt-n4">{{ product.price }}</v-card-title>

        <v-card-actions class="mx-2 mt-n4">
          <v-btn outlined class="mt-n2 add">
            <v-icon color="green" @click="decrement"> mdi-minus </v-icon>
          </v-btn>

          <strong class="mx-2" v-text="bpm"></strong>
          <v-btn outlined class="mt-n2 add">
            <v-icon color="green" @click="increment"> mdi-plus </v-icon>
          </v-btn>
          <v-spacer></v-spacer>
          <router-link :to="{ name: 'order' }">
             
          <v-btn class="mx-2 mt-n3" fab dark small color="green" >
            <v-icon dark> mdi-shopping </v-icon>
          </v-btn>
        </router-link>
        </v-card-actions>
      </v-card>
    </v-col>
  </v-row>
  <v-card style="background-color: rgb(157, 201, 201); margin-top: 100px;" >
  <pack />
  
</v-card>

  <Footer />
</v-app>

</template>

<script>
import Navbar from "../components/Navbar";
import Footer from "../components/Footer";
import Pack from "../components/Pack.vue"
export default {
  data: () => ({
      bpm: 1,
    products: [
      { img: "pr1.png", title: "Cabbage", subtitle: "1kg", price: "Rs13" },
      { img: "pr2.png", title: "Perry's Ice Cream", subtitle: "1kg", price: "Rs223" },
      { img: "pr3.png", title: "Potato", subtitle: "1kg", price: "Rs17" },
      { img: "pr4.png", title: "Bundle Pack", subtitle: "FruitS Snacks", price: "Rs400" },
      { img: "pr5.png", title: "Oreo Biscuit", subtitle: "270GM", price: "Rs90" },
      { img: "pr6.png", title: "Papaya", subtitle: "1kg", price: "Rs30" },
  
    ],
  }),
  components: {
    Navbar,
    Pack,
    Footer,
    
  },
   methods: {
    
      decrement () {
        this.bpm--
      },
      increment () {
        this.bpm++
      },
      
    },

};
</script>

