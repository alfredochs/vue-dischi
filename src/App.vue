<template>
  <div>
    <div>
      <header></header>
      <DischiContainer></DischiContainer>
    </div>
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
  background-color: #192d3c;
}
</style>
