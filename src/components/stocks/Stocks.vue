<template>
  <div class="row">
      <Stock v-for="(stock, key) in stocks" :key="key" :stock="stock"></Stock>
  </div>
</template>

<script>
import Stock from "./Stock.vue";

export default {
  data() {
    return {
      stocks: [
        { id: 1, name: "BMW", price: 110 },
        { id: 2, name: "Google", price: 200 },
        { id: 3, name: "Apple", price: 250 },
        { id: 4, name: "Twitter", price: 8 }
      ]
    };
  },
  components: {
    Stock
  }
};
</script>

<style>

</style>


