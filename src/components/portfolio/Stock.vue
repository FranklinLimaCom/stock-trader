<template>
  <div class="col-4">
    <div class="card text-white bg-success mb-4">
      <div class="card-header">
        {{ stock.name }}
        <small>(Price: {{ stock.price | Quantity: {{ stock.quantity }} }})</small>
      </div>
      <div class="card-body">
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
            class="btn btn-light"
          >Sell</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { mapActions } from "vuex";

export default {
  props: ["stock"],
  data() {
    return {
      quantity: 0
    };
  },
  methods: {
    ...mapActions(["sellStock"]),
    sellStock() {
      const order = {
        stockId: this.stock.id,
        stockPrice: this.stock.price,
        quantity: this.quantity
      };
      this.sellStock();
    }
  }
};
</script>

