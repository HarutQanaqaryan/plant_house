<template>
  <div
    class="filter-dropdown"
    :class="isOpened ? 'opened-block' : 'closed-block'"
  >
    <div class="filter-dropdown_title" @click="showHideDropDown">
      <span>{{ title }}</span>
      <IsOpenBlock :isOpen="isOpened" />
    </div>
    <SimpleSlider :isOpen="isOpened" />
  </div>
</template>

<script>
import IsOpenBlock from "./IsOpenBlock.vue";
import SimpleSlider from "./SimpleSlider.vue";

export default {
  components: {
    IsOpenBlock,
    SimpleSlider,
  },
  props: {
    title: String,
    isOpened: Boolean,
    showHideDropDown: Function,
  },
};
</script>

<style lang="scss">
@import "@/assets/styles/main/body/filter-dropdown.scss";
</style>
