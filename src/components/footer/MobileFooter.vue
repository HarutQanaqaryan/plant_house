<template>
  <div class="mobile-footer">
    <div class="mobile-footer-develop">
      <div>
        <img src="@/assets/icons/logo.svg" class="footer-logo" alt="logo" />
      </div>
      <div class="footer-contact_btn" v-if="!regularScreenWidth">
        <button>Консультация</button>
      </div>
    </div>
    <div class="footer-contact mobile-footer_contact">
      <h4>Создай сад своей мечты!</h4>
      <div>
        <span class="footer-contact_tel">+7 473 300 34 94</span>
        <span class="footer-contact_adress"
          >пос. Отрадное, ул. А.Невского, д. 59</span
        >
      </div>
    </div>
    <div class="footer-contact_social-media mobile-footer_social_media">
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
    </div>
    <span class="footer-develop_description"
      >© 2021 Дом растений. Все права защищены. Выращенно c ❤️ в
      Stebnev-Studio.</span
    >
  </div>
</template>

<script>
export default {
  data() {
    return {
      isHover: false,
      regularScreenWidth: window.screen.width >= 720,
    };
  },
};
</script>

<style lang="scss">
@import "@/assets/styles/main/footer/footer.scss";
</style>

<style lang="scss">
@import "@/assets/styles/main/footer/footer.scss";
</style>
