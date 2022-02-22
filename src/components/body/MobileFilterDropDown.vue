<template>
  <div class="mobile-filter-dropdown">
    <div>
      <div class="mobile-filter-dropdown_title">Фильтр</div>
    </div>
    <div class="mobile-filter-dropdown-arrow">
      <IsOpenBlock :isOpen="false" />
    </div>
  </div>
</template>

<script>
import IsOpenBlock from "./IsOpenBlock.vue";

export default {
  components: {
    IsOpenBlock,
  },
};
</script>

<style lang="scss">
@import "@/assets/styles/main/body/mobile-filter-dropdown.scss";
</style>
