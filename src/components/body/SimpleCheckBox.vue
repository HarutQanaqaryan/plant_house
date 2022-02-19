<template>
  <label>
    <input type="checkbox" />
    <span></span>
    {{ label }}
  </label>
</template>

<script>
export default {
  props: {
    label: String,
  },
};
</script>

<style lang="scss">
@import "@/assets/styles/main/body/checkbox.scss";
</style>
