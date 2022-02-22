<template>
  <div
    class="product-card"
    @mouseover="isHover = true"
    @mouseleave="isHover = false"
  >
    <img :src="img" class="product-card_img" alt="Цветок" />
    <h4 class="product-card_title">{{ title }}</h4>
    <div class="product-card_metka">
      <img
        v-if="hit"
        src="@/assets/icons/metka_hit.svg"
        class="product-card_hit"
      />
      <img
        v-if="newProduct"
        src="@/assets/icons/metka_new.svg"
        class="product-card_new"
      />
      <img
        v-if="stock"
        src="@/assets/icons/metka_stock.svg"
        class="product-card_stock"
      />
    </div>
    <div>
      <div class="product-card_type" v-if="regularScreenWidth">
        <span class="product-card_type-line"></span>
        <h6 class="product-card_type-name">
          {{ type }}
        </h6>
      </div>
      <div class="product-card_basket" v-if="isHover">
        <img src="@/assets/icons/basket.svg" />
      </div>
      <div class="product-card_basket" v-if="!regularScreenWidth">
        <img src="@/assets/icons/basket.svg" />
      </div>
      <div class="product-card_prices">
        <span class="product-card_price" v-if="regularScreenWidth"
          >{{ price }} ₽</span
        ><span class="product-card_discount-price">{{ discountPrice }} ₽</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    img: String,
    title: String,
    type: String,
    price: Number,
    discountPrice: Number,
    newProduct: Boolean,
    hit: Boolean,
    stock: Boolean,
  },
  data() {
    return {
      isHover: false,
      regularScreenWidth: window.screen.width >= 720,
    };
  },
};
</script>

<style lang="scss">
@import "@/assets/styles/main/body/products-card.scss";
</style>
