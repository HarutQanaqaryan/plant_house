<template>
  <div v-if="isOpen">
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
        @input="slideOne"
      />
      <input
        type="range"
        min="0"
        max="3500"
        step="10"
        id="slider-2"
        v-model.number="maxPrice"
        @input="slideTwo"
      />
    </div>
    <div class="prices">
      <span class="price">{{ minPrice }}</span>
      <span class="price">{{ maxPrice }}</span>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      minPrice: 0,
      maxPrice: 3500,
      minGap: 0,
      fillColor: ``,
    };
  },
  props: {
    isOpen: Boolean,
  },
  methods: {
    setFillColor() {
      let percent1 = (this.minPrice / 3500) * 100;
      let percent2 = (this.maxPrice / 3500) * 100;
      return `linear-gradient(to right, #dadae5 ${percent1}% , #97aa12 ${percent1}% , #97aa12 ${percent2}%, #dadae5 ${percent2}%)`;
    },

    slideOne() {
      if (parseInt(this.maxPrice) - parseInt(this.minPrice) <= this.minGap) {
        this.minPrice = parseInt(this.maxPrice) - this.minGap;
      }
      this.setFillColor();
    },
    slideTwo() {
      if (parseInt(this.maxPrice) - parseInt(this.minPrice) <= this.minGap) {
        this.maxPrice = parseInt(this.minPrice) + this.minGap;
      }
      this.setFillColor();
    },
  },
};
</script>

<style lang="scss">
@import "@/assets/styles/main/body/simple-slider.scss";
</style>
