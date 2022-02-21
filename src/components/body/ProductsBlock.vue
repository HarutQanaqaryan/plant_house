<template>
  <div class="products-block">
    <SortByAlphabet />
    <div class="products-block_cards">
      <ProductCard
        v-for="product in products"
        :key="product.id"
        :img="require(`@/assets/data_flowers/${product.img}`)"
        :title="product.name"
        :type="product.type"
        :price="product.price"
        :discountPrice="product.discountPrice"
        :hit="product.hit"
        :newProduct="product.new"
        :stock="product.stock"
      />
      <ProductsPagination currentPage="01" nextPage="02" lastPage="04" />
    </div>
  </div>
</template>

<script>
import SortByAlphabet from "./SortByAlphabet.vue";
import ProductCard from "./ProductCard.vue";
import ProductsPagination from "./ProductsPagination.vue";
import { productsData } from "../../helpers/productsData";

export default {
  components: {
    SortByAlphabet,
    ProductCard,
    ProductsPagination,
  },
  data() {
    return {
      products: productsData,
    };
  },
};
</script>

<style lang="scss">
@import "@/assets/styles/main/body/products-block.scss";
</style>
