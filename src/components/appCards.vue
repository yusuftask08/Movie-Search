<template>
  <div>
      <appCardsItem v-for="movie in movieList"
      :key="movie.imdbID"
      :movie="movie" />
  </div>
</template>
<script>
import appCardsItem from "@/components/appCardsItem"
export default {
  components: {
    appCardsItem,
  },
  props: {
    movieList: {
      type: Array,
      required: true,
    },
  },
  created() {
    this.$store.dispatch("initFavorites");
  },
}
</script>

