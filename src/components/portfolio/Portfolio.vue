<template>
  <div>
      <Stock v-for="(stock, key) in stocks" :key="key" :stock="stock"></Stock>ss
  </div>
</template>

<script>
import { mapGetters } from "vuex";
import Stock from './Stock.vue'

export default {
  computed: {
      ...mapGetters({
          stocks: 'stockPortfolio'
      })
  },
  components: {
      Stock
  }
};
</script>
