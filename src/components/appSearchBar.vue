<template>
  <div>
    
    <div class="slider-area hero-bg1 hero-overly">
      <div
        class="single-slider hero-overly slider-height1 d-flex align-items-center"
      >
      
        <div class="container">
          
          <div class="row justify-content-center">
            <div class="col-xl-10 col-lg-10">
              <!-- Hero Caption -->
              <div class="hero__caption pt-100 ">
                <h1 class="">FİLM BOX</h1>
                <p>En güncel film listesine bizimle ulaşın!</p>
              </div>
              <!--Hero form -->
              <form action="#" class="search-box mb-100">
                <div class="input-form">
                  <input
                    type="text"
                    placeholder="Aramak istediğiniz filmin adını giriniz." @keydown.enter="searchMovie($event.target.value)"
                  />
                </div>

                <div class="search-form header-btns">
                  <a href="#" class="btn"><i class="ti-search"></i> Ara</a>
                </div>
              </form>
              <!-- hero category1 img -->
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import { mapActions } from "vuex";
export default {
  methods: {
    ...mapActions(["searchMovie"]),
  },
};
</script>