<template>
  <main class="body">
    <BreadCrumbs />
    <BodyHeader />
    <FilterProduct />
  </main>
</template>

<script>
import BreadCrumbs from "./BreadCrumbs.vue";
import BodyHeader from "./BodyHeader.vue";
import FilterProduct from "./FilterProducts.vue";

export default {
  name: "PlantHouseBody",
  components: {
    BreadCrumbs,
    BodyHeader,
    FilterProduct,
  },
};
</script>
<style lang="scss">
@import "@/assets/styles/main/body/body.scss";
</style>
