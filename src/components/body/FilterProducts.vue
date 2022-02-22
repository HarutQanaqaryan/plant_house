<template>
  <div class="filter-container">
    <div class="filter">
      <div class="filter-reset">
        <span class="filter-reset-first_line"></span>
        <span class="filter-reset-second_line"></span>
        <span class="filter-reset-title">Сбросить фильтр</span>
      </div>
      <div class="filter_acts">
        <SimpleCheckBox label="Акции" />
        <SimpleCheckBox label="Популярное" />
        <SimpleCheckBox label="Новинки" />
        <SimpleCheckBox label="Эксклюзив" />
      </div>
    </div>
    <DropDown
      v-for="filter in filtersProps"
      :key="filter.id"
      :filterId="filter.id"
      :title="filter.title"
      :items="filter.types"
      :isOpened="filter.isOpen"
      @click="showDropDown"
    />
    <SliderDropDown
      title="Цена"
      :isOpened="isPriceDropDown"
      :showHideDropDown="showSlider"
      :updateMinPrice="updateMinPrice"
      :updateMaxPrice="updateMaxPrice"
    />
    <CheckBoxesDropDown
      title="Цвет"
      :isOpened="isColorsDropDown"
      :showHideDropDown="showColors"
    />
    <LoyaltyProgram />
  </div>
</template>

<script>
import DropDown from "./FilterDropDown.vue";
import SimpleCheckBox from "./SimpleCheckBox.vue";
import CheckBoxesDropDown from "./CheckBoxesDropDown.vue";
import SliderDropDown from "./SliderDropDown.vue";
import LoyaltyProgram from "./LoyaltyProgram.vue";

import { filters } from "@/helpers/filterDropDowns.js";

export default {
  props: {
    updateMinPrice: Function,
    updateMaxPrice: Function,
  },
  components: {
    DropDown,
    SimpleCheckBox,
    CheckBoxesDropDown,
    SliderDropDown,
    LoyaltyProgram,
  },
  data() {
    return {
      filtersProps: [...filters],
      isPriceDropDown: false,
      isColorsDropDown: false,
    };
  },
  methods: {
    showDropDown({ target: { id } }) {
      this.filtersProps = this.filtersProps.map((el) =>
        el.id === parseInt(id) ? { ...el, isOpen: !el.isOpen } : el
      );
    },
    showSlider() {
      this.isPriceDropDown = !this.isPriceDropDown;
    },
    showColors() {
      this.isColorsDropDown = !this.isColorsDropDown;
    },
  },
};
</script>

<style lang="scss">
@import "@/assets/styles/main/body/filter-product.scss";
</style>
