<template>
  <div>
    <div class="slider-area hero-bg1 hero-overly">
      <div
        class="single-slider hero-overly slider-height1 d-flex align-items-center"
      >
        <div class="container">
          <div class="row justify-content-center">
            <div class="col-xl-10 col-lg-10">
              <div class="hero__caption pt-100">
                <h1>FİLM BOX</h1>
                <p>En güncel film listesine bizimle ulaşın!</p>
              </div>
              <form action="#" class="search-box mb-100">
                <div class="input-form">
                  <input
                    v-model="searchText"
                    type="text"
                    placeholder="Aramak istediğiniz filmin adını giriniz."
                  />
                </div>
              <!-- <div class="search-form"> -->
                <div class="header-btns d-none d-lg-block f-right">
              <a @click="searchMovie" href="#" class="btn">FİLM ARA</a>
            </div>
               
              </form>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  data(){
    return{
        searchText: null,
        movieList: [],
    }
  },
  methods: {
    searchMovie(){      
         fetch(`http://www.omdbapi.com/?apikey=ea67c8a9&s=${this.searchText}`)
          .then(search_movie_response => search_movie_response.json() )
          .then(search_movie_response => {
            this.movieList =search_movie_response;
          console.log(search_movie_response);
    })
  }, 
  }
}
</script>