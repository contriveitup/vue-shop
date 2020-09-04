<template>
  <div id="nav">
    <div class="columns">
      <div class="column is-half">
        <div class="is-pulled-left mr-4">
          <img class="image is-32x32" alt="Vue logo" src="../assets/logo.png" />
        </div>
        <div class="is-pulled-left">
          <router-link class="mr-4" to="/">Home</router-link>|
          <router-link class="ml-2" to="/coupons">Coupons</router-link>
        </div>
      </div>
      <div class="column is-half">
        <div class="has-text-right">
          <router-link to="/cart">View Cart ({{ getCartItemsCount }} items)</router-link>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import { mapGetters } from "vuex";
export default {
  name: "Navigation",
  computed: {
    ...mapGetters(["getCartItemsCount", "getCartItems"])
  }
};
</script>
<style lang="scss" scoped>
#nav {
  margin-top: 2rem;
}
</style>
