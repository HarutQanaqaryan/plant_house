<template>
  <MobileNavBar v-if="mobileScreenWidth" />
  <RegularNavBar v-if="regularScreenWidth" />
</template>

<script>
import MobileNavBar from "./MobileNavBar.vue";
import RegularNavBar from "./RegularMenu.vue";

export default {
  name: "PlantHouseHeader",
  components: {
    MobileNavBar,
    RegularNavBar,
  },
  data() {
    return {
      regularScreenWidth: window.screen.width > 720,
      mobileScreenWidth: window.screen.width <= 720,
    };
  },
};
</script>
<style lang="scss">
@import "@/assets/styles/main/header/nav.scss";
</style>
