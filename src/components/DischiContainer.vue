<template>
  <div class="my-container">
    <h1 class="text-white">Lista degli album</h1>

    <div class="row row-cols-1 row-cols-md-5 g-4">
      <div class="col" v-for="(chiave, i) in listaAlbum" :key="i">
        <AlbumCard
          :author="chiave.author"
          :title="chiave.title"
          :poster="chiave.poster"
          :genre="chiave.genre"
          :year="chiave.year"
        ></AlbumCard>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import AlbumCard from "./AlbumCard.vue";
export default {
  components: { AlbumCard },
  name: "DischiContainer",
  data() {
    return {
      listaAlbum: [],
    };
  },
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((resp) => {
        // this.listaAlbum.push(resp.data);
        this.listaAlbum = resp.data.response;
      });
  },
};
</script>

<style lang="scss">
</style>