<template>
  <main class="body">
    <BreadCrumbs />
    <BodyHeader />
    <div class="body-blocks">
      <FilterProduct
        :updateMinPrice="updateMinPrice"
        :updateMaxPrice="updateMaxPrice"
      />
      <ProductsBlock :minPrice="minPrice" :maxPrice="maxPrice" />
    </div>
  </main>
</template>

<script>
import BreadCrumbs from "./BreadCrumbs.vue";
import BodyHeader from "./BodyHeader.vue";
import FilterProduct from "./FilterProducts.vue";
import ProductsBlock from "./ProductsBlock.vue";

export default {
  name: "PlantHouseBody",
  components: {
    BreadCrumbs,
    BodyHeader,
    FilterProduct,
    ProductsBlock,
  },
  data() {
    return { minPrice: 0, maxPrice: 3500 };
  },
  methods: {
    updateMinPrice({ target: { value } }) {
      this.minPrice = parseInt(value);
    },
    updateMaxPrice({ target: { value } }) {
      this.maxPrice = parseInt(value);
    },
  },
};
</script>
<style lang="scss">
@import "@/assets/styles/main/body/body.scss";
</style>
