<template>
  <div v-if="allProducts">
    <div class="columns is-multiline is-desktop is-widescreen is-fullhd">
      <div
        v-for="product in allProducts"
        :key="product.id"
        class="column is-4-fullhd is-4-widescreen is-6-desktop"
      >
        <Product :product="product" />
      </div>
    </div>
  </div>
  <div v-else>
    <facebook-loader></facebook-loader>
  </div>
</template>
<script>
import Product from "./parts/Product";
import { FacebookLoader } from "vue-content-loader";
import { mapActions, mapGetters } from "vuex";
export default {
  name: "Products",
  components: {
    Product,
    FacebookLoader
  },
  data() {
    return {
      products: null
    };
  },
  computed: {
    ...mapGetters(["allProducts"])
  },
  methods: {
    ...mapActions(["fetchProductsFromApi"])
  },
  created() {
    this.fetchProductsFromApi();
  }
};
</script>
