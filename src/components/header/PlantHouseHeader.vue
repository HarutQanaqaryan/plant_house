<template>
  <header class="header">
    <img src="@/assets/icons/logo.svg" alt="logo" />
    <NavBar />
    <a href="/" class="header-tel">+7 473 300 34 94</a>
    <div class="header-icons">
      <img
        src="@/assets/icons/search.svg"
        class="header-icons_item"
        alt="Search"
      />
      <img
        src="@/assets/icons/profile.svg"
        class="header-icons_item"
        alt="Profile"
      />
      <div class="header-basket">
        <img
          src="@/assets/icons/basket.svg"
          class="header-icons_item"
          alt="Basket"
        />
        <span class="header-basket_count">2</span>
      </div>
    </div>
  </header>
</template>

<script>
import NavBar from "@/components/header/NavBar.vue";

export default {
  name: "PlantHouseHeader",
  components: {
    NavBar,
  },
};
</script>
<style lang="scss">
@import "@/assets/styles/main/header/nav.scss";
</style>
