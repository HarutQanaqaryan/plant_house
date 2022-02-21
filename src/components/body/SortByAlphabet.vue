<template>
  <div class="sort-by-alphabet">
    <div class="sort-by-alphabet_title">Сортировать по:</div>
    <div class="sort-by-alphabet_letters">
      <span
        class="sort-by-alphabet_letter"
        v-for="letter in sortAlphabet"
        :key="letter"
        >{{ letter }}</span
      >
    </div>
  </div>
</template>

<script>
import { sortAlphabet } from "../../helpers/sortAlphabet";

export default {
  data() {
    return {
      sortAlphabet,
    };
  },
};
</script>

<style lang="scss">
@import "@/assets/styles/main/body/sort-alphabet-block.scss";
</style>
