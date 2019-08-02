<template>
  <div class="container">    
    <Header class="animated fadeInDown"></Header>    
    <transition enter-active-class="animated fadeIn">
    <router-view></router-view>
    </transition>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import './animate.css'
export default {
  components: {
    Header
  },
  created() {
    this.$store.dispatch('initStocks')
  }
};
</script>

<style>
body {
  padding: 30px;
}


</style>
