<template>
    <div  class="container">
        <div class="card-media">
    <!-- media container -->
    <div class="card-media-object-container">
      
      <img :src="moviePoster" alt="">
      <span class="card-media-object-tag subtle">{{ movie.Year }}</span>
    </div>
    <!-- body container -->
    <div class="card-media-body">
      <div class="card-media-body-top">
        <!-- <div class="card-media-body-top-icons u-float-right">
          <svg fill="#888888" height="16" viewBox="0 0 24 24" width="16" xmlns="http://www.w3.org/2000/svg">
            <path d="M17 3H7c-1.1 0-1.99.9-1.99 2L5 21l7-3 7 3V5c0-1.1-.9-2-2-2z"/>
            <path d="M0 0h24v24H0z" fill="none"/>

          </svg>
        </div> -->
      </div>
      
      <span class="card-media-body-heading">{{ movie.Title }}</span>
          <div class="card-media-body-supporting-bottom card-media-body-supporting-bottom-reveal">
        <span class="card-media-body-supporting-bottom-text subtle">{{ movie.Type }}</span>
        <button  @click="addToFavorites" :class="favoriteClasses">Favorilere Ekle</button>
        <a target="_blank"
          :href="`https://www.imdb.com/title/${movie.imdbID}/`"
          class="button"
          >IMDb</a >
        <!-- <a href="#/" class="card-media-body-supporting-bottom-text card-media-link u-float-right"><i class="is_favourite fa fa-heart"></i>Favorilere Ekle</a> -->
      </div>
    </div>
  </div>
    </div>
    
</template>
<script>
import { mapGetters } from "vuex";
export default {
  props: {
    movie: {
      type: Object,
      required: true,
    },
  },
  methods: {
    addToFavorites() {
      this.$store.dispatch("addToFavorite", this.movie);
    },
  },
  computed: {
    ...mapGetters(["myFavorites"]),
    moviePoster() {
      return this.movie.Poster !== "N/A" ? this.movie.Poster : "/default.png";
    },
    favoriteClasses() {
      return {
        is_favourite:
          this.myFavorites.find((fav) => fav.imdbID === this.movie.imdbID) ||
          false,
      };
    },
  },
};
</script>