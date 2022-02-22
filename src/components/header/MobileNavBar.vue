<template>
  <div class="mobile-navbar">
    <img src="@/assets/icons/logo.svg" class="header-logo" alt="logo" />
    <div class="mobile-navbar-icons">
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
      <BurgerMenu />
    </div>
  </div>
</template>

<script>
import BurgerMenu from "./BurgerMenu.vue";
export default {
  components: {
    BurgerMenu,
  },
};
</script>

<style lang="scss">
@import "@/assets/styles/main/header/mobile-menu.scss";
</style>
