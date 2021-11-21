<template>
  <div class="my-container">
    <!-- <h1 class="text-white">Lista degli album</h1> -->
    <div class="row">
      <div class="col">
        <Select @eventoSelezione="salvaGeneri" :generi="filtroGeneri"> </Select>

        <div class="row row-cols-1 row-cols-md-5 g-4">
          <div class="col" v-for="(chiave, i) in genereDaStampare" :key="i">
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
    </div>
  </div>
</template>

<script>
import axios from "axios";
import AlbumCard from "./AlbumCard.vue";
import Select from "./Select.vue";
export default {
  components: { AlbumCard, Select },
  name: "DischiContainer",
  data() {
    return {
      listaAlbum: [],
      // prova: "",
      salvaOgniGenere: "",
    };
  },
  methods: {
    salvaGeneri(generi) {
      this.salvaOgniGenere = generi;
    },
  },
  // genereDaStampare(genere) {
  //   if (!genere) {
  //     return this.listaAlbum;
  //   }
  //   return this.listaAlbum.filter(
  //     (chiave) => {
  //       return this.prova === chiave.genere;
  //     }
  //     // console.log(genere);
  //     // debugger;
  //   );
  // },

  computed: {
    filtroGeneri() {
      const generiDup = this.listaAlbum.map((disco) => {
        return disco.genre;
      });
      console.log(generiDup);
      const generi = [];
      for (let i = 0; i < generiDup.length; i++) {
        const genere = generiDup[i];
        if (!generi.includes(genere)) {
          generi.push(genere);
        }
      }
      console.log(generi);
      return generi;
    },
    genereDaStampare() {
      if (!this.salvaOgniGenere) {
        return this.listaAlbum;
      }
      return this.listaAlbum.filter(
        (album) => {
          return this.salvaOgniGenere === album.genre;
        }
        // console.log(genere);
        // debugger;
      );
    },
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