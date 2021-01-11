<template>
<div class="container mt-5 ">

   <cardItem v-for="i in 2" :key="i"/>


  </div>
</template>

<script>
import cardItem from "@/components/cardItem";
export default {
  components: {
    cardItem,
  }
}
</script>