<template>
  <main class="body">
    <BreadCrumbs v-if="regularScreenWidth" />
    <BodyHeader />
    <div class="body-blocks">
      <FilterProduct
        v-if="regularScreenWidth"
        :updateMinPrice="updateMinPrice"
        :updateMaxPrice="updateMaxPrice"
      />
      <MobileFilterDropDown v-if="!regularScreenWidth" />
      <ProductsBlock :minPrice="minPrice" :maxPrice="maxPrice" />
    </div>
  </main>
</template>

<script>
import BreadCrumbs from "./BreadCrumbs.vue";
import BodyHeader from "./BodyHeader.vue";
import FilterProduct from "./FilterProducts.vue";
import ProductsBlock from "./ProductsBlock.vue";
import MobileFilterDropDown from "./MobileFilterDropDown.vue";

export default {
  name: "plant-house-body",
  components: {
    BreadCrumbs,
    BodyHeader,
    FilterProduct,
    ProductsBlock,
    MobileFilterDropDown,
  },
  data() {
    return {
      minPrice: 0,
      maxPrice: 3500,
      regularScreenWidth: window.screen.width > 720,
    };
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
