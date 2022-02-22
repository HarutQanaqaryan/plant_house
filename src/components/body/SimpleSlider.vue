<template>
  <div>
    <div class="slider">
      <div
        class="slider-track"
        v-bind:style="{ background: setFillColor() }"
      ></div>
      <input
        type="range"
        min="0"
        max="3500"
        step="10"
        id="slider-1"
        v-model.number="minPrice"
        @input="changeMinPrice"
        @change="updateMinPrice"
      />
      <input
        type="range"
        min="0"
        max="3500"
        step="10"
        id="slider-2"
        v-model.number="maxPrice"
        @input="changeMaxPrice"
        @change="updateMaxPrice"
      />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      minPrice: 0,
      maxPrice: 3500,
    };
  },
  props: {
    changeMinPrice: Function,
    changeMaxPrice: Function,
    updateMinPrice: Function,
    updateMaxPrice: Function,
  },
  methods: {
    setFillColor() {
      let percent1 = (this.minPrice / 3500) * 100;
      let percent2 = (this.maxPrice / 3500) * 100;
      return `linear-gradient(to right, #dadae5 ${percent1}% , #97aa12 ${percent1}% , #97aa12 ${percent2}%, #dadae5 ${percent2}%)`;
    },
  },
  updated() {
    this.setFillColor();
  },
};
</script>

<style lang="scss">
@import "@/assets/styles/main/body/simple-slider.scss";
</style>
