<template>
  <div class="col-md-4">
    <div class="card text-white bg-success mb-4">
      <div class="card-header">
        {{ stock.name }}
        <small>(Price: {{ stock.price }})</small>
      </div>
      <div class="card-body bg-white">
        <div class="float-left">
          <input
            v-model="quantity"
            type="number"
            placeholder="Quantity"
            class="form-control"
            style="width: 170px;"
          />
        </div>

        <div class="float-right">
          <button
            @click="buyStock"
            :disabled="quantity <= 0 || !Number.isInteger(Number(quantity))"
            class="btn btn-success"
          >Buy</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["stock"],
  data() {
    return {
      quantity: 0
    };
  },
  methods: {
    buyStock() {
      const order = {
        stockId: this.stock.id,
        stockPrice: this.stock.price,
        quantity: this.quantity
      };
      console.log(order);
      this.$store.dispatch.buyStock
      this.quantity = 0;
    }
  }
};
</script>


