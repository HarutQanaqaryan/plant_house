<template>
  <div
    class="filter-dropdown"
    :class="isOpened ? 'opened-block' : 'closed-block'"
    @click="showHideDropDown"
    :id="filterId"
  >
    <div class="filter-dropdown_title" :id="filterId">
      <span :id="filterId">{{ title }}</span>
      <IsOpenBlock :isOpen="isOpened" />
    </div>
    <ul v-if="isOpened">
      <li v-for="item in items" :key="item" class="filter-dropdown_item">
        {{ item }}
      </li>
    </ul>
  </div>
</template>

<script>
import IsOpenBlock from "./IsOpenBlock.vue";

export default {
  components: {
    IsOpenBlock,
  },
  props: {
    title: String,
    items: Array,
    isOpened: Boolean,
    showHideDropDown: Function,
    filterId: Number,
  },
};
</script>

<style lang="scss">
@import "@/assets/styles/main/body/filter-dropdown.scss";
</style>
