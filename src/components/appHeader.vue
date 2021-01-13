<template>
<div>
  <header>
    <div class="header-area ">
      <div class="main-header header-sticky">
        <div class="">
          <div class="menu-wrapper d-flex align-items-center justify-content-between">
               <nav class="navbar-expand-lg navbar navbarColor" >
                <a class="navbar-brand collapse navbar-collapse" href="#">Film Box</a>
                <router-link to="/" class="mr-5">Anasayfa</router-link>
                <router-link to="/favorites">Favorilerim</router-link>
              </nav>
            <!-- Header-btn -->
            <div class="header-btns d-none d-lg-block f-right ">
              <a href="#" class="btn mr-5">Giriş</a>
              <a href="#" class="btn">Kayıt Ol</a>
            </div>
            <!-- Mobile Menu -->
            <div class="col-12">
              <div class="mobile_menu d-block d-lg-none"></div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <!-- Header End -->
  </header>
</div>
</template>
<style scoped>

</style>