<template>
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
</template>

<script>
import DropDown from "./FilterDropDown.vue";
import SimpleCheckBox from "./SimpleCheckBox.vue";
import { filters } from "@/helpers/filterDropDowns.js";

export default {
  name: "PlantHouseBody",
  components: {
    DropDown,
    SimpleCheckBox,
  },
  data() {
    return {
      filtersProps: [...filters],
    };
  },
  methods: {
    showDropDown({ target: { id } }) {
      this.filtersProps = this.filtersProps.map((el) =>
        el.id === parseInt(id) ? { ...el, isOpen: !el.isOpen } : el
      );
    },
  },
};
</script>

<style lang="scss">
@import "@/assets/styles/main/body/filter-product.scss";
</style>
