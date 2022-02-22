<template>
  <div class="wrapper">
    <PlantHouseHeader />
    <PlantHouseBody />
  </div>
  <PlantHouseFooter />
</template>

<script>
import PlantHouseHeader from "@/components/header/PlantHouseHeader.vue";
import PlantHouseBody from "@/components/body/PlantHouseBody.vue";
import PlantHouseFooter from "@/components/footer/PlantHouseFooter.vue";

export default {
  name: "HomeView",
  components: {
    PlantHouseHeader,
    PlantHouseBody,
    PlantHouseFooter,
  },
};
</script>

<style>
.wrapper {
  max-width: 1510px;
  margin: 0 auto;
}
@media (max-width: 1024px) {
  .wrapper {
    max-width: 100%;
  }
}
@media (max-width: 720px) {
  .wrapper {
    max-width: 100%;
    padding: 0px 20px 0px 20px;
  }
}
</style>
