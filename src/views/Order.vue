<!-- views/OrderPage.vue -->
<template>
  <v-app style="background-color: rgb(157, 201, 201);">
    <Navbar />
    <v-container>
      <v-row justify="center">
        <v-col cols="12" xs="12" sm="6" md="4">
          <v-card class="mx-auto" max-width="300" color="" flat outlined>
            <v-img max-height="300" max-width="300" contain :src="selectedProduct.img"></v-img>
            <v-card-title>{{ selectedProduct.title }}</v-card-title>
            <v-card-title class="grey--text text-grey-darken-1 caption mt-n6">{{ selectedProduct.subtitle }}</v-card-title>
            <v-card-title class="mt-n4">{{ selectedProduct.price }}</v-card-title>
            <v-card-title class="mt-n4">GST (18%): {{ calculateGST(selectedProduct.price) }}</v-card-title>
            <v-card-title class="mt-n4">Total Amount: {{ calculateTotalAmount(selectedProduct.price) }}</v-card-title>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
    <Footer />
  </v-app>
</template>

<script>
import Navbar from "../components/Navbar";
import Footer from "../components/Footer";

export default {
  props: ['selectedProduct'],
  components: {
    Navbar,
    Footer,
  },
  methods: {
    calculateGST(price) {
      const gst = (18 / 100) * parseFloat(price);
      return gst.toFixed(2);
    },
    calculateTotalAmount(price) {
      const gstAmount = this.calculateGST(price);
      const totalAmount = parseFloat(price) + parseFloat(gstAmount);
      return totalAmount.toFixed(2);
    },
  },
};
</script>
