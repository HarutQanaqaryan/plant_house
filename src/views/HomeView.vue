<template>
  <div class="wrapper">
    <PlantHouseHeader />
    <PlantHouseBody />
  </div>
</template>

<script>
import PlantHouseHeader from "@/components/header/PlantHouseHeader.vue";
import PlantHouseBody from "@/components/body/PlantHouseBody.vue";

export default {
  name: "HomeView",
  components: {
    PlantHouseHeader,
    PlantHouseBody,
  },
};
</script>

<style>
.wrapper {
  margin: 0px 150px 0px 150px;
  padding: 10px;
}
</style>
