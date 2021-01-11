<template>
  
   <search />
   <cards/>
  
</template>

<script>
// @ is an alias to /src
import search from '@/components/search';
import cards from '@/components/cards';

export default {
  name: 'Home',
  components: {
    search,cards
  }
}
</script>
