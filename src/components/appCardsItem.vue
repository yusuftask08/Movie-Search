<template>
    <!-- <div  class="container">
      <div class="card-media">
        <div class="card-media-object-container">
          <img :src="moviePoster" alt="">
          <span class="card-media-object-tag subtle">{{ movie.Year }}</span>
        </div>
        <div class="card-media-body">
          <span class="card-media-body-heading">{{ movie.Title }}</span>
              <div class="card-media-body-supporting-bottom card-media-body-supporting-bottom-reveal">
            <span class="card-media-body-supporting-bottom-text subtle">{{ movie.Type }}</span>
            <button  @click="addToFavorites" :class="favoriteClasses">Favorilere Ekle</button>
            <a target="_blank"
              :href="`https://www.imdb.com/title/${movie.imdbID}/`"
              class="button"
              >IMDb</a >
          </div>
        </div>
      </div>
    </div> -->
      <div class="wrapper">
        <div class="product-img">
          <img :src="moviePoster" height="420" width="327">
        </div>
        <div class="product-info">
          <div class="product-text">
            <h1>{{ movie.Title }}</h1>
            <h2>{{ movie.Year }}</h2>
            <p> {{ movie.Type }}<br> <i class="fas fa-thumbs-up"></i> </p>
          </div>
          <div class="product-price-btn">
            <a :href="`https://www.imdb.com/title/${movie.imdbID}/`" target="_blank"><p><span></span>IMDB</p></a>
            <button @click="addToFavorites" :class="favoriteClasses" type="button">Favorilerime Ekle</button>
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
<style scoped>
body {
  background-color: #fdf1ec;
}

.wrapper {
  height: 420px;
  width: 654px;
  margin: 50px auto;
  border-radius: 7px 7px 7px 7px;
  /* VIA CSS MATIC https://goo.gl/cIbnS */
  -webkit-box-shadow: 0px 14px 32px 0px rgba(0, 0, 0, 0.15);
  -moz-box-shadow: 0px 14px 32px 0px rgba(0, 0, 0, 0.15);
  box-shadow: 0px 14px 32px 0px rgba(0, 0, 0, 0.15);
}

.product-img {
  float: left;
  height: 420px;
  width: 327px;
}

.product-img img {
  border-radius: 7px 0 0 7px;
}

.product-info {
  float: left;
  height: 420px;
  width: 327px;
  border-radius: 0 7px 10px 7px;
  background-color: #ffffff;
}

.product-text {
  height: 300px;
  width: 327px;
}

.product-text h1 {
  margin: 0 0 0 38px;
  padding-top: 52px;
  font-size: 34px;
  color: #474747;
}

.product-text h1,
.product-price-btn p {
  font-family: 'Bentham', serif;
}

.product-text h2 {
  margin: 0 0 47px 38px;
  font-size: 13px;
  font-family: 'Raleway', sans-serif;
  font-weight: 400;
  text-transform: uppercase;
  color: #d2d2d2;
  letter-spacing: 0.2em;
}

.product-text p {
  height: 125px;
  margin: 0 0 0 38px;
  font-family: 'Playfair Display', serif;
  color: #8d8d8d;
  line-height: 1.7em;
  font-size: 15px;
  font-weight: lighter;
  overflow: hidden;
}

.product-price-btn {
  height: 103px;
  width: 327px;
  margin-top: 17px;
  position: relative;
}

.product-price-btn p {
  display: inline-block;
  position: absolute;
  top: -13px;
  height: 50px;
  font-family: 'Trocchi', serif;
  margin: 0 0 0 38px;
  font-size: 28px;
  font-weight: lighter;
  color: #474747;
}

span {
  display: inline-block;
  height: 50px;
  font-family: 'Suranna', serif;
  font-size: 34px;
}
.product-price-btn button {
  float: right;
  display: inline-block;
  height: 50px;
  width: 176px;
  margin: 0 40px 0 16px;
  box-sizing: border-box;
  border: transparent;
  border-radius: 60px;
  font-family: 'Raleway', sans-serif;
  font-size: 14px;
  font-weight: 500;
  text-transform: uppercase;
  letter-spacing: 0.2em;
  color: #ffffff;
  background-color: #9cebd5;
  cursor: pointer;
  outline: none;
}

.product-price-btn button:hover {
  background-color: #79b0a1;
}
</style>
