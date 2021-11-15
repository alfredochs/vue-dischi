<template>
  <div class="bg-dark pagina-intera">
    <DischiContainer></DischiContainer>
  </div>
</template>

<script>
import DischiContainer from "./components/DischiContainer.vue";
export default {
  components: { DischiContainer },
  name: "App",
};
</script>

<style lang="scss">
@import "@/styles/app";
body {
  font-family: "Montserrat";
}
</style>
