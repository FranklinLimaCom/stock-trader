<template>
  <div class="row">
    <Stock v-for="(stock, key) in stocks" :key="key" :stock="stock"></Stock>
  </div>
</template>

<script>
import Stock from "./Stock.vue";
import "../../animate.css"

export default {
  components: {
    Stock
  },
  computed: {
    stocks() {
      return this.$store.getters.stocks;
    }
  }
};
</script>

<style>
</style>


