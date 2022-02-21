<template>
  <main class="body">
    <BreadCrumbs />
    <BodyHeader />
    <div class="body-blocks">
      <FilterProduct />
      <ProductsBlock />
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
};
</script>
<style lang="scss">
@import "@/assets/styles/main/body/body.scss";
</style>
