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
  margin: 0px 150px 0px 150px;
  padding: 10px;
}
</style>
