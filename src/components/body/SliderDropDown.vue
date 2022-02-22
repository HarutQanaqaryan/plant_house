<template>
  <div
    class="filter-dropdown"
    :class="isOpened ? 'opened-block' : 'closed-block'"
  >
    <div class="filter-dropdown_title" @click="showHideDropDown">
      <span>{{ title }}</span>
      <IsOpenBlock :isOpen="isOpened" />
    </div>
    <div v-show="isOpened">
      <SimpleSlider
        :changeMinPrice="setMinPrice"
        :changeMaxPrice="setMaxPrice"
        :updateMinPrice="updateMinPrice"
        :updateMaxPrice="updateMaxPrice"
      />
      <div class="prices">
        <span class="price">{{ minPrice }}</span>
        <span class="price">{{ maxPrice }}</span>
      </div>
    </div>
  </div>
</template>

<script>
import IsOpenBlock from "./IsOpenBlock.vue";
import SimpleSlider from "./SimpleSlider.vue";

export default {
  data() {
    return {
      minPrice: 0,
      maxPrice: 3500,
    };
  },
  components: {
    IsOpenBlock,
    SimpleSlider,
  },
  props: {
    title: String,
    isOpened: Boolean,
    showHideDropDown: Function,
    updateMinPrice: Function,
    updateMaxPrice: Function,
  },
  methods: {
    setMinPrice({ target: { value } }) {
      this.minPrice = value;
    },
    setMaxPrice({ target: { value } }) {
      this.maxPrice = value;
    },
  },
};
</script>

<style lang="scss">
@import "@/assets/styles/main/body/filter-dropdown.scss";
</style>
