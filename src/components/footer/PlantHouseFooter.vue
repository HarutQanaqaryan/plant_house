<template>
  <MobileFooter v-if="mobileScreenWidth" />
  <div class="footer" v-else>
    <div class="footer-develop">
      <img src="@/assets/icons/logo.svg" class="footer-logo" alt="logo" />
      <span
        >© 2021 Дом растений. Все права защищены. Выращенно c ❤️ в
        Stebnev-Studio.</span
      >
    </div>
    <div class="footer-menu" v-if="regularScreenWidth">
      <h4>Главное меню</h4>
      <div class="footer-menu-items">
        <a href="/">О компании</a>
        <a href="/">Акции</a>
        <a href="/">События</a>
        <a href="/">Оплата и доставка</a>
        <a href="/">Программа лояльности</a>
        <a href="/">Контакты</a>
      </div>
    </div>
    <div class="footer-catalog" v-if="regularScreenWidth">
      <h4>Каталог товаров</h4>
      <div class="footer-catalog-items">
        <a href="/">Товары для сада</a>
        <a href="/">Товары для водоемов</a>
        <a href="/">Растения для сада</a>
        <a href="/">Печи, барбекю</a>
        <a href="/">Новогодняя иллюминация</a>
      </div>
    </div>
    <div class="footer-contact_social-media">
      <div class="footer-contact_social-media-icons">
        <span>
          <img src="@/assets/icons/vk-logo.svg" alt="logo" />
        </span>
        <span>
          <img src="@/assets/icons/instagram-logo.svg" alt="logo" />
        </span>
        <span>
          <img src="@/assets/icons/fb-logo.svg" alt="logo" />
        </span>
      </div>
      <div class="footer-contact_btn" v-if="!regularScreenWidth">
        <button>Консультация</button>
      </div>
    </div>
    <div class="footer-contact">
      <h4>Создай сад своей мечты!</h4>
      <div>
        <span class="footer-contact_tel">+7 473 300 34 94</span>
        <span class="footer-contact_adress"
          >пос. Отрадное, ул. А.Невского, д. 59</span
        >
      </div>
      <div class="footer-contact_btn" v-if="regularScreenWidth">
        <button>Консультация</button>
      </div>
    </div>
  </div>
</template>

<script>
import MobileFooter from "./MobileFooter.vue";
export default {
  name: "plant-house-footer",
  components: {
    MobileFooter,
  },
  data() {
    return {
      isHover: false,
      regularScreenWidth: window.screen.width >= 720,
      mobileScreenWidth: window.screen.width <= 400,
    };
  },
};
</script>

<style lang="scss">
@import "@/assets/styles/main/footer/footer.scss";
</style>
