<template>
  <span class="open-close">
    <span class="opened" v-if="isOpen === true"></span>
    <span class="closed" v-if="isOpen === false"
      ><span class="closed-first-line"></span
      ><span class="closed-second-line"></span
    ></span>
  </span>
</template>

<script>
export default {
  props: {
    isOpen: Boolean,
  },
};
</script>

<style lang="scss">
@import "@/assets/styles/main/body/filter-dropdown.scss";
</style>
