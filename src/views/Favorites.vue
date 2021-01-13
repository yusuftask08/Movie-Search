<template>
  <div class="Favori">
    <appCards :movieList="movieList"/>
  </div>
</template>
<script>
import appCards from "@/components/appCards";
import { mapGetters, } from 'vuex';
export default {
   components:{
    appCards,
  },
  computed : {
      ...mapGetters({
          movieList :"myFavorites",
      })
    },
}
</script>
