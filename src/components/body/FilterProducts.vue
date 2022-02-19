<template>
  <div class="filter">
    <div class="filter-reset">
      <span></span>
      <span>Сбросить фильтр</span>
    </div>
    <div class="filter_acts">
      <SimpleCheckBox label="Акции" />
      <SimpleCheckBox label="Популярное" />
      <SimpleCheckBox label="Новинки" />
      <SimpleCheckBox label="Эксклюзив" />
    </div>
  </div>
  <DropDown
    title="Товары для сада"
    v-bind:items="productTypes"
    :isOpened="openedFilter"
    :showHideDropDown="showDropDown"
  />
  <DropDown
    title="Товары для водоемов"
    :items="alltypes"
    :isOpened="openedFilter"
    :showHideDropDown="showDropDown"
  />
  <DropDown
    title="Растения для сада"
    :items="alltypes"
    :isOpened="openedFilter"
    :showHideDropDown="showDropDown"
  />
  <DropDown title="Печи, барбекю" :items="alltypes" :isOpened="openedFilter" />
  <DropDown
    title="Новогодняя иллюминация"
    :items="alltypes"
    :isOpened="openedFilter"
    :showHideDropDown="showDropDown"
  />
</template>

<script>
import DropDown from "./FilterDropDown.vue";
import SimpleCheckBox from "./SimpleCheckBox.vue";

export default {
  name: "PlantHouseBody",
  components: {
    DropDown,
    SimpleCheckBox,
  },
  data() {
    return {
      productTypes: [
        "Газоны и лужайки",
        "Эксклюзивные (+штамбовые)",
        "Хвойные",
        "Лиственные",
        "Плодо-ягодные",
        "Розы",
        "Злаки",
        "Лианы",
        "Многолетние цветы и травы",
        "Однолетние",
      ],
      alltypes: ["Другие", "Другие", "Другие", "Другие"],
      openedFilter: false,
    };
  },
  methods: {
    showDropDown({ target: { name } }) {
      console.log(name);
    },
  },
};
</script>
