<template>
  <div class="filter-dropdown" @click="showHideDropDown">
    <div class="filter-dropdown_title">
      <span>{{ title }}</span>
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
  },
};
</script>

<style lang="scss">
@import "@/assets/styles/main/body/filter-dropdown.scss";
</style>
