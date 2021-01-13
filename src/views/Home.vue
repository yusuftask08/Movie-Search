<template>
   <appSearchBar />
   <appCards :movieList="movieList"/>
</template>
<script>
// @ is an alias to /src
import appSearchBar from '@/components/appSearchBar';
import appCards from '@/components/appCards';
import { mapGetters } from "vuex";

export default {
  components: {
    appSearchBar,
    appCards
  },
  computed : {
      ...mapGetters({
          movieList :"movieItemList",
      })
    }
}
</script>
