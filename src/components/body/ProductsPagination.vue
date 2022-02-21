<template>
  <div class="product-pagination">
    <div>
      <span class="product-pagination_current">{{ currentPage }}</span>
      <span class="product-pagination_next_page">{{ nextPage }}</span>
      <span class="product-pagination_intermediate_pages">. . .</span>
      <span class="product-pagination_last_page">{{ lastPage }}</span>
      <img
        src="@/assets/icons/arrow-right.svg"
        class="product-pagination_next"
      />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    currentPage: Number,
    nextPage: Number,
    lastPage: Number,
  },
};
</script>

<style lang="scss">
@import "@/assets/styles/main/body/product-pagination.scss";
</style>
