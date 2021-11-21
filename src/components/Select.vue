<template>
  <div>
    <select
      class="form-select my-select-container"
      aria-label="Default select example"
      @change="selectGenere()"
      v-model="genere"
    >
      <!-- <option selected>Open this select menu</option> -->
      <option :value="chiave" v-for="(chiave, i) in generi" :key="i">
        {{ chiave }}
      </option>
    </select>
  </div>
</template>

<script>
export default {
  name: "Select",
  data() {
    return {
      genere: "",
    };
  },
  props: {
    generi: Array,
  },
  methods: {
    selectGenere() {
      this.$emit("eventoSelezione", this.genere);
    },
  },
};
</script>

<style lang="scss">
</style>