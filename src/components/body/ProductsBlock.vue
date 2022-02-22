<template>
  <div class="products-block">
    <SortByAlphabet :search="searchProductByLetter" />
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

localStorage.setItem("PRODUCTS", JSON.stringify(productsData));

export default {
  props: {
    minPrice: Number,
    maxPrice: Number,
  },
  components: {
    SortByAlphabet,
    ProductCard,
    ProductsPagination,
  },
  data() {
    return {
      products: productsData,
      productDataStorage: JSON.parse(localStorage.getItem("PRODUCTS")),
    };
  },
  methods: {
    searchProductByLetter({ target: { innerText } }) {
      this.products = this.productDataStorage.filter((el) =>
        el.name.startsWith(innerText)
      );
    },
  },
  updated() {
    this.products = this.productDataStorage.filter(
      (el) =>
        el.discountPrice >= this.minPrice && el.discountPrice <= this.maxPrice
    );
  },
};
</script>

<style lang="scss">
@import "@/assets/styles/main/body/products-block.scss";
</style>
