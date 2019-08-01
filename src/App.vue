<template>
  <div class="container">
    <Header></Header>
    <router-view></router-view>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
export default {
  components: {
    Header
  }
};
</script>

<style>
body {
  padding: 30px;
}
</style>
