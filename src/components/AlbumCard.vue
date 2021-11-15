<template>
  <div class="card border-0 my-bg-dark text-white my-card-container">
    <img :src="poster" class="card-img-top dimensione-img" alt="..." />
    <div class="card-body d-flex flex-column text-center">
      <h5 class="card-title">{{ title }}</h5>
      <div class="small-text">{{ author }}</div>
      <div class="small-text">{{ year }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "AlbumCard",
  props: {
    poster: String,
    title: String,
    author: String,
    genre: String,
    year: String,
  },
};
</script>

    // "poster": "https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg",
    //   "title": "New Jersey",
    //   "author": "Bon Jovi",
    //   "genre": "Rock",
    //   "year": "1988"

