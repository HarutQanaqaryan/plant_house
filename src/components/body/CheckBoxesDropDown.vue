<template>
  <div
    class="filter-dropdown"
    :class="isOpened ? 'opened-block' : 'closed-block'"
  >
    <div class="filter-dropdown_title" @click="showHideDropDown">
      <span>{{ title }}</span>
      <IsOpenBlock :isOpen="isOpened" />
    </div>
    <div class="filter-colors" v-if="isOpened">
      <SimpleCheckBox label="Белый" />
      <SimpleCheckBox label="Желтый" />
      <SimpleCheckBox label="Красный" />
      <SimpleCheckBox label="Зеленый" />
      <SimpleCheckBox label="Лиловый" />
      <SimpleCheckBox label="Бежевый" />
    </div>
  </div>
</template>

<script>
import IsOpenBlock from "./IsOpenBlock.vue";
import SimpleCheckBox from "./SimpleCheckBox.vue";

export default {
  components: {
    IsOpenBlock,
    SimpleCheckBox,
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
